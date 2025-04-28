<!--
Meta Description: # Die Verwendung von "base" in C# ## Synopsis In C# wird das Schlüsselwort "base" verwendet, um auf Mitglieder der Basisklasse zuzugreifen, insbesonde...
Meta Keywords: der, public, base, basisklasse, auf
-->

# Die Verwendung von "base" in C#

## Synopsis
In C# wird das Schlüsselwort "base" verwendet, um auf Mitglieder der Basisklasse zuzugreifen, insbesondere in abgeleiteten Klassen. Es ermöglicht Entwicklern, Konstruktoren, Methoden oder Eigenschaften der übergeordneten Klasse zu verwenden oder zu überschreiben.

## Dokumentation
Das Schlüsselwort "base" spielt eine zentrale Rolle in der objektorientierten Programmierung in C#. Es wird in der Regel in abgeleiteten Klassen verwendet, um auf Mitglieder der Basisklasse zuzugreifen. Dies kann besonders nützlich sein, wenn ein Entwickler die Funktionalität einer Basisklasse erweitern oder ändern möchte.

### Zweck
- **Zugriff auf Basisklassenmitglieder**: Ermöglicht den Zugriff auf Methoden, Eigenschaften oder Konstruktoren der Basisklasse.
- **Konstruktoren aufrufen**: Ermöglicht das Aufrufen des Konstruktors der Basisklasse, um sicherzustellen, dass die Basisklasse ordnungsgemäß initialisiert wird.

### Verwendung
Das Schlüsselwort "base" kann in verschiedenen Kontexten verwendet werden:
1. **Aufruf von Basisklassenkonstruktoren**:
   ```csharp
   public class BaseClass
   {
       public BaseClass(int value)
       {
           // Initialisierungscode
       }
   }

   public class DerivedClass : BaseClass
   {
       public DerivedClass(int value) : base(value)
       {
           // Zusätzlicher Initialisierungscode
       }
   }
   ```

2. **Zugriff auf Basisklassenmethoden**:
   ```csharp
   public class BaseClass
   {
       public virtual void Display()
       {
           Console.WriteLine("BaseClass Display");
       }
   }

   public class DerivedClass : BaseClass
   {
       public override void Display()
       {
           base.Display(); // Aufruf der Methode der Basisklasse
           Console.WriteLine("DerivedClass Display");
       }
   }
   ```

## Beispiele
Hier sind einige einfache Beispiele zur Veranschaulichung der Verwendung von "base":

### Beispiel 1: Zugriff auf Basisklassenkonstruktor
```csharp
public class Animal
{
    public Animal(string name)
    {
        Console.WriteLine($"Animal Name: {name}");
    }
}

public class Dog : Animal
{
    public Dog(string name) : base(name)
    {
        Console.WriteLine("Dog created");
    }
}

// Verwendung
Dog myDog = new Dog("Buddy");
```

### Beispiel 2: Überschreiben einer Methode
```csharp
public class Shape
{
    public virtual void Draw()
    {
        Console.WriteLine("Drawing a shape");
    }
}

public class Circle : Shape
{
    public override void Draw()
    {
        base.Draw(); // Aufruf der Methode in der Basisklasse
        Console.WriteLine("Drawing a circle");
    }
}

// Verwendung
Circle myCircle = new Circle();
myCircle.Draw();
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von "base" ist, dass es nur für Konstruktoren verwendet werden kann. Tatsächlich kann "base" in jedem Kontext verwendet werden, in dem Sie auf Mitglieder der Basisklasse zugreifen möchten. Ein weiteres häufiges Problem ist die Verwendung von "base" in einer statischen Methode. Da "base" eine Instanz der Klasse benötigt, ist es in statischen Kontexten nicht anwendbar.

Zusätzlich ist zu beachten, dass, wenn eine Methode in einer abgeleiteten Klasse nicht überschrieben wird, der Zugriff auf die Methode der Basisklasse einfach ohne "base" erfolgen kann.

## Ein Satz Zusammenfassung
Das Schlüsselwort "base" in C# ermöglicht den Zugriff auf Mitglieder der Basisklasse und ist entscheidend für die Implementierung von Vererbung.