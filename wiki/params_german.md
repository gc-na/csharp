<!--
Meta Description: # params in CSharp: Flexibles Arbeiten mit variablen Argumenten ## Synopsis In CSharp (C#) ermöglicht das Schlüsselwort `params` die Übergabe einer va...
Meta Keywords: params, der, die, von, methode
-->

# params in CSharp: Flexibles Arbeiten mit variablen Argumenten

## Synopsis
In CSharp (C#) ermöglicht das Schlüsselwort `params` die Übergabe einer variablen Anzahl von Argumenten an eine Methode. Diese Funktion erleichtert die Verarbeitung von Listen oder Arrays von Werten, ohne dass der Entwickler die Anzahl der Argumente im Voraus festlegen muss.

## Dokumentation
Das `params`-Schlüsselwort wird in der Methodendeklaration verwendet, um anzugeben, dass die Methode eine beliebige Anzahl von Argumenten eines bestimmten Typs akzeptieren kann. Es muss das letzte Parameter einer Methode sein und kann nur einmal pro Methode verwendet werden.

### Zweck
Der Hauptzweck von `params` ist die Vereinfachung der Methodendeklaration und -nutzung, insbesondere wenn eine Methode mit einer variablen Anzahl von Eingabewerten aufgerufen wird. Dies ist besonders nützlich in Situationen, in denen die Anzahl der Argumente nicht bekannt ist oder variieren kann.

### Verwendung
Um `params` zu verwenden, geben Sie es vor dem Arraytyp in der Methodendeklaration an. Hier ist die grundlegende Syntax:

```csharp
public void MethodeName(params Datentyp[] parameterName)
```

### Details
- **Typ:** Der Typ des `params`-Parameters muss ein Arraytyp sein.
- **Anzahl der Argumente:** Sie können null, ein oder mehrere Argumente übergeben.
- **Argumente:** Wenn Sie beim Aufruf der Methode keine Argumente übergeben, wird ein leeres Array erzeugt.

## Beispiele
### Beispiel 1: Einfache Verwendung von `params`
```csharp
public void AusgabeNamen(params string[] namen)
{
    foreach (string name in namen)
    {
        Console.WriteLine(name);
    }
}

// Aufruf der Methode
AusgabeNamen("Anna", "Bernd", "Clara");
```

### Beispiel 2: Nutzung ohne Argumente
```csharp
public void AusgabeZahlen(params int[] zahlen)
{
    if (zahlen.Length == 0)
    {
        Console.WriteLine("Keine Zahlen übergeben.");
    }
    else
    {
        foreach (int zahl in zahlen)
        {
            Console.WriteLine(zahl);
        }
    }
}

// Aufruf der Methode ohne Argumente
AusgabeZahlen();
```

## Erklärung
### Häufige Fallstricke und Anmerkungen
- **Nur ein `params`-Parameter:** Eine Methode kann nur einen `params`-Parameter haben, und dieser muss der letzte Parameter in der Methodendeklaration sein.
- **Typen:** Wenn Sie mehrere Parameter definieren möchten, die nicht vom Typ `params` sind, muss der `params`-Parameter vom Typ des letzten Parameters sein.
- **Typensicherheit:** `params` ermöglicht nur die Übergabe von Argumenten des angegebenen Typs. Es ist nicht möglich, Argumente eines anderen Typs zu übergeben, es sei denn, sie sind implizit konvertierbar.

## Ein Satz Zusammenfassung
Das `params`-Schlüsselwort in CSharp ermöglicht das einfache Arbeiten mit einer variablen Anzahl von Argumenten in Methoden, was die Flexibilität und Lesbarkeit des Codes erhöht.