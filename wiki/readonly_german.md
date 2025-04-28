<!--
Meta Description: # readonly in C#: Grundlagen und Anwendung ## Synopsis Das Schlüsselwort `readonly` in C# ermöglicht es Entwicklern, Felder zu definieren, die nach ih...
Meta Keywords: readonly, werden, das, die, nicht
-->

# readonly in C#: Grundlagen und Anwendung

## Synopsis
Das Schlüsselwort `readonly` in C# ermöglicht es Entwicklern, Felder zu definieren, die nach ihrer Initialisierung nicht mehr verändert werden können. Dies fördert die Unveränderlichkeit und hilft, Fehler zu vermeiden.

## Documentation
In C# wird das Schlüsselwort `readonly` verwendet, um Felder innerhalb einer Klasse oder Struktur zu deklarieren, die nur während der Initialisierung oder im Konstruktor der Klasse oder Struktur einen Wert zugewiesen bekommen können. Ein `readonly`-Feld kann nicht nach der Initialisierung verändert werden, was bedeutet, dass der Wert konstant bleibt, sobald er festgelegt wurde.

### Zweck
Der Hauptzweck von `readonly` ist es, die Integrität der Daten zu schützen und die Lesbarkeit des Codes zu verbessern. Es ermöglicht Entwicklern, sicherzustellen, dass bestimmte Werte innerhalb einer Klasse nicht unerwartet geändert werden.

### Verwendung
`readonly` kann sowohl für primitive Datentypen als auch für benutzerdefinierte Objekte verwendet werden. Es kann in Klassen und Strukturen eingesetzt werden und wird wie folgt verwendet:

```csharp
class Beispiel
{
    public readonly int MaxWert;

    public Beispiel(int wert)
    {
        MaxWert = wert; // Zuweisung im Konstruktor
    }
}
```

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von `readonly`:

### Beispiel 1: Einfaches `readonly` Feld
```csharp
class Fahrzeug
{
    public readonly string Hersteller;

    public Fahrzeug(string hersteller)
    {
        Hersteller = hersteller; // Initialisierung im Konstruktor
    }
}

// Verwendung
var auto = new Fahrzeug("Toyota");
// auto.Hersteller = "Honda"; // Fehler: readonly-Feld kann nicht geändert werden
```

### Beispiel 2: `readonly` mit einem Array
```csharp
class Lager
{
    public readonly int[] Artikel;

    public Lager(int[] artikel)
    {
        Artikel = artikel; // Initialisierung im Konstruktor
    }
}

// Verwendung
var lager = new Lager(new int[] { 1, 2, 3 });
// lager.Artikel[0] = 5; // Erlaubt, da das Array selbst veränderlich ist
```

### Beispiel 3: `readonly` in einer Struktur
```csharp
struct Punkt
{
    public readonly int X;
    public readonly int Y;

    public Punkt(int x, int y)
    {
        X = x; // Zuweisung
        Y = y; // Zuweisung
    }
}

// Verwendung
var p = new Punkt(10, 20);
// p.X = 15; // Fehler: readonly-Feld kann nicht geändert werden
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von `readonly` ist das Missverständnis über die Mutabilität von Objekten. Während ein `readonly`-Feld nicht neu zugewiesen werden kann, bedeutet das nicht, dass die Daten innerhalb eines Objekts, auf das verwiesen wird, unveränderlich sind. Beispielsweise können Sie die Elemente eines `readonly`-Arrays ändern, da das Array selbst nicht neu zugewiesen wird, sondern nur seine Elemente.

Ein weiterer Punkt ist, dass `readonly`-Felder nicht mit dem `const`-Schlüsselwort verwechselt werden sollten. Im Gegensatz zu `const`, das zur Kompilierzeit festgelegt wird, kann `readonly` zur Laufzeit festgelegt werden, jedoch nur einmal.

## One Line Summary
Das `readonly`-Schlüsselwort in C# schützt Felder vor nachträglicher Änderung und fördert die Unveränderlichkeit von Objekten.