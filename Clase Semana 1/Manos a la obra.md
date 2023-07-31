# Contenido de la Semana 1 - Introducción a la Programación de Software y Paradigmas de Programación Orientada a Objetos

### Cátedra Programación de Software y Programática 

**Presentación:**

¡Hola a todos, me llamo Daniel Villamizar y seré su profesor para este curso de programación orientada a objetos (POO)! Soy ingeniero informático con más de 18 años de experiencia en el campo. He trabajado en una variedad de proyectos, desde software empresarial hasta juegos y aplicaciones móviles. Estoy emocionado de compartir mi conocimiento con ustedes y ayudarlos a aprender los fundamentos de la POO.

En este curso, aprenderemos sobre los conceptos básicos de la POO, como clases, objetos, herencia, polimorfismo e interfaces. También desarrollaremos habilidades prácticas en el desarrollo de software orientado a objetos.

**Al final de este curso, los estudiantes serán capaces de:**

- Definir y explicar los conceptos básicos de la POO.
- Desarrollar clases y objetos en un lenguaje de programación orientado a objetos.
- Utilizar la herencia para extender la funcionalidad de las clases.
- Aplicar el polimorfismo para reutilizar código.
- Implementar interfaces para definir comportamientos comunes.
  
Espero que disfruten este curso tanto como yo. **¡Comencemos!**

**Introducción a la programación orientada a objetos**

**Concepto:** 

La programación orientada a objetos **(POO)** es un paradigma de programación que modela sistemas usando objetos. Un objeto es una entidad que tiene datos y comportamiento. Los datos de un objeto se denominan estado y el comportamiento de un objeto se denomina comportamiento.
La POO es un paradigma poderoso que se utiliza para desarrollar software de alta calidad. 

**Algunas de las ventajas de la POO incluyen:**

- **Facilidad de mantenimiento:** el código orientado a objetos es más fácil de mantener que el código procedural porque los objetos están bien definidos y organizados.
- **Flexibilidad:** la POO es muy flexible y se puede utilizar para desarrollar una amplia gama de aplicaciones.
- **Portabilidad:** el código orientado a objetos es más portable que el código procedural porque los objetos están independientes de la plataforma.

**Herramientas:** Las herramientas que utilizaremos para crear los ejemplos de POO son Visual Studio y C#. Visual Studio es un entorno de desarrollo integrado (IDE) que nos permite crear y depurar programas en C#. C# es un lenguaje de programación orientado a objetos desarrollado por Microsoft.

**Ejercicios:**

- **Cree una clase para representar un automóvil.** La clase debería tener datos para representar el color, el modelo y el año del automóvil. También debería tener métodos para representar el arranque del automóvil, la conducción del automóvil y el estacionamiento del automóvil.
- **Cree una clase para representar una persona.** La clase debería tener datos para representar el nombre, la edad y la dirección de la persona. También debería tener métodos para representar la conversación de la persona, la caminata de la persona y la comida de la persona.
- **Cree una clase para representar un banco.** La clase debería tener datos para representar el nombre del banco, la dirección del banco y la lista de clientes del banco. También debería tener métodos para representar la apertura de una cuenta, la transferencia de fondos y el pago de facturas.

## **Conceptos fundamentales de la POO**

**Los conceptos fundamentales de la POO son:**

- **Clases:** una clase es una plantilla para crear objetos. Una clase define los datos y el comportamiento de los objetos que crea.
- **Objetos:** un objeto es una instancia de una clase. Un objeto tiene los datos y el comportamiento definidos por su clase.
- **Herencia:** la herencia es la capacidad de una clase de heredar los datos y el comportamiento de otra clase.
- **Polimorfismo:** el polimorfismo es la capacidad de una función para realizar diferentes tareas dependiendo del tipo de objeto al que se llama.
- Interfaces: una interfaz es un contrato que define los comportamientos comunes de una clase.

**Ejemplos prácticos de implementación de paradigmas de programación orientada a objetos**

A continuación, se presentan algunos ejemplos prácticos de implementación de paradigmas de programación orientada a objetos:

**Creación de una clase para representar un automóvil:** la clase podría tener datos para representar el color, el modelo y el año del automóvil. También podría tener métodos para representar el arranque del automóvil, la conducción del automóvil y el estacionamiento del automóvil.
  
**Ejemplo Clase Automóvil:**
```
public class Car
{
    public string Color { get; set; }
    public string Model { get; set; }
    public int Year { get; set; }

    public void Start()
    {
        // Iniciar el automóvil
    }

    public void Drive()
    {
        // Conducir el automóvil
    }

    public void Park()
    {
        // Estacionar el automóvil
    }
}
```

- **public class Car:** Esto define la clase "Car", que es una plantilla o molde para crear objetos que representan automóviles.
- **public string Color { get; set; }:** Aquí tenemos una propiedad llamada "Color". Una propiedad es una variable que está asociada a la clase y permite acceder y modificar su valor. En este caso, la propiedad "Color" es una cadena de texto que representa el color del automóvil.
- **public string Model { get; set; }:** Esta es otra propiedad llamada "Model", que representa el modelo del automóvil.
- **public int Year { get; set; }:** La propiedad "Year" es un entero que indica el año de fabricación del automóvil.
- **public void Start():** Aquí tenemos un método llamado "Start". Los métodos son acciones que puede realizar un objeto de la clase. En este caso, el método "Start" representa la acción de iniciar el automóvil.
- **public void Drive():** El método "Drive" representa la acción de conducir el automóvil.
- **public void Park():** Por último, el método "Park" representa la acción de estacionar el automóvil.

Este código define una clase "Car" con atributos que representan el color, modelo y año del automóvil, y métodos que permiten iniciar, conducir y estacionar el automóvil. Esta clase podría utilizarse como base para crear objetos específicos de automóviles con sus características únicas. **Por ejemplo:**

Car miCarro = new Car();
miCarro.Color = "Rojo";
miCarro.Model = "Sedán";
miCarro.Year = 2022;

miCarro.Start(); // Inicia el automóvil
miCarro.Drive(); // Conduce el automóvil
miCarro.Park();  // Estaciona el automóvil

**Para crear la clase "Car" en Visual Studio, sigue los siguientes pasos:**

1.	Abrir Visual Studio: Inicia el entorno de desarrollo integrado (IDE) Visual Studio en tu computadora.

2.	Crear un nuevo proyecto: Selecciona "Archivo" en la barra de menú, luego "Nuevo" y finalmente "Proyecto".

3.	Seleccionar el tipo de proyecto: En la ventana "Nuevo Proyecto", elige el tipo de proyecto que desees crear. Por ejemplo, puedes seleccionar "Aplicación web ASP.NET" si deseas crear una aplicación web con C#.

4.	Elegir la plantilla de proyecto: En la siguiente ventana, selecciona la plantilla que mejor se adapte a tu proyecto. Puedes elegir una plantilla predeterminada para aplicaciones web, como "Aplicación web ASP.NET Vacía".

5.	Nombrar el proyecto y la solución: Dale un nombre a tu proyecto y, si lo deseas, elige una ubicación para guardarlo. También puedes seleccionar o crear una solución para el proyecto.

6.	Crear la clase "Car": Una vez creado el proyecto, haz clic derecho sobre la carpeta del proyecto en el Explorador de soluciones y selecciona "Agregar" > "Nuevo elemento".

7.	Seleccionar "Clase": En la ventana "Agregar nuevo elemento", elige "Clase" y haz clic en "Agregar".

8.	Nombrar la clase: Escribe "Car" como nombre de la clase y asegúrate de que el lenguaje esté configurado en "C#".

9.	Definir los atributos de la clase: Agrega las propiedades "Color", "Model" y "Year" a la clase "Car" utilizando la sintaxis de propiedades de C#. **Por ejemplo:**

public class Car
{
    public string Color { get; set; }
    public string Model { get; set; }
    public int Year { get; set; }
}

Agregar los métodos a la clase: Añade los métodos "Start", "Drive" y "Park" a la clase "Car". Puedes utilizar la misma sintaxis de métodos en C#. Por ejemplo:
public class Car
{
    public string Color { get; set; }
    public string Model { get; set; }
    public int Year { get; set; }

    public void Start()
    {
        // Implementación del método Start
    }

    public void Drive()
    {
        // Implementación del método Drive
    }

    public void Park()
    {
        // Implementación del método Park
    }
}

Una vez que hayamos completado estos pasos, tendrás creada la clase "Car" en tu proyecto de Visual Studio. Puedes utilizar esta clase como base para crear objetos que representen automóviles y utilizar sus atributos y métodos en tu aplicación.

**Creación de una clase para representar una persona:** la clase podría tener datos para representar el nombre, la edad y la dirección de la persona. También podría tener métodos para representar la conversación de la persona, la caminata de la persona y la comida de la persona.

**Ejemplo Clase Persona:**

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Métodos de la clase
    public void Talk()
    {
        // Método "Hablar"
        // Este método representa la acción de hablar con alguien.
        // Dentro de este método, se podría agregar código para mostrar un mensaje en la consola o realizar alguna acción específica relacionada con hablar.
    }

    public void Walk()
    {
        // Método "Caminar"
        // Este método representa la acción de caminar.
        // Al igual que en el método "Talk", se podría agregar código para mostrar mensajes o realizar acciones relacionadas con caminar.
    }

    public void Eat()
    {
        // Método "Comer"
        // Este método representa la acción de comer.
        // Al igual que en los métodos anteriores, aquí también se podría agregar código para mostrar mensajes o realizar acciones relacionadas con comer.
    }
}

**Nota:** Una **"propiedad autoimplementada"** (también conocida como **"propiedad automática"** o **"propiedad auto-implementada"**) es una característica en C# que permite definir rápidamente propiedades de una clase sin necesidad de crear campos privados y métodos **"getter"** y **"setter"** por separado.

En lugar de definir explícitamente un campo privado y métodos **"getter"** y **"setter"** para una propiedad, se puede utilizar la sintaxis de propiedad autoimplementada. Esta sintaxis simplificada permite que el compilador genere automáticamente un campo privado y los métodos de acceso (getter y setter) para la propiedad en tiempo de compilación.
La sintaxis de una propiedad autoimplementada es la siguiente:

public TipoDeDato NombreDePropiedad { get; set; }

**Donde:**

- "public": Es el modificador de acceso que especifica que la propiedad es accesible desde cualquier parte del programa.
- "TipoDeDato": Es el tipo de dato que representa el valor almacenado en la propiedad.
- "NombreDePropiedad": Es el nombre de la propiedad que se va a definir.

Al utilizar esta sintaxis, el compilador crea automáticamente un campo privado para almacenar el valor de la propiedad y genera los métodos "getter" y "setter" para acceder y modificar ese valor. Los nombres de estos campos y métodos serán generados automáticamente por el compilador y no se verán explícitamente en el código fuente.

**Un ejemplo de propiedad autoimplementada sería:**

public class Persona
{
    public string Nombre { get; set; }
    public int Edad { get; set; }
}

En este caso, las propiedades **"Nombre"** y **"Edad"** son propiedades autoimplementadas. El compilador generará automáticamente el campo privado para cada propiedad y los métodos **"getter"** y **"setter"** para acceder y modificar el valor de las propiedades.

Volvamos al ejemplo de la clase persona, la clase **"Person"** tiene tres atributos: **"Name"** (nombre), **"Age"** (edad) y **"Address"** (dirección), todos con sus respectivos métodos para obtener y establecer los valores de los atributos (propiedades autoimplementadas). Además, la clase tiene tres métodos: **"Talk"** (hablar), **"Walk"**(caminar) y **"Eat"** (comer), que representan acciones que una persona podría realizar. Es importante tener en cuenta que, en el código proporcionado, los métodos no contienen implementación específica (el contenido dentro de las llaves está comentado con "//"), ya que es solo una representación básica de la estructura de la clase. En una aplicación real, estos métodos contendrían el código necesario para realizar las acciones mencionadas.
En una aplicación real, los métodos dentro de la clase **"Person"** contendrían el código necesario para realizar las acciones mencionadas en su implementación específica. Aquí te doy un ejemplo de cómo podrían ser implementados los métodos en una aplicación real:

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Métodos de la clase
    public void Talk()
    {
        // Método "Hablar"
        // Implementación específica para el método Talk en una aplicación real:
        Console.WriteLine("Hola, ¿cómo estás?"); // Mostrar un mensaje en la consola.
    }

    public void Walk()
    {
        // Método "Caminar"
        // Implementación específica para el método Walk en una aplicación real:
        Console.WriteLine("Caminando..."); // Mostrar un mensaje en la consola.
    }

    public void Eat()
    {
        // Método "Comer"
        // Implementación específica para el método Eat en una aplicación real:
        Console.WriteLine("¡Hora de comer!"); // Mostrar un mensaje en la consola.
        // Código adicional para realizar acciones relacionadas con comer, como registrar la comida consumida o calcular calorías, por ejemplo.
    }
}

En este ejemplo, hemos agregado una implementación específica para cada uno de los métodos **"Talk"**, **"Walk"** y **"Eat"**. Al llamar a estos métodos en una aplicación real, se mostrarían mensajes específicos en la consola y se podrían llevar a cabo acciones adicionales relacionadas con las acciones que representan.
Es importante destacar que la implementación de los métodos puede variar significativamente dependiendo de la funcionalidad requerida en la aplicación. En una aplicación real, los métodos podrían interactuar con bases de datos, realizar cálculos complejos, comunicarse con servicios externos, entre otras muchas posibilidades. La idea principal es que los métodos contengan el código necesario para realizar las acciones específicas que se deseen lograr en la aplicación en la que se esté trabajando.
En una aplicación real, la implementación de los métodos puede ser mucho más compleja y variada que en el ejemplo que proporcioné anteriormente. Permíteme explicarte con más detalle cómo los métodos podrían interactuar con bases de datos, realizar cálculos complejos y comunicarse con servicios externos:

1.	Interacción con bases de datos: En una aplicación real, los métodos pueden estar diseñados para recuperar y almacenar información en una base de datos. Por ejemplo, el método "Talk" podría almacenar mensajes de conversación en una tabla de la base de datos, mientras que el método "Eat" podría registrar los alimentos consumidos por una persona en una tabla de registro de comidas.
2.	Cálculos complejos: En aplicaciones más complejas, los métodos pueden involucrar algoritmos y cálculos sofisticados. Por ejemplo, en un sistema de procesamiento de imágenes, el método "ProcessImage" podría aplicar filtros, detectar bordes o realizar operaciones matemáticas avanzadas sobre la imagen.
3.	Comunicación con servicios externos: En muchas aplicaciones, es necesario comunicarse con servicios externos, como API web, servicios en la nube o sistemas de terceros. Por ejemplo, el método "GetDataFromExternalAPI" podría hacer una solicitud HTTP a una API externa para obtener datos y luego procesar la respuesta.
4.	Validación y control de errores: En aplicaciones reales, los métodos deben tener en cuenta la validación de datos y el manejo de errores. Por ejemplo, antes de realizar una operación de almacenamiento en la base de datos, el método debe validar los datos de entrada y asegurarse de que sean válidos y seguros.
5.	Seguridad y autenticación: En aplicaciones que manejan información confidencial, los métodos pueden estar involucrados en la autenticación de usuarios y la aplicación de medidas de seguridad para proteger los datos y garantizar que solo los usuarios autorizados tengan acceso a ciertas funcionalidades.
La idea principal es que los métodos estén diseñados para realizar tareas específicas y que sean flexibles y escalables para adaptarse a las necesidades de la aplicación. Cada método debe cumplir con su función asignada y contribuir al funcionamiento adecuado de la aplicación en su conjunto. En el desarrollo de aplicaciones reales, la implementación de los métodos es un proceso complejo y crucial para lograr una funcionalidad completa y efectiva del software.
A continuación, te mostraré cómo se podría reflejar cada uno de los aspectos mencionados en el código de la clase "Persona" en C#:

**1.	Interacción con bases de datos:**

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Método para guardar la información de la persona en la base de datos
    public void SaveToDatabase()
    {
        // Código para conectar con la base de datos y almacenar los datos de la persona.
        // Por ejemplo, utilizando ADO.NET, Entity Framework o algún ORM (Object-Relational Mapping).
    }

    // Método para cargar la información de la persona desde la base de datos
    public void LoadFromDatabase(int personId)
    {
        // Código para buscar la información de la persona en la base de datos utilizando el ID proporcionado.
        // Por ejemplo, utilizando ADO.NET, Entity Framework o algún ORM (Object-Relational Mapping).
    }
}

Para ejemplificar el código de la clase **"Person"** que incluye los métodos para guardar y cargar información de la base de datos, necesitaremos simular una conexión a una base de datos utilizando **Entity Framework**. Entity Framework es un **ORM** (Object-Relational Mapping) que permite mapear objetos en una base de datos relacional y facilita la manipulación de datos. Aquí te presento un ejemplo sencillo de cómo se podría utilizar Entity Framework para guardar y cargar información de la base de datos en la clase "Person":
Supongamos que tenemos una base de datos llamada "PersonDB" con una tabla "People" que tiene las siguientes columnas: **"Id"** (identificador), **"Name"** (nombre), **"Age"** (edad) y **"Address"** (dirección).

using System;
using System.Linq;
using Microsoft.EntityFrameworkCore;

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Método para guardar la información de la persona en la base de datos
    public void SaveToDatabase()
    {
        using (var dbContext = new PersonDbContext())
        {
            // Agregar la persona al contexto de Entity Framework
            dbContext.People.Add(this);

            // Guardar los cambios en la base de datos
            dbContext.SaveChanges();
        }
    }

    // Método para cargar la información de la persona desde la base de datos
    public static Person LoadFromDatabase(int personId)
    {
        using (var dbContext = new PersonDbContext())
        {
            // Buscar la persona en la base de datos por su Id
            var person = dbContext.People.Find(personId);

            return person;
        }
    }
}

public class PersonDbContext : DbContext
{
    // DbSet para la tabla "People" en la base de datos
    public DbSet<Person> People { get; set; }

    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        // Configurar la cadena de conexión a la base de datos
        optionsBuilder.UseSqlServer("Data Source=(localdb)\\MSSQLLocalDB;Initial Catalog=PersonDB;Integrated Security=True");
    }
}

En este ejemplo, hemos creado una clase **"Person"** que tiene los atributos **"Name"**, **"Age"** y **"Address"**, junto con los métodos **"SaveToDatabase"** y **"LoadFromDatabase"**. Para utilizar Entity Framework, hemos creado un contexto de base de datos "PersonDbContext" que hereda de DbContext y que incluye un DbSet para la tabla **"People"**.

En el método **"SaveToDatabase"**, utilizamos el contexto de Entity Framework para agregar la persona actual (this) al contexto y luego guardar los cambios en la base de datos mediante el método **"SaveChanges"**.
En el método **"LoadFromDatabase"**, utilizamos el contexto para buscar una persona en la base de datos por su Id y luego la retornamos.
Es importante tener en cuenta que este es solo un ejemplo básico para ilustrar el uso de Entity Framework en la clase **"Person"**. En una aplicación real, habría más consideraciones de seguridad, manejo de errores y optimización de consultas, entre otros aspectos a tener en cuenta.

A continuación, te mostraré cómo se podría mejorar el código para tener en cuenta consideraciones importantes en una aplicación real, como seguridad, manejo de errores y optimización de consultas utilizando Entity Framework:

using System;
using System.Linq;
using Microsoft.EntityFrameworkCore;

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Método para guardar la información de la persona en la base de datos
    public void SaveToDatabase()
    {
        try
        {
            using (var dbContext = new PersonDbContext())
            {
                // Agregar la persona al contexto de Entity Framework
                dbContext.People.Add(this);

                // Guardar los cambios en la base de datos
                dbContext.SaveChanges();
            }
        }
        catch (DbUpdateException ex)
        {
            // Manejo de errores específicos de Entity Framework al guardar en la base de datos.
            // Aquí podrías realizar acciones como registrar el error en un archivo de registro o notificar al administrador del sistema.
            Console.WriteLine("Error al guardar la persona en la base de datos: " + ex.Message);
        }
    }

    // Método para cargar la información de la persona desde la base de datos
    public static Person LoadFromDatabase(int personId)
    {
        try
        {
            using (var dbContext = new PersonDbContext())
            {
                // Buscar la persona en la base de datos por su Id
                var person = dbContext.People.Find(personId);

                return person;
            }
        }
        catch (Exception ex)
        {
            // Manejo de errores al cargar la información desde la base de datos.
            // Aquí podrías realizar acciones como registrar el error en un archivo de registro o mostrar un mensaje de error al usuario.
            Console.WriteLine("Error al cargar la persona desde la base de datos: " + ex.Message);
            return null;
        }
    }
}

public class PersonDbContext : DbContext
{
    // DbSet para la tabla "People" en la base de datos
    public DbSet<Person> People { get; set; }

    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        // Configurar la cadena de conexión a la base de datos
        optionsBuilder.UseSqlServer("Data Source=(localdb)\\MSSQLLocalDB;Initial Catalog=PersonDB;Integrated Security=True");
    }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        // Configurar reglas de seguridad u otras configuraciones de Entity Framework, si es necesario.
    }
}

**En este ejemplo, hemos realizado las siguientes mejoras:**

**- Manejo de errores:** Se han agregado bloques **"try-catch"** en los métodos **"SaveToDatabase"** y **"LoadFromDatabase"** para capturar excepciones que puedan ocurrir al interactuar con la base de datos a través de Entity Framework. De esta manera, si ocurre algún error, podemos manejarlo adecuadamente y tomar acciones específicas, como registrar el error o mostrar un mensaje de error al usuario.
**- Consideraciones de seguridad:** Aunque en este ejemplo no hemos implementado reglas de seguridad específicas, es importante tener en cuenta que, en una aplicación real, debemos considerar medidas de seguridad, como validar y sanitizar los datos de entrada, proteger la base de datos contra ataques de inyección de SQL y asegurarnos de que los usuarios tengan los permisos adecuados para acceder a los datos.
**- Optimización de consultas:** En este ejemplo, hemos utilizado el método **"Find"** de DbSet para buscar una persona por su Id, que es una consulta eficiente si el Id es una clave primaria. Sin embargo, en aplicaciones más complejas, es posible que necesitemos realizar consultas más elaboradas y optimizarlas utilizando las capacidades de consultas de LINQ o SQL de Entity Framework.

**Nota:** Recuerda que el código real puede variar dependiendo de las necesidades específicas de la aplicación y de las políticas de seguridad y manejo de errores que se deseen implementar. Estas mejoras son solo ejemplos básicos para ilustrar cómo podemos tener en cuenta consideraciones importantes en una aplicación real que utiliza Entity Framework.

**2.	Cálculos complejos:**

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Método para calcular la edad promedio de un grupo de personas
    public static double CalculateAverageAge(List<Person> people)
    {
        // Código para realizar el cálculo del promedio de edades del grupo de personas.
        // Por ejemplo, utilizando LINQ o algoritmos matemáticos específicos.
        int totalAge = 0;
        foreach (Person person in people)
        {
            totalAge += person.Age;
        }
        return totalAge / (double)people.Count;
    }
}


**3.	Comunicación con servicios externos:**

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Método para obtener información de una API externa
    public void GetDataFromExternalAPI(string apiUrl)
    {
        // Código para realizar una solicitud HTTP a la API externa utilizando HttpClient o WebClient, por ejemplo.
        // Luego, procesar la respuesta y actualizar los atributos de la persona con la información obtenida.
    }
}


**4.	Validación y control de errores:**

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Método para validar la edad de una persona
    public bool ValidateAge()
    {
        // Código para verificar que la edad esté dentro de un rango válido (por ejemplo, entre 0 y 120 años).
        // En caso de que la edad no cumpla con los criterios de validación, se podría lanzar una excepción o devolver false.
        if (Age >= 0 && Age <= 120)
        {
            return true;
        }
        return false;
    }
}


**5.	Seguridad y autenticación:**

public class Person
{
    // Atributos de la clase (propiedades autoimplementadas)
    public string Name { get; set; }   // Atributo "Nombre" de tipo cadena de texto (string)
    public int Age { get; set; }       // Atributo "Edad" de tipo entero (int)
    public string Address { get; set; } // Atributo "Dirección" de tipo cadena de texto (string)

    // Método para autenticar a una persona en la aplicación
    public bool Authenticate(string username, string password)
    {
        // Código para verificar que el usuario y contraseña proporcionados coincidan con los almacenados en la base de datos.
        // Si la autenticación es exitosa, se podría devolver true; de lo contrario, false.
    }
}

En cada uno de los métodos mencionados, la implementación dependerá de la lógica específica que se desee lograr en la aplicación. Estos ejemplos ilustran cómo los métodos de la clase "Person" podrían extenderse para incluir funcionalidades más complejas y abarcar distintos aspectos de una aplicación real. Es importante recordar que el código real puede variar dependiendo de los requerimientos y características de cada proyecto en particular.

**Creación de una clase para representar un banco:** la clase podría tener datos para representar el nombre del banco, la dirección del banco y la lista de clientes del banco. También podría tener métodos para representar la apertura de una cuenta, la transferencia de fondos y el pago de facturas.

**Ejemplo Clase Bank:**

public class Bank
{
    public string Name { get; set; }
    public string Address { get; set; }
    public List<Customer> Customers { get; set; }

    public void OpenAccount()
    {
        // Abrir una cuenta bancaria
    }

    public void TransferFunds()
    {
        // Transferir fondos entre cuentas
    }

    public void PayBills()
    {
        // Pagar facturas
    }
}

El código proporcionado define una clase llamada **"Bank"** (Banco en español) que representa un banco en un sistema. Explicaré cada parte del código:

**Atributos de la clase:**

- **"Name":** Representa el nombre del banco y es una propiedad (propiedad autoimplementada) que permite obtener y establecer el valor del nombre del banco.
- **"Address":** Representa la dirección del banco y también es una propiedad que permite obtener y establecer el valor de la dirección.
- **"Customers":** Es una lista de objetos de la clase "Customer" (Cliente en español) que almacena la información de los clientes que tienen cuentas en este banco. Los clientes se almacenarán en una lista y se podrán agregar, eliminar y modificar.

**Métodos de la clase:**

- **"OpenAccount()":** Este método representa la acción de abrir una cuenta bancaria en el banco. Aunque en el código proporcionado no hay implementación detallada (se comentó con **"// Open a bank account"**), se podría escribir el código necesario para llevar a cabo el proceso de apertura de una cuenta, como asignar un número de cuenta único al cliente, establecer el saldo inicial, etc.

- **"TransferFunds()":** Este método representa la acción de transferir fondos entre cuentas. De manera similar al método anterior, la implementación real de la transferencia de fondos se realizaría en el lugar donde se encuentra el comentario **"// Transfer funds between accounts"**. Aquí se manejaría la lógica necesaria para asegurar que la transferencia sea válida y se actualicen los saldos de las cuentas involucradas.

- **"PayBills()":** Este método representa la acción de pagar facturas. Una vez más, la implementación real se realizaría en el lugar del comentario **"// Pay bills"**. Aquí se incluiría la lógica para verificar la disponibilidad de fondos en la cuenta del cliente y, si es posible, efectuar el pago de las facturas.

La clase **"Bank"** representa la entidad del banco y contiene propiedades para su nombre y dirección, una lista de clientes **("Customers")** y métodos para llevar a cabo acciones bancarias como abrir cuentas, transferir fondos y pagar facturas. Sin embargo, para que el código sea completamente funcional, es necesario agregar la implementación detallada de cada método.


- **Objetos:** como lo definimos anteriormente, un objeto es una instancia de una clase. Un objeto tiene los datos y el comportamiento definidos por su clase.

**Por ejemplo**, la clase **Person** podría tener los datos **name**, **age**, y **address**, y los métodos **talk**, **walk**, y **eat**. Un objeto **Person** sería una instancia de la clase **Person**, y tendría los datos y el comportamiento definidos por la clase.

**Ejemplo:**

// Define la clase Person
public class Person
{
    // Declara los datos de la clase Person
    public string Name { get; set; }
    public int Age { get; set; }
    public string Address { get; set; }

    // Declara los métodos de la clase Person
    public void Talk()
    {
        // Imprime el nombre de la persona
        Console.WriteLine(this.Name);
    }

    public void Walk()
    {
        // Imprime el mensaje "La persona está caminando"
        Console.WriteLine("La persona está caminando");
    }

    public void Eat()
    {
        // Imprime el mensaje "La persona está comiendo"
        Console.WriteLine("La persona está comiendo");
    }
}

// Crea una instancia de la clase Person
Person person = new Person();

// Asigna valores a los datos de la instancia
person.Name = "Juan";
person.Age = 25;
person.Address = "Calle 123, Ciudad de México";

// Llama a los métodos de la instancia
person.Talk();
person.Walk();
person.Eat();

**Nota:** Este ejemplo crea una instancia de la clase **Person** y asigna valores a los datos de la instancia. Luego, llama a los métodos de la instancia para imprimir el nombre, la edad y la dirección de la persona, y para imprimir el mensaje **"La persona está caminando"** y **"La persona está comiendo"**.


- **Herencia:** por otro lado la herencia es la capacidad de una clase de heredar los datos y el comportamiento de otra clase.
- 
**Por ejemplo**, la clase Employee podría heredar de la clase Person. Esto significaría que la clase Employee tendría todos los datos y el comportamiento de la clase Person, más algunos datos y comportamiento adicionales específicos para los empleados.

**Ejemplo:**

// La clase Person representa a una persona.
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
    public string Address { get; set; }

    public void Talk()
    {
        // La persona habla.
    }

    public void Walk()
    {
        // La persona camina.
    }

    public void Eat()
    {
        // La persona come.
    }
}

// La clase Employee representa a un empleado.
public class Employee : Person
{
    public string EmployeeId { get; set; }
    public string JobTitle { get; set; }
    public decimal Salary { get; set; }

    public void Work()
    {
        // El empleado trabaja.
    }

    public void GetPaid()
    {
        // El empleado cobra su salario.
    }
}

**Nota:** Como puedes ver, la clase **Employee** hereda de la clase Person. Esto significa que la clase **Employee** tiene todos los datos y el comportamiento de la clase Person, más algunos datos y comportamiento adicionales específicos para los empleados. Por ejemplo, la clase **Employee** tiene los datos **EmployeeId**, **JobTitle**, y **Salary**, y los métodos **Work** y **GetPaid**.

- **Polimorfismo:** el polimorfismo es la capacidad de una función para realizar diferentes tareas dependiendo del tipo de objeto al que se llama.

**Por ejemplo**, la función **display** podría ser polimórfica. Esto significaría que la función display podría ser llamada con diferentes tipos de objetos, y la función se comportaría de forma diferente dependiendo del tipo de objeto. **Por ejemplo**, la función **display** podría ser llamada con un objeto Person, un objeto **Employee**, o un objeto **Customer**. La función display mostraría la información del objeto de una manera diferente dependiendo del tipo de objeto.

**Ejemplo:**

class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        print(f"My name is {self.name}.")

class Dog(Animal):
    def bark(self):
        print("Woof!")

class Cat(Animal):
    def meow(self):
        print("Meow!")

def display_animal(animal):
    animal.speak()

animal = Dog("Spot")
display_animal(animal)
# Output:
# My name is Spot.
# Woof!

animal = Cat("Fluffy")
display_animal(animal)
# Output:
# My name is Fluffy.
# Meow!

**Nota:** Como puede ver, la función **display_animal** puede ser llamada con diferentes tipos de objetos, y la función se comportará de forma diferente dependiendo del tipo de objeto. Cuando la función **display_animal** es llamada con un objeto **Dog**, el método **speak** del objeto **Dog** es llamado. Cuando la función **display_animal** es llamada con un objeto **Cat**, el método **speak** del objeto **Cat** es llamado.

El polimorfismo es una característica poderosa de la programación orientada a objetos que permite que el código sea más general y reutilizable.


- **Interfaces:** una interfaz es un contrato que define los comportamientos comunes de una clase.

**Por ejemplo**, la interfaz IAnimal podría definir los métodos **talk**, **walk**, y **eat**. Esto significaría que cualquier clase que implemente la interfaz **IAnimal** debe tener los métodos **talk**, **walk**, y **eat**.

**Ejemplo:**

// Interface IAnimal
interface IAnimal
{
    // Método talk
    void talk();

    // Método walk
    void walk();

    // Método eat
    void eat();
}

// Clase Dog
class Dog : IAnimal
{
    public void talk()
    {
        // El perro ladra
        Console.WriteLine("Woof!");
    }

    public void walk()
    {
        // El perro camina
        Console.WriteLine("The dog is walking.");
    }

    public void eat()
    {
        // El perro come
        Console.WriteLine("The dog is eating.");
    }
}

// Clase Cat
class Cat : IAnimal
{
    public void talk()
    {
        // El gato maúlla
        Console.WriteLine("Meow!");
    }

    public void walk()
    {
        // El gato camina
        Console.WriteLine("The cat is walking.");
    }

    public void eat()
    {
        // El gato come
        Console.WriteLine("The cat is eating.");
    }
}

// Programa principal
public class MainClass
{
    public static void Main(string[] args)
    {
        // Crea un objeto Dog
        IAnimal dog = new Dog();

        // Llama al método talk()
        dog.talk();

        // Llama al método walk()
        dog.walk();

        // Llama al método eat()
        dog.eat();

        // Crea un objeto Cat
        IAnimal cat = new Cat();

        // Llama al método talk()
        cat.talk();

        // Llama al método walk()
        cat.walk();

        // Llama al método eat()
        cat.eat();
    }
}

**Nota:**Este código crea dos clases, **Dog** y **Cat**, que implementan la interfaz **IAnimal**. La interfaz IAnimal define los métodos **talk**, **walk**, y **eat**. Las clases **Dog** y **Cat** implementan estos métodos para que sus objetos puedan hablar, caminar y comer. El programa principal crea un objeto **Dog** y un objeto **Cat**, y llama a los métodos **talk**, **walk**, y eat en cada objeto. El programa imprime las siguientes salidas:

Woof!
The dog is walking.
The dog is eating.
Meow!
The cat is walking.
The cat is eating.

Este código ilustra cómo las interfaces se pueden utilizar para definir un contrato que debe ser implementado por las clases. Esto ayuda a garantizar que las clases compartan un conjunto común de métodos, lo que puede hacer que el código sea más fácil de mantener y reutilizar.

## **Actividades por parte del estudiante**

A continuación, se presentan algunas actividades que se pueden realizar para reforzar los conceptos de programación orientada a objetos:

- Desarrollar ejercicios prácticos para ilustrar la creación de clases y objetos.
- Desarrollar pequeños programas que involucren la creación de clases y objetos.
- Practicar la herencia para entender cómo se extiende la funcionalidad entre clases relacionadas.
- Realizar ejercicios de polimorfismo para explorar el uso de métodos con comportamientos distintos.
- Implementar interfaces para definir y utilizar comportamientos comunes.
- Realizar una evaluación diagnóstica para medir el conocimiento previo de los estudiantes.
- Realizar una breve prueba escrita para evaluar el nivel de comprensión inicial.
- Discutir los resultados para identificar áreas de oportunidad y fortalezas.


# Evaluación diagnóstica que se puede utilizar para medir el conocimiento previo de los estudiantes sobre programación orientada a objetos (POO):

- Pregunta 1: ¿Cuál es la definición de una clase en POO?

Respuesta: Una clase es una plantilla para crear objetos. Una clase define los datos y el comportamiento de los objetos que crea.

- Pregunta 2: ¿Cuál es la definición de un objeto en POO?

Respuesta: Un objeto es una instancia de una clase. Un objeto tiene los datos y el comportamiento definidos por su clase.

- Pregunta 3: ¿Qué es la herencia en POO?

Respuesta: La herencia es la capacidad de una clase de heredar los datos y el comportamiento de otra clase.

- Pregunta 4: ¿Qué es el polimorfismo en POO?

Respuesta: El polimorfismo es la capacidad de una función para realizar diferentes tareas dependiendo del tipo de objeto al que se llama.

- Pregunta 5: ¿Qué es una interfaz en POO?

Respuesta: Una interfaz es un contrato que define los comportamientos comunes de una clase.

# Prueba escrita que se puede utilizar para evaluar el nivel de comprensión inicial de los estudiantes sobre POO:

- Pregunta 1: Escriba un programa en C# que cree una clase para representar un automóvil. La clase debe tener datos para representar el color, el modelo y el año del automóvil. También debe tener métodos para representar el arranque del automóvil, la conducción del automóvil y el estacionamiento del automóvil.

- Pregunta 2: Escriba un programa en C# que cree una clase para representar una persona. La clase debe tener datos para representar el nombre, la edad y la dirección de la persona. También debe tener métodos para representar la conversación de la persona, la caminata de la persona y la comida de la persona.

- Pregunta 3: Escriba un programa en C# que cree una clase para representar un banco. La clase debe tener datos para representar el nombre del banco, la dirección del banco y la lista de clientes del banco. También debe tener métodos para representar la apertura de una cuenta, la transferencia de fondos y el pago de facturas.
