- Integridade referencial
	- Domínio
	- Vazio
	- Chave
	- Usuário

- Restrições de integridade
	- A integridade de dados tem por finalidade a manutenção e garantia de consistência.

- Tipos de integridade
	- Referencial
		- Garante que dados não sejam corrompidos
		- Impossibilita que a existência de um registro filho sem haver um registro pai.
		- Um registro pai não pode ser excluído se conter um registro filho.
		- Relacionamento determinado por chaves estrangeiras.
	- Vazio
		- Determina se o campo da coluna é opcional ou obrigatório.
	- Chave
		- Determina que os valores inseridos sejam únicos e não nulos (PK).
	- Definida pelo usuário
		- Refere-se a regas de negócios.
		- Determinadas pelos usuários do BD.
	- Domínio
		- Domínio do valor (o valor e seu tipo).
		- Valores aceitos serão inseridos na tabela de acordo com o seu domínio.
		- Categorias
			- Check
			- Nulidade
			- Unique
			- Default