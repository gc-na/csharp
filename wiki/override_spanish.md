<!--
Meta Description: # Override en C#: Entendiendo la Sobrescritura de Métodos ## Sinopsis El término "override" en C# se refiere a la capacidad de una clase derivada para...
Meta Keywords: clase, override, método, base, public
-->

# Override en C#: Entendiendo la Sobrescritura de Métodos

## Sinopsis
El término "override" en C# se refiere a la capacidad de una clase derivada para proporcionar una implementación específica de un método que ya está definido en su clase base. Este mecanismo es fundamental para la programación orientada a objetos, permitiendo la personalización y la extensión del comportamiento de las clases.

## Documentación
La palabra clave `override` se utiliza en C# para sobrescribir un método virtual o abstracto en una clase base. Al utilizar `override`, se permite que una clase derivada defina su propia versión del método, lo que permite modificar o extender su funcionalidad.

### Propósito
El propósito de `override` es permitir que las clases derivadas modifiquen el comportamiento de métodos heredados. Esto es especialmente útil en el contexto de la herencia, donde una clase puede necesitar un comportamiento específico que difiere del que ofrece su clase base.

### Uso
Para utilizar `override`, el método en la clase base debe estar marcado como `virtual` o `abstract`. La clase derivada puede entonces implementar su propia versión del método utilizando la palabra clave `override`.

### Detalles
- **Métodos Virtuales**: Se definen en la clase base con la palabra clave `virtual`, lo que indica que pueden ser sobrescritos.
- **Métodos Abstractos**: Se definen en una clase abstracta con la palabra clave `abstract` y no tienen una implementación en la clase base.

```csharp
public class ClaseBase
{
    public virtual void MostrarMensaje()
    {
        Console.WriteLine("Mensaje desde ClaseBase");
    }
}

public class ClaseDerivada : ClaseBase
{
    public override void MostrarMensaje()
    {
        Console.WriteLine("Mensaje sobrescrito desde ClaseDerivada");
    }
}
```

## Ejemplos
### Ejemplo Básico de Sobrescritura
```csharp
public class Animal
{
    public virtual void HacerSonido()
    {
        Console.WriteLine("Sonido de Animal");
    }
}

public class Perro : Animal
{
    public override void HacerSonido()
    {
        Console.WriteLine("Guau");
    }
}

// Uso
Animal miPerro = new Perro();
miPerro.HacerSonido(); // Salida: Guau
```

### Ejemplo con Método Abstracto
```csharp
public abstract class Figura
{
    public abstract double CalcularArea();
}

public class Circulo : Figura
{
    private double radio;

    public Circulo(double radio)
    {
        this.radio = radio;
    }

    public override double CalcularArea()
    {
        return Math.PI * radio * radio;
    }
}

// Uso
Figura miCirculo = new Circulo(5);
Console.WriteLine(miCirculo.CalcularArea()); // Salida: 78.53981633974483
```

## Explicación
### Errores Comunes
- **Olvidar la palabra clave `virtual` o `abstract`**: Si el método en la clase base no está marcado correctamente, el compilador generará un error al intentar usar `override`.
- **No coincidir la firma del método**: La firma del método en la clase derivada debe coincidir exactamente con la del método en la clase base.
- **Intentar sobrescribir un método no virtual**: Solo los métodos definidos como `virtual` o `abstract` pueden ser sobrescritos.

### Notas Adicionales
- `override` permite que las clases derivadas se comporten de manera diferente a sus clases base sin necesidad de reescribir toda la lógica de la clase base.
- El uso de `base` en el método sobrescrito permite invocar el método de la clase base si es necesario.

## Resumen en Una Línea
La palabra clave `override` en C# permite a las clases derivadas personalizar el comportamiento de métodos heredados de su clase base.