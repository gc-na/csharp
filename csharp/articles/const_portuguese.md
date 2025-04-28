<!--
Meta Description: # Const: Definição e Uso em CSharp ## Sinopse O modificador `const` em CSharp é utilizado para declarar constantes, que são variáveis cujo valor não p...
Meta Keywords: const, uma, que, constantes, csharp
-->

# Const: Definição e Uso em CSharp

## Sinopse
O modificador `const` em CSharp é utilizado para declarar constantes, que são variáveis cujo valor não pode ser alterado após a sua inicialização. Isso garante que as constantes mantenham um valor fixo durante toda a execução do programa.

## Documentação
O modificador `const` é uma palavra-chave em CSharp que permite definir uma variável como constante. As variáveis constantes devem ser inicializadas no momento da declaração e não podem ser atribuídas novamente em qualquer ponto posterior no código. Este recurso é útil para definir valores que não devem mudar, como constantes matemáticas ou configurações que permanecem fixas.

### Propósito
O propósito principal do `const` é proporcionar segurança e clareza no código, evitando modificações acidentais em valores essenciais.

### Uso
Para declarar uma constante em CSharp, você deve usar a palavra-chave `const` seguida do tipo de dado e do nome da constante, terminando com um valor inicial. Exemplo:

```csharp
const int maxTentativas = 5;
const string nomeDoApp = "MeuAplicativo";
```

As constantes podem ser de qualquer tipo de dado, incluindo tipos primitivos como `int`, `string`, `double`, entre outros.

### Detalhes
- As constantes devem ser inicializadas na mesma linha em que são declaradas.
- As constantes são implicitamente `static`, o que significa que pertencem à classe e não a instâncias específicas dela.
- O uso de `const` pode melhorar a legibilidade e a manutenção do código.

## Exemplos
Aqui estão alguns exemplos básicos de como usar `const` em CSharp:

```csharp
// Exemplo de uso de const com um inteiro
const int diasNaSemana = 7;

// Exemplo de uso de const com uma string
const string saudacao = "Olá, mundo!";

// Exemplo de uso com um valor de ponto flutuante
const double pi = 3.14159;
```

## Explicação
Embora o uso de `const` traga muitos benefícios, é importante estar ciente de alguns pontos:

- **Imutabilidade**: Uma vez que uma constante é definida, seu valor não pode ser alterado. Tentar reatribuir um valor a uma constante resultará em um erro de compilação.
- **Contexto de Compilação**: O valor de uma constante deve ser conhecido em tempo de compilação. Portanto, não pode ser atribuído a uma constante um valor que é calculado em tempo de execução.
- **Constantes em Classes**: Ao declarar constantes dentro de uma classe, elas são acessíveis sem a necessidade de criar uma instância da classe.

## Resumo em Uma Linha
O `const` em CSharp é uma palavra-chave que define variáveis constantes, garantindo que seus valores não sejam alterados após a inicialização.