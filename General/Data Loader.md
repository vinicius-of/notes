---
tags:
  - graphql
  - data-loader
---
Fonte: [Dataloader GraphQL Medium](https://medium.com/@emanuelgsouza/conhecendo-o-dataloader-graphql-b1395870c64b)

### O que é um Data Loader?
- É uma biblioteca desenvolvida pela Facebook.
- Seu objetivo é reduzir os *requests* através de ***[[Caching]]*** e compartilhamento de requisições dos dados.

### Problema dos resolve's
- Todos os [[Asynchronous Resolvers|Resolver's]] são assíncronos.
- Cada resolver's será "resolvido" independente e individualmente.
- Logo, se tivermos vários resolver's sendo executado ao mesmo tempo, todos serão executados independente e não compartilharam os dados entre si.
- Assim, se dois resolver's buscarem a mesma informação, independente da ordem de completude, **eles faram duas requisições separadas para buscar o mesmo resultado**.
![[Pasted image 20240814155959.png]]

- Código refatorado para usar *Data loader*.