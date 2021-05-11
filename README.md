iFood 🍇

<!--
HELPERS

Pular linha
<br />

Linha horizontal

<hr />

Link
[Google](https://google.com)

Imagem
![image](https://arquivo.devmedia.com.br/artigos/Thiago_Varallo/Introducao_POO_Java/Introducao_POO_Java2.jpg)
-->

## Tópicos

- [ ] Introdução a programação orientada a objetos - **Eder**
- Classe - **Nina**

  - [x] Objetos - **Nina**
  - [x] Atributos - **Nina**
  - [x] Métodos - **Nina**

- Orientação a objetos
  - [x] Abstração - **Eder**
  - [x] Encapsulamento
  - [ ] Herança
  - [ ] Polimorfismo **Nina**

<!--

Extensão: Markdown preview

Abrir o arquivo bunitin: Ctrl + K, V

 -->

## Introdução a programação orientada a objetos

A programação orientada a objetos, também conhecida como POO, é um dos principais paradigmas de programação, usado e testado extensivamente em casos reais onde um dos requisitos do projeto é escalabilidade para equipes. A orientação a objetos nos traz um nível de abstração e agilidade essencial para o desenvolvimento de grandes projetos.

A POO possui quatro conceitos essenciais para facilitar a compreensão de uma base de código, sendo eles:

- Abstração
- Encapsulamento
- Herança
- Polimorfismo

Além disso, existem muitos prós ao programar usando a LPOO:

- Torna os programas mais gerenciáveis (manutenções e modificações, por exemplo)
- Escalabilidade do programa
- Por trabalhar com objetos, permite que você represente melhor o mundo real
- Os programas em POO são mais fáceis de ler e entender
- Facilita a reutilização de objetos, aumentando a velocidade de programação
- Mais fácil depurar, porque os objetos são autônomos

## Classe

Uma classe é uma espécie de molde para a criação de objetos. Nela, é permitido armazenar propriedades (atributos/características) e métodos (funções). Usamos classes para representar objetos do mundo real no código.

### Características das classes

Toda classe possui um nome;
Possuem visibilidade, exemplo: public, private, protected;
Para criar uma classe basta declarar a visibilidade + digitar a palavra reservada class + NomeDaClasse + abrir e fechar chaves { }.

```java
public class Teste {
  //ATRIBUTOS OU PROPRIEDADES
  //MÉTODOS
}
```

Na imagem abaixo, temos uma representação de classe, contendo as características/atributos dos cachorros: orelhas grandes ou pequenas, por exemplo; e métodos/funções: andar, falar, comer.

![image](https://arquivo.devmedia.com.br/artigos/Thiago_Varallo/Introducao_POO_Java/Introducao_POO_Java2.jpg)

### Objetos

Os objetos são características definidas pelas classes. Neles é permitido instanciar objetos da classe para inicializar os atributos e invocar os métodos.

A figura abaixo mostra que todo objeto é algo que existe, uma coisa concreta. Já a classe é considerada como um modelo ou projeto de um objeto, sendo algo que não consegue tocar.

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

### Métodos

Os métodos possibilitam a comunicação com outros objetos. São ações e, por isso, devem ter verbos como nomes.

Veja no exemplo abaixo a criação do método `latir` dentro da classe `Cachorro`

Explicando o exemplo: aqui criamos a classe `Cachorro` e demos dois atributos a ela (tamanho e nome). Logo depois, criamos o método `latir`, que terá diferentes latidos, dependendo do tamanho do cachorro.

```java
  class Cachorro{
	int tamanho;
	String nome;


	void latir(){
		if(tamanho > 60)
			System.out.println("Wooof, Wooof!");
		else if(tamanho > 14)
			System.out.println("Ruff!, Ruff!");
		else
			System.out.println("Yip!, Yip!");
	}
}
```

<!-- https://stackedit.io/ -->

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

### Polimorfismo

Polimorfismo denota uma situação na qual um objeto pode se comportar de maneiras diferentes ao receber uma mensagem.
Veja o exemplo abaixo. Nele, o método `falar` é sobre escrito na classe filha `Gato` e na classe filha `Leão`. Mesmo que `Gato` e `Leão` tenham a mesma classe mãe, suas ações são diferentes, porque suas implementações são diferentes.
Importância: redução de código, simplicidade, flexibilidade.

```java
abstract class Felino {
  public void falar();
}

public class Gato extends Felino {
  @Override
  public void falar() {
    System.out.println("Miau!");
  }
}

public class Leao extends Felino {
  @Override
  public void falar() {
    System.out.println("Rawrrrrr!");
  }
}
```

Exemplo:
Existem diferentes tipos de livros: ebooks e físicos. Podemos criar uma classe `Livro` e a utilizarmos quando nos referirmos a ebooks e livros físicos também. Veja:

```java
public class App {
  public static void main(String[] args) {
    LivroFisico livroFisico = new LivroFisico("Alice no país das maravilhas", "Lewis Carroll");
    Ebook ebook = new Ebook("Alice no país das maravilhas", "Lewis Carroll");

    CarrinhoDeCompras.adicionaLivro(livroFisico);
    CarrinhoDeCompras.adicionaLivro(ebook);
  }
}

// TODO
// 1 - Livro

// 2 - Carrinho de compras

Livro.adicionar(carrinhoDeCompras);

public class CarrinhoDeCompras {
  private ArrayList<Livro> livros;

  public CarrinhoDeCompras() {
  }

  public void adicionarLivro(Livro livro) {
    this.livros.add(livro);
  }
}

public abstract class Livro {
  private String nome;
  private String autor;
  private boolean preco;
  private boolean isbn;

  public Livro(String nome, String autor, double preco, int isbn) {
    this.isbn = isbn;
    this.nome = nome;
    this.autor = autor;
    this.preco = preco;
  }

  public boolean adicionar(CarrinhoDeCompras carrinhoDeCompras);
}

public class LivroFisico extends Livro {
  private String materialDaCapa;

  public LivroFisico (String nome, String autor, double preco, int isbn, String materialDaCapa) {
    super(nome, autor, preco, isbn);
    this.materialDaCapa = materialDaCapa;
  }

  public boolean adicionar(CarrinhoDeCompras carrinhoDeCompras) {
    carrinhoDeCompras.adicionarLivro(this);
  }
}

// Livro digital com desconto de 20%

public class LivroDigital extends Livro {
  private boolean redimensionavel;

  public void main(String[] args) {
    var HarryPotter = new LivroDigital(...);

    HarryPotter.adicionar(carrinhoDeCompras);
  }

  public LivroDigital (String nome, String autor, double preco, int isbn, boolean redimensionavel) {
    super(nome, autor, preco, isbn);
    this.redimensionavel = redimensionavel;
  }

  // livroDigital

  public boolean adicionar(CarrinhoDeCompras carrinhoDeCompras) {
    var livroDigital = new LivroDigital(this.nome, this.autor, this.preco * 0.8, this.isbn, this.redimensionavel);
    carrinhoDeCompras.adicionaLivro(livroDigital);
  }

}

```

O polimorfismo permite que classes abstratas consigam receber comportamentos através de classes concretas.

<!--

    Autor autor = new Autor();
    autor.setNome("Nathan C.");

    LivroFisico fisico = new LivroFisico(autor);
    fisico.setNome("Java Programming");
    fisico.setValor(180);

    Ebook ebook = new Ebook(autor);
    ebook.setNome("C# Programming");
    ebook.setValor(120);

    CarrinhoCompras carrinho = new CarrinhoCompras();
    carrinho.adicionalLivro(fisico);
    carrinho.adicionalLivro(ebook);

    System.out.println("Total: " + carrinho.getTotal());

 -->
