<!--
Meta Description: # Lanzar Excepciones en C#: Uso del Comando "throw" ## Sinopsis El comando `throw` en C# se utiliza para lanzar excepciones, permitiendo a los desarro...
Meta Keywords: throw, excepciones, que, lanzar, del
-->

# Lanzar Excepciones en C#: Uso del Comando "throw"

## Sinopsis
El comando `throw` en C# se utiliza para lanzar excepciones, permitiendo a los desarrolladores gestionar errores y crear un flujo de control adecuado en sus aplicaciones. Es una herramienta fundamental para el manejo de errores en programación.

## Documentación
El comando `throw` en C# se emplea para lanzar una excepción. Esto es esencial en situaciones donde se detecta un error o una condición anormal que impide que un método continúe su ejecución normal. Al usar `throw`, se puede crear un objeto de excepción y lanzarlo, lo que interrumpe el flujo de ejecución y permite que se maneje el error en un bloque `try-catch`.

### Propósito
- **Manejo de Errores**: `throw` ayuda a identificar y manejar situaciones excepcionales que no son parte del flujo normal del programa.
- **Control del Flujo**: Permite a los desarrolladores interrumpir la ejecución cuando se detecta un error, redirigiendo el flujo a un bloque de manejo de errores.

### Uso
El uso básico del comando `throw` se realiza de la siguiente manera:

```csharp
throw new Exception("Mensaje de error");
```

Aquí, creamos una nueva instancia de `Exception` con un mensaje que describe el error. Esta línea interrumpe la ejecución del programa y lanza la excepción.

Se puede utilizar dentro de métodos o funciones y generalmente se combina con bloques `try-catch` para manejar las excepciones adecuadamente.

## Ejemplos

### Ejemplo 1: Lanzar una Excepción Simple
```csharp
public void ValidarEdad(int edad)
{
    if (edad < 18)
    {
        throw new ArgumentOutOfRangeException("La edad debe ser mayor o igual a 18.");
    }
}
```

### Ejemplo 2: Manejo de Excepciones con `try-catch`
```csharp
try
{
    ValidarEdad(15);
}
catch (ArgumentOutOfRangeException ex)
{
    Console.WriteLine(ex.Message);
}
```

### Ejemplo 3: Crear y Lanzar una Excepción Personalizada
```csharp
public class MiExcepcion : Exception
{
    public MiExcepcion(string mensaje) : base(mensaje) { }
}

public void HacerAlgo()
{
    throw new MiExcepcion("Ocurrió un error en HacerAlgo.");
}
```

## Explicación
Al utilizar `throw`, es importante tener en cuenta algunos puntos clave:

- **Lanzar Excepciones**: No se deben lanzar excepciones sin un mensaje descriptivo, ya que esto dificultará la identificación del problema.
- **Excepciones Personalizadas**: Crear excepciones personalizadas puede ser útil para proporcionar más contexto sobre el error.
- **Bloques `try-catch`**: Siempre que se use `throw`, es recomendable encapsular el código en bloques `try-catch` para manejar adecuadamente las excepciones lanzadas.
- **No Ignorar Excepciones**: Evitar el uso de `throw` sin un manejo adecuado puede llevar a que se ignoren problemas importantes en el código.

## Resumen en Una Línea
El comando `throw` en C# permite lanzar excepciones, facilitando el manejo de errores y el control del flujo en las aplicaciones.