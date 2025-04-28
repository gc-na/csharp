<!--
Meta Description: # Sealed in C#: Eine umfassende Anleitung zu versiegelten Klassen und Methoden ## Synopsis Das Schlüsselwort `sealed` in C# wird verwendet, um zu verh...
Meta Keywords: sealed, die, klasse, der, werden
-->

# Sealed in C#: Eine umfassende Anleitung zu versiegelten Klassen und Methoden

## Synopsis
Das Schlüsselwort `sealed` in C# wird verwendet, um zu verhindern, dass eine Klasse oder Methode von einer anderen Klasse abgeleitet oder überschrieben wird. Dies hilft, die Integrität und das Verhalten von Klassen in der objektorientierten Programmierung zu schützen.

## Documentation
In C# ermöglicht das `sealed`-Schlüsselwort Entwicklern, die Vererbung in ihrer Klassenhierarchie zu kontrollieren. Wenn eine Klasse als `sealed` deklariert wird, kann sie nicht als Basisklasse für andere Klassen verwendet werden. Ebenso kann eine `sealed`-Methode nicht in abgeleiteten Klassen überschrieben werden. Dies ist besonders nützlich, um sicherzustellen, dass bestimmte Implementierungen nicht verändert werden, was die Wartbarkeit und Stabilität des Codes erhöht.

### Verwendung
Das `sealed`-Schlüsselwort wird in der Klassendeklaration oder in der Methode innerhalb einer Klasse platziert. Um eine Klasse als `sealed` zu definieren, verwenden Sie die folgende Syntax:

```csharp
sealed class MeineVersiegelteKlasse
{
    // Klassendeklaration
}
```

Um eine Methode innerhalb einer nicht versiegelten Klasse als `sealed` zu deklarieren, muss die Methode zuerst als `virtual` oder `abstract` in einer Basisklasse definiert werden:

```csharp
class BasisKlasse
{
    public virtual void MeineMethode()
    {
        // Implementierung
    }
}

sealed class AbgeleiteteKlasse : BasisKlasse
{
    public override void MeineMethode()
    {
        // Implementierung
    }
}
```

## Examples
### Beispiel 1: Versiegelte Klasse
```csharp
sealed class VersiegelteKlasse
{
    public void Methode()
    {
        Console.WriteLine("Dies ist eine Methode der versiegelten Klasse.");
    }
}

// Der folgende Code führt zu einem Fehler, da die Klasse nicht abgeleitet werden kann
// class AbgeleiteteKlasse : VersiegelteKlasse { } // Kompilierfehler
```

### Beispiel 2: Versiegelte Methode
```csharp
class BasisKlasse
{
    public virtual void ZeigeNachricht()
    {
        Console.WriteLine("Nachricht von der Basis-Klasse.");
    }
}

class AbgeleiteteKlasse : BasisKlasse
{
    public sealed override void ZeigeNachricht()
    {
        Console.WriteLine("Nachricht von der abgeleiteten Klasse.");
    }
}

// Der folgende Code führt zu einem Fehler, da die Methode nicht überschrieben werden kann
// class WeitereAbgeleiteteKlasse : AbgeleiteteKlasse
// {
//     public override void ZeigeNachricht() { } // Kompilierfehler
// }
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von `sealed` ist die Annahme, dass `sealed` nur für Klassen gilt. Tatsächlich kann es auch für Methoden verwendet werden, die in abgeleiteten Klassen nicht überschrieben werden dürfen. Es ist wichtig, sicherzustellen, dass die Verwendung von `sealed` die gewünschte Flexibilität oder Einschränkung in der Vererbung bietet. Auch sollte darauf geachtet werden, dass versiegelte Klassen nicht als Basisklassen verwendet werden können, was die Wiederverwendbarkeit des Codes einschränken kann.

## One Line Summary
Das `sealed`-Schlüsselwort in C# verhindert die Vererbung von Klassen und das Überschreiben von Methoden, um die Integrität des Codes zu schützen.