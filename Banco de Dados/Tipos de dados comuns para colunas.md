## CHAR

- Define o tamanho específico de texto.
- A definição configura a quantidade de bytes, não a quantidade de caracteres.
- Exemplo
	- `CHAR(10)`
	- Pode armazenar 10 caracteres que usam a codificação de byte único.
	- Entretanto, se essa codificação for, como exemplo, Unicode (dois bytes por caractere), o valor `CHAR(10)` seria menos de 10 caracteres. 

## VARCHAR

- Permite definir o campo para receber textos de tamanhos diversos. Não é necessário definir limite

## TEXT

- Define grandes quantidades de texto.
- Texto não tem limite lógico para o tamanho além o máximo do BD.
	- Este tipo de dado é armazenado na área especifica para `BLOB`'s.
	- Expectativa desde dado é para serem textos grandes.

## INT

- Define números inteiros, sejam eles positivos ou negativos.

## FLOAT, DOUBLE

- Define que também é possível armazenar no banco de dados os números de pontos flutuantes.

## BLOB

- Define o registro de dados binários

[!important]
> Importante saber que sistemas de gestão de banco de dados proporcionam registros do tipo "Auto-numeração". Isso serve para gerar uma numeração exclusiva para cada registro.