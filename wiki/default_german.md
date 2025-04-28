<!--
Meta Description: # C# "default" Schlüsselwort: Verwendung und Bedeutung ## Synopsis Das Schlüsselwort "default" in C# wird verwendet, um den Standardwert eines Datenty...
Meta Keywords: default, ist, standardwert, verwendet, kann
-->

# C# "default" Schlüsselwort: Verwendung und Bedeutung

## Synopsis
Das Schlüsselwort "default" in C# wird verwendet, um den Standardwert eines Datentyps zu erhalten. Es ist besonders nützlich bei generischen Typen und kann in verschiedenen Kontexten eingesetzt werden.

## Dokumentation
In C# ist "default" ein Schlüsselwort, das den Standardwert eines Typs zurückgibt. Der Standardwert variiert je nach Datentyp:

- **Werttypen** wie `int`, `double` oder `bool` haben Standardwerte von `0`, `0.0` und `false` respektive.
- **Referenztypen** wie Klassen und Arrays haben den Standardwert `null`.
- Bei generischen Typen wird der Standardwert des Typs zurückgegeben, der zur Laufzeit verwendet wird.

### Verwendung
Das "default"-Schlüsselwort kann in folgenden Kontexten verwendet werden:

1. **Generische Programmierung**: Wenn Sie mit generischen Typen arbeiten, können Sie mit `default(T)` den Standardwert des Typs `T` zurückgeben.
2. **Switch-Anweisungen**: In `switch`-Anweisungen kann "default" als Standardfall verwendet werden, wenn keine anderen Fälle erfüllt sind.
3. **Initialisierung**: Es kann verwendet werden, um Variablen mit ihren Standardwerten zu initialisieren.

### Syntax
```csharp
T defaultValue = default(T);
```

## Beispiele

### Beispiel 1: Standardwert eines Werttyps
```csharp
int standardInt = default(int); // standardInt ist 0
```

### Beispiel 2: Standardwert eines Referenztyps
```csharp
string standardString = default(string); // standardString ist null
```

### Beispiel 3: Verwendung in generischen Methoden
```csharp
public T GetDefault<T>()
{
    return default(T);
}

// Verwendung
int defaultInt = GetDefault<int>(); // defaultInt ist 0
string defaultString = GetDefault<string>(); // defaultString ist null
```

## Erklärung
Ein häufiger Stolperstein ist die Annahme, dass `default` nur bei Werttypen nützlich ist. Tatsächlich kann es auch bei Referenztypen verwendet werden, um `null` zu erhalten. Bei der Verwendung von `default` in generischen Typen kann es zu Verwirrung kommen, wenn der Benutzer nicht weiß, welcher Typ zur Laufzeit verwendet wird. In solchen Fällen ist es ratsam, die Typen genau zu prüfen, um unerwartete Ergebnisse zu vermeiden.

Zusätzlich kann das Missverständnis aufkommen, dass `default` immer 0 oder `null` zurückgibt, während es tatsächlich von dem spezifischen Typ abhängt. 

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "default" in C# gibt den Standardwert eines Datentyps zurück und ist besonders nützlich in generischen Kontexten.