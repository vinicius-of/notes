## O que é banco de dados?

- Um [[Introdução ao Banco de Dados#^71bdf0|banco de dados]] é um sistema de armazenamento de dados que pode guardar esses dados de forma estruturada ou semi-estruturada.

- Um banco de dados é complexo para armazenar dados porque requer utilizar normalizações e esquemas de modelagem.

- Um banco de dados pode ser categorizado das seguintes formas:
	- [[Relacionamentos|Banco de dados relacional]]
		- Armazena dados estruturados.
		- Representa os dados de forma tabular(tabelas, linhas e colunas).
	- Banco de dados não-relacionais
		- Armazena dados de forma semi-estruturada (Explicado dentro de Big Data).
		- Pode ou não ter semelhanças com dados tabelados.

- Banco de dados são ricos em funcionalidades como:
	- Linguagem especializada para busca e retorno de informação. (SQL)
	- Estratégias de modelagem especializados para otimizar resultados para diferentes casos de uso.
	- Há um controle mais preciso e otimizado sob a transformação de dados em estruturas úteis ou relatórios.

## O que é um Data Warehouse?

![[Pasted image 20251105235148.png]]

- Uma armazém de dados designado para processos analíticos.
- Normalmente trata-se de um banco de dados orientado pela coluna.

- Empresas tendem a ter terabytes e milhões de dados.
- É necessário uma forma rápida de produzir relatórios analíticos a partir deste armazém.

- *Data warehouses* geralmente executam agregações:
	- Uma agregação é o agrupamento de dados como encontrar o total ou a média dos valores.
	- *Data warehouses* são otimizados em torno de colunas.
- *Data warehouses* geralmente são construídos para se manterem "esquentados":
	- Isto significa que eles podem retornas resultados muito rápido mesmo com uma quantidade extremamente alta de dados.

- *Data warehouses* são acessados infrequentemente já que estes não foram construídos com intuito de criar relatórios em tempo real, mas sim uma ou duas vezes na semana.

## O que é armazenamento de chave-valor?

![[Pasted image 20251110235549.png]]

- É uma tipo de armazenamento de dados não-relacional (NoSQL). 
- Comumente utilizado em bancos de dados que utilizam o conceito de*key-value* são simples e fáceis de implementação.
- Armazenamento de dados com chave-valor são simples e rápidos.
- <mark style="color: white; background: #FF5582A6;">Não contém</mark> funcionalidades como:
	- Relacionamentos
	- Indexes
	- Agregações

- Um par de chave-valor são formadas for <mark style="background: #ABF7F7A6;">chaves únicas</mark> ao lado de seu valor.

## O que é um banco de dados orientado a documentos?

![[Pasted image 20251110235812.png]]

- É outro tipo de banco de dados que armazena **documentos** como sua forma primária de estrutura.
- Este pode trabalhar com dados semiestruturados como XML, JSON e entre outros.
- Os documentos são uma subclasse do armazenamento de chave-valor.

## Serviços de banco de dados NoSQL,

- Temos três serviços principais:
	- DynamoDB
	- DocumentDb
	- Amazon Keyspaces

- 