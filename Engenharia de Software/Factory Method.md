---
tags:
  - design-pattern
  - software-engineering
aliases:
  - factory
---
Fonte: Alexander Shvets. Mergulhando em padrões de projetos. pág. 80.

- O **Factory Method** é um padrão criacional de projeto que fornece uma [[Engenharia de Software/Interfaces|interface]] para criar objetos em uma superclasse, mas permite que as **subclasses alterem o tipo de objetos** que serão criados.

## Problema

- Imagine que você criou uma aplicação de gerenciamento de logística em que lida somente com transportes de caminhões e a maior do seu código fica dentro da classe `Caminhão`.
- Depois de um tempo, sua aplicação se torna popular.
- Todos os dias você recebe dezenas de solicitações de empresas diversas de transporte marítimo para incorporar a logística marítima na aplicação.
- O problema é que a maior parte do seu código está acoplada à classe `Caminhão`. Adicionar algo diferente como, por exemplo, `Navio` exigiria alterações em toda a base do código.
- Como resultado, você terá um código bastante sujo, repleto de condicionais que alteram o comportamento da aplicação dependendo da classe de objetos do transporte.

## Solução

- O padrão sugere que você substitua chamadas diretas de construção de objetos (usando o operador `new`) por chamadas para um método fábrica especial.
- Vamos passar a criação do operador `new` para dentro do método fábrica. Objetos retornados por um método fábrica geralmente são chamados de ***produtos***.

![[Pasted image 20250301194124.png]]

- Parece que só mudamos a chamada do construtor de uma parte do programa para outra.
- No entanto, agora você pode sobrescrever o método fábrica em uma subclasse e alterar a classe de produtos que estão sendo criados pelo método.
- Porém, há uma limitação: as subclasses só podem retornar tipos diferentes de produtos se esses produtos tiverem uma classe ou interface base em comum.

![[Pasted image 20250407000522.png]]

- Por exemplo, ambas as classes `Caminhão` e `Navio` devem implementar a interface `Transporte` que declara um método `entregar`.
- Cada classe implementa esse método de sua maneira e supre suas regras de negócios.