<!--
Meta Description: # C#: Verwendung des "continue"-Befehls in Schleifen ## Synopsis Der `continue`-Befehl in C# ermöglicht es Entwicklern, die aktuelle Iteration einer S...
Meta Keywords: der, die, continue, schleife, befehl
-->

# C#: Verwendung des "continue"-Befehls in Schleifen

## Synopsis
Der `continue`-Befehl in C# ermöglicht es Entwicklern, die aktuelle Iteration einer Schleife zu beenden und zur nächsten Iteration überzugehen. Dies ist nützlich, um bestimmte Bedingungen zu überspringen, ohne die gesamte Schleife zu unterbrechen.

## Dokumentation
Der `continue`-Befehl kommt in Schleifenstrukturen wie `for`, `foreach`, `while` und `do-while` zum Einsatz. Wenn der `continue`-Befehl innerhalb einer Schleife ausgeführt wird, wird die restliche Logik der aktuellen Iteration übersprungen, und die Schleife springt direkt zur nächsten Iteration.

### Verwendung
- **Schleifenarten**: `for`, `foreach`, `while`, `do-while`
- **Syntax**: `continue;`
- **Kontext**: Der `continue`-Befehl sollte innerhalb einer Schleife verwendet werden.

### Details
Der `continue`-Befehl ist besonders nützlich, wenn Sie bestimmte Bedingungen in einer Schleife überprüfen und, falls diese erfüllt sind, die aktuelle Iteration abbrechen möchten, während die Schleife weiterhin fortgesetzt wird. Dies führt zu einem klareren und effizienteren Code, da unnötige Berechnungen oder Logik übersprungen werden.

## Beispiele

### Beispiel 1: Verwendung in einer `for`-Schleife
```csharp
for (int i = 0; i < 10; i++)
{
    if (i % 2 == 0) // Überprüfen, ob die Zahl gerade ist
    {
        continue; // Gerade Zahlen überspringen
    }
    Console.WriteLine(i); // Nur ungerade Zahlen werden ausgegeben
}
```

### Beispiel 2: Verwendung in einer `foreach`-Schleife
```csharp
string[] namen = { "Anna", "Bert", "Clara", "Daniel" };
foreach (string name in namen)
{
    if (name.StartsWith("B")) // Namen, die mit 'B' beginnen, überspringen
    {
        continue;
    }
    Console.WriteLine(name); // Ausgabe der übrigen Namen
}
```

### Beispiel 3: Verwendung in einer `while`-Schleife
```csharp
int zahl = 0;
while (zahl < 5)
{
    zahl++;
    if (zahl == 3) // Wenn die Zahl 3 erreicht wird, überspringen
    {
        continue;
    }
    Console.WriteLine(zahl); // Ausgabe der Zahlen 1, 2, 4, 5
}
```

## Erklärung
Ein häufiger Fehler bei der Verwendung des `continue`-Befehls ist das Missverständnis darüber, wie er die Schleifensteuerung beeinflusst. Ein `continue`-Befehl bewirkt, dass nur der aktuelle Iterationsblock übersprungen wird, nicht jedoch die gesamte Schleife. Stellen Sie sicher, dass Sie die Logik richtig strukturieren, um unerwartete Ergebnisse zu vermeiden.

Ein weiterer Punkt ist die Verwendung in verschachtelten Schleifen. Der `continue`-Befehl bezieht sich immer nur auf die nächstgelegene Schleife, in der er sich befindet. Dies kann zu Verwirrung führen, wenn Sie mehrere Schleifen in Ihrem Code haben.

## Ein-Satz-Zusammenfassung
Der `continue`-Befehl in C# überspringt die aktuelle Iteration einer Schleife und fährt mit der nächsten Iteration fort, um eine effiziente Steuerung der Schleifenlogik zu ermöglichen.