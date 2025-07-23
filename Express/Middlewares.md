---
tags:
  - express
  - back-end
---
Fonte: https://expressjs.com/en/guide/using-middleware.html#middleware.error-handling

## Error-handling middleware

- Refere-se a como o Express pega todos os erros que ocorrem enquanto executa *handlers* de rota e  *middlewares*.
- Express vem com um *handler* de erros por padrão.
- Express pega qualquer erro lançado por padrão dentro de métodos de rotas.

```javascript
app.get('/', (req, res) => {
  throw new Error('BROKEN') // Express will catch this on its own.
})
```

- Para erros assíncronos invocados por *handlers* de rota e middlewares, você deve passar para a `next()`.
- Para chamadas assíncronas, o Express já captura erros lançados por eles, como chamadas ou requisições para outros serviços.