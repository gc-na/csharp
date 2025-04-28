<!--
Meta Description: # C# Override: Methodenüberschreibung in der objektorientierten Programmierung ## Synopsis Das Schlüsselwort `override` in C# ermöglicht es, eine Meth...
Meta Keywords: der, die, methode, override, das
-->

# C# Override: Methodenüberschreibung in der objektorientierten Programmierung

## Synopsis
Das Schlüsselwort `override` in C# ermöglicht es, eine Methode in einer abgeleiteten Klasse neu zu implementieren, die in einer Basisklasse als virtuell deklariert wurde. Es erlaubt Entwicklern, das Verhalten von geerbten Methoden anzupassen und zu erweitern.

## Documentation
Das `override`-Schlüsselwort wird in der objektorientierten Programmierung verwendet, um eine Methode, die in einer Basisklasse definiert ist, in einer abgeleiteten Klasse zu überschreiben. Um eine Methode zu überschreiben, muss die Methode in der Basisklasse als `virtual` oder `abstract` deklariert sein. 

### Zweck
Der Hauptzweck der Methodenüberschreibung ist es, polymorphes Verhalten zu ermöglichen, sodass die richtige Methode zur Laufzeit basierend auf dem tatsächlichen Objekttyp aufgerufen wird, anstatt auf dem Typ der Referenzvariable.

### Verwendung
Um `override` zu verwenden, folgen Sie diesen Schritten:
1. Definieren Sie eine virtuelle Methode in der Basisklasse mit dem Schlüsselwort `virtual`.
2. Implementieren Sie die Methode in der abgeleiteten Klasse mit dem Schlüsselwort `override`.

### Details
- Eine Methode, die mit `override` überschrieben wird, muss die gleiche Signatur wie die Methode in der Basisklasse haben.
- Es können nur virtuelle oder abstrakte Methoden überschrieben werden.
- Das `override`-Schlüsselwort verbessert die Lesbarkeit und Wartbarkeit des Codes, indem es klar angibt, dass eine Methode absichtlich überschrieben wird.

## Examples
Hier sind einige grundlegende Beispiele für die Verwendung von `override` in C#:

### Beispiel 1: Grundlagen der Methodenüberschreibung
```csharp
public class Tier
{
    public virtual void LautGeben()
    {
        Console.WriteLine("Das Tier macht ein Geräusch.");
    }
}

public class Hund : Tier
{
    public override void LautGeben()
    {
        Console.WriteLine("Der Hund bellt.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Tier meinTier = new Hund();
        meinTier.LautGeben(); // Ausgabe: Der Hund bellt.
    }
}
```

### Beispiel 2: Verwendung von `virtual` und `override`
```csharp
public class Fahrzeug
{
    public virtual void Fahren()
    {
        Console.WriteLine("Das Fahrzeug fährt.");
    }
}

public class Auto : Fahrzeug
{
    public override void Fahren()
    {
        Console.WriteLine("Das Auto fährt schnell.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Fahrzeug meinFahrzeug = new Auto();
        meinFahrzeug.Fahren(); // Ausgabe: Das Auto fährt schnell.
    }
}
```

## Explanation
Ein häufiger Fehler beim Überschreiben von Methoden besteht darin, die Signatur der Methode in der abgeleiteten Klasse nicht genau zu reproduzieren. Dies kann zu Kompilierungsfehlern führen oder dazu, dass die Basismethode anstelle der überschriebenen Methode aufgerufen wird. 

Ein weiteres Problem ist die Verwendung von `new` anstelle von `override`, was in C# eine neue Methode definiert, die die Methode der Basisklasse verbirgt, anstatt sie zu überschreiben. Dies kann zu Verwirrung führen, da der polymorphe Aufruf nicht wie erwartet funktioniert.

## One Line Summary
Das Schlüsselwort `override` in C# ermöglicht die Anpassung von geerbten Methoden in abgeleiteten Klassen, um polymorphes Verhalten zu unterstützen.