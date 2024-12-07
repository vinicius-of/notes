---
tags:
  - design-pattern
  - software-engineering
---
[Entendendo o Repository Pattern - Renicius Pagotto Fostaini](https://renicius-pagotto.medium.com/entendendo-o-repository-pattern-fcdd0c36b63b)

### Descrição
- [[Padrões de Projeto|Padrão de projeto]] bem utilizado e conhecido no desenvolvimento de sistemas.
- Sua utilização contribui no isolamento da camada de acesso a dados ([[DAL]]) com a [[Camada de negócios|camada de negócio]].
- Permite um encapsulamento da lógica de acesso a dados.
- Impulsiona o uso de [[Injeção de Dependência|injeção de dependência (DI)]].
- Aplica o [[Princípio da persistência ignorante|princípio da persistência ignorante]].
- Nossas entidades da camada de negócio não devem sofrer impactos pela forma em que são persistidas no banco de dados.

### Benefícios
- Permite a troca de [[Banco de dados|banco de dados]] sem afetar o sistema.
- Evita duplicidade de código.
- Facilita implementação de [[Testes unitários|testes unitários]].
- Diminui acoplamento entre classes.
- Padronização de códigos e serviços.

### Implementação
![[Pasted image 20240820113724.png]]
Implementação da entidade de exemplo.

### Repositórios genéricos
![[Pasted image 20240820114552.png]]

- Podem ser utilizadas em qualquer entidade da camada de negócios.
- Diminui a quantidade de código escrito.
- Porém é inviável para uso onde as entidades tem suas particularidades e regras de funcionamento.

### Repositórios especializados
![[Pasted image 20240820113811.png]]

- Esta interface atua como fachada para nossas funções.
- As funções utilizam a entidade `Client` somente.
- É necessário criar uma interface para cada entidade da camada de negócio.
- Trabalho exaustivo, porém teríamos repositórios definidas para cada entidade.