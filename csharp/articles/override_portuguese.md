<!--
Meta Description: # Override em C#: Entenda como Sobrescrever Métodos na Programação Orientada a Objetos ## Sinopse O `override` em C# é uma palavra-chave utilizada na ...
Meta Keywords: override, método, classe, que, base
-->

# Override em C#: Entenda como Sobrescrever Métodos na Programação Orientada a Objetos

## Sinopse
O `override` em C# é uma palavra-chave utilizada na programação orientada a objetos que permite substituir a implementação de um método em uma classe base por uma nova implementação em uma classe derivada. Essa funcionalidade é essencial para o polimorfismo, permitindo que métodos de classes base sejam personalizados nas subclasses.

## Documentação
A palavra-chave `override` é utilizada em C# quando se deseja modificar o comportamento de um método que já foi definido na classe base. Para que um método possa ser sobrescrito, ele deve ser marcado com a palavra-chave `virtual` ou `abstract` na classe base.

### Propósito
O `override` tem como objetivo permitir que classes derivadas alterem o comportamento de métodos herdados, proporcionando flexibilidade e reutilização de código.

### Uso
Para usar o `override`, siga estes passos:

1. Defina um método na classe base usando a palavra-chave `virtual` ou `abstract`.
2. Na classe derivada, declare um método com o mesmo nome e a mesma assinatura, e utilize a palavra-chave `override`.

### Detalhes
- Um método `override` deve ter a mesma assinatura que o método da classe base.
- Métodos marcados como `virtual` podem ser sobrescritos, enquanto os métodos `abstract` devem ser implementados nas classes derivadas.
- O `override` é fundamental para a implementação do polimorfismo em C#, permitindo que o comportamento dos métodos seja determinado em tempo de execução.

## Exemplos

### Exemplo Básico

```csharp
public class Animal
{
    public virtual void FazerSom()
    {
        Console.WriteLine("Som de animal");
    }
}

public class Cachorro : Animal
{
    public override void FazerSom()
    {
        Console.WriteLine("Au Au");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal meuAnimal = new Cachorro();
        meuAnimal.FazerSom(); // Saída: Au Au
    }
}
```

### Exemplo com Método Abstract

```csharp
public abstract class Forma
{
    public abstract double CalcularArea();
}

public class Retangulo : Forma
{
    private double largura;
    private double altura;

    public Retangulo(double largura, double altura)
    {
        this.largura = largura;
        this.altura = altura;
    }

    public override double CalcularArea()
    {
        return largura * altura;
    }
}

class Program
{
    static void Main(string[] args)
    {
        Forma meuRetangulo = new Retangulo(5, 10);
        Console.WriteLine(meuRetangulo.CalcularArea()); // Saída: 50
    }
}
```

## Explicação
Um erro comum ao utilizar a palavra-chave `override` é não coincidir corretamente a assinatura do método na classe derivada com o método da classe base. Além disso, é importante lembrar que não se pode sobrescrever um método que não foi declarado como `virtual` ou `abstract`. Outro ponto a considerar é que, se a classe base for final (não pode ser herdada), você não poderá sobrescrever seus métodos.

## Resumo em Uma Linha
A palavra-chave `override` em C# permite substituir a implementação de métodos de uma classe base em classes derivadas, promovendo a flexibilidade e o polimorfismo na programação orientada a objetos.