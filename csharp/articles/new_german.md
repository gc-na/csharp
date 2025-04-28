<!--
Meta Description: # Das Schlüsselwort "new" in C#: Eine umfassende Anleitung ## Synopsis Das Schlüsselwort "new" in C# wird verwendet, um neue Instanzen von Objekten zu...
Meta Keywords: new, sie, public, das, schlüsselwort
-->

# Das Schlüsselwort "new" in C#: Eine umfassende Anleitung

## Synopsis
Das Schlüsselwort "new" in C# wird verwendet, um neue Instanzen von Objekten zu erstellen und kann auch zur Überlagerung von Membern in abgeleiteten Klassen eingesetzt werden. Dieses Schlüsselwort ist ein grundlegendes Element der objektorientierten Programmierung in C#.

## Dokumentation
Das "new"-Schlüsselwort spielt eine zentrale Rolle in der Programmierung mit C#. Es wird hauptsächlich in zwei Kontexten verwendet:

1. **Objekterstellung**: Mit "new" können Sie neue Instanzen von Klassen oder Strukturen erzeugen. Dies ist der häufigste Anwendungsfall und ermöglicht es Entwicklern, Objekte zu initialisieren und deren Konstruktoren aufzurufen.

   ```csharp
   MyClass obj = new MyClass();
   ```

2. **Member-Überlagerung**: Wenn Sie eine abgeleitete Klasse erstellen, können Sie das "new"-Schlüsselwort verwenden, um einen Member der Basisklasse zu überlagern. Dies ist nützlich, wenn Sie das Verhalten eines geerbten Members ändern möchten.

   ```csharp
   public class BaseClass
   {
       public void Display()
       {
           Console.WriteLine("BaseClass Display");
       }
   }

   public class DerivedClass : BaseClass
   {
       public new void Display()
       {
           Console.WriteLine("DerivedClass Display");
       }
   }
   ```

## Beispiele
### Beispiel 1: Objekterstellung

```csharp
public class Person
{
    public string Name { get; set; }

    public Person(string name)
    {
        Name = name;
    }
}

Person person = new Person("Max Mustermann");
Console.WriteLine(person.Name); // Ausgabe: Max Mustermann
```

### Beispiel 2: Member-Überlagerung

```csharp
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public new void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

Animal myDog = new Dog();
myDog.Speak(); // Ausgabe: Animal speaks
```

Um die überlagerte Methode korrekt aufzurufen, muss der Typ der Referenz auf `Dog` gesetzt werden:

```csharp
Dog myDog = new Dog();
myDog.Speak(); // Ausgabe: Dog barks
```

## Erklärung
Ein häufiges Problem beim Einsatz des "new"-Schlüsselworts ist die Verwirrung zwischen Überlagerung und Überschreibung. Wenn Sie "new" verwenden, wird die Methode in der Basisklasse nicht ersetzt, sondern bleibt weiterhin zugänglich. Dies kann zu unerwartetem Verhalten führen, wenn Sie mit polymorphen Objekten arbeiten. Verwenden Sie `virtual` und `override`, wenn Sie beabsichtigen, das Verhalten einer Methode in einer abgeleiteten Klasse wirklich zu ändern.

Zusätzlich sollten Sie beachten, dass das "new"-Schlüsselwort nicht in allen Kontexten erforderlich ist. Wenn Sie nicht beabsichtigen, eine Member-Überlagerung durchzuführen, können Sie einfach die Basisklasse verwenden.

## Einzeilensummary
Das Schlüsselwort "new" in C# wird verwendet, um neue Objekte zu erstellen und Mitgliedsüberlagerungen in abgeleiteten Klassen zu definieren.