<!--
Meta Description: # Uso da Palavra-Chave "fixed" em C# ## Sinopse A palavra-chave "fixed" em C# é utilizada para fixar a posição de um ponteiro em relação à memória, pe...
Meta Keywords: fixed, uso, que, memória, palavra
-->

# Uso da Palavra-Chave "fixed" em C#

## Sinopse
A palavra-chave "fixed" em C# é utilizada para fixar a posição de um ponteiro em relação à memória, permitindo a manipulação de dados não gerenciados sem que o garbage collector (coletor de lixo) mova esses dados.

## Documentação
A palavra-chave "fixed" é uma parte fundamental da manipulação de ponteiros em C#, especialmente quando se trabalha com interoperabilidade entre C# e código não gerenciado (como C ou C++). O uso de "fixed" é necessário quando se deseja trabalhar com objetos que estão alocados na memória e não devem ser movidos pelo garbage collector.

### Propósito
O propósito principal da palavra-chave "fixed" é garantir que um bloco de memória permaneça estático durante a execução de um bloco de código específico. Isso é particularmente útil quando se está utilizando ponteiros para acessar dados não gerenciados.

### Uso
O "fixed" deve ser utilizado dentro de um bloco `unsafe`, que permite o uso de ponteiros. O uso típico é o seguinte:

```csharp
unsafe
{
    fixed (char* p = str)
    {
        // Operações com o ponteiro p
    }
}
```

### Detalhes
- A palavra-chave "fixed" deve ser usada com tipos que suportam ponteiros, como arrays e strings.
- O uso de "fixed" é restrito a contextos onde o código é marcado como `unsafe` (inseguro).
- O "fixed" não deve ser usado em um contexto onde o garbage collector pode mover a memória referenciada, pois isso pode causar acessos a locais inválidos.

## Exemplos
### Exemplo Básico
```csharp
using System;

class Program
{
    unsafe static void Main()
    {
        char[] myString = { 'H', 'o', 'l', 'a', '!', '\0' };
        
        fixed (char* p = myString)
        {
            Console.WriteLine(p); // Acessa a string diretamente via ponteiro
        }
    }
}
```

### Exemplo com Manipulação de Dados
```csharp
using System;

class Program
{
    unsafe static void Main()
    {
        int[] numbers = { 1, 2, 3, 4, 5 };

        fixed (int* p = numbers)
        {
            for (int i = 0; i < 5; i++)
            {
                Console.WriteLine(*(p + i)); // Acesso aos elementos via ponteiro
            }
        }
    }
}
```

## Explicação
Um erro comum ao utilizar a palavra-chave "fixed" é esquecer de declarar o bloco como `unsafe`. Além disso, o uso inadequado de ponteiros pode levar a vazamentos de memória e acessos a áreas inválidas da memória. É importante sempre garantir que o bloco de código dentro de "fixed" não seja deixado antes da conclusão do seu uso, para evitar que o garbage collector mova a memória.

Além disso, o uso de "fixed" só é permitido em assemblies que tenham a opção de código inseguro habilitada, o que pode ser configurado nas propriedades do projeto.

## Resumo em Uma Linha
A palavra-chave "fixed" em C# é utilizada para fixar ponteiros em memória, permitindo acesso seguro a dados não gerenciados dentro de blocos de código inseguro.