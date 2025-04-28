<!--
Meta Description: # Switch en C#: Todo lo que Necesitas Saber ## Sinopsis El comando `switch` en C# es una estructura de control que permite la selección entre múltiple...
Meta Keywords: break, switch, una, case, que
-->

# Switch en C#: Todo lo que Necesitas Saber

## Sinopsis
El comando `switch` en C# es una estructura de control que permite la selección entre múltiples alternativas basadas en el valor de una expresión. Es útil para mejorar la legibilidad y organización del código cuando se manejan múltiples condiciones.

## Documentación
El `switch` en C# se utiliza para ejecutar diferentes bloques de código en función del valor de una expresión. Esta estructura es especialmente útil cuando se necesita comprobar una variable contra varias opciones posibles. A continuación se presenta la sintaxis básica:

```csharp
switch (expresión)
{
    case valor1:
        // Código a ejecutar si la expresión es igual a valor1
        break;
    case valor2:
        // Código a ejecutar si la expresión es igual a valor2
        break;
    default:
        // Código a ejecutar si no coincide con ninguno de los casos anteriores
        break;
}
```

### Propósito
El propósito del `switch` es simplificar la lógica de selección y hacer que el código sea más fácil de leer y mantener, en comparación con múltiples sentencias `if-else`.

### Uso
- **Expresión**: Debe ser de un tipo compatible con `case`, como `int`, `char`, `string`, o enumeraciones.
- **Case**: Se define cada posible valor que puede tomar la expresión. El bloque asociado se ejecutará si hay una coincidencia.
- **Default**: Es opcional y se ejecuta si no se encuentra ninguna coincidencia.

## Ejemplos

### Ejemplo Básico
```csharp
int dia = 3;

switch (dia)
{
    case 1:
        Console.WriteLine("Lunes");
        break;
    case 2:
        Console.WriteLine("Martes");
        break;
    case 3:
        Console.WriteLine("Miércoles");
        break;
    default:
        Console.WriteLine("Día desconocido");
        break;
}
```

### Ejemplo con String
```csharp
string fruta = "manzana";

switch (fruta)
{
    case "banana":
        Console.WriteLine("Es una banana");
        break;
    case "manzana":
        Console.WriteLine("Es una manzana");
        break;
    default:
        Console.WriteLine("Fruta desconocida");
        break;
}
```

## Explicación
Al usar `switch`, es importante tener en cuenta algunos aspectos:

- **Falta de `break`**: Si olvidas el `break` al final de un caso, el programa continuará ejecutando el siguiente bloque de código, lo que puede provocar resultados inesperados.
  
- **Tipos de datos**: Asegúrate de que los tipos de datos coincidan entre la expresión y los valores de los casos. Usar tipos no compatibles resultará en un error de compilación.

- **Valores duplicados**: No puedes tener dos casos con el mismo valor, ya que causará un error en tiempo de compilación.

## Resumen en una línea
El `switch` en C# es una estructura de control que permite seleccionar entre múltiples alternativas de manera clara y eficiente.