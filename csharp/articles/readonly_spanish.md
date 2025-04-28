<!--
Meta Description: # readonly en C#: Definición y Uso Efectivo ## Sinopsis El modificador `readonly` en C# se utiliza para declarar campos que solo pueden ser asignados ...
Meta Keywords: readonly, que, los, pueden, campos
-->

# readonly en C#: Definición y Uso Efectivo

## Sinopsis
El modificador `readonly` en C# se utiliza para declarar campos que solo pueden ser asignados una vez, ya sea en su declaración o dentro del constructor de la clase. Esto proporciona una forma de garantizar que los valores críticos no se modifiquen después de la inicialización, promoviendo la inmutabilidad.

## Documentación
### Propósito
El propósito del modificador `readonly` es proteger el estado de los objetos y asegurar que ciertos valores permanezcan constantes durante la vida útil de una instancia de la clase. Esto es especialmente útil en situaciones donde la integridad de los datos es crucial.

### Uso
Para declarar un campo como `readonly`, simplemente se antepone la palabra clave `readonly` a la declaración de la variable dentro de una clase. Los campos `readonly` pueden ser inicializados en su declaración o en el constructor de la clase. Sin embargo, no pueden ser asignados fuera de estos contextos.

### Detalles
- Los campos `readonly` pueden ser de cualquier tipo, incluyendo tipos de referencia y tipos de valor.
- En el caso de tipos de referencia, el objeto al que apuntan los campos `readonly` no es inmutable, a menos que el propio objeto sea declarado como `readonly`.
- Se pueden utilizar en estructuras (structs) así como en clases.

## Ejemplos
### Ejemplo Básico de `readonly`
```csharp
public class Persona
{
    public readonly string Nombre;
    
    public Persona(string nombre)
    {
        Nombre = nombre; // Asignación permitida en el constructor
    }
}

// Uso
var persona = new Persona("Juan");
// persona.Nombre = "Pedro"; // Esto causaría un error de compilación
```

### Ejemplo con un Campo `readonly` en un Constructor
```csharp
public class Vehiculo
{
    public readonly int NumeroDeRuedas;

    public Vehiculo(int numeroDeRuedas)
    {
        NumeroDeRuedas = numeroDeRuedas; // Asignación permitida aquí
    }
}

// Uso
var coche = new Vehiculo(4);
// coche.NumeroDeRuedas = 6; // Esto causaría un error de compilación
```

## Explicación
### Errores Comunes
1. **Intentar reasignar un campo `readonly`:** Tratar de modificar el valor de un campo `readonly` después de su inicialización generará un error de compilación.
2. **Inicialización fuera de contexto:** No se permite la inicialización de un campo `readonly` en métodos distintos del constructor o en su declaración.

### Notas Adicionales
- Los campos `readonly` son diferentes de las propiedades `get` en que las propiedades pueden tener lógica adicional para su acceso y pueden ser calculadas, mientras que los campos `readonly` son simplemente valores almacenados.
- Es importante tener en cuenta que `readonly` no significa que el objeto mismo sea inmutable. Solo asegura que la referencia al objeto no se puede cambiar.

## Resumen en una Línea
El modificador `readonly` en C# asegura que un campo solo pueda ser asignado una vez, promoviendo la inmutabilidad y la integridad de los datos en la clase.