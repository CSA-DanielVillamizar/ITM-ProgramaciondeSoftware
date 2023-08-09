# Actividad Semana 1 - Introducción a la Programación de Software y Paradigmas de Programación Orientada a Objetos

### Cátedra Programación de Software y Programática 

**Solución propuesta al caso de negocio:**

Una empresa de alquiler de coches quiere desarrollar un nuevo software que les permita gestionar su flota de coches. El software debe permitir a la empresa hacer lo siguiente:


- Registrar nuevos coches
- Actualizar la información de los coches
- Registrar alquileres
- Generar informes sobre los alquileres

**Conceptos de programación orientada a objetos involucrados:**

- **Clases:** la empresa puede crear diferentes clases para representar los diferentes tipos de objetos que son relevantes para su negocio, como coches, alquileres e informes. Por ejemplo, la clase Coche puede tener atributos como la matrícula, la marca, el modelo y el año. La clase Alquiler puede tener atributos como la fecha de inicio, la fecha de fin, el cliente y el coche. La clase Informe puede tener atributos como el nombre del informe, el período de tiempo y los datos contenidos en el informe.
 

- **Objetos:** la empresa puede crear objetos de cada clase para representar instancias específicas de los objetos representados por las clases. Por ejemplo, la empresa puede crear un objeto Coche para representar un coche específico, como un Ford Fiesta 2023. La empresa puede crear un objeto Alquiler para representar un alquiler específico, como un alquiler de un Ford Fiesta 2023 del 1 de enero al 15 de enero. La empresa puede crear un objeto Informe para representar un informe específico, como un informe de todos los alquileres realizados en el mes de enero.
 

- **Herencia:** la empresa puede utilizar la herencia para crear nuevas clases que hereden de las clases existentes. Por ejemplo, la empresa puede crear una clase CocheDeportivo que herede de la clase Coche. La clase CocheDeportivo puede tener atributos adicionales que no están presentes en la clase Coche, como la potencia del motor y la velocidad máxima.
 

- **Polimorfismo:** la empresa puede utilizar el polimorfismo para permitir que diferentes tipos de objetos respondan a la misma llamada de función de diferentes maneras. Por ejemplo, la empresa puede tener una función calcularCoste() que se puede llamar para calcular el coste de un alquiler. La función calcularCoste() puede ser polimórfica, lo que significa que puede ser llamada para calcular el coste de cualquier tipo de coche, tanto si es un coche de pasajeros como si es un coche deportivo.
 

- **Interfaces:** la empresa puede utilizar interfaces para definir los comportamientos comunes de una clase. Por ejemplo, la empresa puede tener una interfaz Alquilable que define los métodos getMatricula(), getMarca() y getModelo(). Las clases Coche y CocheDeportivo pueden implementar la interfaz Alquilable, lo que significa que deben tener los métodos getMatricula(), getMarca() y getModelo().
  
**Pasos para completar la actividad:**

 

1- Los estudiantes deben crear las clases necesarias para representar los diferentes objetos que son relevantes para el caso de negocio.
2- Los estudiantes deben crear objetos de cada clase para representar instancias específicas de los objetos representados por las clases.
3- Los estudiantes deben utilizar la herencia para crear nuevas clases que hereden de las clases existentes.
4- Los estudiantes deben utilizar el polimorfismo para permitir que diferentes tipos de objetos respondan a la misma llamada de función de diferentes maneras.
5- Los estudiantes deben utilizar interfaces para definir los comportamientos comunes de una clase.

**Ejemplo de solucion propuesta con C#:**

``` C#

// Clase Coche
public class Coche
{
    public string Matricula { get; set; }
    public string Marca { get; set; }
    public string Modelo { get; set; }
    public int Ano { get; set; }
}

// Clase Alquiler
public class Alquiler
{
    public DateTime FechaInicio { get; set; }
    public DateTime FechaFin { get; set; }
    public string Cliente { get; set; }
    public Coche Coche { get; set; }
}

// Clase Informe
public class Informe
{
    public string Nombre { get; set; }
    public DateTime Periodo { get; set; }
    public List<Alquiler> Alquileres { get; set; }
}

// Función para registrar un nuevo coche
public void RegistrarCoche(Coche coche)
{
    // Guardar el coche en la base de datos
}

// Función para actualizar la información de un coche
public void ActualizarCoche(Coche coche)
{
    // Actualizar el coche en la base de datos
}

// Función para registrar un alquiler
public void RegistrarAlquiler(Alquiler alquiler)
{
    // Guardar el alquiler en la base de datos
}

// Función para generar un informe sobre los alquileres
public Informe GenerarInforme(DateTime fechaInicial, DateTime fechaFinal)
{
    // Obtener los alquileres de la base de datos
    // filtrar los alquileres por fecha
    // Crear un informe con los alquileres
    return informe;
}

``` 

**Clases:**

- Coche
- Alquiler
- Informe

**bjetos:**

- coche1
- coche2
- alquiler1
- alquiler2
- informe1

**Herencia:**

- La clase **CocheDeportivo** hereda de la clase **Coche**.

**Polimorfismo:**

- La función **calcularCoste()** es polimórfica, lo que significa que puede ser llamada para calcular el coste de cualquier tipo de coche, tanto si es un coche de pasajeros como si es un coche deportivo.

**Interfaces:**

- La interfaz Alquilable define los métodos **getMatricula()**, **getMarca()** y **getModelo()**. Las clases **Coche** y **CocheDeportivo** pueden implementar la interfaz Alquilable, lo que significa que deben tener los métodos **getMatricula()**, **getMarca()** y **getModelo()**.


**Probar el código**

Una forma es usar un entorno de desarrollo integrado (IDE) como Visual Studio. Un IDE te permite escribir, compilar y ejecutar código.

Para probar el código en un IDE, sigue estos pasos:

1- Abre el IDE y crea un nuevo proyecto.
2- Agrega el código al proyecto.
Compila el proyecto.
Ejecuta el proyecto.
Si el código se compila y ejecuta correctamente, verás la salida en la consola.

**Aquí hay algunos detalles adicionales sobre cada paso:**

- **Abrir el IDE de tu elección:** Puedes usar cualquier IDE que soporte C#, como Visual Studio, Visual Studio Code o JetBrains Rider.
- **Crear un nuevo proyecto:** Cuando creas un nuevo proyecto, el IDE te pedirá que elijas un lenguaje y un tipo de proyecto. En este caso, eliges C# y un proyecto de aplicación de consola.
- **Agregar el código al proyecto:** Una vez que hayas creado un nuevo proyecto, puedes agregar el código al proyecto arrastrando y soltando el archivo de código en el IDE o haciendo clic en el botón Agregar y seleccionando el archivo de código.
- **Compilar el proyecto:** Una vez que hayas agregado el código al proyecto, puedes compilarlo haciendo clic en el botón Compilar. Si el código se compila correctamente, el IDE mostrará una ventana de mensajes que dice "El proyecto se compiló correctamente".
- **Ejecutar el proyecto:** Una vez que el código se haya compilado correctamente, puedes ejecutarlo haciendo clic en el botón Ejecutar. Si el código se ejecuta correctamente, verás la salida en la consola.

Si ves algún error, puedes corregirlo y luego volver a compilar y ejecutar el proyecto.

**IMPORTANTE:** Necesitarás crear una base de datos y agregar las tablas que se usan en el código. Una vez que hayas creado la base de datos, deberás configurar el código para que se conecte a la base de datos. Una vez que el código se haya conectado a la base de datos, podrás usar las funciones para registrar nuevos coches, actualizar la información de los coches, registrar alquileres y generar informes sobre los alquileres.

**Aquí hay algunos detalles adicionales sobre cómo crear una base de datos:**

- **Elegir un tipo de base de datos:** Hay muchos tipos diferentes de bases de datos, como MySQL, PostgreSQL y SQLite. El tipo de base de datos que elijas dependerá de tus necesidades y requisitos.
- **Crear una base de datos:** Una vez que hayas elegido un tipo de base de datos, puedes crear una base de datos usando una herramienta de administración de base de datos como MySQL Workbench, pgAdmin o SQLite Manager.
- **Agregar tablas a la base de datos:** Una vez que hayas creado una base de datos, puedes agregar tablas a la base de datos usando una herramienta de administración de base de datos. Las tablas son la forma en que organizas los datos en una base de datos.
- **Configurar el código para que se conecte a la base de datos:** Una vez que hayas creado la base de datos y agregado las tablas, deberás configurar el código para que se conecte a la base de datos. Esto implica agregar las credenciales de la base de datos al código.

Una vez que hayas realizado todos estos pasos, podrás usar las funciones para registrar nuevos coches, actualizar la información de los coches, registrar alquileres y generar informes sobre los alquileres.

**Pasos para crear la base de datos:**

1. Abre SQL Server Management Studio y conecta a tu servidor.
2. Escribe el siguiente comando para crear la base de datos 
``` SQL
CREATE DATABASE alquiler_de_coches;
```
3. O tambien podras hacerlo haciendo clic derecho en el árbol de objetos y selecciona "Nueva base de datos".
4. En la ventana "Nueva base de datos", escribe "alquiler_de_coches" en el cuadro de texto "Nombre de la base de datos".
5. Haz clic en el botón "Aceptar".


**Script para generar las tablas a la base de datos:**

1. Abre un editor de texto y pega el siguiente código:

``` SQL
CREATE TABLE coches (
  matricula VARCHAR(10) NOT NULL,
  marca VARCHAR(20) NOT NULL,
  modelo VARCHAR(20) NOT NULL,
  ano INT NOT NULL
);

CREATE TABLE alquileres (
  fecha_inicio DATETIME NOT NULL,
  fecha_fin DATETIME NOT NULL,
  cliente VARCHAR(20) NOT NULL,
  coche INT NOT NULL
);

CREATE TABLE informes (
  nombre VARCHAR(20) NOT NULL,
  periodo DATETIME NOT NULL,
  alquileres VARCHAR(MAX) NULL,
);

```
2. Guarda el archivo como database.sql.
3. Vuelve a SQL Server Management Studio y conecta a tu servidor.
4. Haz clic derecho en la base de datos "alquiler_de_coches" y selecciona "Importar".
5. En la ventana "Importar", selecciona el archivo database.sql y haz clic en el botón "Aceptar".
6.  o también pueder dar clic derecho en la base de datos "alquiler_de_coches" y selecciona "Nueva consulta" o "query" y pegar el código anterior y luego dar clic en ejecutar.


**Configuración del código para que se conecte a la base de datos:**

1. Abre el archivo de código en un editor de texto o IDE Visual Studio.
2. Busca la sección **ConnectionStrings**.
3. Agrega la siguiente conexión a la sección **ConnectionStrings**:

``` SQL
<add name="AlquilerDeCochesConnectionString" connectionString="Data Source=localhost;Initial Catalog=AlquilerDeCoches;User ID=<username>;Password=<password>" />
```

4. Guarda el archivo de código.
5. Compila el archivo de código.
6. Ejecuta el archivo de código.

Una vez que hayas realizado todos estos pasos, podrás usar las funciones para registrar nuevos coches, actualizar la información de los coches, registrar alquileres y generar informes sobre los alquileres.


**Ejemplo de solucion propuesta con Python:**

``` Python

class Coche:
    """
    Esta clase representa un coche.

    Args:
        matricula (str): La matrícula del coche.
        marca (str): La marca del coche.
        modelo (str): El modelo del coche.
        ano (int): El año del coche.

    Methods:
        getMatricula(self): Devuelve la matrícula del coche.
        getMarca(self): Devuelve la marca del coche.
        getModelo(self): Devuelve el modelo del coche.
        getAno(self): Devuelve el año del coche.
    """

    def __init__(self, matricula, marca, modelo, ano):
        self.matricula = matricula
        self.marca = marca
        self.modelo = modelo
        self.ano = ano

    def getMatricula(self):
        return self.matricula

    def getMarca(self):
        return self.marca

    def getModelo(self):
        return self.modelo

    def getAno(self):
        return self.ano

class CocheDeportivo(Coche):
    """
    Esta clase representa un coche deportivo.

    Inherits from:
        Coche

    Args:
        matricula (str): La matrícula del coche deportivo.
        marca (str): La marca del coche deportivo.
        modelo (str): El modelo del coche deportivo.
        ano (int): El año del coche deportivo.
        potencia (int): La potencia del coche deportivo.
        velocidad_maxima (int): La velocidad máxima del coche deportivo.

    Methods:
        getPotencia(self): Devuelve la potencia del coche deportivo.
        getVelocidadMaxima(self): Devuelve la velocidad máxima del coche deportivo.
    """

    def __init__(self, matricula, marca, modelo, ano, potencia, velocidad_maxima):
        super().__init__(matricula, marca, modelo, ano)
        self.potencia = potencia
        self.velocidad_maxima = velocidad_maxima

    def getPotencia(self):
        return self.potencia

    def getVelocidadMaxima(self):
        return self.velocidad_maxima

class Alquiler:
    """
    Esta clase representa un alquiler de coche.

    Args:
        fecha_inicio (datetime): La fecha de inicio del alquiler.
        fecha_fin (datetime): La fecha de fin del alquiler.
        cliente (str): El nombre del cliente.
        coche (Coche): El coche alquilado.

    Methods:
        getFechaInicio(self): Devuelve la fecha de inicio del alquiler.
        getFechaFin(self): Devuelve la fecha de fin del alquiler.
        getCliente(self): Devuelve el nombre del cliente.
        getCoche(self): Devuelve el coche alquilado.
    """

    def __init__(self, fecha_inicio, fecha_fin, cliente, coche):
        self.fecha_inicio = fecha_inicio
        self.fecha_fin = fecha_fin
        self.cliente = cliente
        self.coche = coche

    def getFechaInicio(self):
        return self.fecha_inicio

    def getFechaFin(self):
        return self.fecha_fin

    def getCliente(self):
        return self.cliente

    def getCoche(self):
        return self.coche

class Informe:
    """
    Esta clase representa un informe de alquileres de coches.

    Args:
        nombre (str): El nombre del informe.
        periodo (datetime): El periodo del informe.
        datos (list): Una lista de alquileres.

    Methods:
        getNombre(self): Devuelve el nombre del informe.
        getPeriodo(self): Devuelve el periodo del informe.
        getDatos(self): Devuelve la lista de alquileres.
    """

    def __init__(self, nombre, periodo, datos):
        self.nombre = nombre
        self.periodo = periodo
        self.datos = datos

    def getNombre(self):
        return self.nombre

    def getPeriodo(self):
        return self.periodo

    def getDatos(self):
        return self.datos


```
Estas clases pueden ser utilizadas para crear objetos que representan los diferentes tipos de objetos que son relevantes para el caso de negocio. Por ejemplo, la empresa puede crear un objeto **Coche** para representar un coche específico, como un Ford Fiesta 2023. La empresa puede crear un objeto **Alquiler** para representar un alquiler específico, como un alquiler de un Ford Fiesta 2023 del 1 de enero al 15 de enero. La empresa puede crear un objeto **Informe** para representar un informe específico, como un informe de todos los alquileres realizados en el mes de enero.

La herencia puede ser utilizada para crear nuevas clases que heredan de las clases existentes. Por ejemplo, la empresa puede crear una clase **CocheDeportivo** que herede de la clase Coche. La clase **CocheDeportivo** puede tener atributos adicionales que no están presentes en la clase **Coche**, como la potencia del motor y la velocidad máxima.

El polimorfismo puede ser utilizado para permitir que diferentes tipos de objetos respondan a la misma llamada de función de diferentes maneras. Por ejemplo, la empresa puede tener una función **calcularCoste()** que se puede llamar para calcular el coste de un alquiler. La función **calcularCoste()** puede ser polimórfica, lo que significa que puede ser llamada para calcular el coste de cualquier tipo de coche, tanto si es un coche de pasajeros como si es un coche deportivo.

Las interfaces pueden ser utilizadas para definir los comportamientos comunes de una clase. Por ejemplo, la empresa puede tener una interfaz **Alquilable** que define los métodos **getMatricula()**, **getMarca()** y **getModelo()**. Las clases **Coche** y **CocheDeportivo** pueden implementar la interfaz Alquilable, lo que significa que deben tener los métodos **getMatricula()**, **getMarca()** y **getModelo()**.


**Preguntas de discusión:**

1- ¿Cuáles son las ventajas de utilizar programación orientada a objetos?
2- ¿Cuáles son los desafíos de utilizar programación orientada a objetos?
3- ¿Cómo puede la programación orientada a objetos ayudar a la empresa de alquiler de coches a gestionar su flota de coches?

**Ventajas de utilizar programación orientada a objetos**

- La programación orientada a objetos (OOP) es un paradigma de programación que facilita la creación de software modular y reutilizable.
- OOP permite a los desarrolladores pensar en términos de objetos del mundo real, lo que puede hacer que el código sea más fácil de entender y mantener.
- OOP puede ayudar a los desarrolladores a crear software más robusto y escalable.

**Desafíos de utilizar programación orientada a objetos**

- OOP puede ser más complejo que otros paradigmas de programación, como la programación imperativa.
- OOP puede ser más difícil de depurar.
- OOP puede ser más difícil de escalar.

**Cómo puede la programación orientada a objetos ayudar a la empresa de alquiler de coches a gestionar su flota de coches**

La programación orientada a objetos puede ayudar a la empresa de alquiler de coches a gestionar su flota de coches de varias maneras. Por ejemplo, OOP puede utilizarse para:

- Crear objetos que representen coches, alquileres e informes.
- Almacenar datos sobre coches, alquileres e informes.
- Realizar operaciones sobre coches, alquileres e informes.
- Generar informes sobre coches, alquileres e informes.

OOP puede ayudar a la empresa de alquiler de coches a gestionar su flota de coches de forma más eficiente y eficaz.

