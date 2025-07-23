## Estrutura e Layout do projeto

- Primeira fase é análise de **requisitos** e **delimitação** dos objetivos do banco de dados.
- Segunda fase é a organização dos dados em **tabelas**.
- Terceira fase é a especificação de chaves primárias e relacionamentos.
- Quarta fase é a padronização/formalização de tabelas.

> [!INFO] Resumo
> Primeira fase = análise de requisitos e delimitação
> Segunda fase = Organização
> Terceira fase = Especificação
> Quarta fase = padronização

### 1. Análise de requisitos

- Considerar as perspectivas envolvidas referentes à criação de um banco de dados para uma entidade qualquer.
- Fazer coleta de informações que podem ser úteis.
	- Realizar entrevistas com potênciais usuários.
	- Pesquisar bancos semelhantes para entender melhor o funcionamento.

- Analisar o banco de dados antigo se tiver.
- Verificar o que pode ser aproveitado.
- Fazer uma lista conceitual para orientar sobre quais dados é desejável armazenar.

Essas informações levantadas construirão um inventário de dados e descreverá tabelas e campos contidos.

> [!warning] 
> Evitar o uso de um mesmo ponto de dados em duas ou mais tabelas, porque isso geraria complexidade.

### 2. Estrutura de banco de dados

- Necessário entender como dados relacionais são estruturados
- Necessário uma representação visual do BD.

- Os dados relacionais serão agrupados em tabelas formadas em linhas e colunas.
- Cada linha da tabela é um registro.
- As colunas representam atributos ou campos.
	- Conterão um único tipo de informação.

> [!warning]
> Os dados devem permanecer consistentes entre um e outro.

	- Atribuir tipo apropriado para cada coluna.

...[[Tipos de dados comuns para colunas]]...

- Uma versão mais geral do BD pode ser obtida com uso de DER.

> [!TIP] Dica
> Nome de usuários são boas PKs.

> [!warning]
> Estrutura de dados lógicos e de dados físicos devem estar estimadas na capacidade do tamanho. Isso é importante para determinar o nível de desempenho e o espaço de armazenamento.

- Tudo isso faz parte da segunda etapa.
	- Esquematizar a estrutura por representação gráfica.
	- Desenvolver tabelas.
	- Compreender a relevância de determinar o nível de desempenho e espaço de armazenamento.
	- Delimitar tipos de relações entre as diferentes tabelas.

### 3. Criando relações

> [!SUCCESS] Definição
> A identificação da cardinalidade auxilia o desenvolvedor ou o admin do BD na **divisão de dados em tabelas de forma eficiente**.

#### Relação uma a uma (1:1)

- Cardinalidade de 1 para 1.
- Indica relações que são **unitárias**.
- Pode ser feito com uma coluna sendo repetida em ambas as tabelas e sendo PKs.

#### Relação uma para muitas (1:n)

- Um registro se associa a diversas entradas existentes em outra tabela.
- Exemplo seria um quadro de cursos e alunos, onde que um curso pode ter vários alunos, mas cada aluno somente pode estar associado a um curso.

#### Relação muitas para muitas (n:n)

- Diversas entidades de uma tabela associadas a diversas de outra tabela.
- Exemplo seria em um contexto de vendas e produtos, onde uma venda pode ter vários produtos e um produto pode estar em várias vendas.

#### Relações recursivas

- Relações em uma tabela que apontam para si mesma.
- Exemplo seria uma tabela de colaboradores com um atributo chamado "diretor". Este campo aponta para outra instância da mesma tabela.
- Denominado também como *autorrelacionamento*.
- Casos especiais e pouco recorrentes.

#### Relações redudantes

- Entidades são relacionadas mais de uma vez, podendo ser de forma direta ou indireta.
- Entidades podem indicar relações mesmo sem explicitamente estarem conectadas.
- Por isso existe uma redundância entre essas relações.
- Exemplo seria um contexto de `Alunos`, `Professores` e `Aulas`.
	- O `Aluno` está diretamente relacionado com o `Professor`.
	- O `Aluno` está diretamente relacionado com a `Aula`.
	- O `Professor` está diretamente relacionado com a `Aula`
	- Se a relação entre `Aluno`-`Professor` for removida, daria para inferir qual o professor do aluno por meio da tabela `Aula`.

### 4. Normalização/Formalização

>[!SUCCESS] Definição
>	A última etapa do projeto é a padronização de tabelas. Ocorre após a confecção do esquema de tabelas.

- Serão aplicadas as regras de normalização.
- Sua função é de atuar na certificação da estrutura correta das tabelas.
- Regras similares aos padrões de qualidade são aplicados dentro das indústrias.
- Isto trata-se de uma prática imposta com o surgimento de banco de dados especializados em processamento de transações on-line (Conhecido também como OLTP).

#### Primeira Forma Normal (1FN)

- [[Introdução ao Banco de Dados#Normalização]]
- Explicado por completo aqui.
- Procura normalizar especificações em cada uma das células da tabela.
- Devem somente comportar um valor.
- Atributos devem ser atômicas e isentos de grupos repetidos.

#### Segunda Forma Normal (2FN)

- Esse formulário aponta para os atributos que devem ser dependentes somente de uma chave primária.
- A intenção é de organizar os relacionamentos e evitar as duplicações.

#### Terceira Forma Normal (3FN)

- Adicionará a premissa de que toda coluna com atributos não-chave sejam independentes de outros atributos não-chaves.
- Devem continuar dependentes das chaves-primárias.
- Significa que alterações em um atributo não-chave não pode alterar outros atributos.