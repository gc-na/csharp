<!--
Meta Description: # Uso do "params" em C#: Entendendo o Passagem de Parâmetros Variáveis ## Sinopse O modificador `params` em C# é uma funcionalidade que permite passar...
Meta Keywords: params, exemplo, que, método, soma
-->

# Uso do "params" em C#: Entendendo o Passagem de Parâmetros Variáveis

## Sinopse
O modificador `params` em C# é uma funcionalidade que permite passar um número variável de argumentos para um método, facilitando a manipulação de listas de dados sem a necessidade de definir explicitamente um array.

## Documentação
O `params` é utilizado na declaração de métodos em C# para permitir que você passe um número indefinido de argumentos como um único parâmetro. Isso é especialmente útil quando o número de entradas não é conhecido em tempo de compilação. Para utilizar o `params`, ele deve ser o último parâmetro da lista de parâmetros do método e deve ser do tipo array.

### Propósito
O principal objetivo do `params` é simplificar a chamada de métodos que exigem múltiplos argumentos, tornando o código mais limpo e legível.

### Uso
Para usar o `params`, declare um método com o modificador seguido do tipo de dados e um nome de parâmetro. O método pode então ser chamado com zero ou mais argumentos do tipo especificado.

```csharp
public void MeuMetodo(params int[] numeros)
{
    foreach (var numero in numeros)
    {
        Console.WriteLine(numero);
    }
}
```

## Exemplos
### Exemplo Básico
Aqui está um exemplo simples que demonstra o uso de `params`:

```csharp
public class ExemploParams
{
    public void Somar(params int[] numeros)
    {
        int soma = 0;
        foreach (var numero in numeros)
        {
            soma += numero;
        }
        Console.WriteLine($"A soma é: {soma}");
    }
}

// Uso do método
ExemploParams exemplo = new ExemploParams();
exemplo.Somar(1, 2, 3); // Saída: A soma é: 6
exemplo.Somar(4, 5);    // Saída: A soma é: 9
exemplo.Somar();        // Saída: A soma é: 0
```

### Exemplo com Diferentes Tipos
O `params` só pode ser usado com um único tipo de dados, mas você pode criar métodos sobrecarregados para diferentes tipos:

```csharp
public class ExemploParamsDiferentes
{
    public void ExibirMensagens(params string[] mensagens)
    {
        foreach (var mensagem in mensagens)
        {
            Console.WriteLine(mensagem);
        }
    }
}

// Uso do método
ExemploParamsDiferentes exemplo = new ExemploParamsDiferentes();
exemplo.ExibirMensagens("Olá", "Mundo", "CSharp!"); 
```

## Explicação
Um erro comum ao usar `params` é tentar passar múltiplos arrays ou diferentes tipos de dados em um único parâmetro `params`. Lembre-se de que ele aceita apenas um tipo de dado e deve ser o último parâmetro na declaração do método. Além disso, embora você possa chamar um método `params` sem fornecer argumentos, tenha em mente que isso resultará em um array vazio, e não em um `null`.

### Considerações
- O `params` pode ser muito útil em métodos que precisam trabalhar com listas de elementos, como operações de soma, concatenação de strings, entre outros.
- Cuidado para não confundir `params` com a sobrecarga de métodos; eles possuem propósitos diferentes.

## Resumo em Uma Linha
O `params` em C# permite que métodos aceitem um número variável de argumentos, simplificando a passagem de múltiplos parâmetros.