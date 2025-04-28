<!--
Meta Description: # Uso de la sentencia "case" en C# ## Sinopsis La sentencia `case` en C# se utiliza dentro de la estructura de control `switch` para manejar múltiples...
Meta Keywords: case, break, switch, console, writeline
-->

# Uso de la sentencia "case" en C#

## Sinopsis
La sentencia `case` en C# se utiliza dentro de la estructura de control `switch` para manejar múltiples condiciones de manera eficiente y legible.

## Documentación
La sentencia `case` permite evaluar una expresión y ejecutar diferentes bloques de código dependiendo del valor de esa expresión. Se utiliza comúnmente en conjunción con la sentencia `switch`, la cual evalúa una variable o expresión y dirige el flujo del programa a la cláusula `case` correspondiente.

### Propósito
El propósito de `case` es simplificar la toma de decisiones en el código, especialmente cuando se tienen múltiples condiciones que se deben evaluar contra un mismo valor.

### Uso
La sintaxis básica para usar `case` dentro de un `switch` es la siguiente:

```csharp
switch (expresión)
{
    case valor1:
        // Código para valor1
        break;
    case valor2:
        // Código para valor2
        break;
    default:
        // Código por defecto si no coincide con ningún caso
        break;
}
```

- **expresión**: La variable o expresión que se evalúa.
- **valor1, valor2, ...**: Los valores específicos que se comparan con la expresión.
- **break**: Termina la ejecución del bloque `switch` y sale de él. Si se omite, la ejecución caerá en el siguiente caso (esto se conoce como "fall-through").

## Ejemplos
### Ejemplo 1: Uso básico de `case`

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
        Console.WriteLine("Día no válido");
        break;
}
```

### Ejemplo 2: Múltiples casos

```csharp
char letra = 'A';
switch (letra)
{
    case 'A':
    case 'E':
    case 'I':
    case 'O':
    case 'U':
        Console.WriteLine("Es una vocal.");
        break;
    default:
        Console.WriteLine("Es una consonante.");
        break;
}
```

## Explicación
Al usar `case`, es importante recordar que cada bloque de código debe terminar con una instrucción `break`, de lo contrario, el flujo continuará ejecutando el siguiente bloque, lo que puede causar resultados inesperados. Además, el `switch` y sus `case` pueden ser utilizados con tipos de datos enteros, caracteres y cadenas, pero no con tipos de datos flotantes.

También es posible utilizar la instrucción `when` para añadir condiciones adicionales a un `case`, lo que permite una mayor flexibilidad en la evaluación.

```csharp
int numero = 10;
switch (numero)
{
    case int n when n < 0:
        Console.WriteLine("Número negativo");
        break;
    case int n when n == 0:
        Console.WriteLine("Cero");
        break;
    case int n when n > 0:
        Console.WriteLine("Número positivo");
        break;
}
```

## Resumen en una línea
La sentencia `case` en C# permite gestionar múltiples condiciones en un bloque `switch` de forma clara y estructurada.