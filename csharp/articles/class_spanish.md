<!--
Meta Description: # Clases en C#: Definición, Uso y Ejemplos ## Sinopsis Las clases en C# son plantillas que permiten crear objetos, encapsulando datos y comportamiento...
Meta Keywords: clase, public, una, coche, clases
-->

# Clases en C#: Definición, Uso y Ejemplos

## Sinopsis
Las clases en C# son plantillas que permiten crear objetos, encapsulando datos y comportamientos relacionados. Son un componente fundamental de la programación orientada a objetos en este lenguaje.

## Documentación
En C#, una clase es una estructura que define un tipo de objeto. Una clase puede contener campos (variables), métodos (funciones), propiedades, eventos, y otros tipos de miembros. Las clases permiten organizar y modularizar el código, promoviendo la reutilización y la mantenibilidad.

### Propósito
El propósito principal de las clases es crear una representación de un concepto o entidad del mundo real dentro de un programa, agrupando datos y comportamientos asociados. Esto facilita la creación de aplicaciones más complejas y escalables.

### Uso
Para definir una clase en C#, se utiliza la palabra clave `class`, seguida del nombre de la clase y un bloque de código que contiene sus miembros. A continuación se presenta la sintaxis básica:

```csharp
class NombreDeLaClase
{
    // Campos
    public int campo1;
    
    // Propiedades
    public string Propiedad1 { get; set; }
    
    // Métodos
    public void Metodo1()
    {
        // Lógica del método
    }
}
```

Las clases se pueden instanciar utilizando el operador `new`:

```csharp
NombreDeLaClase objeto = new NombreDeLaClase();
```

## Ejemplos
### Ejemplo 1: Clase simple
```csharp
class Persona
{
    public string Nombre { get; set; }
    public int Edad { get; set; }

    public void Saludar()
    {
        Console.WriteLine($"Hola, soy {Nombre} y tengo {Edad} años.");
    }
}

// Uso de la clase
Persona persona = new Persona();
persona.Nombre = "Juan";
persona.Edad = 30;
persona.Saludar(); // Salida: Hola, soy Juan y tengo 30 años.
```

### Ejemplo 2: Clase con constructor
```csharp
class Coche
{
    public string Marca { get; set; }
    public string Modelo { get; set; }

    // Constructor
    public Coche(string marca, string modelo)
    {
        Marca = marca;
        Modelo = modelo;
    }

    public void MostrarDetalles()
    {
        Console.WriteLine($"Coche: {Marca} {Modelo}");
    }
}

// Uso de la clase
Coche coche = new Coche("Toyota", "Corolla");
coche.MostrarDetalles(); // Salida: Coche: Toyota Corolla
```

## Explicación
Al trabajar con clases en C#, es importante tener en cuenta algunos errores comunes:

- **Acceso a miembros**: Asegúrate de que los modificadores de acceso (como `public`, `private`, etc.) se establezcan correctamente para evitar errores de acceso.
- **Instanciación**: Recuerda que para utilizar una clase, debes crear una instancia de ella utilizando el operador `new`.
- **Constructor no llamado**: Si olvidas llamar al constructor al instanciar la clase, los campos no se inicializarán correctamente.
- **Uso de `static`**: Si un miembro de la clase es estático, se accede a él sin crear una instancia de la clase. Esto puede causar confusión si no se entiende bien su uso.

## Resumen en una línea
Las clases en C# son estructuras que encapsulan datos y comportamientos, permitiendo la creación de objetos en la programación orientada a objetos.