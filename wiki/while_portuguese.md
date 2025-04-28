<!--
Meta Description: # Estrutura de Controle “while” em CSharp: Entenda e Aprenda a Usar ## Sinopse A estrutura de controle "while" em CSharp permite a execução repetida d...
Meta Keywords: condição, que, while, contador, bloco
-->

# Estrutura de Controle “while” em CSharp: Entenda e Aprenda a Usar

## Sinopse
A estrutura de controle "while" em CSharp permite a execução repetida de um bloco de código enquanto uma condição específica for verdadeira. Essa funcionalidade é fundamental para a criação de loops que dependem de avaliações dinâmicas.

## Documentação
### Propósito
O comando "while" é utilizado para executar um bloco de código repetidamente, desde que a condição especificada retorne verdadeiro. Isso é útil em situações onde o número de iterações não é conhecido antes da execução.

### Uso
A sintaxe básica do comando "while" é a seguinte:

```csharp
while (condição)
{
    // bloco de código a ser executado
}
```

1. **Condição:** Uma expressão booleana que é avaliada antes da execução do bloco. Se a condição for verdadeira, o código dentro do bloco será executado. Se for falsa, a execução do loop é interrompida.
2. **Bloco de Código:** O código dentro das chaves `{}` que será executado repetidamente.

### Detalhes
- O "while" é uma estrutura de controle que pode levar a loops infinitos se a condição nunca se tornar falsa.
- É importante garantir que, dentro do loop, a condição será eventualmente falsa para evitar loops que nunca terminam.

## Exemplos

### Exemplo 1: Contagem Simples
```csharp
int contador = 0;
while (contador < 5)
{
    Console.WriteLine("Contador: " + contador);
    contador++;
}
```
**Saída:**
```
Contador: 0
Contador: 1
Contador: 2
Contador: 3
Contador: 4
```

### Exemplo 2: Entrada do Usuário
```csharp
string entrada;
do
{
    Console.Write("Digite 'sair' para encerrar: ");
    entrada = Console.ReadLine();
} while (entrada != "sair");
```

## Explicação
### Armadilhas Comuns
- **Loop Infinito:** Um erro comum é não alterar a condição do loop, resultando em uma execução interminável. Certifique-se de que a condição seja atualizada dentro do bloco.
- **Condição Sempre Verdadeira:** Outra armadilha é usar uma condição que sempre retorne verdadeiro, como `while (true)`, sem um mecanismo de saída adequado.
- **Uso de Variáveis Não Inicializadas:** Garantir que todas as variáveis usadas na condição estejam inicializadas corretamente antes do loop.

### Dicas Adicionais
- Para loops que precisam executar pelo menos uma vez, considere o uso do `do-while`, que garante a execução do bloco antes de verificar a condição.
- Sempre revise a lógica de saída do loop para garantir que a condição será, de fato, falsa em algum momento.

## Resumo em Uma Linha
O "while" em CSharp é uma estrutura de controle que executa um bloco de código repetidamente enquanto uma condição booleana for verdadeira.