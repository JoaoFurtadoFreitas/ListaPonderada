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

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

A alternativa correta é A. A variável x, declarada com var, é içada (hoisting), ou seja, é reconhecida antes de sua atribuição, mas sem valor, resultando em undefined. Já a variável y, declarada com let, não é içada da mesma forma e não pode ser acessada antes da sua declaração, resultando em um erro de referência (ReferenceError).

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

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

A alternativa correta é a A, pois o erro do if consiste na sentença lógica incompleta, já que a não está sendo comparado a nada, o que gera um erro lógico.

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

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

A resposta correta é B, ou seja, o código imprime 200. A função recebe tipo como "eletronico", o que deveria gerar um resultado de 1000, porém não há um break na no case "eletronico", o que faz o código seguir para o próximo caso que faz o preco receber o valor 200, e então o break é usado, deixando preco com o valor 200.
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

d) 24

A saída será 24, ou seja, alternativa D. Resultado usa o método map com uma arrow function para multiplicar os valores do array números por 2. Já o método filter filtra os valores que são menores que 5 e o metodo reduce chama uma função callback para somar os valores maiores que 5, resultando 6+8+10=24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

A resposta correta é C, pois o método splice substitui os elementos do array nas posições 1 e dois pelos elementos "abacaxi" e "manga".
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

A alternativa correta é a letra A, pois ambas as afirmações são verdadeiras, e a segunda justifica a primeira. A herança em JavaScript é utilizada para compartilhar métodos e propriedades entre classes, permitindo que uma classe herde características de outra sem a necessidade de repetir código, o que torna a primeira afirmação verdadeira. Além disso, a herança em JavaScript é implementada por meio da palavra-chave extends, que permite que uma classe derive de outra, confirmando a veracidade da segunda afirmação. Como o uso de extends é o mecanismo que possibilita a herança mencionada na primeira afirmação, pode-se concluir que a segunda afirmação justifica a primeira, tornando a alternativa A correta.
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

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

A alternativa correta é a A, pois a classe funcionario usa extends para herdar os metodos da classe pessoa, e como os atributos nome e idade são públicos, podem ser acessados diretamente pela classe filha. Já o método apresentar da classe Funcionario sobrepõe o da classe Pessoa, pois dentro dele é chamado o apresentrar da classe pai, somada ao complemento desse método. 

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

A alternativa correta é a letra B, pois a asserção é verdadeira e a razão é falsa. O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras distintas, o que está correto na asserção. Em JavaScript, o polimorfismo pode ser implementado de várias formas, como a sobrescrita de métodos em classes derivadas, mas não através de sobrecarga de métodos como ocorre em linguagens como Java e C++, pois JavaScript não suporta sobrecarga nativa de métodos em uma mesma classe. Assim, a razão está incorreta, tornando a alternativa B a resposta correta.

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
Resposta: 

```javascript
function somaArray(numeros) {
    var soma=0;//soma é declarado e inicializado como 0
    for (let i = 0; i < numeros.length; i++) { //substitui-se .size por .length, uma propriedade mais adequada para tamanho de array
        soma += (2*numeros[i]); //soma recebe seu proprio valor somado ao dobro do valor do elemento da posição i
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

A herança funciona para herdar os valores de nome e preço, assim como o método calcularDesconto, que é escrito pela classe filha quando há a necessidade de modificar o comportamento definido originalmente na classe pai. Esse processo, conhecido como sobrescrita de métodos, permite que a classe filha personalize a funcionalidade herdada sem precisar reescrever toda a estrutura da classe base. Dessa forma, a herança promove a reutilização de código, tornando o desenvolvimento mais eficiente e flexível, além de facilitar a manutenção e a extensão das funcionalidades existentes.
 
```javascript
  class Produto {
  constructor(nome, preco) {
    this.nome = nome;
    this.preco = preco;
  }
  
  calcularDesconto() {
    this.preco *= 0.9; // Desconto de 10%
  }
}

class Livro extends Produto {
  constructor(nome, preco) {
    super(nome, preco);
  }
  
  calcularDesconto() {
    this.preco *= 0.8; // Desconto de 20% para livros
  }
}
  ```

