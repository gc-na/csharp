<!--
Meta Description: # Der C# Befehl "break": Verwendung und Beispiele ## Synopsis Der `break`-Befehl in C# wird verwendet, um die Ausführung von Schleifen oder Switch-Anw...
Meta Keywords: break, die, der, oder, switch
-->

# Der C# Befehl "break": Verwendung und Beispiele

## Synopsis
Der `break`-Befehl in C# wird verwendet, um die Ausführung von Schleifen oder Switch-Anweisungen vorzeitig zu beenden und so den Programmfluss zu steuern.

## Documentation
Der `break`-Befehl ist ein Steuerflussbefehl in C#, der es ermöglicht, eine Schleife (wie `for`, `while`, oder `do-while`) oder eine Switch-Anweisung vorzeitig zu verlassen. Dies kann nützlich sein, wenn eine bestimmte Bedingung erfüllt ist oder wenn ein bestimmtes Ereignis eintritt, das die Fortsetzung der Schleife oder der Switch-Anweisung nicht mehr sinnvoll macht.

### Verwendung
Um den `break`-Befehl zu verwenden, platzieren Sie ihn innerhalb einer Schleife oder eines Switch-Blocks. Wenn der `break`-Befehl ausgeführt wird, wird die Kontrolle sofort an die nächste Anweisung nach der Schleife oder dem Switch-Block übergeben.

### Syntax
```csharp
break;
```

## Examples
Hier sind einige grundlegende Beispiele für die Verwendung des `break`-Befehls:

### Beispiel 1: Verwendung in einer Schleife
```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        break; // verlässt die Schleife, wenn i gleich 5 ist
    }
    Console.WriteLine(i);
}
```
*Ausgabe:*
```
0
1
2
3
4
```

### Beispiel 2: Verwendung in einer Switch-Anweisung
```csharp
int day = 4;
switch (day)
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
    case 4:
        Console.WriteLine("Donnerstag");
        break;
    default:
        Console.WriteLine("Ungültiger Tag");
        break;
}
```
*Ausgabe:*
```
Donnerstag
```

## Explanation
Ein häufiger Fehler beim Einsatz des `break`-Befehls ist, ihn außerhalb eines Schleifen- oder Switch-Blocks zu verwenden, was zu einem Kompilierungsfehler führt. Zudem kann der `break`-Befehl nur die innere Schleife oder den inneren Switch-Block beenden, wenn er in verschachtelten Strukturen verwendet wird.

Ein weiterer Punkt ist, dass der `break`-Befehl nicht für `foreach`-Schleifen verwendet werden sollte, um die Iteration zu beenden, da die Verwendung von `break` in diesem Kontext den gesamten Block verlässt, nicht nur die aktuelle Iteration.

## One Line Summary
Der `break`-Befehl in C# stoppt die Ausführung von Schleifen oder Switch-Anweisungen und übergibt die Kontrolle an die nächste Anweisung.