Referências:
https://refactoring.guru/design-patterns/builder

## Introdução

O Builder Pattern trata-se de um padrão de criação que lida com construção de instâncias complexas de forma mais concisa e flexível, permitindo que uma classe base possa criar diversas formas e características sem necessitar de uma chuva de parâmetros para construí-lo, evitando o uso de undefined/null como argumentos.

(Adicionar um resumo da formação do problema)
(Um breve explicação sobre a conclusão e como este padrão atua)

## Objetivo

(Explicar qual o objetivo do desenvolvimento deste tema)

## Formação do problema

Um exemplo seria a construção de uma casa, vamos detalhar melhor o problema citado.

Devemos criar para representar a construção completa de uma casa e suas características, como telhado, parede, chão, portas, janelas, chaminé, cor e entre outros. Para implementarmos de forma concreta, uma das soluções seria criar uma classe chamada `Casa` e seu *constructor* recebendo esses detalhes.

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

### Argumento 1

O problema com esta solução é, além de uma implementação inchada para uma **única** instância, fica extremamente rígida. 

```typescript
const novaCasa = new Casa('ceramica', 'concreto', 'madeira', true, true, 'vermelho')
```

Foram ao todo 6 valores passados para a criação de uma instância. Se quisermos alterar qualquer detalhe sobre a `novaCasa`, seguindo a orientação de objetos, seria assim:

### Argumento 2

```typescript
novaCasa.setTelhado('concreto')
novaCasa.setParede('drywall')
novaCasa.setJanelas(false)
```

Três chamadas de métodos para alcançar o resultado desejado.

### Argumento 3

Entretanto, em Orientação a Objetos, existe a opção de metodologia de heranças para criar subclasses/classes filhos às necessidades do desenvolvimento. Com isso, pode ser:

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

Este método resolve parcialmente o problema descrito. Pode-se observar que as instanciações de novas classes livram o problema de inflação de parâmetros. Todavia, isto é uma solução temporária se não for repensada brevemente, (por conta da necessidade) de criar uma nova classe para cada variação desejada da classe pai. (Ademais continuamos com o problema de caso queiramos modificar detalhes individuais sobre o conteúdo de um objeto, seria necessário modificar por meio de métodos ou acessos diretos ao atributo.)
## Explicação da solução

O padrão de projeto *Builder Pattern* tem como ideia principal permitir construções rápidas e flexíveis de objetos por passo-a-passo sem precisar criar classes fortemente conectadas ou inflar o código fonte da aplicação. 

Para isso, é removido o código de construção da classe em si e mové-la para objetos separados chamados *builders*.



## Metodologia

## Conclusão