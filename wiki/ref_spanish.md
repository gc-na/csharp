<!--
Meta Description: # Uso de 'ref' en C#: Guía Completa para Programadores ## Sinopsis La palabra clave `ref` en C# permite pasar argumentos por referencia a métodos, fac...
Meta Keywords: ref, método, que, int, valor
-->

# Uso de 'ref' en C#: Guía Completa para Programadores

## Sinopsis
La palabra clave `ref` en C# permite pasar argumentos por referencia a métodos, facilitando la modificación de variables originales dentro de esos métodos.

## Documentación
La palabra clave `ref` se utiliza en C# para pasar parámetros a métodos por referencia, en lugar de por valor. Esto significa que cualquier cambio realizado en el parámetro dentro del método se reflejará en la variable original que fue pasada como argumento.

### Propósito
El propósito principal de `ref` es permitir que un método modifique el valor de un argumento que es pasado. Esto es útil en situaciones donde se necesita que el método devuelva múltiples valores o cuando se desea evitar la copia de grandes estructuras de datos.

### Uso
Para utilizar `ref`, debes declarar tanto el parámetro del método como el argumento al llamar al método con la palabra clave `ref`. 

#### Declaración del Método
```csharp
void MiMetodo(ref int numero)
{
    numero += 10; // Modifica el valor del número pasado por referencia
}
```

#### Llamada al Método
```csharp
int valor = 5;
MiMetodo(ref valor); // valor ahora es 15
```

## Ejemplos

### Ejemplo 1: Uso Básico de `ref`
```csharp
using System;

class Programa
{
    static void Main()
    {
        int x = 10;
        Console.WriteLine($"Antes: {x}");
        Aumentar(ref x);
        Console.WriteLine($"Después: {x}");
    }

    static void Aumentar(ref int numero)
    {
        numero++;
    }
}
```
**Salida:**
```
Antes: 10
Después: 11
```

### Ejemplo 2: Múltiples Valores
```csharp
using System;

class Programa
{
    static void Main()
    {
        int a = 5, b = 10;
        Console.WriteLine($"Antes: a = {a}, b = {b}");
        SumarYMultiplicar(ref a, ref b);
        Console.WriteLine($"Después: a = {a}, b = {b}");
    }

    static void SumarYMultiplicar(ref int x, ref int y)
    {
        x += 5;  // x se convierte en 10
        y *= 2;  // y se convierte en 20
    }
}
```
**Salida:**
```
Antes: a = 5, b = 10
Después: a = 10, b = 20
```

## Explicación
Al utilizar `ref`, es importante tener en cuenta lo siguiente:

- **Inicialización Obligatoria**: Las variables que se pasan como `ref` deben estar inicializadas antes de ser pasadas al método. No puedes pasar una variable no inicializada.
- **Consistencia de Llamada**: La palabra clave `ref` debe usarse tanto en la declaración del método como en la llamada al método.
- **No se puede mezclar con `out`**: `ref` y `out` no pueden ser usados juntos en la misma llamada; `out` se utiliza para pasar argumentos que no necesitan ser inicializados antes de la llamada.

## Resumen en una línea
La palabra clave `ref` en C# permite pasar parámetros por referencia a métodos, permitiendo la modificación directa de las variables originales.