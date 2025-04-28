<!--
Meta Description: # Verwendung des Schlüsselworts "virtual" in C# ## Synopsis Das Schlüsselwort "virtual" in C# ermöglicht die Definition von Methoden und Eigenschaften...
Meta Keywords: virtual, methode, public, das, die
-->

# Verwendung des Schlüsselworts "virtual" in C#

## Synopsis
Das Schlüsselwort "virtual" in C# ermöglicht die Definition von Methoden und Eigenschaften in einer Basisklasse, die in abgeleiteten Klassen überschrieben werden können. Dies fördert die Flexibilität und Wiederverwendbarkeit des Codes.

## Dokumentation
In C# dient das Schlüsselwort "virtual" dazu, eine Methode oder Eigenschaft in einer Klasse zu deklarieren, die von abgeleiteten Klassen überschrieben werden kann. Wenn eine Methode als "virtual" markiert wird, signalisiert dies, dass die Methode polymorph ist und an die spezifischen Implementierungen der abgeleiteten Klassen angepasst werden kann.

### Verwendung
Das Schlüsselwort "virtual" wird in der Basisklasse verwendet, um eine Methode oder Eigenschaft zu definieren. Um diese Methode oder Eigenschaft in einer abgeleiteten Klasse zu überschreiben, wird das Schlüsselwort "override" verwendet. Dies ist besonders nützlich in der objektorientierten Programmierung, wo eine Basisklasse allgemeine Funktionalität bereitstellt und abgeleitete Klassen spezifischere Implementierungen liefern.

### Details
- **Deklaration**: Um eine Methode oder Eigenschaft als "virtual" zu kennzeichnen, fügen Sie das Schlüsselwort vor der Rückgabetyp-Deklaration hinzu.
- **Überschreibung**: Abgeleitete Klassen verwenden das Schlüsselwort "override", um die virtuelle Methode zu überschreiben.
- **Virtual vs. Override**: Eine virtuelle Methode kann in einer abgeleiteten Klasse mehrfach überschrieben werden, und der Aufruf einer solchen Methode erfolgt zur Laufzeit basierend auf dem tatsächlichen Typ des Objekts.

## Beispiele
### Beispiel 1: Virtuelle Methode
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

public class Programm
{
    public static void Main()
    {
        Tier meinTier = new Hund();
        meinTier.LautGeben(); // Ausgabe: Der Hund bellt.
    }
}
```

### Beispiel 2: Virtuelle Eigenschaft
```csharp
public class Fahrzeug
{
    public virtual int Geschwindigkeit { get; set; } = 0;
}

public class Auto : Fahrzeug
{
    public override int Geschwindigkeit { get; set; } = 100;
}

public class Programm
{
    public static void Main()
    {
        Fahrzeug meinFahrzeug = new Auto();
        Console.WriteLine(meinFahrzeug.Geschwindigkeit); // Ausgabe: 100
    }
}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von "virtual" ist das Verständnis der Polymorphie. Wenn Sie eine virtuelle Methode in einer Basisklasse definieren, sollten Sie sicherstellen, dass die Methode sinnvoll in den abgeleiteten Klassen überschrieben wird. Andernfalls kann das Verhalten des Programms unvorhersehbar sein. Ein weiterer Punkt ist, dass nicht alle Methoden in einer Basisklasse als "virtual" deklariert werden sollten, da dies den Code unnötig komplex machen kann, wenn es keine Notwendigkeit für eine Überschreibung gibt.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "virtual" in C# ermöglicht die flexible Überschreibung von Methoden und Eigenschaften in abgeleiteten Klassen und unterstützt so die objektorientierte Programmierung.