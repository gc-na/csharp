<!--
Meta Description: # "finally" in C#: Verwendung und Bedeutung ## Synopsis Das Schlüsselwort "finally" in C# wird in Verbindung mit Try-Catch-Blöcken verwendet, um siche...
Meta Keywords: finally, der, wird, try, block
-->

# "finally" in C#: Verwendung und Bedeutung

## Synopsis
Das Schlüsselwort "finally" in C# wird in Verbindung mit Try-Catch-Blöcken verwendet, um sicherzustellen, dass ein bestimmter Codeblock immer ausgeführt wird, unabhängig davon, ob eine Ausnahme aufgetreten ist oder nicht.

## Dokumentation
Das "finally"-Schlüsselwort ist ein wichtiger Bestandteil der Fehlerbehandlung in C#. Es wird in einem `try-catch-finally`-Block eingesetzt, um einen Codeabschnitt zu kennzeichnen, der immer ausgeführt wird, nachdem der `try`-Block abgeschlossen ist, egal ob eine Ausnahme aufgetreten ist oder nicht.

### Zweck
Der Hauptzweck von "finally" besteht darin, Ressourcen freizugeben oder Aufräumarbeiten durchzuführen, die unabhängig vom Erfolg oder Misserfolg des `try`-Blocks notwendig sind. Dies ist besonders nützlich bei der Arbeit mit Systemressourcen wie Dateien oder Netzwerkverbindungen.

### Verwendung
Ein typischer Aufbau sieht wie folgt aus:

```csharp
try
{
    // Code, der eine Ausnahme auslösen könnte
}
catch (Exception ex)
{
    // Fehlerbehandlung
}
finally
{
    // Code, der immer ausgeführt wird
}
```

Der `finally`-Block wird immer zuletzt ausgeführt, selbst wenn im `try`-Block eine Ausnahme auftritt oder der Prozess durch ein `return`-Statement vorzeitig verlassen wird.

## Beispiele
Hier sind einige grundlegende Beispielanwendungen des "finally"-Schlüsselworts:

### Beispiel 1: Ressourcenfreigabe

```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        FileStream fs = null;
        try
        {
            fs = new FileStream("test.txt", FileMode.Open);
            // Arbeiten mit der Datei
        }
        catch (FileNotFoundException ex)
        {
            Console.WriteLine("Datei nicht gefunden: " + ex.Message);
        }
        finally
        {
            if (fs != null)
            {
                fs.Close();
                Console.WriteLine("Dateistream erfolgreich geschlossen.");
            }
        }
    }
}
```

### Beispiel 2: Datenbankverbindung

```csharp
using System;
using System.Data.SqlClient;

class Program
{
    static void Main()
    {
        SqlConnection connection = null;
        try
        {
            connection = new SqlConnection("connectionString");
            connection.Open();
            // Arbeiten mit der Datenbank
        }
        catch (SqlException ex)
        {
            Console.WriteLine("Datenbankfehler: " + ex.Message);
        }
        finally
        {
            if (connection != null)
            {
                connection.Close();
                Console.WriteLine("Datenbankverbindung erfolgreich geschlossen.");
            }
        }
    }
}
```

## Erklärung
Ein häufiger Fehler beim Umgang mit `finally` ist zu glauben, dass der Code im `finally`-Block nicht ausgeführt wird, wenn eine Ausnahme im `try`-Block auftritt. Tatsächlich wird der `finally`-Block immer ausgeführt, es sei denn, die Anwendung wird abrupt beendet oder der Prozess stürzt ab. Eine weitere häufige Fallstrick ist das unzureichende Handling von Nullwerten im `finally`-Block, was zu zusätzlichen Ausnahmen führen kann, wenn auf nicht initialisierte Ressourcen zugegriffen wird.

## Einzeilensummary
Das `finally`-Schlüsselwort in C# garantiert die Ausführung eines Codeblocks zur Aufräumung von Ressourcen, unabhängig davon, ob im `try`-Block eine Ausnahme auftritt oder nicht.