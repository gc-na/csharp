<!--
Meta Description: # C# Struct: Eine umfassende Anleitung zu Strukturen in C# ## Synopsis In C# sind Strukturen (structs) benutzerdefinierte Datentypen, die es ermöglich...
Meta Keywords: strukturen, sie, public, int, eine
-->

# C# Struct: Eine umfassende Anleitung zu Strukturen in C#

## Synopsis
In C# sind Strukturen (structs) benutzerdefinierte Datentypen, die es ermöglichen, mehrere verwandte Variablen zusammenzufassen und als eine Einheit zu verwalten. Sie sind werttypbasiert und bieten eine effiziente Möglichkeit, Daten zu modellieren.

## Dokumentation
### Zweck
Strukturen in C# dienen dazu, Daten zu organisieren, die logisch zusammengehören. Sie sind besonders nützlich, wenn Sie kleine, einfache Datenobjekte benötigen, die keine umfangreiche Funktionalität erfordern.

### Verwendung
Eine Struktur wird in C# mit dem Schlüsselwort `struct` definiert. Sie kann Felder, Eigenschaften und Methoden enthalten, ist jedoch nicht so flexibel wie eine Klasse. Strukturen sind Werttypen, was bedeutet, dass sie im Stack gespeichert werden und bei der Zuweisung oder Übergabe an Methoden kopiert werden.

### Details
- **Definition einer Struktur**: Eine Struktur wird ähnlich wie eine Klasse definiert:
  ```csharp
  struct Punkt
  {
      public int X;
      public int Y;

      public Punkt(int x, int y)
      {
          X = x;
          Y = y;
      }

      public void Verschieben(int dx, int dy)
      {
          X += dx;
          Y += dy;
      }
  }
  ```
- **Instanziierung**: Strukturen können direkt instanziiert werden, ohne dass ein `new`-Operator erforderlich ist, wenn sie als Parameter übergeben werden.
- **Immutabilität**: Es ist eine gute Praxis, Strukturen unveränderlich zu gestalten, indem nur schreibgeschützte Eigenschaften bereitgestellt werden.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von Strukturen in C#:

### Beispiel 1: Einfache Struktur
```csharp
struct Rechteck
{
    public int Breite;
    public int Höhe;

    public int Fläche()
    {
        return Breite * Höhe;
    }
}

Rechteck rect = new Rechteck { Breite = 5, Höhe = 10 };
int fläche = rect.Fläche(); // 50
```

### Beispiel 2: Struktur mit Konstruktor
```csharp
struct Kreis
{
    public double Radius;

    public Kreis(double radius)
    {
        Radius = radius;
    }

    public double Umfang()
    {
        return 2 * Math.PI * Radius;
    }
}

Kreis k = new Kreis(3);
double umfang = k.Umfang(); // 18.84955592153876
```

## Erklärung
### Häufige Fallstricke
- **Referenz vs. Werttyp**: Da Strukturen Werttypen sind, kann es zu Verwirrung kommen, wenn man denkt, dass sie wie Referenztypen funktionieren. Änderungen an einer Struktur in einer Methode wirken sich nicht auf die ursprüngliche Struktur aus.
- **Standardkonstruktor**: Strukturen haben keinen parameterlosen Konstruktor, was bedeutet, dass Sie immer die Felder initialisieren müssen, bevor Sie die Struktur verwenden.
- **Größe der Struktur**: Bei komplexen Strukturen kann die Verwendung von Strukturen anstelle von Klassen den Speicherverbrauch erhöhen, da sie im Stack und nicht im Heap gespeichert werden.

## Ein-Satz-Zusammenfassung
In C# sind Strukturen benutzerdefinierte Werttypen, die eine effiziente Möglichkeit bieten, verwandte Daten zu gruppieren und zu verwalten.