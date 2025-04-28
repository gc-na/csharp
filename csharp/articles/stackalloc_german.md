<!--
Meta Description: # stackalloc in C#: Effiziente Speicherallokation im Stack ## Synopsis `stackalloc` ist ein Schlüsselwort in C#, das es Entwicklern ermöglicht, Speich...
Meta Keywords: stackalloc, ist, int, der, die
-->

# stackalloc in C#: Effiziente Speicherallokation im Stack

## Synopsis
`stackalloc` ist ein Schlüsselwort in C#, das es Entwicklern ermöglicht, Speicherplatz auf dem Stack für einfache Datenstrukturen wie Arrays zu reservieren. Dies geschieht zur Laufzeit und bietet eine effiziente Möglichkeit, temporäre Daten zu verwalten, ohne den Garbage Collector zu belasten.

## Dokumentation
### Zweck
`stackalloc` wird verwendet, um Arrays von Werttypen direkt im Stack-Speicher zu allokieren. Dies hat den Vorteil, dass der Speicher sofort freigegeben wird, wenn der aktuelle Kontext verlassen wird (z.B. beim Verlassen einer Methode). Es eignet sich besonders für Performance-kritische Anwendungen, wo häufige Speicherzuweisungen und -freigaben erforderlich sind.

### Verwendung
Um `stackalloc` zu verwenden, muss es innerhalb eines unsicheren Kontextes (unsafe) oder in einem Kontext mit einem `Span<T>`-Typ verwendet werden. Es kann nur für Werttypen verwendet werden und ist nicht für Referenztypen geeignet.

#### Syntax
```csharp
Span<T> span = stackalloc T[n];
```
Hierbei ist `T` der Typ der Werte und `n` die Anzahl der Elemente.

### Details
- `stackalloc` kann nur in Methoden verwendet werden.
- Der zugewiesene Speicher ist nicht für die Verwendung außerhalb des aktuellen Scopes geeignet.
- Der Speicher wird nicht durch den Garbage Collector verwaltet, was die Leistung verbessert.

## Beispiele
### Einfaches Beispiel
```csharp
public void Beispiel()
{
    Span<int> zahlen = stackalloc int[5];
    for (int i = 0; i < zahlen.Length; i++)
    {
        zahlen[i] = i * 10;
    }

    foreach (var zahl in zahlen)
    {
        Console.WriteLine(zahl);
    }
}
```

### Verwendung in einer Methode
```csharp
public void Summiere(int anzahl)
{
    Span<int> werte = stackalloc int[anzahl];
    for (int i = 0; i < anzahl; i++)
    {
        werte[i] = i + 1;
    }

    int summe = 0;
    for (int i = 0; i < werte.Length; i++)
    {
        summe += werte[i];
    }

    Console.WriteLine($"Die Summe ist: {summe}");
}
```

## Erklärung
### Häufige Fallstricke
1. **Speicherüberlauf**: Da `stackalloc` Speicher im Stack allokiert, ist die Größe begrenzt. Zu große Arrays können zu einem Stack Overflow führen.
2. **Unsichere Kontexte**: Wenn `stackalloc` in einem unsicheren Kontext verwendet wird, müssen Sie sicherstellen, dass Ihr Projekt für unsicheren Code konfiguriert ist.
3. **Lebensdauer von Span<T>**: `Span<T>`-Objekte, die mit `stackalloc` erstellt wurden, dürfen nicht außerhalb des Scopes verwendet werden, da sie auf Stack-Speicher zeigen, der nach dem Verlassen des Scopes nicht mehr gültig ist.

### Zusätzliche Hinweise
- `stackalloc` ist in C# 7.2 und späteren Versionen verfügbar.
- Es ist eine nützliche Funktion in Hochleistungsanwendungen wie Spielen oder Echtzeitsystemen, wo Effizienz entscheidend ist.

## Ein-Satz-Zusammenfassung
`stackalloc` ermöglicht die effiziente Allokation von Arrays im Stack, was die Leistung von temporären Datenstrukturen in C# verbessert.