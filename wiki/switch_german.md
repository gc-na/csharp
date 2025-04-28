<!--
Meta Description: # Switch-Anweisung in C#: Eine umfassende Anleitung ## Synopsis Die `switch`-Anweisung in C# ermöglicht es Entwicklern, mehrere Bedingungen zu prüfen ...
Meta Keywords: case, break, switch, anweisung, die
-->

# Switch-Anweisung in C#: Eine umfassende Anleitung

## Synopsis
Die `switch`-Anweisung in C# ermöglicht es Entwicklern, mehrere Bedingungen zu prüfen und verschiedene Codeblöcke basierend auf dem Wert einer Variablen auszuführen. Sie ist eine elegante Alternative zu langen `if-else`-Ketten und verbessert die Lesbarkeit des Codes.

## Dokumentation
Die `switch`-Anweisung in C# wird verwendet, um einen Ausdruck mit mehreren möglichen Werten zu vergleichen. Sie ist besonders nützlich, wenn der Ausdruck nur eine begrenzte Anzahl von möglichen Werten hat. Die Syntax der `switch`-Anweisung ist wie folgt:

```csharp
switch (ausdruck)
{
    case wert1:
        // Anweisungen für wert1
        break;
    case wert2:
        // Anweisungen für wert2
        break;
    default:
        // Anweisungen, wenn kein Wert übereinstimmt
        break;
}
```

### Verwendung
- **Feldtyp**: Der Ausdruck, der in der `switch`-Anweisung verwendet wird, kann vom Typ `int`, `char`, `string`, oder sogar `enum` sein.
- **case-Anweisungen**: Jede `case`-Anweisung repräsentiert einen möglichen Wert des Ausdrucks, und der Code innerhalb dieser `case` wird ausgeführt, wenn der Ausdruck mit dem Wert übereinstimmt.
- **default-Anweisung**: Optional kann eine `default`-Anweisung verwendet werden, um Anweisungen auszuführen, wenn keiner der `case`-Werte übereinstimmt.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung der `switch`-Anweisung:

### Beispiel 1: Ganzzahl Vergleich

```csharp
int tag = 3;
switch (tag)
{
    case 1:
        Console.WriteLine("Montag");
        break;
    case 2:
        Console.WriteLine("Dienstag");
        break;
    case 3:
        Console.WriteLine("Mittwoch");
        break;
    default:
        Console.WriteLine("Ungültiger Tag");
        break;
}
```

### Beispiel 2: String Vergleich

```csharp
string farbe = "rot";
switch (farbe)
{
    case "rot":
        Console.WriteLine("Die Farbe ist Rot");
        break;
    case "blau":
        Console.WriteLine("Die Farbe ist Blau");
        break;
    case "grün":
        Console.WriteLine("Die Farbe ist Grün");
        break;
    default:
        Console.WriteLine("Unbekannte Farbe");
        break;
}
```

## Erklärung
Einige häufige Fallstricke bei der Verwendung der `switch`-Anweisung sind:

- **Fehlendes `break`**: Wenn die `break`-Anweisung vergessen wird, wird die Ausführung in die nächste `case`-Anweisung „durchfallen“ (fall-through), was zu unerwartetem Verhalten führen kann.
- **Typen von Ausdrücken**: Der `switch`-Ausdruck muss einen kompatiblen Typ zu den `case`-Werten haben. Ein `int`-Wert kann nicht mit einem `string`-Wert verglichen werden.
- **Mehrere `case`-Werte**: Es ist möglich, mehrere `case`-Werte zusammenzufassen, um denselben Codeblock auszuführen:

```csharp
switch (zahl)
{
    case 1:
    case 2:
    case 3:
        Console.WriteLine("Zahl ist 1, 2 oder 3");
        break;
    default:
        Console.WriteLine("Zahl ist größer als 3 oder negativ");
        break;
}
```

## Ein-Satz-Zusammenfassung
Die `switch`-Anweisung in C# ist ein strukturiertes Kontrollflussmittel, das es ermöglicht, basierend auf dem Wert eines Ausdrucks mehrere Bedingungen elegant zu prüfen.