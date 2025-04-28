<!--
Meta Description: # int en C#: Tipos de Datos Enteros en CSharp ## Sinopsis El tipo de dato `int` en C# es un tipo de datos primitivo que se utiliza para representar nú...
Meta Keywords: int, tipo, para, que, csharp
-->

# int en C#: Tipos de Datos Enteros en CSharp

## Sinopsis
El tipo de dato `int` en C# es un tipo de datos primitivo que se utiliza para representar números enteros. Tiene un rango limitado y es ampliamente utilizado en programación para realizar operaciones matemáticas y lógicas.

## Documentación
El tipo `int` en C# es un alias para el tipo `Int32` y se utiliza para almacenar valores enteros de 32 bits. Su rango va desde -2,147,483,648 hasta 2,147,483,647. `int` es un tipo de dato con signo, lo que significa que puede contener tanto números positivos como negativos.

### Propósito
El tipo `int` se utiliza en una variedad de escenarios, incluidos cálculos matemáticos, contadores en bucles, y almacenamiento de valores que no requieren decimales.

### Uso
Para declarar una variable de tipo `int`, simplemente se utiliza la palabra clave `int` seguida del nombre de la variable. Por ejemplo:

```csharp
int contador;
```

También se puede inicializar en el momento de la declaración:

```csharp
int contador = 10;
```

## Ejemplos
### Ejemplo 1: Declaración y Asignación
```csharp
int edad = 25;
Console.WriteLine(edad);
```

### Ejemplo 2: Operaciones Aritméticas
```csharp
int a = 5;
int b = 10;
int suma = a + b;
Console.WriteLine(suma); // Salida: 15
```

### Ejemplo 3: Uso en un Bucle
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

## Explicación
### Errores Comunes
- **Desbordamiento**: Al intentar asignar un valor que excede el rango permitido para `int`, se produce un desbordamiento. Por ejemplo, asignar 2,147,483,648 a una variable `int` generará un error.
- **No Inicializado**: Si una variable `int` no se inicializa antes de su uso, el compilador generará un error de referencia a una variable no asignada.

### Notas Adicionales
- Para trabajar con números enteros más grandes, se puede utilizar el tipo `long`, que permite un rango mayor.
- C# permite la conversión entre tipos de datos, pero se debe tener cuidado al convertir entre tipos para evitar pérdidas de datos.

## Resumen en Una Línea
El tipo `int` en C# es un tipo de dato primitivo que representa números enteros de 32 bits, ideal para cálculos y contadores.