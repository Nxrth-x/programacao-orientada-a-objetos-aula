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

- [x] Introdução a programação orientada a objetos - **Eder**
- Classe - **Nina**

  - [x] Objetos - **Nina**
  - [x] Atributos - **Nina**
  - [x] Métodos - **Nina**

- Orientação a objetos
  - [x] Abstração - **Eder**
  - [x] Encapsulamento - **Eder**
  - [ ] Herança
  - [x] Polimorfismo **Nina**

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
    Cachorro rex = new Cachorro();
    rex.nome = "Rex";
    rex.corOlhos = "amarelo";
    rex.peso = 22;
    rex.quantPatas = 3;

    Cachorro bob = new Cachorro();
    bob.nome = "Bob";
    bob.corOlhos = "marrom";
    bob.peso = 13;
    bob.quantPatas = 4;
  }
}
```

### Métodos

Os métodos possibilitam a comunicação com outros objetos. São ações e, por isso, devem ter verbos como nomes.

Veja no exemplo abaixo a criação do método `latir` dentro da classe `Cachorro`

Explicando o exemplo: aqui criamos a classe `Cachorro` e demos dois atributos a ela (tamanho e nome). Logo depois, criamos o método `latir`, que terá diferentes latidos, dependendo do tamanho do cachorro.

```java
class Cachorro{
  String nome;
  int tamanho;

  public Cachorro(String nome, int tamanho) {
    this.nome = nome;
    this.tamanho = tamanho;
  }

  void latir() {
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

### Encapsulamento

Encapsulamento (também conhecido como visibilidade), é um conceito da programação orientada a objetos que nos permite esconder detalhes de implementação de uma classe. Utilizamos o encapsulamento para expor somente as características fudamentais para o funcionamento da classe, bem como também fortalecer a regra de negócio em determinadas ocasiões.

#### Exemplo

Você possui um usuário em seu sistema, ele possui `nome`, `e-mail` e `senha` como atributos. A senha deverá ser oculta das outras classes da sua aplicação, para evitar problemas de segurança. No seu sistema também, quando o `e-mail` do usuário é alterado, também lhe é mandado uma mensagem no novo e-mail informando a alteração. Como fazemos isso?

```java
public class Usuario {
  public String nome;
  // E-mail e senha são atributos privados
  private String email;
  private String senha;

  public Usuario(String nome, String email, String senha) {
    this.nome = nome;
    this.email = email;
    this.senha = senha;
  }

  public String getEmail() {
    return this.email;
  }

  public boolean setEmail(String novoEmail) {
    this.email = novoEmail;

    // Envia uma mensagem para o usuário
    // no novo e-mail informando a troca
    ServicoDeEmail.enviarEmail(novoEmail);

    return true;
  }

  public boolean setSenha(String novaSenha) {
    // Se o tamanho da senha for maior
    // ou igual a 8, alterar e retornar
    // Verdadeiro
    if(novaSenha.size() >= 8) {
      this.senha = novaSenha;
      return true;
    }

    // Retornar falso caso a senha
    // não seja válida
    return false;

  }
}
```

Com isso conseguimos estabelecer regras de negócio para o nosso sistema de maneira que somente os detalhes fundamentais sejam visíveis para as outras classes.

### Herança

Herança é um conceito da orientação a objetos que tem como principal intuíto a reusabilidade de código. A herança permite que classes possam herdar comportamentos e qualidades de uma classe base, extendendo assim suas funcionalidade e garantindo assim uma reusabilidade maior de código.

No exemplo a seguir exemplificaremos a partir de uma classe `Humano`.

```java
public class Humano {
  public String nome;
  public int idade;
  public char sexo;

  public Humano(String nome, int idade, char sexo) {
    this.nome = nome;
    this.idade = idade;
    this.sexo = sexo;
  }
}

public class Bebe extends Humano {
  public void chorar() {
    System.out.println("Buááááá!");
  }
}

public class Adulto extends Humano {
  private String cpf;

  public Adulto(String nome, int idade, char sexo, String cpf) {
    super(nome, idade, sexo);
    this.cpf = cpf;
  }

  public void pagarBoleto() {
    System.out.println("Num guento mais pagar boleto. ;-;");
  }
}
```

Nesse exemplo temos duas subclasses de humano, `Bebê` e `Adulto`, onde as duas estendem os atributos de `Humano`, porém possuem diferentes `atributos` e `métodos`.

### Polimorfismo

Polimorfismo denota uma situação na qual um objeto pode se comportar de maneiras diferentes ao receber uma mensagem.

> Importância: redução de código, simplicidade, flexibilidade.

Veja o exemplo abaixo. Nele, o método `falar` é sobre escrito na classe filha `Gato` e na classe filha `Leão`. Mesmo que `Gato` e `Leão` tenham a mesma classe mãe, suas ações são diferentes, porque suas implementações são diferentes.

```java
public class App {
  public static void main() {
    var gato = new Gato();
    var leao = new Leao();

    apresentarFelino("Gato", gato);
    apresentarFelino("Leão", leao);
  }

  // Aplicação do polimorfismo
  public static void apresentarFelino(String tipo, Felino felino) {
    System.out.printf("O %d diz:", tipo);
    Felino.falar();
  }
}


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

O polimorfismo nos permite programar para abstrações, onde o programa não se importa com o tipo de felino passado para o método `apresentarFelino`, uma vez que todas suas subclasses devem implementar o método falar.
