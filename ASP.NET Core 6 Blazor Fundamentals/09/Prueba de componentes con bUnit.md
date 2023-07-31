# Adición de autenticación y autorización

Cátedra Programación de Software y Programática - Fundamentos de ASP.NET Core 6 Blazor

Introducción al módulo

En este punto, nuestra aplicación está bien, bastante abierta. Todos pueden buscar la aplicación, una vez que se implemente, por supuesto, y todos pueden ver los detalles de los empleados. No creo que esa sea realmente una opción viable. Al menos necesitaremos una forma de asegurarnos de que solo las personas a las que se les permite ver los datos en nuestra aplicación puedan hacerlo. Por lo tanto, en este módulo, primero presentaremos la autenticación y, además, también podemos introducir la autorización para personalizar lo que los usuarios pueden ver o hacer en la aplicación. Que también introduciremos en nuestra aplicación. Sigo siendo Gill Cleeren y también lo guiaré a través de este módulo. Antes de comenzar con el proceso de asegurar la aplicación, quiero darle una breve descripción de los diferentes aspectos que rodean este tema en general. La autenticación y la seguridad son realmente importantes y algunos temas de interés deben abordarse de manera diferente, ya que estamos trabajando aquí con una aplicación del lado del cliente que se ejecuta completamente en el navegador. Como la autenticación se puede hacer, bueno, digamos de mala manera, es mejor confiar en alguien que ya lo haya hecho antes, y por eso mismo voy a confiar aquí en un proveedor de identidad externo, Auth0. Primero voy a explicar qué hace y cómo configurar una aplicación en Auth0. Una vez que todo esté configurado, es hora de agregar la autenticación a la aplicación, por lo que esos serán los temas que cubriremos a continuación. Luego, otra parte importante es que la API se llama a sí misma. Esos también tendrán que estar asegurados. Finalmente, agregaremos autorización para que podamos configurar lo que los usuarios pueden ver y hacer en la aplicación, bueno, en función de los roles. Un montón de contenido interesante, creo. Sumerjámonos.

Protección de la aplicación Blazor

Y comencemos con una breve introducción sobre la autenticación y, más específicamente, la autenticación en la aplicación Blazor WebAssembly, y lo que debemos tener en cuenta. Como expliqué en la introducción, creo que es un hecho que necesitaremos que nuestros usuarios inicien sesión en la aplicación antes de que puedan hacer algo con ella. El proceso de inicio de sesión es una cosa, pero dado que las aplicaciones Blazor _____ son, de hecho, aplicaciones del lado del cliente, también será necesario implementar otras medidas. Comenzaremos con la configuración de la parte de autenticación, lo que significa que debemos verificar que el usuario es realmente quien dice ser. Una vez que hayamos podido verificar eso, procederemos con la autorización. La parte de autorización nos permitirá verificar si el usuario tiene permiso para hacer lo que está tratando de hacer en la aplicación, por ejemplo, navegar a una página determinada. Según los permisos, también podemos, por ejemplo, ocultar ciertos elementos del menú. Desde mi aplicación, ya estamos interactuando con nuestra API, y esas llamadas API también las tendremos que revisar. En este punto, nuestros puntos finales de API están completamente abiertos. No se están haciendo controles al respecto. Eso también tendrá que cambiar. Tendremos que verificar, en función de un token, si la solicitud entrante está permitida o no y exponer los datos solo si estamos seguros de que lo están. Quiero enfatizar aquí nuevamente que al compilar y asegurar aplicaciones Blazor, debemos prestar mucha atención. Ya sabemos que todo se ejecuta del lado del cliente y, de forma predeterminada, todo lo que está disponible para el cliente, debemos asumir que se puede modificar. Por lo tanto, solo podemos usar la autorización en la aplicación Blazor para alternar las opciones de la interfaz de usuario, como ocultar un botón. Los usuarios pueden omitir los controles y, por lo tanto, debemos asegurarnos de que todo lo que los usuarios intentan enviar o solicitar desde el back-end se valida allí en el servidor. Ese es el único lugar donde tenemos la capacidad de evitar la exposición de datos que el usuario no puede ver o modificar. Agregar autenticación a Blazor requiere algo de trabajo, pero la buena noticia es que hay algunos bloques importantes que ya obtenemos de forma gratuita, y harán que el trabajo sea mucho más fácil y seguro, ya que queremos evitar tener que rodar nuestros propios mecanismos de seguridad. Para empezar, en nuestra aplicación Blazor WebAssembly, confiaremos en gran medida en un paquete NuGet llamado Microsoft.AspNetCore.Components.WebAssembly.Authentication. Veremos cómo se usa este paquete en las demostraciones. Nos ayudará mucho con la autenticación a través de OIDC, que significa OpenID Connect. A continuación, obtendremos mucha ayuda del servicio AuthenticationStateProvider. Como su nombre lo indica, este se utilizará para saber dentro de la aplicación cuál es el estado de autenticación. De hecho, lo utilizan los componentes integrados que veremos más adelante para conocer el estado de autenticación e incluye el componente AuthorizeView. También usaremos CascadingAuthenticationState. Un parámetro en cascada se define en un nivel superior y estará disponible automáticamente para todos los componentes anidados. Está _____ en cascada a través de toda la jerarquía y todos los componentes pueden usarlo. El CascadingAuthenticationState es un parámetro que obtenemos de forma gratuita, y cuando lo ponemos en el nivel más alto de nuestra aplicación, por lo tanto, en App.razor, todos los componentes pueden usarlo para conocer el estado de autenticación de la aplicación. Lo usaremos en nuestro propio código para tomar decisiones basadas en el estado de autenticación. Blazor utiliza de forma predeterminada la autenticación basada en OIDC, que significa OpenID Connect. El paquete NuGet, por lo que el paquete MicrosoftAspNetCore.Components.WebAssembly.Authentication, es compatible con esto. También proporciona un conjunto de primitivas para la autenticación contra los back-ends de Asp.Net Core, e integra Asp.Net Core Identity con soporte de autorización de API construido sobre Duende Identity Server. Sin embargo, no usaremos Identity Server en este curso, pero afortunadamente, también funciona con otros proveedores de identidad de terceros, que son compatibles con OIDC. Usaremos, como ya se mencionó, Auth0 en la siguiente parte de este módulo. Una vez que tenga los componentes básicos para la autenticación en su lugar, podemos ver las características integradas que viene con Blazor en el departamento de autorización. AuthorizeView es un componente integrado que nos permite mostrar u ocultar contenido en la interfaz de usuario, en función de si el usuario que lo está viendo realmente está autorizado para hacerlo. Así que esto es una cosa de la interfaz de usuario, de verdad. Podemos usarlo, por ejemplo, para ocultar la opción del menú de administración en una aplicación si el usuario no tiene el rol de administrador. El siguiente es el atributo Autorizar, que puede conocer de otras tecnologías de Asp.Net Core como MVC, y de hecho hace lo mismo. En un componente Razor, podemos agregar el atributo Autorizar y, si el usuario no está autorizado para ver el componente, será redirigido al flujo de inicio de sesión. Al igual que en Asp.Net Core, por ejemplo, el atributo Autorizar se puede combinar con una lista de roles. Tienen un control más detallado sobre qué roles se requieren para trabajar con el componente. Un descargo de responsabilidad está en su lugar aquí. El proceso de asegurar una aplicación correctamente puede ser una gran tarea. Por lo tanto, he optado por una solución práctica para poder proteger la aplicación, pero existen muchas otras opciones. Definitivamente no es el objetivo de este curso cubrir todas las opciones. Tengo algunos cursos dedicados a la autenticación en la parte de Blazor aquí que van mucho más allá en este tema. Echa un vistazo a estos si quieres aprender mucho más sobre esto. por lo tanto, buscó una solución práctica para poder asegurar la aplicación, pero existen muchas otras opciones. Definitivamente no es el objetivo de este curso cubrir todas las opciones. Tengo algunos cursos dedicados a la autenticación en la parte de Blazor aquí que van mucho más allá en este tema. Echa un vistazo a estos si quieres aprender mucho más sobre esto. por lo tanto, buscó una solución práctica para poder asegurar la aplicación, pero existen muchas otras opciones. Definitivamente no es el objetivo de este curso cubrir todas las opciones. Tengo algunos cursos dedicados a la autenticación en la parte de Blazor aquí que van mucho más allá en este tema. Echa un vistazo a estos si quieres aprender mucho más sobre esto.

Agregar un proveedor de identidad

Ahora tiene una primera buena idea de la autenticación en las aplicaciones Blazor. Hagámoslo ahora práctico y comencemos a introducir la autenticación en Bethany's Pie Shop HRM. Comenzaré agregando un proveedor de identidad. Para que podamos realizar la autenticación, así como el proceso de autorización, utilizaremos un proveedor de identidad. Pero ¿por qué, y qué es eso realmente? Bueno, me alegra que hayas preguntado. En general, cuando se habla de seguridad y autenticación, hay muchas cosas que pueden salir mal, y cuando algo en el área de seguridad sale mal, por lo general es bastante malo. Para una aplicación como Bethany's Pie Shop HRM, esto puede significar que se otorga acceso no autorizado a los datos personales de sus empleados. Definitivamente algo malo. Implementar su propio sistema de seguridad rara vez es una buena idea, ya que siempre habrá cosas en las que no pensó, aumentando el riesgo de dejar una puerta abierta en alguna parte. También desea almacenar la menor cantidad de información posible, como contraseñas, en su propio sistema. Por estas razones, hoy en día a menudo usamos de forma predeterminada un proveedor de identidad. Este es un servicio externo que es responsable del proceso de autenticación y autorización, y hará cosas como almacenar las contraseñas por usted. Además, el acceso a otros recursos, como las API, se puede controlar a través de un proveedor de identidad. Los proveedores de identidad pública incluyen Facebook, Twitter y Microsoft. Blazor puede funcionar con proveedores compatibles con OpenID Connect, y es posible que ya haya oído hablar de algunos de ellos. Duende IdentityServer es uno, pero requiere la mayor parte de la configuración manual, por lo que no lo usaremos aquí. Okta y Auth0 son dos proveedores de identidad muy conocidos, y las digo de una vez ya que Auth0 fue adquirida por Okta. Sin embargo, las diferentes soluciones tienen un objetivo diferente, y usaremos en este curso Auth0, que considero una opción muy amigable para los desarrolladores. Otra opción comúnmente utilizada es Azure Active Directory. Como tal, usaremos Auth0 en este curso. Verá que una vez que todo esté configurado en nuestra aplicación, los usuarios iniciarán sesión en nuestra aplicación a través de Auth0. No ofreceremos registro en nuestra aplicación, pero eso también se puede delegar a Auth0. Entonces, tanto para el inicio de sesión como para el registro opcional, los usuarios del sitio serán enviados a Auth0. Iniciarán sesión con una cuenta en Auth0 y, por supuesto, Auth0 sabe que los usuarios están tratando de buscar en nuestra aplicación. No sabemos en nuestra aplicación sobre las credenciales que proporciona el usuario, por lo que no hay riesgo de almacenar de forma insegura estas credenciales en nuestra aplicación. Una vez que haya iniciado sesión y, por lo tanto, las credenciales se aprueben en Auth0 para nuestra aplicación, Auth0 redirigirá a nuestra aplicación y nuestra aplicación lo tomará desde allí. Este proceso se llama el flujo, y tengo diferentes opciones aquí. Blazor usará el flujo PKCE, abreviatura de Proof Key for Code Exchange. Veremos los detalles, los pasos de este flujo, en la siguiente diapositiva. Otra cosa que realmente me gustó de Auth0 es el hecho de que es gratis para hasta 7000 usuarios, y ese es el caso incluso de las aplicaciones comerciales. ¿Qué tan bueno es eso? Estos son los detalles del flujo de autenticación que usaremos entre nuestra aplicación Blazor y Auth0, que es nuestro proveedor de OIDC. Tenga en cuenta que no será diferente si usa otro proveedor, para que podamos tomar este conocimiento y aplicarlo a cualquier otro proveedor compatible con OIDC, como IdentityServer. Entonces, primero, cuando el usuario hace clic en el botón de inicio de sesión o presiona un componente donde se aplica el atributo Autorizar, será redirigido directamente a Auth0. Por lo tanto, el usuario abandona su aplicación brevemente y ve la página de inicio de sesión de Auth0 donde puede iniciar sesión con sus credenciales. Después de que el inicio de sesión fue exitoso, son redirigidos a nuestra aplicación. En la configuración que necesitaremos hacer de Auth0, se configurará una URL de redirección y en la que se usa aquí. Junto con esta redirección a nuestra aplicación, se incluye un llamado código de autorización y el usuario ahora está de vuelta en nuestra aplicación. Nuestra aplicación Blazor ahora usará el código de autorización para volver a llamar a Auth0, y eso dará como resultado la devolución de un token de acceso y una identificación.

Demostración: Registro de la aplicación con Auth0

Como se ha dicho, el primer paso de toda esta cadena será configurar Auth0 para lo que acabamos de explicar. Comenzaremos con la creación de una cuenta Auth0 y luego registraremos nuestra aplicación con Auth0 para que, entre otras cosas, sepa a dónde redirigir después de un inicio de sesión exitoso. Como dije en las diapositivas, vamos a usar Auth0 como proveedor de identidad. Nos dará una manera fácil de configurar la autenticación en nuestra aplicación, como veremos en esta demostración. Primero, debemos configurar una cuenta con Auth0 y, como se dijo, puede hacerlo gratis para hasta 7,000 usuarios en su aplicación, por lo que incluso con un plan gratuito ya puede hacer mucho, incluso para aplicaciones comerciales. Primero, dirígete a auth0.com y crea una cuenta. Voy a suponer que puedes hacerlo tú mismo. Así que te veré en el otro sitio. He usado mi cuenta de Gmail, y luego tendré acceso por defecto a la aplicación más adelante. Al pasar por el asistente de registro, también podrá elegir un dominio de arrendatario, y tendrá que ser único. También puede elegir en qué región desea que se almacenen sus datos. Una vez que haya iniciado sesión, diríjase a la sección Aplicaciones, y allí podemos hacer clic en Crear aplicación. En el cuadro de diálogo que aparece, primero ingresaremos el nombre de la aplicación que, por supuesto, podemos elegir. Entraré aquí BethanysPieShopHRM. Luego, en el tipo de aplicación, seleccione Aplicación de una sola página. Eso es exactamente lo que es nuestra aplicación Blazor, una aplicación, un SPA que se ejecuta en el navegador del cliente. Otros marcos SPA incluyen Angular y React. Finalmente, haremos clic en Crear. Con la aplicación creada, haga clic en Configuración aquí, y allí necesitaremos copiar tanto el Dominio como la ID del Cliente para más adelante. Así que póngalos por ahora en su Bloc de notas, y llegaremos a ellos cuando estemos trabajando en la aplicación en las próximas demostraciones. A continuación, diríjase a la sección URI de la aplicación y, en las URL de devolución de llamada permitidas, ingrese el URI de la aplicación que se ejecuta en su máquina. En el mío, eso es https://localhost:7039, y luego agregue el sufijo /authentication/login‑callback. Esto se usa para que Auth0 sepa dónde devolver la llamada después de la autenticación. En el campo URL de cierre de sesión permitidas, ingrese https://localhost:7039/. Esto se usa para redirigir después de cerrar la sesión. Finalmente, presione Guardar cambios y asegúrese de que su configuración se guarde correctamente. Una vez hecho esto, la aplicación está configurada en el lado de las cosas de Auth0.

Autenticación en la Aplicación

Auth0 ahora está configurado y conoce nuestra aplicación. Ahora, debemos volver a centrar nuestra atención en nuestra aplicación y realizar cambios en el código y la configuración allí para que funcione con nuestra cuenta Auth0. Mostraré esto principalmente en una demostración, pero quiero aclarar las cosas de antemano, mostrarle los pasos que deberemos seguir en la próxima demostración. Y veamos estos pasos uno por uno. Primero, lo que haré es informar a nuestra aplicación Blazor WebAssembly sobre la configuración de Auth0 que copiamos en la demostración anterior. Este será el ID del cliente y la autoridad, valores que obtuvimos mientras caminábamos a través de la configuración de nuestra aplicación en Auth0. Luego, debemos agregar el paquete que le presenté anteriormente en este módulo, el paquete Microsoft.AspNetCore.Components.WebAssembly.Authentication. Usamos Auth0, pero dado que es un proveedor de OIDC, el paquete de autenticación funciona bien con él. También se necesita otra referencia de archivo de JavaScript en la página de alojamiento, por lo que el host.cshtml, y agregaremos una referencia de secuencia de comandos al archivo de autenticación‑servicio.js, que viene con el paquete de autenticación. Con soporte para el paquete NuGet, ahora podemos llamar a un método de extensión, AddOidcAuthentication en nuestro Program.cs, apuntando a la configuración en appsettings.json. A continuación, nos dirigiremos a App.razor donde envolveremos todo en un CascadingAuthenticationState. Ese será un parámetro en cascada que contiene información sobre, bueno, el estado de autenticación para que lo usen otros componentes. Recuerde, los parámetros en cascada están disponibles en componentes anidados, por lo que como envolvemos todo en el nivel App.razor, esta información puede ser utilizada por todos los componentes de la aplicación. También usaremos AuthorizeView en App.razor. Finalmente, vamos a usar algunos componentes nuevos, Authentication.razor y AuthenticationStatus.razor. Dije nuevos componentes, pero de hecho puede encontrar el código para estos casi en un proyecto recién creado que creamos en Visual Studio con la autenticación habilitada. Te mostraré esto en la demostración. En resumen, Authentication.razor se usará para manejar diferentes etapas de autenticación y AuthenticationStatus se usará para mostrar el botón de inicio de sesión o el botón de cierre de sesión combinado con el nombre de usuario actualmente conectado. Mucha de la funcionalidad relacionada con la autenticación viene con Blazor integrado, lo que puede hacer que a veces parezca que las cosas están sucediendo, bueno, mágicamente. Me puedo identificar totalmente con eso, a veces se siente así, pero eso se debe a que ya hay muchas cosas allí. Uno de esos comportamientos predeterminados es que, por ejemplo, cuando tocamos un componente donde se aplica el atributo Autorizar, seremos redirigidos a la autenticación/inicio de sesión si el usuario aún no está autenticado. Eso puede ser manejado por la página de autenticación recién mencionada, que, debido a la configuración, redirigirá a Auth0. Después de un inicio de sesión exitoso, los usuarios serán redirigidos a nuestra aplicación, a la devolución de llamada de autenticación/inicio de sesión, y cuando la aplicación carga este punto final, la respuesta de autenticación se procesa automáticamente, lo que hace que el token esté disponible para nuestra aplicación. cuando tocamos un componente donde se aplica el atributo Autorizar, seremos redirigidos a la autenticación/inicio de sesión si el usuario aún no está autenticado. Eso puede ser manejado por la página de autenticación recién mencionada, que, debido a la configuración, redirigirá a Auth0. Después de un inicio de sesión exitoso, los usuarios serán redirigidos a nuestra aplicación, a la devolución de llamada de autenticación/inicio de sesión, y cuando la aplicación carga este punto final, la respuesta de autenticación se procesa automáticamente, lo que hace que el token esté disponible para nuestra aplicación. cuando tocamos un componente donde se aplica el atributo Autorizar, seremos redirigidos a la autenticación/inicio de sesión si el usuario aún no está autenticado. Eso puede ser manejado por la página de autenticación recién mencionada, que, debido a la configuración, redirigirá a Auth0. Después de un inicio de sesión exitoso, los usuarios serán redirigidos a nuestra aplicación, a la devolución de llamada de autenticación/inicio de sesión, y cuando la aplicación carga este punto final, la respuesta de autenticación se procesa automáticamente, lo que hace que el token esté disponible para nuestra aplicación.

Demostración: agregar autenticación con Auth0

Como se dijo, aprenderemos más aquí haciendo todo esto en una demostración grande. Así que configuremos la autenticación en nuestra aplicación ahora usando Auth0. Ahora agregaré la autenticación a la aplicación misma y seguiremos los pasos que acabo de describir en las diapositivas. Primero, crearemos un archivo AppSettings.json, un archivo estático que vivirá en el directorio wwwroot y contendrá los valores que acabamos de copiar de Auth0. Reemplace su contenido predeterminado con la nota Auth0 que contiene Authority y ClientId, y como se dijo, pegue los valores que acaba de copiar en la demostración anterior. ¡Cuidado! Cuando los copia desde Auth0, no comienza con HTTPS. El valor aquí debe comenzar con HTTPS. El segundo paso fue agregar el paquete NuGet de autenticación. Diríjase a NuGet, así que administre los paquetes de NuGet y agregue Microsoft.AspNetCore. Paquete Componentes.WebAssembly.Authentication. También necesitamos traer una referencia de script en index.html. Así que iremos allí y agregaremos una referencia a AuthenticationService.js, que viene incluido con la biblioteca de autenticación. Aquí, verá que se usa la misma sintaxis que usamos antes al hacer referencia a archivos estáticos de una biblioteca. Este script nos ayudará a ejecutar las operaciones de autenticación en el lado del cliente. En el tercer paso. Con el paquete agregado, ahora podemos ir a program.cs y agregar los servicios adicionales requeridos al contenedor DI. Estamos usando aquí AddOidcAuthentication que no es específico de Auth0 que viene con el paquete de autenticación, pero se puede usar para Auth0, ya que es un proveedor de OIDC. Sin embargo, lo estamos configurando para usar el parámetro de sección Auth0 de appettings.json. En esta línea aquí, estamos especificando el flujo que queremos usar, y ese aquí es el flujo del código de autorización. Ahora podemos, como parte del cuarto paso, comenzar a realizar ajustes en la propia aplicación. En primer lugar, diríjase a Importaciones y traiga Microsoft.AspNetCore.Components.Authorization y Microsoft.AspNetCore.Authorization usando declaraciones. Con estos agregados, continuaremos en la propia App.razor. Echa un vistazo a los cambios que he hecho aquí. Estoy usando AuthorizeRouteView aquí dentro de Found. Como el nombre revela, este buscará si el usuario está autenticado para ver la página solicitada. Al hacerlo, se muestra este contenido y, si el usuario no tiene permiso para ver la página solicitada, se muestra el contenido No autorizado. Esta información estará disponible para el componente CascadingAuthenticationState, que rodea al enrutador. Esto lo llena automáticamente el sistema de autenticación de Blazor, y sus componentes integrados lo usan para obtener información de autenticación, y también podemos usarlo manualmente. A continuación, necesitaremos crear dos componentes, uno para permitir que el usuario inicie sesión y otro para mostrar el estado de la autenticación. Así que mostrará el nombre de usuario si está conectado. Primero, trabajemos en el componente que nos permitirá realizar el inicio de sesión. Lo llamaré Authentication.razor. Aquí está el código para este componente, y lo puse en la carpeta Páginas. Recuerde que agregamos en Auth0 algunas URL para registrar la devolución de llamada y el cierre de sesión. Bueno, usarlos en la aplicación en realidad requiere que creemos una página en la aplicación que manejará estas diferentes etapas de autenticación, y esa será esta página. Contiene el componente RemoteAuthenticatedView, que administra el estado de autenticación del usuario e interactuará con el servidor de autorización del lado de Auth0. Es nuevamente un componente que viene con el paquete de autenticación, pero que podemos usar en combinación con Auth0. Para iniciar sesión, no se necesita código adicional, pero para cerrar sesión, como podemos ver, se necesita algo de lógica adicional. Esto es necesario para desconectarse de Auth0. A continuación, agregué otro componente y esta vez en el soporte Componentes, ya que no es un componente de página completa. Este es el componente AuthenticationStatus, y puede ver su código aquí. Este componente lo colocaremos en el diseño y se usará para mostrar si el usuario ha iniciado sesión o no. De lo contrario, se muestra el enlace de inicio de sesión y, si ha iniciado sesión, se muestra el nombre de usuario. así como un botón para cerrar sesión. Eso ahora nos está redirigiendo a la página de autenticación, /logout, que luego desencadena el proceso de cierre de sesión. Todo esto es de nuevo usando AuthorizeView. Aquí está el diseño principal actualizado con este componente ahora incluido. Con esto, la aplicación está correctamente configurada, creo. Ahora podemos probarlo. Aquí está la aplicación en ejecución. Ahora podemos iniciar sesión, seremos redirigidos a Auth0, que es Iniciar sesión aquí, y ahora nos hemos autenticado con éxito en la aplicación. Aunque ahora podemos autenticarnos en la aplicación, aún es posible navegar directamente a las páginas y omitir la autenticación. Lo arreglaremos en la próxima demostración. Aquí está el diseño principal actualizado con este componente ahora incluido. Con esto, la aplicación está correctamente configurada, creo. Ahora podemos probarlo. Aquí está la aplicación en ejecución. Ahora podemos iniciar sesión, seremos redirigidos a Auth0, que es Iniciar sesión aquí, y ahora nos hemos autenticado con éxito en la aplicación. Aunque ahora podemos autenticarnos en la aplicación, aún es posible navegar directamente a las páginas y omitir la autenticación. Lo arreglaremos en la próxima demostración. Aquí está el diseño principal actualizado con este componente ahora incluido. Con esto, la aplicación está correctamente configurada, creo. Ahora podemos probarlo. Aquí está la aplicación en ejecución. Ahora podemos iniciar sesión, seremos redirigidos a Auth0, que es Iniciar sesión aquí, y ahora nos hemos autenticado con éxito en la aplicación. Aunque ahora podemos autenticarnos en la aplicación, aún es posible navegar directamente a las páginas y omitir la autenticación. Lo arreglaremos en la próxima demostración. todavía es posible navegar directamente a las páginas y omitir la autenticación. Lo arreglaremos en la próxima demostración. todavía es posible navegar directamente a las páginas y omitir la autenticación. Lo arreglaremos en la próxima demostración.

Configuración de autorización

Con la autenticación agregada, ahora veremos lo que necesitamos para agregar la autorización. Nuevamente, haremos esto principalmente en una demostración. Los dos bloques de construcción más importantes para agregar compatibilidad con la autorización son el atributo Authorize y el componente AuthorizeView. Cuando agregamos el atributo Autorizar a un componente, que está disponible a través del enrutamiento, por lo general, una página, el usuario será redirigido a la página de Autenticación. Si queremos cambiar la visibilidad de parte de la interfaz de usuario en función de la información de autorización, podemos usar el componente AuthorizeView. En ese componente, podemos especificar qué contenido anidado se puede mostrar si el usuario está correctamente autenticado o tiene los roles correctos. De lo contrario, se mostrará otro contenido o ningún contenido.

Demostración: configuración de la autorización

Volvamos a Visual Studio y ahora usemos el atributo Autorizar para ocultar componentes de página completos detrás del muro de inicio de sesión. Luego, también usaremos el componente AuthorizeView para ocultar partes del menú si el usuario no está autenticado. Ahora podemos proteger las páginas a las que no queremos que accedan los usuarios no autenticados agregando el atributo Autorizar. Aquí está la descripción general de los empleados, y ahora he agregado el @atributo [Autorizar] aquí. Si ahora volvemos a ejecutar la aplicación, veremos que ya no podemos acceder a la página si no estamos logueados. Eso es lo que queríamos. Y también deberíamos echar otro vistazo al menú, ya que incluso cuando no estamos conectados, me muestra los enlaces para agregar un nuevo empleado, así como un enlace a la descripción general del empleado. Ahora he agregado AuthorizeView alrededor de estos dos NavLinks. Esto hará que estos elementos del menú no se muestren. Si volvemos a ejecutar la aplicación, vemos que estos dos ahora están ocultos cuando no hemos iniciado sesión. Por supuesto, se mostrarán nuevamente cuando hayamos iniciado sesión correctamente.

Demostración Protección de las llamadas a la API

En la última parte, ahora presentaremos una capa más de seguridad asegurando las llamadas API, y esto lo haremos completamente en demostraciones. Primero, regresaré a Auth0 y registraré mi API allí. En la segunda parte de la demostración, ahora configuraremos los extremos de la API en la aplicación y luego haremos cambios para que las llamadas a la API también se autentiquen. En este punto, la API no está protegida y, básicamente, todos pueden acceder a ella. Esa no será una buena solución en una situación del mundo real. Y terminemos esta configuración observando cómo podemos bloquear el acceso no autorizado a la API. Al final, ocultar ciertas funciones de la aplicación Blazor no ayudará, ya que se ejecuta en el lado del cliente y los usuarios siempre pueden omitir las medidas de seguridad que ponemos dentro de la aplicación Blazor. Primero regresaremos a la interfaz Auth0, y aquí, ahora seleccionaremos las API. Haremos clic en Crear API. En el cuadro de diálogo, le daremos a la API un nombre nuevamente y un identificador conocido como Audiencia. Como dice aquí, se recomienda que esta sea una URL, pero no se usará. De hecho, no es necesario que sea una URL real. Deje el Algoritmo de firma en su valor predeterminado y luego haga clic en Crear. En este punto, Auth0 está configurado. Ahora, tenemos que volver a Visual Studio y hacer cambios en appsettings.json del proyecto API para el que contiene los controles. Allí, ahora agregaremos el código de configuración para todos los Auth0. El dominio es el mismo que ya usamos, pero ahora sin HTTPS. Luego, en la Audiencia, coloque el identificador de la API. También necesitamos traer un paquete NuGet que nos ayudará con la autorización de las API del servidor, y ese es el paquete Microsoft.AspNetCore.Authentication.JwtBearer. Con ese paquete agregado, ahora necesitamos hacer algunos cambios en program.cs nuevamente. El código que agregué aquí ahora configuró nuestro proyecto API para usar autorización basada en tokens de portador. En otras palabras, se deberá enviar un token junto con la solicitud y se validará. Solo si el token está incluido y es válido, se otorgará acceso a la API. También necesitamos incorporar middleware para que se admitan la autenticación y la autorización. Ahora podemos volver a nuestros controladores y agregar aquí también el atributo Autorizar. He hecho esto ahora para el EmployeeController. Si ahora ejecutamos nuestra aplicación nuevamente, obtendremos una excepción. De hecho, ¿qué está pasando ahora? Pues seguimos desde nuestra aplicación Blazor, intentando enviar la petición sin token incluido, y eso ahora está bloqueado por la API. Por lo tanto, tendremos que realizar cambios adicionales en la aplicación Blazor para que se incluya el token. Ese token es el token de acceso y podemos configurar fácilmente Blazor para incluir el token con cualquier llamada a la API que hagamos. Para hacer esto en el programa, cuando hago mis llamadas usando HttpClient, ahora voy a decir que quiero usar BaseAddressAuthorizationMessageHandler como el controlador de mensajes HTTP. Esto adjuntará el token para nosotros automáticamente a la solicitud realizada al URI basado en aplicaciones. Así que ese es el que aloja el controlador. Mientras estamos en el programa, también necesitamos agregar esta línea aquí. Estoy agregando aquí el parámetro Audiencia. Esto le permitirá a Auth0 saber que estamos llamando a la API, que se identifica por el valor de configuración de Audiencia. Todavía tenemos que hacer otro cambio, y eso es agregar Audience en appsettings.json de la aplicación Blazor. Ese es el identificador que creamos para la API. Si ahora volvemos a ejecutar la aplicación, nuestra API está, por supuesto, protegida y nuestra aplicación Blazor vuelve a funcionar bien, ahora incluye el token con la solicitud HTTP.

Resumen

Buen trabajo. Nuestra aplicación ahora está asegurada. En este módulo, hemos introducido con éxito la autenticación mediante el uso de un proveedor OIDC. Como mencioné, a veces se hacen muchas cosas por ti, y eso es algo bueno. Uno de los principales ayudantes aquí es la biblioteca de autenticación, a la que nos referimos como un paquete NuGet. Eso funciona bien en combinación con Auth0, el proveedor OIDC que hemos usado aquí. Finalmente, también analizamos cómo podemos proteger las API, nuevamente con la ayuda de Auth0. ¿Estamos seguros de que nuestros componentes funcionan bien? Deberíamos escribir algunas pruebas para eso, y eso es lo que haremos en el siguiente módulo.