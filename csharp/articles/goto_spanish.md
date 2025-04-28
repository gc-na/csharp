<!--
Meta Description: # Uso de "goto" en C#: Guía Completa y Ejemplos Prácticos ## Sinopsis El comando `goto` en C# permite transferir el flujo de ejecución del programa a ...
Meta Keywords: goto, del, puede, que, uso
-->

# Uso de "goto" en C#: Guía Completa y Ejemplos Prácticos

## Sinopsis
El comando `goto` en C# permite transferir el flujo de ejecución del programa a una etiqueta especificada. Aunque su uso ha sido objeto de controversia, puede ser útil en ciertas situaciones de control de flujo.

## Documentación
El `goto` es una declaración que permite saltar a una etiqueta dentro del mismo bloque de código. Su sintaxis es simple:

```csharp
goto etiqueta;
```

### Propósito
El propósito principal del `goto` es proporcionar una forma de salir de bucles o saltar a una sección del código de manera directa, lo que puede ser útil en ciertos escenarios de programación.

### Uso
Para utilizar `goto`, debes definir primero una etiqueta en el código, que se identifica con un nombre seguido de dos puntos (`:`). Luego, desde cualquier parte del mismo método, puedes usar `goto` para saltar a esa etiqueta.

### Detalles
- El `goto` solo se puede usar dentro del mismo método.
- No se puede utilizar para saltar entre métodos diferentes.
- Es importante tener cuidado al usar `goto`, ya que puede llevar a un código menos legible y más difícil de mantener.

## Ejemplos

### Ejemplo 1: Uso básico de `goto`

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Inicio");
        goto Salto;
        
        Console.WriteLine("Este mensaje no se mostrará.");

        Salto:
        Console.WriteLine("Salto a esta línea.");
    }
}
```

### Ejemplo 2: Uso en bucles

```csharp
using System;

class Program
{
    static void Main()
    {
        int i = 0;

        while (i < 5)
        {
            i++;
            if (i == 3)
            {
                goto Fin; // Salta a la etiqueta Fin cuando i es 3
            }
            Console.WriteLine($"Valor de i: {i}");
        }

        Fin:
        Console.WriteLine("Fin del bucle.");
    }
}
```

## Explicación
El uso del `goto` puede llevar a ciertos problemas:
- **Legibilidad del código**: El `goto` puede hacer que el flujo del programa sea difícil de seguir, lo que puede complicar la depuración y el mantenimiento.
- **Estructuras de control alternativas**: Se recomienda utilizar estructuras de control más claras como `if`, `for`, `while` o `switch`, que ofrecen un control de flujo más estructurado y legible.
- **Limitaciones**: No se puede salir de estructuras como `try-catch` o saltar a métodos diferentes, lo que limita su aplicabilidad.

## Resumen en una línea
El `goto` en C# permite saltar a etiquetas en el mismo método, pero su uso debe ser limitado por su potencial para disminuir la legibilidad del código.