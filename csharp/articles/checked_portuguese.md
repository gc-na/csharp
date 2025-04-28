<!--
Meta Description: # Comando "checked" em CSharp: Controle de Overflow em Operações Aritméticas ## Sinopse O comando "checked" em CSharp é utilizado para habilitar a ver...
Meta Keywords: checked, overflow, int, uma, csharp
-->

# Comando "checked" em CSharp: Controle de Overflow em Operações Aritméticas

## Sinopse
O comando "checked" em CSharp é utilizado para habilitar a verificação de estouro (overflow) em operações aritméticas, garantindo que os cálculos que excedem os limites dos tipos de dados sejam tratados de maneira adequada.

## Documentação
O "checked" é uma palavra-chave em CSharp que assegura que as operações aritméticas, como adição, subtração e multiplicação, sejam monitoradas para overflow. Quando o overflow ocorre dentro de um bloco "checked", uma exceção do tipo `OverflowException` é lançada, permitindo que o programador lide com a situação de forma controlada.

### Uso
A palavra-chave "checked" pode ser utilizada de duas formas:

1. **Bloco Checked:** Envolve um bloco de código onde todas as operações aritméticas são verificadas.
2. **Expressão Checked:** Aplica a verificação de overflow a uma única expressão.

### Exemplo de Sintaxe
```csharp
checked
{
    // Operações aritméticas com verificação de overflow
}
```
ou
```csharp
int resultado = checked(a + b);
```

## Exemplos
### Exemplo 1: Uso de Bloco Checked
```csharp
try
{
    checked
    {
        int a = int.MaxValue;
        int b = 1;
        int resultado = a + b; // Isso lançará uma OverflowException
    }
}
catch (OverflowException ex)
{
    Console.WriteLine("Ocorreu um overflow: " + ex.Message);
}
```

### Exemplo 2: Uso de Expressão Checked
```csharp
try
{
    int a = int.MaxValue;
    int b = 1;
    int resultado = checked(a + b); // Isso também lançará uma OverflowException
}
catch (OverflowException ex)
{
    Console.WriteLine("Ocorreu um overflow: " + ex.Message);
}
```

## Explicação
É importante notar que o "checked" serve apenas para tipos de valor que suportam overflow, como `int`, `long`, etc. Se o overflow ocorrer em um tipo que não suporta isso, como `float` ou `double`, a operação será realizada normalmente, sem lançar uma exceção.

### Armadilhas Comuns
- **Desempenho:** O uso de "checked" pode impactar o desempenho de aplicações em cenários críticos, pois a verificação adiciona uma sobrecarga.
- **Uso desnecessário:** Em situações onde o overflow não é uma preocupação, o uso de "checked" pode ser evitado, simplificando o código.

## Resumo em Uma Linha
O comando "checked" em CSharp é utilizado para habilitar a verificação de overflow em operações aritméticas, lançando exceções quando os limites dos tipos de dados são excedidos.