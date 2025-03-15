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

b) A saída será 5 seguido de 10

**c) A saída será undefined seguido de undefined**

d) A saída será erro em ambas as linhas que utilizam console.log

A resposta certa é a C, pois como as variáveis foram declaradas depois de serem chamadas, a chamada console.log não as identifica.


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

**a) Substituir if (a || b === 0) por if (a === 0 || b === 0)**

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

A resposta A é certa, pois a condicinal do if esta escrita de forma errada, da forma que esta, seria executado que b===0, sendo que A alternativa mantém o recurso || que foi utilizado corretamente e corrige o erro citado.

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

a) O código imprime 1000.

**b) O código imprime 200.**

c) O código imprime 50.

d) O código gera um erro.

A alternativa B esta correta, pois chamar a função calcularPreco e utilizar como objeto "eletrônico", o recurso switch seleciona o case no qual o a variável preço recebe o valor de 1000, mas como não tem um 'break' logo depois, ele continua e para no case que atribui 200 para o valor da variável.

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

**d) 24**

A resposta certa é D, pois o array de números passam de [1, 2, 3, 4, 5] para [1, 4, 6, 8, 10] no numeros.map, depois são filtrados, passando apenas os que maiores que 5: [6, 8, 10], por último eles são somados uns aos outros 6 + 8 + 10 = 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

**c) ["banana", "abacaxi", "manga", "laranja"]**

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

A alternativa correta é a C, pois o recurso splice modifica um array de forma que o primeiro elemento do parentêses indica a partir de qual item começa a modificação, ou seja, começa a partir do item "maça"; o segundo elemento do parentêses diz quantos itens são removidos, logo, dois itens serão removidos; por último, os elementos seguintes indicam as substituições. Com isso, "maça" e "uva" são removidos, assim como "abacaxi" e "manga" são adicionados, formando o array ["banana", "abacaxi", "manga", "laranja"].
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


**a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.**

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

A alternativa A é a correta, pois as duas afirmações são verdadeiras. A primeira está correta, a herança compartilha métodos e propriedades, assim como a segunda afirmação justiica a primeira, uma vez que o termo extends permite que uma classe herde uma herança.
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

**a) I e II são verdadeiras.**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

A alternativa correta é A, pois a classe Funcionario herda de Pessoa, permitindo o acesso direto aos atributos nome e idade. Além disso, o método apresentar() de Funcionario sobrepõe o da classe Pessoa, mas ainda chama super.apresentar(); antes de exibir o salário. A afirmação III é falsa, pois JavaScript suporta herança de classes com extends.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

**b) A asserção é verdadeira e a razão é falsa.**

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

A alternativa correta é B, pois a asserção é verdadeira ja que o polimorfismo permite que diferentes objetos respondam à mesma chamada de método de formas distintas. No entanto, a razão é falsa, pois JavaScript não suporta sobrecarga de métodos como em outras linguagens; em vez disso, utiliza a sobrescrita de métodos para implementar o polimorfismo.

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {
    let soma = 0; //inicializar a variável soma para acumular os valores corretamente.

    for (let i = 0; i < numeros.length; i++) { //'size' não é uma propriedade de arrays em JavaScript. O correto é 'length'.
        soma = 2*numeros[i]; //usar '+=', pois a soma deve acumular o dobro de cada número do array.
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4])); //saída esperada: 20

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.