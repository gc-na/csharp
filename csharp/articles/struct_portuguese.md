<!--
Meta Description: # Estruturas em C#: Entenda o Uso de "struct" ## Sinopse As estruturas em C# (structs) são tipos de valor que permitem agrupar dados relacionados sob ...
Meta Keywords: uma, que, struct, structs, dados
-->

# Estruturas em C#: Entenda o Uso de "struct"

## Sinopse
As estruturas em C# (structs) são tipos de valor que permitem agrupar dados relacionados sob um mesmo tipo, proporcionando uma forma de organizar informações de maneira eficiente e intuitiva.

## Documentação
As `structs` em C# são tipos de dados que permitem a definição de um novo tipo composto por um conjunto de campos. Elas são especialmente úteis para agrupar dados que pertencem a uma única entidade e são frequentemente utilizadas para representar objetos simples ou dados que não requerem a complexidade de uma classe.

### Propósito
O propósito das `structs` é permitir a criação de tipos de dados personalizados que podem encapsular dados e comportamentos relacionados, oferecendo uma alternativa leve em comparação com as classes. Como tipos de valor, as structs são armazenadas na pilha (stack), enquanto as classes são armazenadas no heap.

### Uso
Para definir uma `struct`, utilizamos a palavra-chave `struct`, seguida pelo nome da estrutura e um bloco de código que contém os campos e métodos. A declaração de uma struct é similar à declaração de uma classe, mas com algumas diferenças importantes, principalmente em relação ao gerenciamento de memória e comportamento de cópia.

### Exemplo de Definição de uma Struct
```csharp
public struct Ponto
{
    public int X;
    public int Y;

    public Ponto(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void Mostrar()
    {
        Console.WriteLine($"Ponto: ({X}, {Y})");
    }
}
```

## Exemplos
### Exemplo de Uso Básico
```csharp
class Program
{
    static void Main()
    {
        Ponto ponto1 = new Ponto(5, 10);
        ponto1.Mostrar(); // Saída: Ponto: (5, 10)

        Ponto ponto2 = ponto1; // Cópia de ponto1
        ponto2.X = 20; // Modifica ponto2, não ponto1
        ponto1.Mostrar(); // Saída: Ponto: (5, 10)
        ponto2.Mostrar(); // Saída: Ponto: (20, 10)
    }
}
```

### Modificando Estruturas
```csharp
public struct Retangulo
{
    public int Largura;
    public int Altura;

    public int Area()
    {
        return Largura * Altura;
    }
}

class Program
{
    static void Main()
    {
        Retangulo ret = new Retangulo { Largura = 4, Altura = 5 };
        Console.WriteLine($"Área: {ret.Area()}"); // Saída: Área: 20
    }
}
```

## Explicação
### Armadilhas Comuns
- **Cópia de Valores**: Por serem tipos de valor, ao atribuir uma `struct` a outra, é feita uma cópia de todos os dados. Isso pode levar a um comportamento inesperado se você não perceber que alterações em uma instância não afetam a outra.
- **Imutabilidade**: Se você precisa de um comportamento semelhante ao de objetos imutáveis, deve implementar a `struct` de maneira a não permitir alterações após a criação.
- **Sem Herança**: `structs` não suportam herança, o que limita sua reutilização em hierarquias de tipos.

### Notas Adicionais
- As `structs` podem implementar interfaces, permitindo que você utilize polimorfismo, mas não podem herdar de outras `structs` ou classes.
- Utilize `structs` principalmente para dados pequenos que serão frequentemente copiados, como coordenadas ou pares de valores.

## Resumo em Uma Linha
As `structs` em C# são tipos de valor que agrupam dados relacionados, permitindo uma organização eficiente e intuitiva de informações.