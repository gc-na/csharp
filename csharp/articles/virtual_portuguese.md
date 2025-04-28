<!--
Meta Description: # A Palavra-Chave "virtual" em C#: Entenda seu Uso e Importância ## Sinopse A palavra-chave `virtual` em C# permite que métodos, propriedades, indexad...
Meta Keywords: virtual, classe, que, método, public
-->

# A Palavra-Chave "virtual" em C#: Entenda seu Uso e Importância

## Sinopse
A palavra-chave `virtual` em C# permite que métodos, propriedades, indexadores e eventos em uma classe base sejam sobrescritos em classes derivadas, proporcionando flexibilidade no polimorfismo e na programação orientada a objetos.

## Documentação
A palavra-chave `virtual` é um modificador que indica que um membro de uma classe pode ser sobrescrito em uma classe derivada. Essa funcionalidade é essencial para implementar polimorfismo, permitindo que o comportamento de um método ou propriedade seja alterado em subclasses.

### Propósito
O principal objetivo do uso de `virtual` é permitir que subclasses forneçam sua própria implementação de um método definido na classe base, promovendo a reutilização de código e a extensibilidade.

### Uso
Para declarar um método virtual, você precisa usar a palavra-chave `virtual` antes do tipo de retorno do método na classe base. Para sobrescrever esse método em uma classe derivada, você deve usar a palavra-chave `override`. 

### Detalhes
- **Métodos Virtuais**: Quando um método é declarado como `virtual`, você pode sobrescrevê-lo em qualquer classe derivada usando `override`.
- **Propriedades Virtuais**: Propriedades podem também ser marcadas como `virtual`, permitindo que suas implementações sejam alteradas em subclasses.
- **Performance**: O uso de métodos virtuais pode impactar a performance devido à necessidade de resolução em tempo de execução.

## Exemplos

### Exemplo 1: Método Virtual
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

// Uso
Animal meuAnimal = new Cachorro();
meuAnimal.FazerSom(); // Saída: Au Au
```

### Exemplo 2: Propriedade Virtual
```csharp
public class Forma
{
    public virtual double Area { get; }
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

    public override double Area => largura * altura;
}

// Uso
Forma meuRetangulo = new Retangulo(5, 10);
Console.WriteLine(meuRetangulo.Area); // Saída: 50
```

## Explicação
Ao usar `virtual` e `override`, é importante entender que:

- **Não Sobrescrever**: Se um método virtual não for sobrescrito em uma classe derivada, a implementação da classe base será utilizada.
- **Base Virtual**: Você pode chamar o método da classe base a partir da classe derivada usando `base.NomeDoMetodo()`.
- **Limitações**: Métodos virtuais não podem ser estáticos ou privados, já que a intenção é que eles sejam acessíveis e modificáveis em subclasses.

## Resumo em Uma Linha
A palavra-chave `virtual` em C# permite que métodos e propriedades de uma classe base sejam sobrescritos em classes derivadas, promovendo flexibilidade e polimorfismo na programação orientada a objetos.