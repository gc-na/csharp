<!--
Meta Description: # Rückgabewert in CSharp: Verwendung und Beispiele ## Synopsis Das Schlüsselwort `return` in CSharp wird verwendet, um den Wert einer Methode zurückzu...
Meta Keywords: methode, return, das, wert, die
-->

# Rückgabewert in CSharp: Verwendung und Beispiele

## Synopsis
Das Schlüsselwort `return` in CSharp wird verwendet, um den Wert einer Methode zurückzugeben und die Ausführung der Methode zu beenden.

## Dokumentation
Das `return`-Schlüsselwort ist ein grundlegendes Element der CSharp-Programmiersprache, das es ermöglicht, einen Wert aus einer Methode an den Aufrufer zurückzugeben. Jede Methode, die einen Rückgabewert erwartet, muss das `return`-Schlüsselwort verwenden, um den entsprechenden Wert zurückzugeben. Für Methoden, die keinen Wert zurückgeben (void), ist `return` optional, kann aber verwendet werden, um die Ausführung der Methode vorzeitig zu beenden.

### Verwendung
- **Rückgabe eines Wertes**: Eine Methode kann einen bestimmten Datentyp haben (z.B. `int`, `string`, `bool`), und das `return`-Schlüsselwort gibt einen Wert dieses Typs zurück.
- **Vorzeitige Beendigung**: Das `return`-Schlüsselwort kann auch verwendet werden, um die Ausführung einer Methode vorzeitig zu beenden, ohne einen Wert zurückzugeben.

### Details
- Der Rückgabewert muss mit dem Rückgabetyp der Methode übereinstimmen.
- Wenn eine Methode als `void` deklariert ist, darf das `return`-Schlüsselwort ohne Wert verwendet werden, um die Methode zu verlassen.
- Mehrere `return`-Anweisungen können in einer Methode vorhanden sein, aber nur eine wird ausgeführt, wenn die Methode aufgerufen wird.

## Beispiele

### Beispiel 1: Einfache Rückgabe eines Wertes
```csharp
public int Addiere(int a, int b)
{
    return a + b;
}
```

### Beispiel 2: Vorzeitiges Beenden einer Methode
```csharp
public void PrüfeZahl(int zahl)
{
    if (zahl < 0)
    {
        Console.WriteLine("Zahl ist negativ.");
        return; // Vorzeitige Beendigung
    }
    Console.WriteLine("Zahl ist positiv oder null.");
}
```

### Beispiel 3: Rückgabe eines boolschen Wertes
```csharp
public bool IstGerade(int zahl)
{
    return zahl % 2 == 0; // Gibt true zurück, wenn die Zahl gerade ist
}
```

## Erklärung
Ein häufiger Fehler beim Arbeiten mit `return` ist das Zurückgeben eines Wertes, der nicht mit dem Rückgabetyp der Methode übereinstimmt. Dies führt zu einem Kompilierungsfehler. Ein weiteres häufiges Problem ist das Vergessen, `return` in einer Methode zu verwenden, die einen Wert zurückgeben muss, was ebenfalls zu einem Fehler führen kann.

Es ist wichtig, darauf zu achten, dass alle möglichen Ausführungspfade in einer Methode einen `return`-Wert zurückgeben, um sicherzustellen, dass der Compiler keine Warnungen oder Fehler ausgibt.

## Ein-Satz-Zusammenfassung
Das `return`-Schlüsselwort in CSharp wird verwendet, um einen Wert aus einer Methode zurückzugeben und die Ausführung der Methode zu beenden.