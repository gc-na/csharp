<!--
Meta Description: # foreach em C#: Iterando Estruturas de Dados com Eficiência ## Sinopse O comando `foreach` em C# é uma estrutura de controle que permite iterar sobre...
Meta Keywords: foreach, uma, coleção, sobre, que
-->

# foreach em C#: Iterando Estruturas de Dados com Eficiência

## Sinopse
O comando `foreach` em C# é uma estrutura de controle que permite iterar sobre coleções de dados, como arrays e listas, de maneira simples e legível. Ele é amplamente utilizado para percorrer elementos sem a necessidade de um índice explícito.

## Documentação
O `foreach` é uma das principais construções de loop em C#. Seu propósito é facilitar a iteração sobre elementos em coleções que implementam a interface `IEnumerable`, como arrays, listas, dicionários e muitos outros tipos de coleções. 

### Uso Básico
A sintaxe do `foreach` é a seguinte:

```csharp
foreach (tipo elemento in coleção)
{
    // Código a ser executado para cada elemento
}
```

- **tipo**: O tipo de dado dos elementos na coleção.
- **elemento**: Uma variável que representa o elemento atual da coleção durante cada iteração.
- **coleção**: A coleção que está sendo percorrida.

### Detalhes
- O `foreach` não permite modificar a coleção durante a iteração. Tentar fazê-lo resultará em uma exceção em tempo de execução.
- O `foreach` é particularmente útil para coleções que implementam `IEnumerable`, pois permite um acesso sequencial aos elementos sem expor a lógica interna da coleção.

## Exemplos

### Exemplo 1: Iterando sobre um Array
```csharp
string[] frutas = { "Maçã", "Banana", "Laranja" };

foreach (string fruta in frutas)
{
    Console.WriteLine(fruta);
}
```

### Exemplo 2: Iterando sobre uma Lista
```csharp
List<int> numeros = new List<int> { 1, 2, 3, 4, 5 };

foreach (int numero in numeros)
{
    Console.WriteLine(numero * 2);
}
```

### Exemplo 3: Iterando sobre um Dicionário
```csharp
Dictionary<string, int> idade = new Dictionary<string, int>
{
    { "Ana", 25 },
    { "Bruno", 30 },
    { "Carlos", 35 }
};

foreach (var par in idade)
{
    Console.WriteLine($"{par.Key}: {par.Value} anos");
}
```

## Explicação
Embora o `foreach` seja uma ferramenta poderosa, existem algumas armadilhas comuns:

1. **Imutabilidade durante a iteração**: Não é possível modificar a coleção enquanto se itera sobre ela. Tentar adicionar ou remover elementos resultará em uma `InvalidOperationException`.
   
2. **Tipos de dados**: O tipo do elemento no `foreach` deve corresponder ao tipo dos elementos da coleção. Um tipo incompatível resultará em erros de compilação.

3. **Desempenho**: Em algumas coleções, como listas ligadas, o `foreach` pode apresentar desempenho inferior em comparação com loops `for` tradicionais, especialmente quando o acesso aleatório é necessário.

## Resumo em Uma Linha
O `foreach` em C# é uma estrutura de controle que simplifica a iteração sobre coleções, promovendo um código mais limpo e legível.