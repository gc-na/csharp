<!--
Meta Description: # C# Kurzdatentyp: Verwendung und Beispiele ## Synopsis Der `short` Datentyp in C# ist ein ganzzahliger Datentyp, der 16 Bit Speicherplatz benötigt un...
Meta Keywords: short, der, ist, datentyp, und
-->

# C# Kurzdatentyp: Verwendung und Beispiele

## Synopsis
Der `short` Datentyp in C# ist ein ganzzahliger Datentyp, der 16 Bit Speicherplatz benötigt und Werte im Bereich von -32.768 bis 32.767 speichern kann. Er wird häufig verwendet, um Speicherplatz zu sparen, wenn die Werte in diesem Bereich liegen.

## Dokumentation
Der `short` Datentyp ist Teil der .NET-Typen und wird durch das Schlüsselwort `short` deklariert. Er ist ein vorzeichenbehafteter Datentyp, was bedeutet, dass er sowohl positive als auch negative Werte speichern kann. Der `short` Datentyp ist nützlich in Situationen, in denen der volle Bereich eines `int` (32 Bit) nicht benötigt wird, und trägt zur Optimierung der Speichernutzung bei.

### Verwendung
Um einen `short` Datentyp zu deklarieren, verwenden Sie die folgende Syntax:

```csharp
short variableName;
```

Sie können auch einen Wert zuweisen:

```csharp
short myShort = 1000;
```

### Details
- **Größe:** 16 Bit
- **Wertebereich:** -32.768 bis 32.767
- **Standardwert:** 0

Der `short` Datentyp ist nützlich in Arrays, Strukturen und für die Interoperabilität mit unmanaged Code, wo der Speicherplatz begrenzt ist.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von `short` in C#:

### Einfaches Beispiel
```csharp
short zahl = 15000;
Console.WriteLine(zahl); // Ausgabe: 15000
```

### Verwendung in Berechnungen
```csharp
short a = 5000;
short b = 3000;
short summe = (short)(a + b);
Console.WriteLine(summe); // Ausgabe: 8000
```

### Array von Shorts
```csharp
short[] zahlenArray = new short[5] { 1, 2, 3, 4, 5 };
foreach (short zahl in zahlenArray)
{
    Console.WriteLine(zahl); // Ausgabe: 1, 2, 3, 4, 5
}
```

## Erklärung
Ein häufiges Problem beim Arbeiten mit `short` ist der Überlauf. Wenn Sie Operationen durchführen, die zu einem Wert führen, der außerhalb des Bereichs von `short` liegt, wird eine `OverflowException` ausgelöst, es sei denn, Sie verwenden einen checked-Block:

```csharp
short a = 32767;
short b = 1;
short ergebnis = checked((short)(a + b)); // Löst eine OverflowException aus
```

Es ist auch wichtig, `short` in Berechnungen zu casten, da C# standardmäßig mit `int` arbeitet. Dies kann zu unerwarteten Ergebnissen führen, wenn Sie `short`-Werte direkt addieren oder subtrahieren.

## Ein Satz Zusammenfassung
Der `short` Datentyp in C# ist ein 16-Bit vorzeichenbehafteter Ganzzahltyp, der Werte im Bereich von -32.768 bis 32.767 speichert und zur Optimierung des Speicherplatzes verwendet wird.