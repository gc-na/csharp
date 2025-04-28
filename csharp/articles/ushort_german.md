<!--
Meta Description: # Verständnis des Datentyps "ushort" in C# ## Synopsis Der `ushort`-Datentyp in C# ist ein nicht signierter 16-Bit-Ganzzahltyp, der Werte im Bereich v...
Meta Keywords: ushort, der, von, ist, ein
-->

# Verständnis des Datentyps "ushort" in C#

## Synopsis
Der `ushort`-Datentyp in C# ist ein nicht signierter 16-Bit-Ganzzahltyp, der Werte im Bereich von 0 bis 65.535 speichert und häufig zur Optimierung des Speicherverbrauchs verwendet wird.

## Dokumentation
Der `ushort` (kurz für "unsigned short") ist ein grundlegender Datentyp in C#, der zur Speicherung von nicht negativen Ganzzahlen dient. Er gehört zur Gruppe der primitiven Datentypen und wird oft in Szenarien verwendet, in denen nur positive Werte benötigt werden, wie z.B. bei Indizes, Zählungen oder anderen numerischen Werten, die nicht negativ sein können.

### Zweck
Der Hauptzweck von `ushort` besteht darin, Speicherplatz zu sparen, da er nur 2 Bytes belegt, im Vergleich zu 4 Bytes für den `int`-Datentyp. Dies ist besonders vorteilhaft in großen Datenstrukturen oder Arrays, wo der Speicherverbrauch minimiert werden soll.

### Verwendung
Um `ushort` in C# zu verwenden, deklarieren Sie eine Variable wie folgt:
```csharp
ushort myNumber = 50000;
```

### Details
- **Wertebereich**: 0 bis 65.535
- **Standardwert**: 0
- **Typkonvertierung**: `ushort` kann leicht in andere numerische Typen konvertiert werden, jedoch muss darauf geachtet werden, dass bei der Konvertierung von größeren Datentypen auf `ushort` der Wertebereich berücksichtigt wird, um Überläufe zu vermeiden.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von `ushort`:

### Beispiel 1: Deklaration und Zuweisung
```csharp
ushort alter = 25;
Console.WriteLine(alter); // Ausgabe: 25
```

### Beispiel 2: Arithmetische Operationen
```csharp
ushort a = 30000;
ushort b = 20000;
ushort summe = (ushort)(a + b); // Beachten Sie die Typumwandlung
Console.WriteLine(summe); // Ausgabe: 50000
```

### Beispiel 3: Verwendung in einer Schleife
```csharp
for (ushort i = 0; i < 10; i++)
{
    Console.WriteLine(i); // Ausgabe: 0 bis 9
}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `ushort` ist die Typumwandlung. Wenn Sie versuchen, einen Wert zuzuweisen, der außerhalb des zulässigen Bereichs liegt, tritt ein Überlauf auf und es wird eine Ausnahme ausgelöst. Zudem sollten Sie vorsichtig sein, wenn Sie `ushort`-Variablen in arithmetischen Operationen verwenden, da der Compiler möglicherweise keine automatische Typkonvertierung vornimmt. In solchen Fällen ist eine explizite Umwandlung erforderlich, um sicherzustellen, dass die Berechnung korrekt durchgeführt wird.

## Ein-Satz-Zusammenfassung
Der `ushort`-Datentyp in C# ist ein nicht signierter 16-Bit-Ganzzahltyp, der zur Speicherung positiver Ganzzahlen von 0 bis 65.535 verwendet wird und hilft, den Speicherverbrauch zu optimieren.