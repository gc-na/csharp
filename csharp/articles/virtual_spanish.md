<!--
Meta Description: # Uso de "virtual" en C#: Conceptos y Ejemplos ## Sinopsis La palabra clave "virtual" en C# permite la creación de métodos que pueden ser sobreescrito...
Meta Keywords: virtual, public, que, class, clave
-->

# Uso de "virtual" en C#: Conceptos y Ejemplos

## Sinopsis
La palabra clave "virtual" en C# permite la creación de métodos que pueden ser sobreescritos en clases derivadas, facilitando así la implementación de polimorfismo. 

## Documentación
En C#, la palabra clave `virtual` se utiliza para declarar un método, propiedad, indexador o evento en una clase base que puede ser sobreescrito por una clase derivada. Esto es fundamental para la programación orientada a objetos, ya que permite definir comportamientos que pueden ser modificados o extendidos en subclases.

### Propósito
El propósito de `virtual` es proporcionar una forma flexible de definir métodos que se comportan de manera diferente en las clases derivadas, lo que promueve la reutilización de código y la adaptación de funcionalidades.

### Uso
Para utilizar `virtual`, simplemente se antepone la palabra clave al método en la clase base. En la clase derivada, se utiliza la palabra clave `override` para implementar el nuevo comportamiento.

```csharp
public class Animal
{
    public virtual void HacerSonido()
    {
        Console.WriteLine("El animal hace un sonido.");
    }
}

public class Perro : Animal
{
    public override void HacerSonido()
    {
        Console.WriteLine("El perro ladra.");
    }
}
```

## Ejemplos
### Ejemplo básico de uso
```csharp
class Vehiculo
{
    public virtual void Describir()
    {
        Console.WriteLine("Este es un vehículo.");
    }
}

class Coche : Vehiculo
{
    public override void Describir()
    {
        Console.WriteLine("Este es un coche.");
    }
}

class Programa
{
    static void Main()
    {
        Vehiculo miVehiculo = new Coche();
        miVehiculo.Describir(); // Salida: Este es un coche.
    }
}
```

### Ejemplo con propiedades
```csharp
public class Forma
{
    public virtual double Area { get; }
}

public class Cuadrado : Forma
{
    private double lado;
    
    public Cuadrado(double lado)
    {
        this.lado = lado;
    }

    public override double Area
    {
        get { return lado * lado; }
    }
}
```

## Explicación
Algunos puntos importantes a considerar al utilizar `virtual` incluyen:

- **Polimorfismo**: Permite que un objeto de tipo base se comporte como un objeto de tipo derivado, lo que es clave para el polimorfismo.
- **Llamadas a métodos base**: Desde un método sobreescrito, puedes llamar al método base utilizando `base.NombreDelMetodo()`.
- **Acceso a miembros no virtuales**: Los métodos no declarados como `virtual` no pueden ser sobreescritos, lo que limita la flexibilidad.
- **Rendimiento**: Aunque el uso de métodos virtuales es poderoso, puede tener un impacto ligero en el rendimiento debido a la necesidad de resolver la llamada al método en tiempo de ejecución.

## Resumen en una línea
La palabra clave `virtual` en C# permite la creación de métodos que pueden ser sobreescritos en clases derivadas, facilitando el polimorfismo.