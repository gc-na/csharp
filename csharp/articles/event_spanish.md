<!--
Meta Description: # Eventos en C#: Todo lo que Necesitas Saber ## Sinopsis Los eventos en C# son una forma fundamental de implementar la programación basada en eventos,...
Meta Keywords: evento, que, eventos, public, mensaje
-->

# Eventos en C#: Todo lo que Necesitas Saber

## Sinopsis
Los eventos en C# son una forma fundamental de implementar la programación basada en eventos, permitiendo que las clases se comuniquen entre sí de manera eficiente y reactiva.

## Documentación
### Propósito
Los eventos en C# permiten a las clases notificar a otras clases o componentes cuando ocurre un cambio o una acción específica. Esto es especialmente útil en aplicaciones con interfaces gráficas de usuario (GUI) y en sistemas que requieren una respuesta a acciones del usuario o cambios en el estado.

### Uso
Para declarar un evento, se utiliza la palabra clave `event`, seguida del tipo de delegado que define la firma de los métodos que pueden suscribirse al evento. A continuación, se puede invocar el evento desde un método en la clase que lo declara.

### Detalles
1. **Definición de Delegado**: Antes de declarar un evento, se debe definir un delegado que especifique el tipo de método que puede manejar el evento.
   
   ```csharp
   public delegate void MiDelegado(string mensaje);
   ```

2. **Declaración del Evento**: Se declara el evento utilizando la palabra clave `event`.

   ```csharp
   public event MiDelegado MiEvento;
   ```

3. **Invocación del Evento**: Para invocar el evento, se debe comprobar si hay suscriptores y, en caso afirmativo, invocar el evento.

   ```csharp
   protected virtual void OnMiEvento(string mensaje)
   {
       MiEvento?.Invoke(mensaje);
   }
   ```

4. **Suscripción al Evento**: Otras clases pueden suscribirse al evento utilizando el operador `+=`.

   ```csharp
   MiEvento += MetodoQueEscucha;
   ```

## Ejemplos
### Ejemplo Básico de un Evento

```csharp
using System;

public delegate void MiDelegado(string mensaje);

public class Emisor
{
    public event MiDelegado MiEvento;

    public void EjecutarEvento()
    {
        OnMiEvento("¡Evento ejecutado!");
    }

    protected virtual void OnMiEvento(string mensaje)
    {
        MiEvento?.Invoke(mensaje);
    }
}

public class Receptor
{
    public void MetodoQueEscucha(string mensaje)
    {
        Console.WriteLine(mensaje);
    }
}

class Program
{
    static void Main(string[] args)
    {
        Emisor emisor = new Emisor();
        Receptor receptor = new Receptor();

        emisor.MiEvento += receptor.MetodoQueEscucha;
        emisor.EjecutarEvento();
    }
}
```

### Salida Esperada
```
¡Evento ejecutado!
```

## Explicación
### Errores Comunes
- **No Comprobar Suscriptores**: Es crucial verificar si hay suscriptores al evento antes de invocarlo para evitar excepciones de referencia nula.
- **Fugas de Memoria**: Las suscripciones a eventos pueden causar fugas de memoria si los objetos suscriptores no se eliminan correctamente. Utiliza `-=` para desuscribirte de eventos en el destructor o en la lógica de finalización.

### Notas Adicionales
- Los eventos son una parte integral del patrón de diseño Observer, facilitando una arquitectura más limpia y modular.
- Los eventos pueden ser multicast, lo que significa que múltiples métodos pueden suscribirse y ser notificados cuando se invoca el evento.

## Resumen en Una Línea
Los eventos en C# son mecanismos que permiten la comunicación entre objetos mediante la notificación de cambios o acciones, promoviendo un diseño basado en eventos.