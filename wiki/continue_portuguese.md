<!--
Meta Description: # Comando "continue" em CSharp: Entenda o seu uso e funcionalidades ## Sinopse O comando `continue` em CSharp é utilizado dentro de estruturas de repe...
Meta Keywords: continue, loop, que, código, csharp
-->

# Comando "continue" em CSharp: Entenda o seu uso e funcionalidades

## Sinopse
O comando `continue` em CSharp é utilizado dentro de estruturas de repetição, permitindo que a iteração atual de um loop seja interrompida e a próxima iteração seja iniciada imediatamente, ignorando qualquer código subsequente na execução do loop.

## Documentação
O `continue` é uma instrução de controle de fluxo que pode ser aplicada em loops como `for`, `foreach`, `while` e `do-while`. Quando o `continue` é chamado, ele faz com que a execução salte para o início do loop, avaliando a condição do loop novamente.

### Propósito
O propósito do comando `continue` é fornecer um meio de pular a parte restante do código em um loop quando uma condição específica é atendida, permitindo que o programador controle o fluxo da execução de forma eficiente.

### Uso
O `continue` pode ser usado em qualquer loop que suporte iterações. A estrutura básica para seu uso é a seguinte:

```csharp
for (int i = 0; i < 10; i++)
{
    if (i % 2 == 0) // Se i é par
    {
        continue; // Pula o código a seguir para números pares
    }
    Console.WriteLine(i); // Apenas números ímpares serão exibidos
}
```

## Exemplos
Aqui estão alguns exemplos práticos que ilustram o uso do `continue`.

### Exemplo 1: Usando `continue` em um loop `for`
```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        continue; // Ignora o número 5
    }
    Console.WriteLine(i); // Exibe 0, 1, 2, 3, 4, 6, 7, 8, 9
}
```

### Exemplo 2: Usando `continue` em um loop `while`
```csharp
int i = 0;
while (i < 10)
{
    i++;
    if (i % 2 == 0) // Se i é par
    {
        continue; // Ignora a parte abaixo para números pares
    }
    Console.WriteLine(i); // Exibe apenas números ímpares
}
```

## Explicação
Embora o `continue` seja uma ferramenta poderosa, é importante estar ciente de algumas armadilhas comuns:

- **Escopo do loop**: O `continue` só afeta o loop mais interno. Se você tiver loops aninhados, o `continue` se aplicará apenas ao loop em que está diretamente presente.
- **Código após `continue`**: Qualquer código que esteja após a instrução `continue` dentro do bloco do loop não será executado na iteração atual.
- **Legibilidade do código**: O uso excessivo de `continue` pode dificultar a leitura do código. É recomendável usá-lo com moderação e clareza.

## Resumo em uma linha
O comando `continue` em CSharp permite pular a execução do restante de um loop e iniciar a próxima iteração imediatamente, facilitando o controle do fluxo em loops.