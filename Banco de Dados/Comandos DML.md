## DML (Data Manipulation Language)

- Comandos que abarcam as operações realizadas em um banco de dados.
- Incluir, editar, excluir e consultar (CRUD).

### INSERT

- Usado para inserir dados em uma tabela.
- Sintaxe
	- `INSERT INTO (NomeTabela) (Coluna1, Coluna2, Coluna3, ...) VALUES (Valor1, Valor2, Valor3,...)`

### SELECT

- Utilizado para visualizar os dados cadastrados ou ainda recuperar dados.
- Sintaxe
	- `SELECT (Coluna) FROM (NomeTabela)`

### DELETE

- Utilizado para remover registros
- Sintaxe
	- `DELETE FROM (NomeTabela) WHERE (NomeColuna)=(Valor)`
## WHERE

- Proporciona uma condição específica de execução quando associado à alguns comandos.
- Limita os resultados e ações apenas às linhas compatíveis com a condição.
- Mais funcionalidades com [[Sufixos para comando WHERE|Sufixos]]
- Sintaxe
	- `SELECT * FROM TableClients WHERE PAIS="BRASIL"`

### UPDATE

- Utilizado para atualização de registros.
- Sintaxe
	- `UPDATE (NomeTabela) SET (NomeColuna)=(NovoValor) WHERE (NomeColuna)=(ValorCondicional)`