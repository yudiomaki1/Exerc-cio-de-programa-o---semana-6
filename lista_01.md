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
a) A saída será undefined seguido de erro ✅

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log 

Justificativa: <br>
O resultado será undefined porque o "console.log(x)" foi utilizado antes de "x" ter um valor atribuido a ele. <br>
Já o erro ocorre porque a variavel "let" não permite o acesso antes de sua inicialização, diferente da variavel "var" 

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

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)✅

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Justificativa: <br>
Alternativa B, assim o codigo irá analisar se ambos os numeros são iguais a zero, para assim identificar de forma correta se é ou não um numero invalido 
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

b) O código imprime 200. ✅

c) O código imprime 50.

d) O código gera um erro.

Justificativa: <br>
Após o case "eletronico" não há um break, por isso o codigo continuou a ser executado até que h aja um break. Assim retornando o valor 200.
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

d) 24 ✅

Justificativa:<br>
Primeiramente a função ".map" vai multiplicar o array "numeros" por 2. Resultado: numeros = [2, 4, 6, 8, 10] <br>
A Função ".filter" vai remover numeros menores ou iguais a 5 do array. Resultado: numeros = [6, 8, 10] <br>
.reduce vai reduzir todos os numeros a um unico valor, nesse caso irá somar todos os numeros. Resultado: numeros = [24]
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"] ✅

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

Justificativa: <br>
Na linha de comando ``lista.splice(1, 2, "abacaxi", "manga");`` o numero 1 define a posição na qual começará a modificação, o numero 2 define a quantidade de elementos que devem ser removidos a partir da posição definida, as strings "abacaxi" e "manga" serão adicionadas substituindo os itens removidos do array.
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira. ✅

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Justificativa: <br>
As duas afirmações estão corretas e se justificam, não seria possivel herdar nenhuma classe sem a utilização de "extends".
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

a) I e II são verdadeiras. ✅

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

Justificativa: <br>
Ao utilizar `extends` e a classe herdar os atributos da classe mãe, todos os atributos podem ser acessados diretamente.
A classe filha ao utilizar `apresentar()` sobrepôs a função da classe mãe, porém, ao utilizar `super.apresentar()` a função da classe mãe e chamada.
O JavaScript suporta perfeitamente classes.

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa. ✅

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Justificativa: <br>
A razão esta incorreta, o polimorfismo pode ocorrer como no exercicio anterior, onde a classe mãe foi sobreposta, ou através do duck typing.

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.length; i++) {
        soma = 2*numeros[i];
    }
    return soma;
} 
console.log(somaArray([1, 2, 3, 4]));
```

Código Corrigido: <br>
```javascript
function somaArray(numeros) {
    let soma = 0;   //agora "soma" não é mais undefined.

    //A estrutura for é utilizada para a seleção dos numeros individualmente.
    for (i = 0; i < numeros.length; i++) {  //o uso de .length é mais adequado para acessar array. 
        soma += 2*numeros[i];    // "+=" É utilizado para que os numeros sejam multiplicados e após somados, anteriormente eles eram apenas multiplicados por 2.       
    }
    return soma; 
} 
console.log(somaArray([1, 2, 3, 4]));
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

``` javascript
class Produto{
    constructor(nome, preco){  //define os atributos nome e preço
        this.nome = nome;
        this.preco = preco;
    }
    calcularDesconto(){
        return this.preco*0.9  //calcula o desconto de 10%
    }
}

class Livro extends Produto{  // A classe "Livro" herda a classe "Produto"ao utilizar "extends" 
    constructor(nome, preco){  //Define os atributos
    super(nome, preco)  //inicializa os atributos herdados da classe "Produto"
    }
    calcularDesconto(){
        return this.preco*0.8  //calcula o desconto de 20%
    }
}
```
Explicação:<br>
A classe "Livro" herda os atributos de "Produto", e as acessa através da utilização de "super(nome, preco)"

