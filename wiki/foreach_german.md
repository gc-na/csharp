<!--
Meta Description: # C# foreach Schleife: Ein umfassender Leitfaden zur Verwendung in C# ## Synopsis Die `foreach`-Schleife in C# ist eine leistungsstarke Kontrollstrukt...
Meta Keywords: die, der, foreach, und, sammlung
-->

# C# foreach Schleife: Ein umfassender Leitfaden zur Verwendung in C#

## Synopsis
Die `foreach`-Schleife in C# ist eine leistungsstarke Kontrollstruktur, die es Entwicklern ermöglicht, effizient durch Sammlungen und Arrays zu iterieren. Sie vereinfacht den Code und erhöht die Lesbarkeit, indem sie die Notwendigkeit von Indizes eliminiert.

## Dokumentation
Die `foreach`-Schleife wird in C# verwendet, um über Elemente in einer Sammlung oder einem Array zu iterieren. Sie ist besonders nützlich, wenn Sie alle Elemente einer Liste oder eines Arrays ohne manuelles Verwalten von Schleifenindizes durchlaufen möchten.

### Zweck
Der Hauptzweck der `foreach`-Schleife ist es, die Iteration über Datenstrukturen zu vereinfachen, wodurch der Code klarer und weniger fehleranfällig wird.

### Verwendung
Die Syntax der `foreach`-Schleife in C# lautet wie folgt:

```csharp
foreach (Datentyp element in Sammlung)
{
    // Code, der mit dem Element arbeitet
}
```

Hierbei steht `Datentyp` für den Typ der Elemente in der Sammlung, `element` ist eine Variable, die jedes Element der Sammlung während der Iteration darstellt, und `Sammlung` ist die Datenstruktur, über die iteriert wird (z.B. ein Array oder eine Liste).

## Beispiele
### Beispiel 1: Iteration über ein Array
```csharp
string[] farben = { "Rot", "Grün", "Blau" };

foreach (string farbe in farben)
{
    Console.WriteLine(farbe);
}
```
In diesem Beispiel wird über ein Array von Farben iteriert und jede Farbe in der Konsole ausgegeben.

### Beispiel 2: Iteration über eine Liste
```csharp
List<int> zahlen = new List<int> { 1, 2, 3, 4, 5 };

foreach (int zahl in zahlen)
{
    Console.WriteLine(zahl * 2);
}
```
Hier wird eine Liste von Ganzzahlen durchlaufen, und jede Zahl wird verdoppelt und ausgegeben.

## Erklärung
Einige häufige Fallstricke und Anmerkungen zur `foreach`-Schleife sind:

- **Unveränderlichkeit**: In einer `foreach`-Schleife können die Elemente der Sammlung nicht verändert werden. Wenn Sie versuchen, ein Element zu ändern, während Sie über die Sammlung iterieren, wird eine Ausnahme ausgelöst.
  
- **NullReferenceException**: Achten Sie darauf, dass die Sammlung nicht null ist. Ein Versuch, über eine null-Sammlung zu iterieren, führt zu einer `NullReferenceException`.

- **Typensicherheit**: Der Datentyp des Elements muss mit dem Typ der Elemente in der Sammlung übereinstimmen. Bei Mismatch wird ein Kompilierungsfehler angezeigt.

## Ein-Satz-Zusammenfassung
Die `foreach`-Schleife in C# ermöglicht eine einfache und leserliche Iteration über Sammlungen und Arrays, ohne sich um Indizes kümmern zu müssen.