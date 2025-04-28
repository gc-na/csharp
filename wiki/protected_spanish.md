<!--
Meta Description: # Modificador de Acceso "protected" en C#: Todo lo que Necesitas Saber ## Sinopsis El modificador de acceso `protected` en C# es utilizado para restri...
Meta Keywords: protected, acceso, clase, que, una
-->

# Modificador de Acceso "protected" en C#: Todo lo que Necesitas Saber

## Sinopsis
El modificador de acceso `protected` en C# es utilizado para restringir la visibilidad de miembros de una clase, permitiendo su acceso solo dentro de la misma clase y en clases derivadas. Este concepto es fundamental en la programación orientada a objetos y facilita la encapsulación y la herencia.

## Documentación
El modificador `protected` es uno de los modificadores de acceso disponibles en C#. Su propósito principal es proporcionar un nivel de acceso que permite que los miembros de una clase sean accesibles solo dentro de la propia clase y por las clases que heredan de ella. Esto es útil para proteger los datos de la clase base mientras se permite que las clases derivadas accedan a esos datos.

### Uso
Para declarar un miembro (método, propiedad, campo, etc.) como `protected`, simplemente se coloca la palabra clave `protected` antes de la declaración del miembro. Por ejemplo:

```csharp
public class ClaseBase
{
    protected int numero;
    
    protected void MetodoProtegido()
    {
        // Lógica del método
    }
}
```

En este ejemplo, `numero` y `MetodoProtegido` son accesibles desde la clase `ClaseBase` y cualquier clase que herede de ella.

### Detalles
- `protected` puede ser combinado con otros modificadores de acceso como `internal` para crear un acceso más restringido (por ejemplo, `protected internal`).
- Los miembros `protected` no son accesibles desde instancias de la clase base, solo desde clases derivadas. Esto significa que no puedes acceder a ellos directamente desde fuera de la jerarquía de herencia.
- La herencia es un concepto clave en la programación orientada a objetos en C#, y el uso de `protected` es esencial para manejar la visibilidad y el acceso a los miembros de la clase de manera segura.

## Ejemplos
A continuación, se presentan ejemplos básicos del uso del modificador `protected`.

### Ejemplo 1: Uso en una Clase Derivada
```csharp
public class ClaseBase
{
    protected int numero = 10;
}

public class ClaseDerivada : ClaseBase
{
    public void MostrarNumero()
    {
        Console.WriteLine(numero); // Acceso permitido
    }
}
```

### Ejemplo 2: Intento de Acceso fuera de la Jerarquía
```csharp
public class ClaseBase
{
    protected int numero = 10;
}

public class OtraClase
{
    public void Metodo()
    {
        ClaseBase obj = new ClaseBase();
        // Console.WriteLine(obj.numero); // Error: 'ClaseBase.numero' es inaccesible debido a su modificador de acceso 'protected'
    }
}
```

## Explicación
Un error común al utilizar `protected` es intentar acceder a un miembro `protected` desde una instancia de la clase base en lugar de dentro de una clase derivada. Este tipo de acceso resultará en un error de compilación, ya que la visibilidad está restringida intencionadamente.

Otro punto a considerar es la combinación de `protected` con otros modificadores de acceso. Por ejemplo, `protected internal` permite el acceso tanto a clases derivadas como a clases dentro del mismo ensamblado, lo que puede ser útil en ciertos escenarios.

## Resumen en Una Línea
El modificador de acceso `protected` en C# permite que los miembros de una clase sean accesibles solo desde la misma clase y sus clases derivadas, promoviendo la encapsulación y una mejor gestión de la herencia.