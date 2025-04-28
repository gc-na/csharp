<!--
Meta Description: # int em C#: Compreendendo o Tipo de Dado Inteiro ## Sinopse O tipo `int` em C# é um dos tipos de dados primitivos utilizados para armazenar números i...
Meta Keywords: int, tipo, para, que, você
-->

# int em C#: Compreendendo o Tipo de Dado Inteiro

## Sinopse
O tipo `int` em C# é um dos tipos de dados primitivos utilizados para armazenar números inteiros. Ele é amplamente utilizado em operações aritméticas, contadores e para manipulação de dados numéricos.

## Documentação
O `int` é um tipo de dado que representa um número inteiro de 32 bits com sinal, o que significa que ele pode armazenar valores que vão de -2.147.483.648 a 2.147.483.647. Esse tipo é parte da linguagem C# e é usado frequentemente em diversas aplicações, desde cálculos simples até lógica de programação complexa.

### Uso
Para declarar uma variável do tipo `int`, você pode usar a seguinte sintaxe:

```csharp
int numero;
```

Você também pode inicializar a variável no momento da declaração:

```csharp
int numero = 10;
```

O `int` pode ser utilizado em operações aritméticas, como adição, subtração, multiplicação e divisão.

### Detalhes
- O `int` ocupa 4 bytes de memória.
- O valor padrão de um `int` não inicializado é 0.
- Para conversões entre tipos, você pode utilizar métodos como `Convert.ToInt32()` ou a conversão explícita.

## Exemplos
Aqui estão alguns exemplos básicos de uso do tipo `int`:

### Declaração e Inicialização
```csharp
int idade = 25;
```

### Operações Aritméticas
```csharp
int a = 10;
int b = 5;
int soma = a + b; // soma = 15
int subtracao = a - b; // subtracao = 5
int multiplicacao = a * b; // multiplicacao = 50
int divisao = a / b; // divisao = 2
```

### Uso em Estruturas de Controle
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

## Explicação
Um erro comum ao trabalhar com o tipo `int` é a tentativa de armazenar valores fora do intervalo permitido. Por exemplo, se você tentar atribuir um valor maior que 2.147.483.647 a um `int`, você receberá um erro de compilação.

Outro ponto importante é a divisão entre inteiros. Quando você divide dois inteiros, o resultado será truncado (parte decimal descartada). Para obter um resultado decimal, pelo menos um dos operandos deve ser do tipo `double` ou `float`.

### Exemplo de Erro de Divisão
```csharp
int resultado = 5 / 2; // resultado será 2, não 2.5
```

## Resumo em Uma Linha
O tipo `int` em C# é um tipo de dado primitivo que armazena números inteiros de 32 bits, sendo fundamental para operações numéricas e lógicas.