---
tags:
  - software-engineering
  - design-pattern
aliases:
  - KISS
---
Fonte: http://principles-wiki.net/principles:keep_it_simple_stupid

- O princípio de KISS é sobre buscar pela simplicidade.
- Linguagens de programação, frameworks e [[APIs]] tem formas poderosas para criar soluções sofisticadas.
- Só que alguns desenvolvedores veem-se tentados a criar soluções "espertas" para usar essas funcionalidades complexas.

- Uma solução que segue o KISS pode aparentar ser chato ou estúpido, mas é simples e compreensível.

## Racionalização

- Soluções simples são mais fáceis de manter.
- A vantagem da simplicidade é mais vantajoso quando a pessoa que mantém o software não é o mesmo que o escreveu.

## Estratégias

- Evitar herança, polimorfismo, ligação dinâmica e entre outros conceitos complicados de [[POO]]. Use delegação e construções *if*.
- Evite otimizações *low-level* de algoritmos, especialmente quando envolvendo Assembler, operações-bit e ponteiros.
- Use soluções de força-bruta simples em vez de algoritmos complicados.
- Evite ter várias classes e métodos.