<!--
Meta Description: # CSharp: Das Schlüsselwort "protected" – Eine umfassende Anleitung ## Synopsis Das Schlüsselwort "protected" in C# ist ein Zugriffsmodifizierer, der ...
Meta Keywords: protected, der, auf, zugriff, public
-->

# CSharp: Das Schlüsselwort "protected" – Eine umfassende Anleitung

## Synopsis
Das Schlüsselwort "protected" in C# ist ein Zugriffsmodifizierer, der den Zugriff auf Mitglieder einer Klasse steuert. Es ermöglicht den Zugriff auf diese Mitglieder innerhalb der Klasse selbst sowie in abgeleiteten Klassen, jedoch nicht von außerhalb dieser Klassenhierarchie.

## Documentation
In C# wird das Schlüsselwort "protected" verwendet, um den Zugriff auf Klassenmitglieder (wie Felder, Methoden und Eigenschaften) zu beschränken. Es ist nützlich in der objektorientierten Programmierung, insbesondere bei der Vererbung. Wenn ein Mitglied einer Klasse als "protected" deklariert wird, können nur die abgeleiteten Klassen und die Klasse selbst darauf zugreifen, was die Kapselung fördert und die Integrität der Daten schützt.

### Verwendung
Um ein Mitglied als "protected" zu deklarieren, fügen Sie das Schlüsselwort "protected" vor dem Typ des Mitglieds hinzu. Beispiel:

```csharp
public class BasisKlasse
{
    protected int geschuetzteVariable;

    protected void GeschuetzteMethode()
    {
        // Methodenkörper
    }
}

public class AbgeleiteteKlasse : BasisKlasse
{
    public void BeispielMethode()
    {
        geschuetzteVariable = 10; // Zugriff auf geschützte Variable
        GeschuetzteMethode(); // Zugriff auf geschützte Methode
    }
}
```

In diesem Beispiel hat die `AbgeleiteteKlasse` Zugriff auf die geschützten Mitglieder von `BasisKlasse`.

## Examples
Hier sind einige einfache Beispiele zur Veranschaulichung der Verwendung des "protected"-Schlüsselworts:

### Beispiel 1: Geschützte Variable
```csharp
public class Fahrzeug
{
    protected string marke;

    public Fahrzeug(string marke)
    {
        this.marke = marke;
    }
}

public class Auto : Fahrzeug
{
    public Auto(string marke) : base(marke) { }

    public void ZeigeMarke()
    {
        Console.WriteLine(marke); // Zugriff auf die geschützte Variable
    }
}
```

### Beispiel 2: Geschützte Methode
```csharp
public class Tier
{
    protected void LautGeben()
    {
        Console.WriteLine("Tier macht Geräusch");
    }
}

public class Hund : Tier
{
    public void Bellen()
    {
        LautGeben(); // Zugriff auf die geschützte Methode
        Console.WriteLine("Wuff!");
    }
}
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von "protected" ist, dass Entwickler möglicherweise versuchen, von einer nicht abgeleiteten Klasse auf geschützte Mitglieder zuzugreifen, was zu einem Kompilierungsfehler führt. Es ist wichtig, die Hierarchie der Klassen zu beachten und sicherzustellen, dass der Zugriff nur innerhalb der vorgesehenen Abstraktionen erfolgt.

Ein weiterer Punkt zu beachten ist, dass "protected" den Zugriff auf Mitglieder innerhalb der gleichen Assembly nicht gewährt, es sei denn, sie befinden sich in abgeleiteten Klassen. Dies kann zu Verwirrung führen, wenn man versucht, auf geschützte Mitglieder von einer anderen Klasse innerhalb der gleichen Assembly zuzugreifen.

## One Line Summary
Das Schlüsselwort "protected" in C# sichert den Zugriff auf Klassenmitglieder nur für die Klasse selbst und deren abgeleitete Klassen.