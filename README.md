# Trabalho de LPOO - Orientação a objetos

iFood 🍇

## Tópicos

- [ ] Introdução a programação orientada a objetos - **Eder**
- Classe - **Nina**

  - [ ] Objetos - **Nina**
  - [ ] Atributos - **Nina**
  - [ ] Métodos

- Orientação a objetos
  - [ ] Abstração - **Eder**
  - [ ] Encapsulamento
  - [ ] Herança
  - [ ] Polimorfismo

## Introdução a programação orientada a objetos

A programação orientada a objetos é um dos principais paradigmas de programação, usado e testado extensivamente em casos reais onde um dos requisitos do projeto é escalabilidade para equipes. A orientação a objetos nos traz um nível de abstração e agilidade essêncial para o desenvolvimento de grandes projetos.

A programação orientada a objetos possui quatro conceitos essenciais para sua compreensão, sendo eles:

- Abstração
- Encapsulamento
- Herança
- Polimorfismo

Esses são conceitos importantes para facilitar a compreensão de uma base de código;

<!-- Continuar isso daqui quando tiver mais ideia -->

> Enchendo linguiça... 🐷

## Classe

Uma classe é uma espécie de molde
para a criação de objetos. Nela, é permitido armazenar propriedades (atributos/características) e métodos (função).

- Características das classes
Toda classe possui um nome;
Possuem visibilidade, exemplo: public, private, protected;
Para criar uma classe basta _declarar a visibilidade + digitar a palavra reservada class + NomeDaClasse + abrir e fechar chaves { }._

  <br>
  
  ```java
   public class Teste{
  //ATRIBUTOS OU PROPRIEDADES
  //MÉTODOS
  }
  ```
<!--
Pular linha
<br />

Linha horizontal

<hr />

Link
[Google](https://google.com)

Imagem
![image](https://arquivo.devmedia.com.br/artigos/Thiago_Varallo/Introducao_POO_Java/Introducao_POO_Java2.jpg)
-->

Na imagem abaixo, temos uma representação de classe, contendo as características/atributos dos cachorros: orelhas grandes ou pequenas, por exemplo; e métodos/funções: andar, falar, comer.

![image](https://arquivo.devmedia.com.br/artigos/Thiago_Varallo/Introducao_POO_Java/Introducao_POO_Java2.jpg)

### Objetos

Os objetos são características definidas pelas classes. Neles é permitido instanciar objetos da classe para inicializar os atributos e invocar os métodos.

A figura abaixo mostra que todo objeto é algo que existe, uma coisa concreta, já a classe é considerada como um modelo ou projeto de um objeto, sendo algo que não consegue tocar.

![image](https://arquivo.devmedia.com.br/artigos/Thiago_Varallo/Introducao_POO_Java/Introducao_POO_Java3.jpg)

### Atributos

Os atributos são as propriedades de um objeto. Veja no exemplo abaixo a definição da classe `Cachorro`, que tem como atributos nome, peso, cor dos olhos e quantidade de patas.

```java
public class Cachorro {
	public String nome;
	public int peso;
	public String corOlhos;
	public int quantPatas;
}
```

Na imagem abaixo, criamos alguns objetos do tipo `Cachorro` e designamos a eles alguns atributos:

```java
public class TestaCaes {
	public static void main(String[] args) {
		Cachorro cachorro1 = new Cachorro("Bob", 12);

		Cachorro cachorro2 = new Cachorro();
		cachorro2.nome = "Rex";
		cachorro2.corOlhos = "amarelo";
		cachorro2.peso = 22;
		cachorro2.quantPatas = 3;

		Cachorro cachorro3 = new Cachorro();
		cachorro3.nome = "Bob";
		cachorro3.corOlhos = "marrom";
		cachorro3.peso = 13;
		cachorro3.quantPatas = 4;
	}
}
```

### Abstração

A abstração é a base para a programação orientada a objetos, ela nos permite representar qualidades e ações da vida real em código. Demonstraremos a seguir dois exemplos, um no paradigma estrutural e um segundo em orientação a objetos

<!-- Exemplo programação estrutural -->

#### Exemplo 1 - Paradigma estrutural

Imagine o seguinte caso: Você precisa representar uma `pessoa` dentro do seu código, essa pessoa possui `nome` e `idade` e também pode `dizer olá`. No paradigma estutural fariamos da seguinte forma:

```java
public class App {
  public static void main(String[] args) {
    // Qualidades
    String nomePessoa1 = "John";
    int idadePessoa1 = 19;

    // Comportamento
    System.out.printf("%s tem %d anos e diz: Olá!\n", nomePessoa1, idadePessoa1);
  }
}
```

Neste exemplo reparamos alguns problemas do paradigma estrutural: Os detalhes de implementação ficam expostos, as informações da pessoa são públicos e, em geral, o código tende a ficar desorganizado.

#### Exemplo 2 - Paradigma orientado a objetos

<!-- Exemplo programação orientada a objetos -->

Nesse segundo exemplos temos o código representado em orientação a objetos, onde um objeto do tipo pessoa possui os atributos `nome`, `idade` e também possui o método `dizerOla`.

```java
public class App {
  public static void main(String[] args) {
    // Comporamento e qualidades agrupadas em uma abstração
    Pessoa pessoa1 = new Pessoa("John", 19);

    // Execução de um comportamento de um determinado objeto
    pessoa1.dizerOla();
  }
}

public class Pessoa {
  String nome;
  int idade;

  public Pessoa(String nome, int idade) {
    this.nome = nome;
    this.idade = idade;
  }

  public void dizerOla() {
    System.out.printf("%s tem %d anos e diz: Olá!\n", this.nome, this.idade);
  }
}
```

Nesse exemplo, tudo o que um usuário que irá utilizar a classe precisa saber é como instanciar um objeto do tipo `Pessoa`. Contrário ao outro exemplo, ele não precisa saber os detalhes de implementação de um objeto desse tipo, caso precise que uma pessoa diga olá o método `.dizerOla()` poderá ser chamado.

## Olá, mundo!
