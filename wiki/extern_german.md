<!--
Meta Description: # CSharp "extern": Verwendung und Bedeutung in der Programmierung ## Synopsis Das Schlüsselwort `extern` in CSharp wird verwendet, um anzugeben, dass ...
Meta Keywords: extern, die, der, wird, verwendet
-->

# CSharp "extern": Verwendung und Bedeutung in der Programmierung

## Synopsis
Das Schlüsselwort `extern` in CSharp wird verwendet, um anzugeben, dass eine Methode oder eine Variable in einer anderen Assemblierung oder einer externen Bibliothek definiert ist.

## Dokumentation
Das `extern`-Schlüsselwort hat in CSharp zwei primäre Verwendungszwecke:

1. **Extern Methods**: Es ermöglicht die Deklaration von Methoden, die in einer externen DLL (Dynamic Link Library) definiert sind. Dies ist häufig der Fall bei der Interoperabilität mit nicht verwalteten Code, wie z.B. Windows-API-Funktionen.

   ```csharp
   [DllImport("user32.dll")]
   public static extern int MessageBox(int hWnd, string text, string caption, uint type);
   ```

   In diesem Beispiel wird die `MessageBox`-Methode aus der `user32.dll` importiert, um eine Windows-Nachrichtbox anzuzeigen.

2. **Extern Variables**: Es kann auch verwendet werden, um externe Variablen zu deklarieren, die in anderen Modulen definiert sind, was in der Regel in C oder C++-Kontexten verwendet wird.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung des `extern`-Schlüsselworts:

### Beispiel 1: Verwendung von extern mit DllImport
```csharp
using System;
using System.Runtime.InteropServices;

class Program
{
    [DllImport("user32.dll")]
    public static extern int MessageBox(int hWnd, string text, string caption, uint type);
    
    static void Main()
    {
        MessageBox(0, "Hallo, Welt!", "Nachricht", 0);
    }
}
```

### Beispiel 2: Externe Variablen (Kontext C/C++)
In C# wird `extern` zur Deklaration von externen Variablen nicht verwendet, da C# nicht das Konzept von externen Variablen in demselben Maße wie C oder C++ unterstützt.

## Erklärung
Ein häufiges Missverständnis beim Arbeiten mit dem `extern`-Schlüsselwort ist, dass es nicht für die Deklaration von Variablen in C# verwendet wird. In C# wird normalerweise der `extern`-Modifikator nur für Methoden in Verbindung mit der `DllImport`-Attribut verwendet, um interopérable Aufrufe zu ermöglichen. 

Ein weiterer wichtiger Punkt ist, dass beim Arbeiten mit externen Methoden die richtige Verwendung von DllImport und dem richtigen Datentyp wichtig ist, um sicherzustellen, dass die Methode ordnungsgemäß funktioniert und keine Speicherprobleme auftreten.

## Einzeilensummary
Das `extern`-Schlüsselwort in CSharp wird verwendet, um Methoden zu deklarieren, die in externen Bibliotheken oder DLLs definiert sind.