<!--
Meta Description: # Decimal em C#: O Que Você Precisa Saber ## Sinopse O tipo de dado `decimal` em C# é uma opção de alta precisão ideal para representar valores monetá...
Meta Keywords: decimal, que, precisão, para, tipo
-->

# Decimal em C#: O Que Você Precisa Saber

## Sinopse
O tipo de dado `decimal` em C# é uma opção de alta precisão ideal para representar valores monetários e cálculos financeiros, onde a precisão é crucial.

## Documentação
O `decimal` é um tipo de dado numérico em C# que permite a representação de números de ponto fixo com uma precisão alta. Ele é especialmente útil em aplicações financeiras e científicas onde a precisão é vital. O tipo `decimal` fornece uma representação de até 28-29 dígitos significativos e é armazenado como um inteiro de 128 bits, o que evita erros de arredondamento que podem ocorrer com outros tipos numéricos.

### Uso
Para declarar uma variável do tipo `decimal`, você pode usar a seguinte sintaxe:
```csharp
decimal valor = 10.5m;
```
Note que o sufixo `m` é necessário para indicar que o número é do tipo `decimal`. Sem ele, o compilador interpretará o número como um `double`, o que pode resultar em perda de precisão.

### Detalhes
- **Intervalo**: O intervalo de valores que um `decimal` pode armazenar vai de -79,228,162,514,264,337,593,543,950,335 a 79,228,162,514,264,337,593,543,950,335.
- **Precisão**: O tipo `decimal` tem uma precisão de 28-29 dígitos significativos.
- **Arredondamento**: O `decimal` evita erros de arredondamento que ocorrem frequentemente com tipos de ponto flutuante, tornando-o mais apropriado para cálculos financeiros.

## Exemplos
### Declaração e Atribuição
```csharp
decimal preco = 19.99m;
decimal desconto = 0.15m;
decimal precoFinal = preco - (preco * desconto);
Console.WriteLine(precoFinal); // Saída: 16.99
```

### Operações Matemáticas
```csharp
decimal produto1 = 10.00m;
decimal produto2 = 20.50m;
decimal total = produto1 + produto2;
Console.WriteLine(total); // Saída: 30.50
```

### Comparação
```csharp
decimal a = 0.1m;
decimal b = 0.1m;
bool iguais = (a == b);
Console.WriteLine(iguais); // Saída: True
```

## Explicação
Embora o `decimal` seja uma excelente escolha para operações financeiras, existem alguns pontos a serem observados:

1. **Desempenho**: O `decimal` é mais lento que os tipos `int` ou `double` devido à sua complexidade de armazenamento e à precisão que fornece. Para cálculos que não exigem alta precisão, considere usar tipos inteiros ou `double`.

2. **Sufixo 'm'**: Sempre lembre-se de usar o sufixo `m` ao declarar literais `decimal`. O esquecimento deste sufixo resultará em um erro de compilação.

3. **Conversão**: Ao converter entre tipos, esteja ciente das possíveis perdas de precisão. Evite converter de `double` para `decimal` sem considerar o risco de arredondamento.

## Resumo em Uma Frase
O tipo `decimal` em C# é ideal para cálculos financeiros, proporcionando alta precisão e evitando erros de arredondamento comuns em outros tipos numéricos.