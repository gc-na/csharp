<!--
Meta Description: # Verwendung des Schlüsselworts "explicit" in C# ## Synopsis Das Schlüsselwort "explicit" in C# wird verwendet, um eine explizite Typumwandlung zu ken...
Meta Keywords: explicit, die, der, temperature, public
-->

# Verwendung des Schlüsselworts "explicit" in C#

## Synopsis
Das Schlüsselwort "explicit" in C# wird verwendet, um eine explizite Typumwandlung zu kennzeichnen. Es ermöglicht Entwicklern, benutzerdefinierte Konvertierungsoperatoren zu definieren, die eine klarere und sicherere Typumwandlung zwischen benutzerdefinierten Datentypen ermöglichen.

## Dokumentation
Das Schlüsselwort "explicit" wird in C# genutzt, um einen Konvertierungsoperator zu erstellen, der eine Typumwandlung von einem Typ zu einem anderen durchführt. Solche Konvertierungsoperatoren sind nützlich, wenn eine automatische Umwandlung zwischen Typen nicht sicher ist und der Entwickler die Verantwortung für die Umwandlung übernehmen möchte. 

### Zweck
Das Hauptziel von "explicit" ist es, sicherzustellen, dass der Entwickler die Typumwandlung absichtlich vornimmt, wodurch potenzielle Laufzeitfehler vermieden werden, die bei einer impliziten Umwandlung auftreten könnten.

### Verwendung
Um einen expliziten Konvertierungsoperator zu definieren, wird das Schlüsselwort "explicit" vor der Definition des Operators verwendet. Dieser Operator kann dann in einer Konvertierung zwischen benutzerdefinierten Typen aufgerufen werden.

### Details
- Ein expliziter Konvertierungsoperator kann nur dann verwendet werden, wenn der Entwickler den Typ sicher umwandeln kann.
- Der Operator muss in einer Klasse oder Struktur definiert werden und kann nur für den aktuellen Typ oder einen anderen benutzerdefinierten Typ verwendet werden.
- Der Aufruf des expliziten Konvertierungsoperators erfordert eine Cast-Operation.

## Beispiele
Hier sind einige einfache Beispiele zur Verwendung des "explicit"-Schlüsselworts:

```csharp
public class Fahrenheit
{
    public double Temperature { get; }

    public Fahrenheit(double temperature)
    {
        Temperature = temperature;
    }

    // Expliziter Konvertierungsoperator zu Celsius
    public static explicit operator Celsius(Fahrenheit f)
    {
        return new Celsius((f.Temperature - 32) * 5 / 9);
    }
}

public class Celsius
{
    public double Temperature { get; }

    public Celsius(double temperature)
    {
        Temperature = temperature;
    }
}

// Verwendung
Fahrenheit f = new Fahrenheit(100);
Celsius c = (Celsius)f; // Erfordert explizite Typumwandlung
```

## Erklärung
Ein häufiges Problem bei der Verwendung von "explicit" ist, dass Entwickler möglicherweise vergessen, die Cast-Operation durchzuführen, was zu einem Kompilierungsfehler führt. Es ist wichtig, sich daran zu erinnern, dass die Verwendung von "explicit" bedeutet, dass die Umwandlung nicht automatisch erfolgt. Zudem sollte darauf geachtet werden, dass die Implementierung des Konvertierungsoperators robust ist, um unerwartete Ergebnisse oder Fehler während der Laufzeit zu vermeiden.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "explicit" in C# ermöglicht eine sichere und kontrollierte Typumwandlung durch die Definition expliziter Konvertierungsoperatoren.