<!--
Meta Description: # stackalloc em C#: Alocação de Memória no Stack ## Sinopse O `stackalloc` é uma palavra-chave em C# que permite alocar memória no stack (pilha) para ...
Meta Keywords: stackalloc, memória, tipos, alocação, array
-->

# stackalloc em C#: Alocação de Memória no Stack

## Sinopse
O `stackalloc` é uma palavra-chave em C# que permite alocar memória no stack (pilha) para tipos de dados primitivos, oferecendo uma alternativa eficiente e de baixo custo para a alocação de memória no heap.

## Documentação
O `stackalloc` é utilizado para criar um bloco de memória contígua no stack, que é liberado automaticamente quando o escopo do método é encerrado. Essa abordagem é especialmente útil para a alocação de arrays de tipos primitivos, como `int`, `float`, ou `byte`, sem a sobrecarga da coleta de lixo.

### Propósito
A principal finalidade do `stackalloc` é otimizar a performance em situações onde a alocação e desalocação de memória ocorrem rapidamente, eliminando a necessidade de alocar e liberar memória no heap.

### Uso
O `stackalloc` é utilizado dentro de um método e deve ser seguido pelo tipo de dado e, em seguida, o comprimento do array que deseja alocar. A sintaxe básica é:

```csharp
var array = stackalloc Tipo[Tamanho];
```

### Detalhes
- O `stackalloc` só pode ser usado com tipos de valor, como structs e tipos primitivos.
- A memória alocada com `stackalloc` é liberada automaticamente quando o método retorna, o que reduz a necessidade de gerenciamento manual de memória.
- O uso de `stackalloc` pode causar uma exceção `StackOverflowException` se a quantidade de memória alocada exceder a capacidade da pilha.

## Exemplos

### Exemplo 1: Alocação Simples
```csharp
public void ExemploStackalloc()
{
    int* array = stackalloc int[5];
    for (int i = 0; i < 5; i++)
    {
        array[i] = i * 10;
    }
    
    // Saída dos valores alocados
    for (int i = 0; i < 5; i++)
    {
        Console.WriteLine(array[i]);
    }
}
```

### Exemplo 2: Uso com Tipos de Dados Diferentes
```csharp
public void ExemploStackallocFloat()
{
    float* array = stackalloc float[3] { 1.0f, 2.0f, 3.0f };

    for (int i = 0; i < 3; i++)
    {
        Console.WriteLine(array[i]);
    }
}
```

## Explicação
Embora o `stackalloc` ofereça várias vantagens, existem algumas armadilhas comuns a serem consideradas:

- **Limite de Tamanho**: O tamanho da memória alocada não deve exceder a capacidade do stack, que geralmente varia de acordo com a configuração do runtime.
- **Uso de Tipos de Referência**: O `stackalloc` não pode ser usado para alocar tipos de referência, como classes, o que limita seu uso a tipos de valor.
- **Scoped**: A memória alocada existe apenas durante a execução do método. Qualquer tentativa de acessar a memória após a execução do método resultará em comportamento indefinido.

## Resumo em Uma Linha
O `stackalloc` em C# permite a alocação eficiente de memória no stack para tipos de valor, proporcionando uma alternativa rápida à alocação no heap.