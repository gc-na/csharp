<!--
Meta Description: # Const en C#: Definición, Uso y Ejemplos ## Sinopsis La palabra clave `const` en C# se utiliza para declarar constantes, que son valores inmutables q...
Meta Keywords: que, una, const, ser, constantes
-->

# Const en C#: Definición, Uso y Ejemplos

## Sinopsis
La palabra clave `const` en C# se utiliza para declarar constantes, que son valores inmutables que se conocen en tiempo de compilación y no pueden ser modificados durante la ejecución del programa.

## Documentación
En C#, `const` es un modificador que se aplica a las variables para indicar que su valor es constante. Una variable declarada como `const` debe ser inicializada al momento de su declaración y no puede ser cambiada posteriormente. Es importante destacar que las constantes son de tipo estático, lo que significa que su valor se determina en tiempo de compilación y no puede ser alterado en tiempo de ejecución.

### Propósito
El propósito principal de `const` es proporcionar una forma de definir valores que no cambiarán a lo largo del ciclo de vida de la aplicación. Esto ayuda a mejorar la legibilidad del código y a evitar errores que pueden surgir al modificar valores que deberían permanecer constantes.

### Uso
Para declarar una constante en C#, se utiliza la palabra clave `const`, seguida del tipo de la constante, el nombre de la constante y su valor inicial. A continuación se muestra la sintaxis básica:

```csharp
const tipo nombre_constante = valor;
```

### Detalles
- Las constantes pueden ser de cualquier tipo de datos, incluidos tipos primitivos (como `int`, `float`, `string`, etc.) y tipos definidos por el usuario.
- Las constantes deben ser inicializadas en el momento de su declaración.
- Las constantes son implícitamente `static`, lo que significa que pertenecen a la clase en lugar de a instancias individuales de la clase.

## Ejemplos
### Ejemplo 1: Declaración de una constante entera
```csharp
const int MaxIntentos = 5;
```

### Ejemplo 2: Declaración de una constante de cadena
```csharp
const string NombreEmpresa = "Mi Empresa S.A.";
```

### Ejemplo 3: Uso de una constante en una función
```csharp
void Proceso() {
    for (int i = 0; i < MaxIntentos; i++) {
        // Lógica del proceso
    }
}
```

## Explicación
Al trabajar con `const`, es importante tener en cuenta algunas consideraciones:

- **Inmutabilidad**: Una vez que se asigna un valor a una constante, no se puede cambiar. Intentar hacerlo resultará en un error de compilación.
- **Alcance**: Las constantes pueden tener diferentes niveles de alcance (por ejemplo, pueden ser locales a un método o globales dentro de una clase).
- **Uso de `readonly`**: Si se necesita una variable que pueda ser asignada una vez pero cuya asignación no se conoce hasta el tiempo de ejecución, se debe utilizar `readonly` en lugar de `const`.
- **Tipo de datos**: Las constantes no pueden ser de tipo referencia que no sean cadenas (`string`), ya que su valor debe ser conocido en tiempo de compilación.

## Resumen en una línea
La palabra clave `const` en C# se utiliza para declarar constantes inmutables que se conocen en tiempo de compilación y no pueden ser modificadas en tiempo de ejecución.