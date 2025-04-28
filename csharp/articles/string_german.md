<!--
Meta Description: # C# String: Eine umfassende Anleitung zu Strings in C# ## Synopsis In C# ist `string` ein grundlegender Datentyp, der verwendet wird, um Textdaten zu...
Meta Keywords: string, strings, csharp, ist, ein
-->

# C# String: Eine umfassende Anleitung zu Strings in C#

## Synopsis
In C# ist `string` ein grundlegender Datentyp, der verwendet wird, um Textdaten zu speichern und zu verarbeiten. Strings sind unveränderlich und bieten eine Vielzahl von Methoden zur Manipulation von Text.

## Dokumentation
### Zweck
Der `string`-Datentyp in C# repräsentiert eine Sequenz von Unicode-Zeichen. Strings sind unveränderlich, was bedeutet, dass einmal erstellte Strings nicht mehr verändert werden können. Jede Modifikation an einem String führt zur Erzeugung eines neuen String-Objekts.

### Verwendung
Strings werden häufig in der Programmierung verwendet, um Text darzustellen, Eingaben vom Benutzer zu verarbeiten oder Daten aus Dateien und Datenbanken zu lesen. In C# können Strings durch einfache Zuweisung erstellt werden:

```csharp
string meinText = "Hallo, Welt!";
```

### Details
- **Unveränderlichkeit**: Wenn Sie einen String ändern, wird ein neuer String erstellt. Dies kann Auswirkungen auf die Leistung haben, wenn viele Änderungen vorgenommen werden.
- **Interpolierte Strings**: C# unterstützt interpolierte Strings, was die Einfügung von Variablen in Strings erleichtert:

```csharp
string name = "Max";
string begruessung = $"Hallo, {name}!";
```

- **String-Methoden**: C# bietet eine Vielzahl von eingängigen Methoden zur Arbeit mit Strings, z.B. `Length`, `Substring`, `IndexOf`, `ToUpper`, `ToLower`, und viele mehr.

## Beispiele
### Einfaches Beispiel
```csharp
string text = "Hallo, Welt!";
Console.WriteLine(text);
```

### Interpolation und Formatierung
```csharp
string vorname = "Max";
string nachname = "Mustermann";
string vollstaendigerName = $"{vorname} {nachname}";
Console.WriteLine(vollstaendigerName);
```

### String-Manipulation
```csharp
string original = "CSharp ist toll!";
string subString = original.Substring(0, 6); // "CSharp"
string upperCase = original.ToUpper(); // "CSHARP IST TOLL!"
```

## Erklärung
### Häufige Fallstricke
- **Unveränderlichkeit**: Da Strings unveränderlich sind, kann das häufige Erstellen neuer Strings zu einer erhöhten Speicherlast führen. Es wird empfohlen, `StringBuilder` zu verwenden, wenn viele Modifikationen an einem String erforderlich sind.
  
- **Null-Referenzen**: Ein nicht initialisierter String kann `null` sein, was zu einer `NullReferenceException` führen kann, wenn Sie versuchen, darauf zuzugreifen. Überprüfen Sie immer, ob ein String `null` ist, bevor Sie darauf zugreifen.

- **Leere Strings vs. null**: Ein leerer String (`""`) ist nicht dasselbe wie `null`. Es ist wichtig, den Unterschied zu kennen, um unerwartete Fehler zu vermeiden.

## Ein-Satz-Zusammenfassung
In C# ist `string` ein unveränderlicher Datentyp zur Speicherung und Verarbeitung von Text, der eine Vielzahl nützlicher Methoden zur Manipulation von Zeichenfolgen bietet.