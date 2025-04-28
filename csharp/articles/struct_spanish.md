<!--
Meta Description: # Estructuras en C#: Todo lo que Necesitas Saber ## Sinopsis En C#, una `struct` (estructura) es un tipo de dato que permite agrupar datos relacionado...
Meta Keywords: que, estructuras, las, public, int
-->

# Estructuras en C#: Todo lo que Necesitas Saber

## Sinopsis
En C#, una `struct` (estructura) es un tipo de dato que permite agrupar datos relacionados y definir tipos de datos compuestos. Las estructuras son tipos de valor, lo que significa que se almacenan en la pila y tienen un comportamiento diferente en comparación con las clases.

## Documentación
Las estructuras en C# se utilizan para encapsular un conjunto de variables relacionadas, permitiendo la creación de nuevos tipos que pueden ser utilizados en el código. A diferencia de las clases, que son tipos de referencia, las estructuras son tipos de valor, lo que implica que se copian al asignarlas a otra variable o pasarlas a un método.

### Propósito
El propósito principal de las estructuras es proporcionar una forma eficiente de agrupar datos sin la sobrecarga de la creación de un objeto de clase. Son especialmente útiles para representar datos simples y son ideales para operaciones de rendimiento crítico.

### Uso
Para definir una estructura en C#, se utiliza la palabra clave `struct` seguida del nombre de la estructura. A continuación se puede definir un conjunto de campos y métodos.

```csharp
struct Punto
{
    public int X;
    public int Y;

    public Punto(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void Mostrar()
    {
        Console.WriteLine($"Punto: ({X}, {Y})");
    }
}
```

## Ejemplos
### Ejemplo 1: Definición y Uso Básico de una Estructura
```csharp
struct Persona
{
    public string Nombre;
    public int Edad;

    public Persona(string nombre, int edad)
    {
        Nombre = nombre;
        Edad = edad;
    }
}

class Programa
{
    static void Main(string[] args)
    {
        Persona p1 = new Persona("Juan", 30);
        Console.WriteLine($"Nombre: {p1.Nombre}, Edad: {p1.Edad}");
    }
}
```

### Ejemplo 2: Estructura con Métodos
```csharp
struct Rectangulo
{
    public int Ancho;
    public int Alto;

    public Rectangulo(int ancho, int alto)
    {
        Ancho = ancho;
        Alto = alto;
    }

    public int Area()
    {
        return Ancho * Alto;
    }
}

class Programa
{
    static void Main(string[] args)
    {
        Rectangulo rect = new Rectangulo(5, 10);
        Console.WriteLine($"Área del rectángulo: {rect.Area()}");
    }
}
```

## Explicación
Aunque las estructuras son útiles, hay algunas consideraciones importantes a tener en cuenta:

- **Inmutabilidad:** A menudo, se recomienda que las estructuras sean inmutables, es decir, que sus campos no se puedan modificar una vez que se han construido. Esto ayuda a evitar confusiones sobre el estado de los datos.
  
- **Tamaño y Complejidad:** Las estructuras son más eficientes para almacenar datos pequeños y simples. Si una estructura se vuelve demasiado grande o compleja, es mejor considerar el uso de una clase.

- **No Herencia:** Las estructuras no pueden heredar de otras estructuras o clases, ni ser la base de otras estructuras. Sin embargo, pueden implementar interfaces.

- **Constructor por Defecto:** C# no permite definir un constructor por defecto explícito en las estructuras, ya que cada estructura tiene un constructor por defecto implícito que inicializa todos los campos a sus valores predeterminados.

## Resumen en Una Línea
Las estructuras en C# son tipos de valor que permiten agrupar datos relacionados, proporcionando una forma eficiente de crear nuevos tipos de datos compuestos.