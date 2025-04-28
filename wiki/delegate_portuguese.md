<!--
Meta Description: # Delegados em C#: Entendendo e Utilizando ## Sinopse Os delegados em C# são tipos seguros que encapsulam métodos, permitindo que você armazene referê...
Meta Keywords: delegados, que, void, métodos, você
-->

# Delegados em C#: Entendendo e Utilizando

## Sinopse
Os delegados em C# são tipos seguros que encapsulam métodos, permitindo que você armazene referências a métodos e os invoque de forma flexível e dinâmica.

## Documentação
Os delegados são uma das características mais poderosas e flexíveis da linguagem C#. Eles permitem que métodos sejam passados como parâmetros e usados como callbacks, facilitando a implementação de eventos e a programação orientada a eventos.

### Propósito
O propósito principal de um delegado é fornecer um mecanismo para referenciar métodos, possibilitando a execução de um método que pode ser definido em tempo de execução.

### Uso
Para declarar um delegado, você utiliza a palavra-chave `delegate`, seguida pela assinatura do método que ele pode referenciar. A sintaxe básica é a seguinte:

```csharp
public delegate void MeuDelegado(string mensagem);
```

Uma vez que o delegado é definido, você pode criar instâncias dele e associá-las a métodos que correspondam à sua assinatura:

```csharp
void MeuMetodo(string msg)
{
    Console.WriteLine(msg);
}

MeuDelegado deleg = new MeuDelegado(MeuMetodo);
deleg("Olá, Delegados!");
```

### Detalhes
- **Multicast Delegates**: Delegados podem apontar para múltiplos métodos. Isso é feito utilizando o operador `+=`.
- **Anônimos**: Você também pode usar expressões lambda para criar delegados de maneira mais concisa.

## Exemplos
### Exemplo Básico
```csharp
using System;

public delegate void Notificacao(string mensagem);

class Program
{
    static void Main()
    {
        Notificacao notificar = new Notificacao(MostrarMensagem);
        notificar("Bem-vindo ao mundo dos delegados!");
    }

    static void MostrarMensagem(string msg)
    {
        Console.WriteLine(msg);
    }
}
```

### Exemplo com Multicast Delegates
```csharp
using System;

public delegate void Notificacao(string mensagem);

class Program
{
    static void Main()
    {
        Notificacao notificar = MostrarMensagem1;
        notificar += MostrarMensagem2;

        notificar("Olá, Mundo!");
    }

    static void MostrarMensagem1(string msg)
    {
        Console.WriteLine("Mensagem 1: " + msg);
    }

    static void MostrarMensagem2(string msg)
    {
        Console.WriteLine("Mensagem 2: " + msg);
    }
}
```

### Exemplo com Expressão Lambda
```csharp
using System;

class Program
{
    delegate void Calculadora(int x, int y);

    static void Main()
    {
        Calculadora soma = (x, y) => Console.WriteLine(x + y);
        soma(5, 10); // Saída: 15
    }
}
```

## Explicação
### Armadilhas Comuns
- **Tipo Incompatível**: Certifique-se de que os métodos que você está tentando atribuir a um delegado tenham a mesma assinatura. Caso contrário, você receberá um erro de compilação.
- **Delegados Multicast**: Quando você usa delegados multicast (múltiplos métodos), os resultados podem ser inesperados se não forem manipulados corretamente, pois eles invocam todos os métodos na lista em ordem.

### Notas Adicionais
- Delegados são frequentemente usados em eventos e são uma parte fundamental do modelo de eventos do C#.
- A utilização de delegados pode aumentar a legibilidade e a manutenção do código, permitindo que você separe a lógica de controle da lógica de execução.

## Resumo em uma Linha
Delegados em C# são tipos que permitem a encapsulação e invocação de métodos, facilitando a programação orientada a eventos e o uso de callbacks.