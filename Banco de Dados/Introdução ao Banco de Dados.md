---
tags:
  - back-end
  - database
  - software-engineering
aliases:
  - bd
  - BD
  - database
  - banco de dados
---
- Definição de modelagem de dados
	- Metodologia
	- Determina regras e negócio
	- E arquitetura do BD

- Representação ou abstração de informação da realidade

- Modelo Conceitual
- Modelo Lógico
- Modelo Físico

- Modelo de tarefa do usuário
	- Definição de regras de negócio
	- Relatório descritivo do processo

- Modelo Conceitual
	- Definição dos objetos e das regras de negócio
	- Mapeamento de domínios

- Modelo lógico
	- Definição de regras e tecnologia
	- Dados, funções e regras

- Modelo físico
	- Implementação
	- Interface gráfica, banco de dados e programas

- SGBD
	- Manejar criação, atualização, remoção e etc.

- Minimundo
	- Esquema dos conceitos da realidade em relação ao escopo do objeto.

- Abstração
	- Representação mental a partir do minimundo.

### SGBD (Sistema de Gerenciamento do Banco de Dados)

- Objetivo
	- Armazenar dados
	- Permitir operações de usuários

- Funcionalidades
	- Segurança contra acessos maliciosos
	- Proteção contra falhas sistemáticas
	- Distribuição de dados

- Usuários
	- Programador
	- Usuário final
	- DBA

### Bando de dados

^71bdf0

- Repositório para armazenar informações
- Retrata minimundo e quaisquer mudanças nestes dados

#### Arquiteturas

- Centralizada
- Descentralizada
- Distribuída
- Replicada

### Banco de dados relacional

- Teoria Relacional
- Constitui um modo de detalhar o banco a partir de conceitos matemáticos.

#### Tabelas

- Relação
	- Grupo de dados organizados em colunas e linhas
- Atributos
	- Colunas -> Atributos dos dados
- Linhas
	- Tuplas -> Valores dos atributos

- Não existem linhas idênticas
- Utilizar nomes para referenciar as colunhas
- Não há tabelas com nomes iguais
- Não existem subgrupos

#### Domínio

- Consiste em ser um grupo de relações que são determinados e nomeados
- Grupo de valores **atômicos** 

- Exemplos
	- Aniversário -> Grupo de 8 dígitos
	- Celular -> Grupo de 11 dígitos
	- Setor -> Grupo de setores de uma organização

- O conceito de domínio no contexto do banco de dados é a representação de valores ligados a uma coluna de uma tabela.

- Valores são definidos e nomeados de acordo com os atributos.

#### Chave primária

- Impede repetições de registros a partir da definição de um atributo/coluna como único
	- Exemplo: Matrícula de um aluno

- A tabela pode ter somente uma chave primária, a questão com chaves compostas é que é **uma chave primária** composta por vários atributos dentro da tabela.

- Chaves Simples
	- Constituído por um único campo da tabela
	- Não terá dois valores iguais entre registros
	- Não pode ser nulo

- Chave Composta
	- Constituída por mais de um campo
	- Valores podem se repetir, mas não a combinação dos mesmos

- Chave estrangeira
	- Faz referência a ligação entre diferentes tabelas.
	- Uma chave primária que pertence a outra tabela.
	- Tem como objetivo identificar o relacionamento entre tabelas

- Objetivos
	- Valor
	- Registro

#### Normalização

- Consiste em um conjunto de regras que buscam organização de um projeto de BD.
- Reduzir quantidade de informações desnecessárias
- Ampliar integridade e desempenho

- Primeira Forma Normal (1FN)
	- Tabela com todas as colunas compostas por um único valor/valor atômico
	- Remover itens repetidos da estrutura e dos registros

- Segunda Forma Normal (2FN)
	- A tabela precisa ser 1FN
	- Contém atributos que não participam da chave primária, mas depende dela.
	- Em uma tabela de chaves compostas, o atributo só precisa depender de qualquer chave definida.

- Terceira Forma Normal
	- A tabela precisa ser 2FN.
	- A tabela não pode conter campos que dependam de outros não definidos como chaves.
	- Uma coluna pode depender de uma chave primária e depender de um campo que não é, logo temos que desfazer a segunda relação e manter a primeira.