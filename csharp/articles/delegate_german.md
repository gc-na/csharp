<!--
Meta Description: # Delegates in C#: Eine umfassende Anleitung ## Synopsis Delegates sind ein zentraler Bestandteil der C#-Programmierung, die es Entwicklern ermögliche...
Meta Keywords: delegates, die, public, delegate, methoden
-->

# Delegates in C#: Eine umfassende Anleitung

## Synopsis
Delegates sind ein zentraler Bestandteil der C#-Programmierung, die es Entwicklern ermöglichen, Methoden als Parameter zu übergeben und die Funktionalität von Anwendungen durch Callback-Mechanismen zu erweitern.

## Dokumentation
In C# sind Delegates Typen, die Referenzen auf Methoden speichern. Sie sind ähnlich wie Zeiger auf Funktionen in anderen Programmiersprachen, bieten jedoch zusätzliche Sicherheit. Delegates werden häufig für Ereignisse und Callback-Methoden verwendet.

### Zweck
Der Hauptzweck von Delegates besteht darin, die Flexibilität und Wiederverwendbarkeit des Codes zu erhöhen, indem sie es ermöglichen, Methoden dynamisch auszuwählen und auszuführen. Dies ist besonders nützlich in Szenarien wie Ereignisbehandlung oder asynchronen Programmierung.

### Verwendung
Ein Delegate wird definiert, indem der `delegate`-Schlüsselwort gefolgt von einem Rückgabetyp und einer Methodensignatur verwendet wird. Delegates können Instanzen von Methoden zugewiesen werden, die mit der definierten Signatur übereinstimmen.

#### Beispiel einer Delegate-Deklaration:
```csharp
public delegate void MyDelegate(string message);
```

Um einen Delegate zu verwenden, müssen Sie eine Instanz des Delegates erstellen und eine Methode zuweisen, die der Signatur entspricht:

```csharp
MyDelegate del = new MyDelegate(MyMethod);
del("Hallo Welt!");
```

### Details
Delegates können mehr als eine Methode gleichzeitig aufrufen, indem Sie Multicast-Delegates verwenden. Diese Delegates sind eine Sammlung von Delegates, die in einer Kette ausgeführt werden.

### Multicast-Delegate Beispiel:
```csharp
public delegate void MyMultiDelegate(string message);
public static void Method1(string msg) { Console.WriteLine("Method1: " + msg); }
public static void Method2(string msg) { Console.WriteLine("Method2: " + msg); }

MyMultiDelegate del = Method1;
del += Method2; // Hinzufügen einer weiteren Methode
del("Hallo Multicast!");
```

## Beispiele
### Einfaches Delegate Beispiel
```csharp
public delegate int MathOperation(int x, int y);

public class Program
{
    public static int Add(int a, int b) => a + b;

    public static void Main()
    {
        MathOperation operation = new MathOperation(Add);
        int result = operation(5, 3);
        Console.WriteLine(result); // Ausgabe: 8
    }
}
```

### Verwendung mit Ereignissen
```csharp
public class Button
{
    public delegate void ClickHandler();
    public event ClickHandler Click;

    public void OnClick()
    {
        Click?.Invoke();
    }
}

public class Program
{
    public static void Main()
    {
        Button button = new Button();
        button.Click += () => Console.WriteLine("Button wurde geklickt!");
        button.OnClick(); // Ausgabe: Button wurde geklickt!
    }
}
```

## Erklärung
Ein häufiges Missverständnis bei Delegates ist, dass sie nur für Ereignisse verwendet werden können. Delegates sind vielseitig und können überall dort eingesetzt werden, wo eine Funktion als Parameter benötigt wird. Ein weiteres wichtiges Konzept ist die Verwendung von `null`-Prüfungen, bevor ein Delegate aufgerufen wird, um Nullreferenz-Ausnahmen zu vermeiden.

### Häufige Fallstricke:
- **Unzureichende Signaturübereinstimmung**: Stellen Sie sicher, dass die Methoden, die einem Delegate zugewiesen werden, die gleiche Signatur aufweisen.
- **Multicast-Delegates**: Wenn mehrere Methoden an einen Multicast-Delegate angehängt sind, wird die Rückgabewerte der Methoden nicht aggregiert, sondern nur die letzte Methode wird zurückgegeben.

## Einzeiliges Fazit
Delegates in C# sind mächtige Typen, die es Entwicklern ermöglichen, Methoden flexibel zu verwalten und die Struktur von Anwendungen durch Callback-Mechanismen zu verbessern.