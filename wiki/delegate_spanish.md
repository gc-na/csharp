<!--
Meta Description: # Delegados en C#: Una Guía Completa ## Sinopsis Los delegados en C# son tipos de datos que representan referencias a métodos. Permiten encapsular mét...
Meta Keywords: delegado, que, métodos, delegados, una
-->

# Delegados en C#: Una Guía Completa

## Sinopsis
Los delegados en C# son tipos de datos que representan referencias a métodos. Permiten encapsular métodos como objetos y facilitan la programación de eventos y la implementación de patrones de diseño.

## Documentación
Los delegados son una característica fundamental en C#, que permite la creación de tipos que pueden referirse a uno o más métodos. Un delegado puede ser considerado como un puntero a un método, proporcionando una forma flexible de invocar métodos, especialmente en programación orientada a eventos.

### Propósito
El propósito principal de los delegados es permitir la ejecución de métodos de forma indirecta, facilitando la programación de eventos y las callbacks. También se utilizan para implementar patrones como el patrón de observador.

### Uso
Para declarar un delegado, se utiliza la palabra clave `delegate` seguida de la firma del método que el delegado puede invocar. Una vez que se declara, se puede instanciar y asociar a uno o varios métodos. 

```csharp
public delegate void MiDelegado(string mensaje);
```

Una vez que se ha declarado el delegado, se puede crear una instancia y asignarle un método que coincida con su firma:

```csharp
MiDelegado delegado = new MiDelegado(MetodoEjemplo);
delegado("Hola, mundo!");
```

### Detalles
- Los delegados son tipos seguros y permiten la verificación en tiempo de compilación.
- Pueden ser multicasting, es decir, pueden referirse a múltiples métodos.
- Los delegados pueden ser anónimos, utilizando expresiones lambda.

## Ejemplos
### Ejemplo 1: Delegado Simple
```csharp
using System;

public delegate void MensajeDelegado(string mensaje);

class Programa
{
    static void MostrarMensaje(string mensaje)
    {
        Console.WriteLine(mensaje);
    }

    static void Main()
    {
        MensajeDelegado delegado = MostrarMensaje;
        delegado("¡Hola desde un delegado!");
    }
}
```

### Ejemplo 2: Delegado Multicast
```csharp
using System;

public delegate void Operacion(int numero);

class Programa
{
    static void Imprimir(int numero) 
    {
        Console.WriteLine("Número: " + numero);
    }

    static void Duplicar(int numero) 
    {
        Console.WriteLine("Duplicado: " + (numero * 2));
    }

    static void Main()
    {
        Operacion operacion = Imprimir;
        operacion += Duplicar; // Agregando otro método al delegado
        operacion(5);
    }
}
```

## Explicación
Al trabajar con delegados, es importante tener en cuenta que:
- **Tipos de firma**: La firma del método debe coincidir exactamente con la firma del delegado para que la asignación sea válida.
- **Multicasting**: Cuando se utilizan delegados multicasting, el orden de ejecución es el orden en que se agregaron los métodos.
- **NullReferenceException**: Si un delegado no tiene métodos asignados, intentar invocarlo resultará en una excepción.

## Resumen en una Línea
Los delegados en C# son tipos de datos que permiten encapsular métodos como objetos, facilitando la programación de eventos y la flexibilidad en la invocación de métodos.