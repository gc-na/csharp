<!--
Meta Description: # CSharp "sizeof": Größe von Datentypen bestimmen ## Synopsis Der `sizeof`-Operator in CSharp ist ein Schlüsselwort, das die Größe eines Datentyps in ...
Meta Keywords: sizeof, die, größe, der, ist
-->

# CSharp "sizeof": Größe von Datentypen bestimmen

## Synopsis
Der `sizeof`-Operator in CSharp ist ein Schlüsselwort, das die Größe eines Datentyps in Bytes zur Compile-Zeit bestimmt. Es wird häufig verwendet, um die Speichergröße von Werttypen zu ermitteln, und ist besonders nützlich in der Systemprogrammierung und beim Arbeiten mit unmanaged Code.

## Dokumentation
Der `sizeof`-Operator gibt die Größe eines Datentyps zurück, die zur Compile-Zeit bekannt ist. Dieser Operator kann nur mit bestimmten Datentypen verwendet werden, hauptsächlich mit Werttypen wie `int`, `float`, `double`, `structs` und `enum`. Für Referenztypen (z. B. Klassen) gibt `sizeof` nicht die Größe des Objekts zurück, sondern nur die Größe der Referenz.

### Verwendung
Um `sizeof` zu verwenden, schreiben Sie einfach `sizeof(Typ)`, wobei `Typ` der Datentyp ist, dessen Größe Sie ermitteln möchten. Beachten Sie, dass der `sizeof`-Operator nur mit statisch bekannten Typen funktioniert, wodurch er in unsafe Kontexten nützlich ist.

### Details
- **Syntax**: `sizeof(Typ)`
- **Rückgabewert**: Ein `int`, der die Größe des angegebenen Typs in Bytes darstellt.
- **Einschränkungen**: 
  - Funktioniert nicht mit generischen Typen (außer wenn sie in einem `unsafe`-Block verwendet werden).
  - Kann nicht auf Referenztypen angewendet werden.

## Beispiele
### Beispiel 1: Größe eines primitiven Datentyps
```csharp
int sizeOfInt = sizeof(int); // Gibt 4 zurück
```

### Beispiel 2: Größe eines Structs
```csharp
struct MyStruct {
    public int a;
    public double b;
}

int sizeOfMyStruct = sizeof(MyStruct); // Gibt 16 zurück
```

### Beispiel 3: Größe eines Enums
```csharp
enum MyEnum : byte {
    Value1,
    Value2
}

int sizeOfEnum = sizeof(MyEnum); // Gibt 1 zurück
```

## Erklärung
Ein häufiger Fallstrick bei der Verwendung von `sizeof` ist die Annahme, dass es auch für Referenztypen funktioniert. Tatsächlich gibt `sizeof` nur die Größe der Referenz zurück, nicht die Größe des gesamten Objekts, auf das verwiesen wird. Wenn Sie die Größe eines Objekts zur Laufzeit bestimmen möchten, sollten Sie stattdessen die `Marshal.SizeOf`-Methode verwenden.

Ein weiterer Punkt ist, dass `sizeof` in einem `unsafe`-Kontext verwendet werden kann, um die Größe von benutzerdefinierten oder generischen Typen zu bestimmen. Hierbei müssen Sie jedoch sicherstellen, dass die Verwendung des `unsafe`-Konzepts in Ihrer Anwendung gerechtfertigt ist.

## Einzeilige Zusammenfassung
Der `sizeof`-Operator in CSharp ermittelt die Größe von Werttypen zur Compile-Zeit und ist ein wichtiges Werkzeug für die Speicherverwaltung in der Programmierung.