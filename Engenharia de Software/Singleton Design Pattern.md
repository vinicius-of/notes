---
tags:
  - design-pattern
  - software-engineering
aliases:
  - Singleton
  - SDP
---
Fontes: 
- https://gist.github.com/PiyushMittl/ab105ca8220010365e66e9d16c0b3d72
- SHVETS, A. **Mergulho nos Padrões de Projeto**. Disponível em: <https://refactoring.guru/pt-br/design-patterns/book>.

## Padrão de Projeto Singleton

- Singleton é um padrão de projeto criacional que permite a você garantir uma classe tenha apenas uma instância, enquanto provê um ponto de acesso global para essa instância.
- A razão mais comum é controlar o acesso a algum recurso compartilhado como base de dados ou um arquivo.
- Este padrão viola o princípio de responsabilidade única.

- Objetos globais fornecem um ponto de acesso global para aquela instância.
- São inseguros uma vez que qualquer código pode sobrescrever os conteúdos daquelas variáveis.
- O padrão Singleton permite que você acesse algum objeto de qualquer lugar do programa, contudo ele também protege aquela instância de ser sobrescrita por outro código.

## Implementação

1. Fazer o construtor padrão privado, para prevenir que outros objetos usem o operador `new` com a  classe singleton.
2. Criar um método estático de criação que age como um construtor. 
	1. Esse método chama o construtor privado por debaixo dos panos.
	2. Esse método cria um objeto e o salva em um campo estático.
	3. Todas as chamadas seguintes para esse método retornam o objeto em cache.
3. Assim, o seu código será capaz de chamar o método estático da singleton e sempre que aquele método é chamado, o mesmo objeto é retornado.

## Estrutura

![[Pasted image 20250206161925.png]]

1. A classe **Singleton** declara o método estático `getInstance` que retorna a mesma instância de sua própria classe.
2. O construtor deve ser escondido do cliente.

## Exemplo

```
class Database is
	private static field instance: Database

	private constructor Database() is
		// ...Algum código de inicialização, tal como uma conexão com um servidor de base de dados...

	public static method getInstance() is
		if (Database.instance == null) then
			// Certifique que a instância ainda não foi inicializada por outra thread enquanto está estiver esperando pela liberação do "lock".
			acquireThreadLock() and then

			if (Database.instance == null) then
				Database.instance = new Database()
		return Database.instance

	public method query(sql) is
	//...Código para fazer solicitações à base de dados...

class Application is
	method main() is
		Database db = Database.getInstance()
		db.query('Select...')
		Database db2 = Database.getInstance()
		db2.query('Select...')

// db e db2 vão conter a mesma instância.
```

## Aplicabilidade

- Quando uma classe em seu programa deve ter apenas uma instância disponível para todos os clientes.
- Como exemplo um objeto de base de dados único compartilhado por diferentes partes do programa.
- O padrão singleton desabilita todos os outros meios de criar objetos da específica classe exceto pelo método especial de criação.
- Este método cria ou retorna a instância existente.