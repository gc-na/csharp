<!--
Meta Description: # Uso de "static" en C#: Guía Completa ## Sinopsis La palabra clave "static" en C# se utiliza para declarar miembros de clase que pertenecen a la clas...
Meta Keywords: clase, static, miembros, public, que
-->

# Uso de "static" en C#: Guía Completa

## Sinopsis
La palabra clave "static" en C# se utiliza para declarar miembros de clase que pertenecen a la clase en sí, en lugar de a cualquier instancia específica de la clase. Esto permite que se acceda a estos miembros sin necesidad de crear un objeto de la clase.

## Documentación
### Propósito
La palabra clave "static" se utiliza para definir miembros (variables, métodos, propiedades) que son compartidos entre todas las instancias de una clase. Esto significa que hay una sola copia de un miembro estático, independientemente de cuántas instancias de la clase se creen.

### Uso
Los miembros estáticos se declaran utilizando la palabra clave "static" antes del tipo de dato. Los métodos y propiedades estáticas se pueden acceder directamente a través del nombre de la clase, sin crear una instancia de la misma.

#### Ejemplo de declaración de un miembro estático
```csharp
public class Contador
{
    public static int TotalContadores = 0;

    public Contador()
    {
        TotalContadores++;
    }
}
```

En el ejemplo anterior, `TotalContadores` es un miembro estático que cuenta cuántas instancias de `Contador` han sido creadas.

## Ejemplos
### Ejemplo 1: Método estático
```csharp
public class Utilidades
{
    public static int Sumar(int a, int b)
    {
        return a + b;
    }
}

// Uso
int resultado = Utilidades.Sumar(5, 3);
Console.WriteLine(resultado); // Salida: 8
```

### Ejemplo 2: Propiedades estáticas
```csharp
public class Configuracion
{
    public static string NombreAplicacion { get; set; } = "MiApp";
}

// Uso
Console.WriteLine(Configuracion.NombreAplicacion); // Salida: MiApp
```

## Explicación
### Problemas Comunes y Notas
1. **Persistencia de Datos**: Como los miembros estáticos son compartidos, cualquier cambio en un miembro estático se reflejará en todas las instancias de la clase. Esto puede llevar a errores si no se gestiona correctamente.

2. **No se puede acceder a miembros de instancia**: Dentro de un contexto estático, no se puede acceder a miembros no estáticos directamente, ya que los miembros no estáticos requieren una instancia de la clase.

3. **Uso de Constructores**: Los miembros estáticos pueden inicializarse en un constructor estático, que se ejecuta una vez cuando la clase se carga por primera vez. Esto es útil para la configuración de datos estáticos.

### Ejemplo de constructor estático
```csharp
public class BaseDeDatos
{
    public static string CadenaConexion;

    static BaseDeDatos()
    {
        CadenaConexion = "Servidor=localhost;BaseDeDatos=MiDB;";
    }
}

// Uso
Console.WriteLine(BaseDeDatos.CadenaConexion); // Salida: Servidor=localhost;BaseDeDatos=MiDB;
```

## Resumen en una línea
La palabra clave "static" en C# permite declarar miembros de clase que son compartidos entre todas las instancias, proporcionando acceso sin necesidad de crear un objeto.