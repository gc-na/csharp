<!--
Meta Description: # CSharp: Manejo de Cadenas (Strings) en C# ## Sinopsis En C#, una cadena (string) es una secuencia de caracteres utilizada para representar texto. Es...
Meta Keywords: cadenas, string, texto, para, una
-->

# CSharp: Manejo de Cadenas (Strings) en C#

## Sinopsis
En C#, una cadena (string) es una secuencia de caracteres utilizada para representar texto. Este tipo de dato es fundamental en la programación, permitiendo la manipulación de texto de manera eficiente y sencilla.

## Documentación

### Propósito
La clase `String` en C# se utiliza para trabajar con secuencias de caracteres. Permite la creación, modificación y análisis de texto, facilitando tareas como la concatenación, búsqueda y manipulación de cadenas.

### Uso
Para declarar una cadena en C#, se utiliza la palabra clave `string`, seguida del nombre de la variable. Las cadenas pueden ser inicializadas con texto entre comillas dobles. C# también proporciona una amplia variedad de métodos para operar con cadenas, como `Length`, `Substring`, `ToUpper`, y `ToLower`, entre otros.

### Detalles
- **Inmutabilidad**: Las cadenas en C# son inmutables, lo que significa que no se pueden cambiar una vez creadas. Cualquier operación que parezca modificar una cadena en realidad retorna una nueva cadena.
- **Interpolación de cadenas**: C# permite la interpolación de cadenas, lo que facilita la inserción de variables en cadenas de texto de manera legible, usando el símbolo `$` antes de la cadena.
- **Cadenas de texto multi-línea**: Para cadenas que abarcan varias líneas, se pueden usar literales de cadena verbatim, que comienzan con `@`.

## Ejemplos

### Declaración y inicialización
```csharp
string saludo = "Hola, mundo!";
```

### Concatenación de cadenas
```csharp
string nombre = "Juan";
string mensaje = saludo + " Mi nombre es " + nombre + ".";
```

### Uso de métodos de la clase String
```csharp
string texto = "programación en C#";
int longitud = texto.Length; // Retorna la longitud de la cadena
string textoMayusculas = texto.ToUpper(); // Convierte a mayúsculas
string subcadena = texto.Substring(0, 11); // Extrae "programación"
```

### Interpolación de cadenas
```csharp
string edad = "30";
string presentación = $"Hola, me llamo {nombre} y tengo {edad} años.";
```

### Cadenas de texto multi-línea
```csharp
string textoMultiLinea = @"Hola, 
esto es un texto 
en múltiples líneas.";
```

## Explicación
Al trabajar con cadenas en C#, es importante tener en cuenta su inmutabilidad, ya que puede llevar a confusiones en el uso de memoria si se realizan múltiples concatenaciones. En lugar de utilizar el operador `+` para concatenar múltiples cadenas, es recomendable usar `StringBuilder` para mejorar el rendimiento en operaciones que requieren múltiples modificaciones.

Además, la comparación de cadenas es sensible a mayúsculas y minúsculas por defecto. Para realizar comparaciones insensibles, se puede utilizar el método `String.Equals` con el parámetro `StringComparison.OrdinalIgnoreCase`.

## Resumen en una frase
En C#, las cadenas son secuencias inmutables de caracteres utilizadas para representar y manipular texto de manera efectiva.