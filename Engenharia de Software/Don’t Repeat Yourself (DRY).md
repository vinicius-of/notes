---
tags:
  - design-pattern
  - software-engineering
aliases:
  - DRY
---
Fonte: https://injulkarnilesh.github.io/design-principles/DRY/

- DRY significa "Don't Repeat Yourself" (Não se repita).
- Não é sobre repetir código, mas sim duplicar lógica de negócios ou ideia de negócios.

> Toda parte de conhecimento deve ter uma única, não-ambíguo, representação autoritária dentro do sistema.

- Aqui o conhecimento é a representação da funcionalidade do negócio ou da entidade de negócio.
- Isso também envolve o princípio de [[Single Responsability Principle (SRP)|SRP]].

- Nem toda duplicação de código causa a duplicação da lógica.
- O DRY refere-se somente à duplicações que causam representações ambíguas de fontes de conhecimento diferentes ou iguais em vários lugares.

Exemplos: https://github.com/injulkarnilesh/design-principles/tree/master/DRY/example