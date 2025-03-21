# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 
O valor de x será exibido como undefined, pois foi declarado com var. Isso acontece porque variáveis declaradas com var são içadas para o topo do escopo, permitindo que sejam acessadas antes da atribuição, mas com um valor indefinido. Já y, que foi declarado com let, provoca um erro ao ser acessado antes da sua definição, pois variáveis declaradas com let não permitem acesso antes da inicialização.

**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

Se o operador lógico || for utilizado, a mensagem "Erro: número inválido" será exibida sempre que pelo menos um dos valores for igual a zero, independentemente do outro. Por outro lado, com o operador &&, essa mensagem só será mostrada caso ambos os números sejam 0.
______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```
b) O código imprime 200.

Quando o código encontra "eletrônico", ele começa atribuindo 1000. Mas como não tem um break, ele segue para o próximo caso, que muda o valor para 200. Só depois disso o break aparece e interrompe tudo, fazendo com que 200 seja impresso.

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
d) 24

O código primeiro dobra cada número da lista. Depois, remove os que são maiores que 5. No final, soma os que restaram e chega em 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

c) ["banana", "abacaxi", "manga", "laranja"]

A lista original tem "maçã" e "uva" nas posições 1 e 2, que são removidas e substituídas por "abacaxi" e "manga". No final, a lista fica como ["banana", "abacaxi", "manga", "laranja"].
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

A primeira afirmação está certa, porque a herança evita a repetição de código ao compartilhar métodos e propriedades entre classes. A segunda também é verdadeira, já que extends é uma forma de herança em JavaScript, mas não é a única. Também é possível usar protótipos (Object.create(), por exemplo). Por isso, a segunda afirmação não justifica a primeira.
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

A classe Funcionario estende Pessoa, e o super(nome, idade) chama o construtor da classe pai para inicializar os atributos. O método apresentar() de Funcionario sobrescreve o da classe Pessoa, mas super.apresentar() permite acessar a versão original. O JavaScript moderno dá suporte a classes e herança usando class e extends.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

b) A asserção é verdadeira e a razão é falsa.

O polimorfismo na POO possibilita que instâncias de diversas classes reajam de maneira distinta a uma mesma chamada, levando em conta suas características individuais. No entanto, ele não pode ser obtido por meio da sobrecarga de métodos, pois esse mecanismo apenas reconhece a versão mais recente associada ao identificador do método.
______



# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
Código funcionando:

// Declara a função que calcula a soma dos elementos de um array multiplicados por 2
function somaArray(numeros) {

    // Inicializa a variável que armazenará o resultado da soma
    let soma = 0;

    // Percorre todos os elementos do array
    for (let i = 0; i < numeros.length; i++) {
        // Multiplica cada elemento por 2 e adiciona ao total
        soma += 2 * numeros[i];
    }
    
    // Retorna o resultado final da soma
    return soma;
}

// Chama a função com um array de números e exibe o resultado no console
console.log(somaArray([1, 2, 3, 4]));

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

class Produto {
    // Define os atributos básicos de um produto
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }
  
    calcularDesconto() {
        // Aplica um desconto padrão de 10% sobre o preço original
        const desconto = this.preco * 0.10;
        return this.preco - desconto;
    }

    precificar() {
        // Exibe o nome do produto e seu preço no console
        console.log(`Produto: ${this.nome}, Preço: ${this.preco}.`);
    }
}

class Livro extends Produto {
    // Inicializa um objeto da classe Livro com os mesmos atributos da classe pai
    constructor(nome, preco, autor) {
        super(nome, preco); // Chama o construtor da classe Produto
        this.autor = autor; // Adiciona um atributo específico para livros
    }
  
    calcularDesconto() {
        // Redefine a regra de desconto para livros, aplicando 20% de desconto
        const desconto = this.preco * 0.20;
        return this.preco - desconto;
    }

    precificar() {
        // Exibe as informações específicas do livro
        console.log(`Livro: ${this.nome}, Preço: ${this.preco}, Autor: ${this.autor}.`);
    }
}
A herança permite que a classe Livro utilize as propriedades e métodos da classe Produto por meio da palavra-chave extends. No entanto, é possível sobrescrever métodos herdados para adaptar comportamentos específicos. Por exemplo, calcularDesconto() é redefinido na classe Livro para oferecer um desconto maior. Para que essa personalização funcione corretamente, as instâncias da classe devem ser criadas e configuradas com os valores desejados.








