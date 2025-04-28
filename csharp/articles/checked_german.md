<!--
Meta Description: # Verwendung von "checked" in C#: Fehlerüberwachung bei arithmetischen Operationen ## Synopsis Das Schlüsselwort "checked" in C# dient dazu, Überläufe...
Meta Keywords: checked, die, int, das, schlüsselwort
-->

# Verwendung von "checked" in C#: Fehlerüberwachung bei arithmetischen Operationen

## Synopsis
Das Schlüsselwort "checked" in C# dient dazu, Überläufe bei arithmetischen Operationen zu erkennen und eine Ausnahme auszulösen, wenn der Wert eines Ausdrucks den maximalen oder minimalen Bereich des Datentyps überschreitet.

## Dokumentation
Das `checked`-Schlüsselwort wird in C# verwendet, um sicherzustellen, dass arithmetische Berechnungen innerhalb der Grenzen des Datentyps bleiben. Wenn eine Berechnung zu einem Überlauf führt, wird eine `OverflowException` ausgelöst. Dies ist besonders nützlich, wenn Programmierer sicherstellen möchten, dass ihre Berechnungen korrekt sind und keine unerwarteten Ergebnisse aufgrund von Überläufen auftreten.

### Verwendung
Das `checked`-Schlüsselwort kann sowohl für einzelne Ausdrücke als auch für Codeblöcke verwendet werden. Hier sind die grundlegenden Anwendungsformen:

1. **Für einen einzelnen Ausdruck**:
   ```csharp
   int result = checked(a + b);
   ```

2. **Für einen Codeblock**:
   ```csharp
   checked
   {
       int sum = a + b;
       // Weitere Berechnungen
   }
   ```

### Details
- Das `checked`-Schlüsselwort kann nur mit arithmetischen Operationen (Addition, Subtraktion, Multiplikation) verwendet werden.
- Es kann in Kombination mit dem `unchecked`-Schlüsselwort verwendet werden, um Überprüfungen zu deaktivieren, wenn dies gewünscht ist.
- Die Verwendung von `checked` verbessert die Sicherheit des Codes, da es hilft, Fehler frühzeitig zu erkennen.

## Beispiele

### Beispiel 1: Einfacher Ausdruck
```csharp
int a = int.MaxValue;
int b = 1;

try
{
    int result = checked(a + b);
}
catch (OverflowException)
{
    Console.WriteLine("Überlauf erkannt!");
}
```

### Beispiel 2: Codeblock
```csharp
int a = 10;
int b = 20;

try
{
    checked
    {
        int sum = a + b;
        Console.WriteLine("Die Summe ist: " + sum);
    }
}
catch (OverflowException)
{
    Console.WriteLine("Überlauf erkannt!");
}
```

## Erklärung
Ein häufiger Fehler beim Arbeiten mit `checked` ist es, die Ausnahme nicht zu behandeln. Wenn eine Berechnung einen Überlauf verursacht und keine `try-catch`-Anweisung vorhanden ist, wird das Programm abstürzen. Programmierer sollten immer sicherstellen, dass sie den Code so strukturieren, dass Überläufe angemessen behandelt werden. 

Ein weiteres zu beachtendes Detail ist, dass `checked` keine Auswirkungen auf die Leistung hat, solange keine Überläufe auftreten. In der Regel wird die Fehlersuche durch die Verwendung von `checked` erleichtert, da Überläufe sofort erkannt werden.

## Einzeilige Zusammenfassung
Das `checked`-Schlüsselwort in C# ermöglicht die Überwachung von Überläufen bei arithmetischen Operationen und löst eine Ausnahme aus, wenn der Wert eines Ausdrucks den zulässigen Bereich überschreitet.