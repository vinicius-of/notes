Referências:
https://refactoring.guru/design-patterns/builder

## Introdução

O Builder Pattern é um padrão de criação que lida com construção de instâncias complexas de forma mais concisa e flexível, permitindo que com uma classe base consiga criar diversas formas e características sem necessitar de uma chuva de parâmetros para construí-lo, evitando o uso de undefined/null como argumentos.

## Objetivo

Analisar alguns problemas que o Builder Pattern foi descrito para resolver.

## Formação do problema

Ao encontrar uma situação em que é necessário criar uma instância de uma classe complexa e relativamente grande (mais que 3 parâmetros), utilizar a palavra-chave `new` (ou congruentes a funcionalidade em outras linguagens) torna-se inflado e gigante com abertura para erros como inserir `null`, `undefined` ou quaisquer outros valores falsos e opcionais. 

Além disso, a implementação do construtor na classe aumenta sua complexidade dependendo da implementação das regras de negócios para chegar a um resultado satisfatório como verificações de valores, transformações ou atribuições mais complexas.

A exemplo das problemáticas citadas, correlaciona-se a construção de uma casa, vejamos a seguir: 

A implementação abaixo representa a construção de uma classe chamada `Casa` e suas características como:  telhado, parede, chão, portas, janelas e cor.

```typescript
class Casa{

	private telhado;
	private parede;
	private chao;
	private portas;
	private janelas;
	private cor;

	constructor(telhado, parede, chao, portas, janelas, cor) {
		this.telhado = telhado;
		this.parede = parede;
		this.chao = chao;
		this.portas = portas;
		this.janelas = janelas;
		this.cor = cor;
	}
	
	/*
	
	...Setters e Getters teóricos...
	
	*/
}
```

Dessa maneira, a classe possui 6 parâmetros no `constructor` e a depender dos requisitos, pode chegar até 12 métodos de acessos para seus dados. 
### Construtores grandes

O problema com esta solução é uma criação inchada para uma **única** instância e extremamente rígida para modificações.

```typescript
const novaCasa = new Casa('ceramica', 'concreto', 'madeira', true, true, 'vermelho')
```

Ao todo os 6 valores passados para a criação de uma instância. Isso não é prático para escrever, ler e entender onde cada valor será atribuído, abrindo espaço para erros.

### Argumento 2

Outro problema existe na opção de usar heranças para criar subclasses/classes filhos as necessidades do desenvolvimento. Seguindo o exemplo abaixo:

```typescript
class Casa{

	private telhado;
	private parede;
	private chao;
	private portas;
	private janelas;
	private cor;

	constructor(telhado, parede, chao, portas, janelas, cor) {
		this.telhado = telhado;
		this.parede = parede;
		this.chao = chao;
		this.portas = portas;
		this.janelas = janelas;
		this.cor = cor;
	}
	
	/*
	
	...Setters e Getters teóricos...
	
	*/
}

class CasaDeMadeira extends Casa {
	constructor(portas, janelas) {
		super('ceramica', 'madeira', 'madeira', portas, janelas, 'marrom')
		
	}
}

class CasaDeConcreto extends Casa {
	constructor(portas, janelas) {
		super('concreto', 'concreto', 'concreto', false, false, 'cinza')
		
	}
}

const novaCasaDeMadeira = new CasaDeMadeira(true, false)

const novaPrisão = new CasaDeConcreto(false, false)

```

Este método resolve parcialmente o problema descrito.  Observa-se que as instâncias das novas classes resolvem o problema de inflação de parâmetros. Todavia, isto é uma solução que resolve caso o número de possibilidades seja pequena, mas lembrando que a herança cria dependências fortes entre a classe pai e as classes filhos. Se houver alterações na classe pai, isso terá um efeito em cascata onde todo filho poderá ser modificado para acomodas tais mudanças.

## Explicação da solução

O padrão de projeto *Builder Pattern* tem como ideia principal permitir construções rápidas e flexíveis de objetos por passo-a-passo sem precisar criar classes fortemente conectadas ou inflar o código fonte da aplicação. 

Para isso, é mover o código de construção da classe para objetos separados chamados *builders*. Esta classe deve conter diversos métodos que permitam adicionar valores ao que está sendo construído. Usando o exemplo anterior:

```typescript
export class Casa {
// Para facilitar a explicação, foram feitos modificações a classe original, não recomendo para utilização em aplicações reais.
  telhado: any;
  paredes: any;
  chao: any;
  portas: any;
  janelas: any;
  cor: any;
  
  constructor() {}
}

class CasaBuilder {
  casa: Casa = new Casa();
  
  constructor() {}

  buildParede(paredes) {
    this.casa.paredes = paredes;
    return this;
  }

  buildTelhado(tipo: string) {
    this.casa.telhado = tipo;
    return this;
  }

  buildChao(chao: string) {
    this.casa.chao = chao;
    return this;
  }

  /* Podem existir mais métodos para definir o que desejar */

  retornarResultado() {
    return this.casa;
  }

}

const builder = new CasaBuilder();
const novaCasa = CasaBuilder()
	.buildParede('madeira')
	.buildTelhado('ceramica')
	.buildChao('pedra')
	.retornarResultado();
```

A partir da classe *CasaBuilder*, é possível construir uma nova instância da casa utilizando qualquer método descrito e chegar no resultado desejado. Outra vantagem é aproveitar da dependência fraca do *builder* com a classe *Casa* e criar outros *builders* com diferentes implementações  para cada representação desejada.

```typescript
class CasaDePedraBuilder {

  casa = new Casa();
  
  buildParedes(paredes) {
    if (paredes !== "pedra") {
      throw new Error("A parede só pode ser de pedra");
    }
    this.casa.paredes = paredes;
    return this;
  }

  buildTelhado(tipo: string) {
    this.casa.telhado = tipo;
    return this;
  }

  buildChao(chao: string) {
    this.casa.chao = chao;
    return this;
  }

  retornarResultado() {
    return this.casa;
  }
}
```
## Conclusão

Portanto, é notável que o *Builder Pattern* resolve um problema específico com praticidade e facilita a execução para o código-fonte.
