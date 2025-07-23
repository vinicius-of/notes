- Principais conceitos sobre os bancos de dados relacionais
- Finalidade é armazenar e prover acessos de dados relacionados

## Modelo Entidade-Relacionamento (MER)

- Forma de unificação das visões de um banco de dados relacional
- Baseada na Teoria Relacional

- Diagrama Entidade-Relacionamento
	- Representação visual de objetos de dados

### Elementos do MER

- Entidades
	- Qualquer coisa ou objeto que se pretende guardar informações
- Relacionamentos
	- Consiste na demonstração de associações entre entidades
- Atributos
	- Detalhes, características vinculadas à entidade.
	- Descreve uma entidade pelos atributos.

#### Entidades

- Entidades fortes
	- Não depende de outras entidades
	- Sua existência independe de outras entidades
	- Exemplo: Produto de uma loja

- Entidades fracas
	- Sua existência depende de outra entidade
	- Sozinha não tem propósito
	- Exemplo: Venda de um produto

- Entidades associativas
	- Existe quando necessário vincular uma entidade a um relacionamento existente.
	- Exemplo: Brinde por causa da venda de um produto

#### Relacionamentos

- Cardinalidade é a definição do grau de relação entre duas entidades ou tabelas.

- Tipos
	- 1 para 1 (1..1): As duas entidades se referem apenas a uma ocorrência da outra.
	- 1 para n (1..n): Uma entidade pode mencionar mais de uma ocorrência da outra, mas não o vice-versa.
	- n para n (n..n): Cada entidade pode mencionar múltiplas ocorrências sobre a outra sem restrição.

#### Atributos

- Tipos de atributos
	- Chave/identificador
		- Apenas para definir identificação da ocorrência
	- Não-chaves/descritores
		- Detalha características da entidade
	- Atributos referenciais
		- Simboliza um vínculo de uma entidade com outra
		- Não faz parte da entidade/objeto
		- Somente faz referência a outra entidade ou objeto.

- Subcategorias de atributos descritores
	- Simples
		- Atributo atômico, único valor
	- Composto
		- Vários atributos determinam a informação da entidade
		- Exemplo: Endereço com CEP, Número, Rua e etc.
	- Multivalorado
		- Valor é constituído por mais de um valor
		- Exemplo como "Telefone" que uma pessoa pode ter diversos.
		- Para normalizar, adicione um asterisco ao nome do atributo. 
	- Derivado
		- Atributos que tem relacionamento entre si.
		- "data-nascimento" e "idade" podem indicar o valor entre si.
	- Determinante
		- Distingue entidade de forma única
		- Não há valores repetidos.
		- Exemplo: Matrícula, CNPJ

