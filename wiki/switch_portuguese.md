<!--
Meta Description: # Comando Switch em C#: Entenda e Aprenda a Usá-lo de Forma Eficiente ## Sinopse O comando `switch` em C# é uma estrutura de controle que permite sele...
Meta Keywords: switch, uma, break, código, expressão
-->

# Comando Switch em C#: Entenda e Aprenda a Usá-lo de Forma Eficiente

## Sinopse
O comando `switch` em C# é uma estrutura de controle que permite selecionar uma execução de bloco de código com base no valor de uma expressão. Ele é uma alternativa mais legível e organizada ao uso de múltiplos condicionais `if`.

## Documentação
O `switch` é utilizado para testar uma expressão contra uma série de valores possíveis, chamados de "casos". Quando o valor da expressão corresponde a um dos casos, o bloco de código associado é executado.

### Estrutura Básica
A estrutura básica de um `switch` em C# é a seguinte:

```csharp
switch (expressão)
{
    case valor1:
        // Código a ser executado se expressão == valor1
        break;
    case valor2:
        // Código a ser executado se expressão == valor2
        break;
    default:
        // Código a ser executado se nenhum caso for correspondido
        break;
}
```

### Propósito e Uso
- **Organização**: O `switch` melhora a legibilidade do código ao evitar múltiplos `if` aninhados.
- **Eficiência**: Pode ser mais eficiente em termos de desempenho em comparação com vários `if` quando há muitos casos a serem testados.

### Detalhes
- O `switch` pode usar tipos primitivos como `int`, `char`, `string`, e também tipos enumerados.
- O uso da palavra-chave `break` é crucial, pois impede que a execução "caia" no próximo caso. Se não for utilizado, o controle continuará a executar o próximo bloco de código até encontrar um `break` ou o final do `switch`.
- O bloco `default` é opcional e é executado se nenhum dos casos for atendido.

## Exemplos

### Exemplo 1: Uso Básico com Inteiros
```csharp
int dia = 3;

switch (dia)
{
    case 1:
        Console.WriteLine("Domingo");
        break;
    case 2:
        Console.WriteLine("Segunda-feira");
        break;
    case 3:
        Console.WriteLine("Terça-feira");
        break;
    default:
        Console.WriteLine("Dia inválido");
        break;
}
```

### Exemplo 2: Uso com Strings
```csharp
string fruta = "maçã";

switch (fruta)
{
    case "banana":
        Console.WriteLine("Você escolheu uma banana.");
        break;
    case "maçã":
        Console.WriteLine("Você escolheu uma maçã.");
        break;
    default:
        Console.WriteLine("Fruta desconhecida.");
        break;
}
```

## Explicação
Um erro comum ao usar `switch` é esquecer o `break`, o que pode levar a uma execução indesejada de múltiplos casos (chamado de "fall-through"). Além disso, o `switch` não permite a avaliação de expressões complexas diretamente nos casos; cada caso deve ser um valor constante.

Outra observação importante é que, a partir do C# 8.0, o `switch` também suporta a expressão `switch` que pode simplificar ainda mais a sintaxe.

## Resumo em Uma Linha
O comando `switch` em C# é uma estrutura de controle que permite a execução de blocos de código com base no valor de uma expressão, oferecendo uma alternativa mais clara aos condicionais `if`.