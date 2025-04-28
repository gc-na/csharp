<!--
Meta Description: # A Palavra-chave "readonly" em C#: Entenda Como Utilizá-la ## Sinopse A palavra-chave "readonly" em C# permite que você declare campos que podem ser ...
Meta Keywords: readonly, public, campo, que, construtor
-->

# A Palavra-chave "readonly" em C#: Entenda Como Utilizá-la

## Sinopse
A palavra-chave "readonly" em C# permite que você declare campos que podem ser atribuídos apenas durante a inicialização ou dentro de um construtor, garantindo que seu valor não seja alterado posteriormente. Este recurso é essencial para a proteção de dados em objetos, promovendo a imutabilidade.

## Documentação
A palavra-chave `readonly` é utilizada na definição de campos em classes e estruturas. Um campo declarado como `readonly` pode ser inicializado no momento da declaração ou no construtor da classe, mas não pode ser modificado após isso. Isso assegura que o estado do objeto permaneça consistente e evita alterações indesejadas.

### Propósito
O uso de `readonly` é recomendado quando você deseja que um campo tenha um valor fixo após a inicialização. Isso é especialmente útil em situações onde a integridade dos dados é crucial, como em objetos de configuração ou constantes.

### Uso
Para declarar um campo como `readonly`, você deve preceder a declaração do campo com a palavra-chave `readonly`. Aqui está a sintaxe básica:

```csharp
public class Exemplo
{
    public readonly int campoReadonly;

    public Exemplo(int valor)
    {
        campoReadonly = valor; // Atribuição permitida aqui
    }
}
```

## Exemplos
### Exemplo 1: Definição Básica
```csharp
public class Produto
{
    public readonly string Nome;

    public Produto(string nome)
    {
        Nome = nome; // Atribuição no construtor
    }
}

// Uso
var produto = new Produto("Camiseta");
Console.WriteLine(produto.Nome); // Saída: Camiseta
```

### Exemplo 2: Tentativa de Modificação
```csharp
public class Carro
{
    public readonly string Modelo;

    public Carro(string modelo)
    {
        Modelo = modelo;
    }
}

// Uso
var carro = new Carro("Fusca");
// carro.Modelo = "Civic"; // Erro de compilação: não é possível modificar o campo readonly
```

## Explicação
Ao usar a palavra-chave `readonly`, é importante entender algumas armadilhas comuns:

1. **Atribuição fora do construtor**: Tentar modificar um campo `readonly` fora do construtor resultará em um erro de compilação. Isso é intencional, pois o objetivo do `readonly` é proteger o campo de modificações externas.

2. **Objetos mutáveis**: Se você atribuir um objeto que é mutável a um campo `readonly`, você ainda poderá modificar as propriedades desse objeto, mesmo que não possa reatribuir o campo em si. Por exemplo:

    ```csharp
    public class Pessoa
    {
        public readonly List<string> Hobbies = new List<string>();
    }

    var pessoa = new Pessoa();
    pessoa.Hobbies.Add("Futebol"); // Isso é permitido, pois estamos modificando o conteúdo da lista
    ```

3. **Inicialização em campos estáticos**: Campos `readonly` também podem ser usados em campos estáticos, mas devem ser atribuídos no momento da declaração ou em um construtor estático.

## Resumo em Uma Linha
A palavra-chave `readonly` em C# permite a definição de campos que podem ser atribuídos apenas durante a inicialização ou no construtor, garantindo a imutabilidade do seu valor após a criação do objeto.