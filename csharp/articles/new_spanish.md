<!--
Meta Description: # El Uso de "new" en C#: Creación de Objetos y Ocultación de Miembros ## Sinopsis La palabra clave "new" en C# se utiliza principalmente para crear in...
Meta Keywords: clase, new, base, una, creación
-->

# El Uso de "new" en C#: Creación de Objetos y Ocultación de Miembros

## Sinopsis
La palabra clave "new" en C# se utiliza principalmente para crear instancias de objetos y para ocultar miembros de una clase base en una clase derivada. Es esencial para la programación orientada a objetos, permitiendo la inicialización de objetos y el manejo de la herencia.

## Documentación
### Propósito
La palabra clave "new" cumple dos funciones principales en C#:
1. **Creación de instancias**: Permite la creación de nuevos objetos de una clase.
2. **Ocultación de miembros**: Permite a los desarrolladores ocultar miembros (propiedades, métodos, etc.) de una clase base en una clase derivada.

### Uso
1. **Creación de Objetos**:
   La forma más común de utilizar "new" es en la creación de instancias de una clase:
   ```csharp
   ClaseNombre objeto = new ClaseNombre();
   ```
   Aquí, `ClaseNombre` es el nombre de la clase y `objeto` es la referencia al nuevo objeto creado.

2. **Ocultación de Miembros**:
   Cuando una clase derivada tiene un miembro que tiene el mismo nombre que uno en la clase base, se puede usar "new" para ocultar el miembro de la clase base:
   ```csharp
   class Base {
       public void Metodo() {
           Console.WriteLine("Método de la clase base");
       }
   }

   class Derivada : Base {
       public new void Metodo() {
           Console.WriteLine("Método de la clase derivada");
       }
   }
   ```

## Ejemplos
### Ejemplo 1: Creación de un Objeto
```csharp
public class Persona {
    public string Nombre { get; set; }

    public Persona(string nombre) {
        Nombre = nombre;
    }
}

// Creación de una instancia de Persona
Persona p = new Persona("Juan");
Console.WriteLine(p.Nombre); // Salida: Juan
```

### Ejemplo 2: Ocultación de Miembros
```csharp
class Animal {
    public void HacerSonido() {
        Console.WriteLine("Sonido de Animal");
    }
}

class Perro : Animal {
    public new void HacerSonido() {
        Console.WriteLine("Guau");
    }
}

// Uso de la clase Perro
Perro miPerro = new Perro();
miPerro.HacerSonido(); // Salida: Guau
```

## Explicación
Al utilizar "new" para ocultar miembros, es importante tener en cuenta que el miembro oculto no se puede acceder mediante una referencia de la clase base. Esto puede llevar a confusiones si no se entiende bien el contexto de la herencia. También es crucial recordar que la ocultación no es lo mismo que la sobrecarga, ya que en el caso de la ocultación, el método del tipo base no se invoca.

### Puntos Clave:
- **Instanciación**: La creación de un objeto requiere el uso de "new".
- **Ocultación**: Se debe usar "new" explícitamente para ocultar un miembro de la clase base.
- **Referencias**: Al usar referencias de clase base, se invocará el método de la clase base, no el de la derivada.

## Resumen en Una Línea
La palabra clave "new" en C# se utiliza para crear instancias de objetos y para ocultar miembros de una clase base en una clase derivada.