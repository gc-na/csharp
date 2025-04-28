<!--
Meta Description: # Uso de "base" en C#: Comprendiendo el Acceso a Miembros de la Clase Base ## Sinopsis El keyword `base` en C# se utiliza para acceder a los miembros ...
Meta Keywords: base, clase, public, class, acceder
-->

# Uso de "base" en C#: Comprendiendo el Acceso a Miembros de la Clase Base

## Sinopsis
El keyword `base` en C# se utiliza para acceder a los miembros (métodos, propiedades, índices, etc.) de la clase base desde una clase derivada. Es fundamental para la herencia, permitiendo a los desarrolladores invocar implementaciones específicas de la clase base y facilitar la extensión de funcionalidades.

## Documentación
El keyword `base` en C# permite a las clases derivadas acceder a los miembros de su clase base. Esto se utiliza principalmente en dos contextos: al llamar a constructores de la clase base y al acceder a métodos o propiedades que han sido sobreescritos en la clase derivada.

### Propósito
Su propósito principal es permitir que los desarrolladores manipulen y accedan a las funcionalidades de la clase base, incluso cuando estas han sido sobreescritas o cuando se necesita inicializar la clase base antes de ejecutar el código de la clase derivada.

### Uso
El uso de `base` se puede ver en las siguientes situaciones:

1. **Llamar a un Constructor de la Clase Base**
   ```csharp
   public class ClaseBase
   {
       public ClaseBase(int valor) { /* Inicialización */ }
   }

   public class ClaseDerivada : ClaseBase
   {
       public ClaseDerivada(int valor) : base(valor) 
       {
           // Código adicional
       }
   }
   ```

2. **Acceder a Métodos Sobreescritos**
   ```csharp
   public class ClaseBase
   {
       public virtual void Metodo()
       {
           Console.WriteLine("Método de ClaseBase");
       }
   }

   public class ClaseDerivada : ClaseBase
   {
       public override void Metodo()
       {
           base.Metodo(); // Llama al método de ClaseBase
           Console.WriteLine("Método de ClaseDerivada");
       }
   }
   ```

## Ejemplos
### Ejemplo 1: Llamada a un Constructor de la Clase Base
```csharp
public class Animal
{
    public Animal(string nombre)
    {
        Console.WriteLine($"Animal creado: {nombre}");
    }
}

public class Perro : Animal
{
    public Perro(string nombre) : base(nombre)
    {
        Console.WriteLine("Perro creado");
    }
}

// Uso
var miPerro = new Perro("Fido");
```

### Ejemplo 2: Accediendo a un Método Sobreescrito
```csharp
public class Vehiculo
{
    public virtual void MostrarTipo()
    {
        Console.WriteLine("Soy un vehículo");
    }
}

public class Coche : Vehiculo
{
    public override void MostrarTipo()
    {
        base.MostrarTipo(); // Llama al método de Vehiculo
        Console.WriteLine("Soy un coche");
    }
}

// Uso
var miCoche = new Coche();
miCoche.MostrarTipo();
```

## Explicación
Al utilizar `base`, es importante recordar que solo se puede acceder a miembros de la clase base que no sean privados. Además, si el miembro ha sido sobreescrito en la clase derivada, `base` permite llamar al miembro original de la clase base, lo que puede ser útil para extender la funcionalidad sin perder la lógica de la clase base.

Es común que los desarrolladores novatos olviden la palabra clave `base` al intentar acceder a los métodos de la clase base, lo que puede llevar a confusiones o errores de compilación. También, si no se llama adecuadamente al constructor de la clase base, se pueden producir excepciones en tiempo de ejecución.

## Resumen en una Línea
El keyword `base` en C# permite acceder a miembros de la clase base desde una clase derivada, facilitando la herencia y la extensión de funcionalidades.