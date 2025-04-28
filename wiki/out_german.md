<!--
Meta Description: # C# "out" Schlüsselwort: Verwendung und Beispiele ## Synopsis Das "out"-Schlüsselwort in C# ermöglicht es, Argumente an Methoden zu übergeben, die vo...
Meta Keywords: der, out, methode, werden, parameter
-->

# C# "out" Schlüsselwort: Verwendung und Beispiele

## Synopsis
Das "out"-Schlüsselwort in C# ermöglicht es, Argumente an Methoden zu übergeben, die von der Methode geändert und zurückgegeben werden, ohne dass ein Rückgabewert erforderlich ist.

## Dokumentation
Das "out"-Schlüsselwort wird in C# verwendet, um Parameter an Methoden zu übergeben, die innerhalb der Methode verändert werden sollen. Es ermöglicht, mehrere Werte aus einer Methode zurückzugeben, ohne dass mehrere Rückgabewerte definiert werden müssen. Ein "out"-Parameter muss innerhalb der Methode, in der er definiert ist, initialisiert werden, bevor die Methode zurückkehrt. 

### Zweck
- Ermöglicht die Rückgabe von mehreren Werten aus einer Methode.
- Erleichtert die Handhabung von Fehlern und Statusinformationen.

### Verwendung
Um einen "out"-Parameter zu deklarieren, wird das Schlüsselwort "out" vor dem Datentyp des Parameters in der Methodendefinition verwendet. Bei der Aufrufung der Methode muss der übergebene Parameter nicht initialisiert werden. 

### Details
- "out"-Parameter müssen vor der Rückkehr der Methode initialisiert werden.
- Sie sind nützlich für die Fehlerbehandlung und für Methoden, die mehrere Werte zurückgeben müssen.

## Beispiele
```csharp
using System;

class Program
{
    static void Main()
    {
        int result;
        bool isSuccessful = TryParseInt("123", out result);
        
        if (isSuccessful)
        {
            Console.WriteLine($"Erfolgreich geparst: {result}");
        }
        else
        {
            Console.WriteLine("Parsing fehlgeschlagen.");
        }
    }

    static bool TryParseInt(string input, out int number)
    {
        return int.TryParse(input, out number);
    }
}
```

In diesem Beispiel wird ein "out"-Parameter verwendet, um einen ganzzahligen Wert aus der Methode `TryParseInt` zurückzugeben.

## Erklärung
Ein häufiger Stolperstein beim Arbeiten mit "out"-Parametern ist das Missverständnis, dass der Parameter vor der Verwendung initialisiert werden muss. Bei der Methode muss jedoch sichergestellt werden, dass der "out"-Parameter vor der Rückkehr der Methode einen Wert erhält. Ein weiteres häufiges Problem ist das Verwechseln von "out" mit "ref": Bei "ref" muss der Parameter vor dem Aufruf der Methode initialisiert werden, während dies bei "out" nicht erforderlich ist.

## Ein-Satz-Zusammenfassung
Das "out"-Schlüsselwort in C# ermöglicht es, Werte aus Methoden zurückzugeben, indem Parameter übergeben werden, die innerhalb der Methode verändert werden.