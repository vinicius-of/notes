Existem outras formas de utilizar

## WHERE BETWEEN

- Permite definir intervalo de valores a ser selecionado.
- Sintaxe
	- `SELECT * FROM (NomeTabela) WHERE (NomeColuna) BETWEEN (Valor1) AND (Valor2)`

## WHERE IN

- Cria uma lista de dados que será retornado na consulta.
- Server como atalho para múltiplos comandos `OR`.
- Sintaxe
	- `SEELCT * FROM (NomeTabela) WHERE (NomeColuna) IN (Valor1, Valor2, Valor3)`
- No exemplo acima, o comando `SELECT` retornará todos os registros que conterem qualquer valor indicado na coluna.

## WHERE NOT

- Utilizado quando não é desejado visualizar qualquer dado.
- Sintaxe
	- `SELECT * FROM (NomeTabela) WHERE NOT (NomeColuna)=(ValorNaoDesejado)`

## WHERE LIKE

- Verifica se uma séria de caracteres corresponde a um padrão especificado.
- Precisa ser utilizado em conjunto com os comandos abaixo para seu funcionamento.

### Colchetes `[ ]`

- Qualquer caractere único no intervalo ou conjunto.
- Exemplo
	- ``[a-f]`` é igual à `[abcdef]`
	- Será retornado qualquer valor que corresponder com a expressão acima.
	- `...WHERE (NomeColuna) LIKE "[D-X]ia"`

### Variação dos Colchetes `[^]`

- Qualquer caractere único que não esteja no intervalo ou conjunto.
- Exemplo
	- `...WHERE (NomeColuna) LIKE "Mi[^A]%"`