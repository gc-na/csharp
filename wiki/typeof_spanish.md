<!--
Meta Description: # typeof en C#: Uso y Aplicaciones ## Sinopsis `typeof` es un operador en C# que se utiliza para obtener el objeto `Type` que representa el tipo de un...
Meta Keywords: tipo, typeof, tipos, que, miclase
-->

# typeof en C#: Uso y Aplicaciones

## Sinopsis
`typeof` es un operador en C# que se utiliza para obtener el objeto `Type` que representa el tipo de una clase, estructura, interfaz o enumeración. Es una herramienta esencial para la reflexión y la manipulación dinámica de tipos en tiempo de ejecución.

## Documentación
El operador `typeof` permite a los desarrolladores obtener información detallada sobre los tipos en C#. Se utiliza comúnmente en escenarios donde se necesita identificar o trabajar con tipos de datos en tiempo de ejecución, como en la reflexión, la creación de instancias, y la verificación de tipos.

### Propósito
El propósito principal de `typeof` es proporcionar acceso al metadato del tipo en cuestión, permitiendo así realizar operaciones como la comparación de tipos, la creación de instancias mediante el uso de reflexión y la obtención de información sobre los miembros del tipo.

### Uso
El operador `typeof` se utiliza de la siguiente manera:

```csharp
Type tipo = typeof(NombreDelTipo);
```

Donde `NombreDelTipo` puede ser una clase, estructura, interfaz o enumeración definida en el código.

### Detalles
- `typeof` devuelve un objeto `Type` que representa el tipo especificado.
- Se puede utilizar en cualquier contexto donde se necesite el tipo, como en la declaración de variables, comprobaciones de tipo, y más.
- No se puede utilizar con tipos genéricos sin especificar un argumento de tipo.

## Ejemplos

### Ejemplo básico
```csharp
using System;

class Program
{
    static void Main()
    {
        Type tipoEntero = typeof(int);
        Console.WriteLine("El tipo es: " + tipoEntero);
    }
}
```
**Salida:**
```
El tipo es: System.Int32
```

### Uso con clases personalizadas
```csharp
public class MiClase {}

class Program
{
    static void Main()
    {
        Type tipoMiClase = typeof(MiClase);
        Console.WriteLine("El tipo es: " + tipoMiClase);
    }
}
```
**Salida:**
```
El tipo es: MiClase
```

### Uso en reflexión
```csharp
using System;
using System.Reflection;

public class MiClase {}

class Program
{
    static void Main()
    {
        Type tipo = typeof(MiClase);
        MethodInfo[] metodos = tipo.GetMethods();
        Console.WriteLine("Métodos de MiClase:");
        foreach (var metodo in metodos)
        {
            Console.WriteLine(metodo.Name);
        }
    }
}
```
**Salida:**
```
Métodos de MiClase:
ToString
Equals
GetHashCode
...
```

## Explicación
Uno de los errores comunes al usar `typeof` es intentar aplicarlo a tipos genéricos sin proporcionar un argumento de tipo específico. Por ejemplo, `typeof(List<>)` no es válido; se debe usar `typeof(List<string>)` o cualquier otro tipo concreto.

Otro aspecto a tener en cuenta es que `typeof` no evalúa la instancia del tipo, sino que solo proporciona información sobre el tipo en sí. Esto significa que no se puede utilizar para obtener información sobre instancias de tipos en tiempo de ejecución, ya que se debe usar el operador `is` o el método `GetType()` para eso.

## Resumen en una línea
El operador `typeof` en C# se utiliza para obtener el tipo de una clase, estructura, interfaz o enumeración, facilitando la reflexión y la manipulación dinámica de tipos en programación.