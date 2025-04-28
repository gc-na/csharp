<!--
Meta Description: # UShort em C#: Entendendo o Tipo de Dado Integros de 16 Bits ## Sinopse O `ushort` em C# é um tipo de dado que representa um inteiro sem sinal de 16 ...
Meta Keywords: ushort, que, tipo, valores, uma
-->

# UShort em C#: Entendendo o Tipo de Dado Integros de 16 Bits

## Sinopse
O `ushort` em C# é um tipo de dado que representa um inteiro sem sinal de 16 bits, permitindo armazenar valores entre 0 e 65.535. É uma escolha útil para otimizar o uso de memória em aplicações que não requerem números negativos.

## Documentação
### O que é o `ushort`?
O `ushort` (abreviação de "unsigned short") é um tipo de dado primitivo em C# que armazena inteiros não negativos. Ele ocupa 2 bytes (16 bits) de memória e é ideal para situações onde apenas valores positivos são necessários.

### Uso do `ushort`
O `ushort` é frequentemente utilizado em cenários que envolvem contagem, índices de arrays, e outras operações que não requerem números negativos. 

#### Declaração e Inicialização
A declaração de uma variável do tipo `ushort` é feita da seguinte forma:

```csharp
ushort numero;
```

Você também pode inicializar uma variável no momento da declaração:

```csharp
ushort numero = 50000;
```

### Detalhes
- **Intervalo de Valores:** O `ushort` pode armazenar valores entre 0 e 65.535.
- **Conversão:** É possível realizar a conversão entre `ushort` e outros tipos de dados numéricos, mas deve-se ter cuidado com o intervalo para evitar exceções.
- **Operações:** O `ushort` suporta operações aritméticas, comparação e operações bit a bit, assim como outros tipos numéricos.

## Exemplos
### Exemplo 1: Declaração e Atribuição

```csharp
ushort idade = 25;
Console.WriteLine(idade); // Saída: 25
```

### Exemplo 2: Aritmética com `ushort`

```csharp
ushort a = 1000;
ushort b = 2000;
ushort soma = (ushort)(a + b);
Console.WriteLine(soma); // Saída: 3000
```

### Exemplo 3: Conversão de Tipos

```csharp
int numeroInt = 30000;
ushort numeroUshort = (ushort)numeroInt; // Conversão explícita
Console.WriteLine(numeroUshort); // Saída: 30000
```

## Explicação
### Armadilhas Comuns
- **Exceções de Overflow:** Uma operação que resulta em um número maior que 65.535 causará uma exceção de overflow em tempo de execução. É importante verificar os limites dos valores antes de realizar operações.
- **Conversão de Tipos:** Ao converter de um tipo maior para `ushort`, deve-se garantir que o valor está dentro do intervalo do `ushort` para evitar perda de dados.

### Notas Adicionais
- O uso do `ushort` pode ser vantajoso em aplicações de baixo consumo de memória, como em sistemas embarcados ou jogos, onde a eficiência é crítica.
- Em situações onde valores negativos podem ser necessários, considere o uso do tipo `short`, que é a versão com sinal de 16 bits.

## Resumo em Uma Linha
O `ushort` é um tipo de dado em C# que representa um inteiro sem sinal de 16 bits, ideal para armazenar valores entre 0 e 65.535.