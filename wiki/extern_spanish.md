<!--
Meta Description: # Uso de "extern" en C#: Definición y Ejemplos ## Sinopsis La palabra clave `extern` en C# se utiliza para declarar métodos o variables que están defi...
Meta Keywords: extern, que, gestionado, con, métodos
-->

# Uso de "extern" en C#: Definición y Ejemplos

## Sinopsis
La palabra clave `extern` en C# se utiliza para declarar métodos o variables que están definidos en otro lugar, usualmente en una biblioteca externa o en código no gestionado.

## Documentación
La palabra clave `extern` es fundamental para trabajar con interop en C#. Permite a los desarrolladores invocar funciones que no están escritas en C# pero que son accesibles a través de bibliotecas de enlace dinámico (DLL) o APIs de sistemas operativos.

### Propósito
- Facilitar la interoperabilidad con código no gestionado.
- Permitir la llamada a funciones de bibliotecas externas que no están escritas en C#.

### Uso
La sintaxis general para declarar un método `extern` es la siguiente:

```csharp
[DllImport("nombre_de_la_biblioteca.dll")]
public static extern tipo_de_retorno NombreDelMetodo(parametros);
```

Donde:
- `DllImport` se utiliza para especificar la biblioteca externa.
- `tipo_de_retorno` es el tipo que devuelve el método.
- `NombreDelMetodo` es el nombre de la función que se invocará.
- `parametros` son los parámetros que se pasarán a la función.

### Detalles
- `extern` se puede utilizar solo con métodos estáticos.
- Los métodos declarados como `extern` deben ser implementados en la biblioteca externa y no deben contener cuerpo en C#.

## Ejemplos

### Ejemplo 1: Llamada a una función de la API de Windows
```csharp
using System;
using System.Runtime.InteropServices;

class Program
{
    [DllImport("user32.dll")]
    public static extern int MessageBox(int hWnd, string text, string caption, int type);

    static void Main()
    {
        MessageBox(0, "Hola desde C#!", "Título", 0);
    }
}
```

### Ejemplo 2: Uso de un método externo con parámetros
```csharp
using System;
using System.Runtime.InteropServices;

class Program
{
    [DllImport("kernel32.dll")]
    public static extern IntPtr GetModuleHandle(string lpModuleName);

    static void Main()
    {
        IntPtr handle = GetModuleHandle("kernel32.dll");
        Console.WriteLine($"Módulo manejado: {handle}");
    }
}
```

## Explicación
Al usar `extern`, es importante tener en cuenta lo siguiente:
- **Compatibilidad de tipos**: Debes asegurarte de que los tipos de datos de C# coincidan con los tipos esperados en la biblioteca externa.
- **Manejo de excepciones**: Las excepciones en el código no gestionado pueden no ser capturadas directamente en C#, lo que puede llevar a comportamientos inesperados.
- **Rendimiento**: Las llamadas a métodos externos pueden ser más lentas que las llamadas internas debido a la sobrecarga de la transición entre el código gestionado y no gestionado.

## Resumen en una línea
La palabra clave `extern` en C# permite declarar métodos que se implementan en bibliotecas externas, facilitando la interoperabilidad con código no gestionado.