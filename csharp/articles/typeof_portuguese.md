<!--
Meta Description: # typeof em C#: Entenda o Comando e Suas Aplicações ## Sinopse O comando `typeof` no C# é uma ferramenta poderosa que permite obter o tipo de uma clas...
Meta Keywords: typeof, tipo, que, tipos, uma
-->

# typeof em C#: Entenda o Comando e Suas Aplicações

## Sinopse
O comando `typeof` no C# é uma ferramenta poderosa que permite obter o tipo de uma classe, estrutura ou interface em tempo de compilação, facilitando a reflexão e a manipulação de tipos.

## Documentação
O `typeof` é um operador do C# que retorna um objeto `Type` que representa o tipo especificado como argumento. Este operador é amplamente utilizado em cenários onde a informação sobre o tipo de um objeto é necessária, especialmente em contextos de reflexão, serialização e quando se trabalha com métodos genéricos.

### Propósito
O principal propósito do `typeof` é fornecer uma maneira de trabalhar com tipos de forma dinâmica, permitindo que o desenvolvedor obtenha metadados sobre um tipo específico.

### Uso
A sintaxe básica do `typeof` é:

```csharp
Type tipo = typeof(NomeDaClasse);
```

Aqui, `NomeDaClasse` deve ser substituído pelo nome do tipo desejado, que pode ser uma classe, interface ou estrutura.

### Detalhes
- O operador `typeof` é avaliado em tempo de compilação, o que significa que você deve usar um tipo conhecido no momento da escrita do código.
- Ele é frequentemente utilizado em cenários de reflexão, onde se pode invocar métodos ou acessar propriedades de um tipo sem conhecê-lo em tempo de execução.
- O `typeof` pode ser usado para verificar se um objeto é de um determinado tipo ou para comparar tipos.

## Exemplos
### Exemplo 1: Obter o Tipo de uma Classe
```csharp
using System;

class Program
{
    static void Main()
    {
        Type tipo = typeof(string);
        Console.WriteLine(tipo.FullName); // Saída: System.String
    }
}
```

### Exemplo 2: Usando typeof em Métodos Genéricos
```csharp
using System;

class Program
{
    static void ExibirTipo<T>()
    {
        Console.WriteLine(typeof(T).FullName);
    }

    static void Main()
    {
        ExibirTipo<int>(); // Saída: System.Int32
        ExibirTipo<string>(); // Saída: System.String
    }
}
```

### Exemplo 3: Verificação de Tipo
```csharp
using System;

class Program
{
    static void Main()
    {
        object obj = "Texto";
        if (obj.GetType() == typeof(string))
        {
            Console.WriteLine("O objeto é uma string.");
        }
    }
}
```

## Explicação
Embora o `typeof` seja uma ferramenta útil, existem algumas armadilhas comuns que os desenvolvedores devem evitar:

- **Tipos Não Reconhecidos**: Ao usar `typeof`, certifique-se de que o tipo existe e é acessível no contexto atual. Tipos não reconhecidos resultarão em erros de compilação.
- **Limitações de Tipo**: O `typeof` não pode ser usado com tipos que não são conhecidos em tempo de compilação, como tipos anônimos ou tipos definidos em tempo de execução.
- **Confusão com o Operador `is`**: O operador `is` é usado para verificar se um objeto é de um determinado tipo em tempo de execução, enquanto `typeof` é usado para obter o tipo em tempo de compilação.

## Resumo em Uma Linha
O operador `typeof` em C# permite obter informações sobre tipos em tempo de compilação, sendo essencial para reflexão e manipulação de tipos.