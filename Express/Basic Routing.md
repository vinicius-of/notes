---
tags:
  - back-end
  - express
---
Fonte: https://expressjs.com/en/guide/routing.html

- Routing* refere-se à determinar como uma aplicação responde a requisição do cliente para um [[Endpoint|endpoint]] particular.
- Cada rota pode ter um ou mais *handlers functions*, que executarão quando a rota for encontrada.
- Você pode prover múltiplos *callbacks* para se comportarem como [[General/Middlewares|middleware]] para lidar com a requisição.
- Você pode usar esse mecanismo para impor pré-condições em uma rota, assim passar o controle para as rotas subsequentes se não tiver razão para proceder com a rota atual.

```javascript
const cb0 = function (req, res, next) {
  console.log('CB0')
  next()
}

const cb1 = function (req, res, next) {
  console.log('CB1')
  next()
}

const cb2 = function (req, res) {
  res.send('Hello from C!')
}

app.get('/example/c', [cb0, cb1, cb2])
```

## app.route()

- Você pode criar *handlers* de rotas encadeadas para um caminho de rota usando `app.route()`. 
- Isso permite que o caminho seja especificado em um único local, criando rotas modulares e reduzindo redundâncias e *typos*.

```javascript
app.route('/book')
  .get((req, res) => {
    res.send('Get a random book')
  })
  .post((req, res) => {
    res.send('Add a book')
  })
  .put((req, res) => {
    res.send('Update the book')
  })
```

## express.Router

- Use o classe `express.Router` para criar *handlers* de rota modulares.
- Uma instância `Router` é um [[General/Middlewares|middleware]] e um sistema de routas.

```javascript
const express = require('express')
const router = express.Router()

// middleware that is specific to this router
const timeLog = (req, res, next) => {
  console.log('Time: ', Date.now())
  next()
}
router.use(timeLog)

// define the home page route
router.get('/', (req, res) => {
  res.send('Birds home page')
})
// define the about route
router.get('/about', (req, res) => {
  res.send('About birds')
})

module.exports = router
```

- Carregue o módulo de rotas no app:

```javascript
const birds = require('./birds')
app.use('/birds', birds)
```

- Deste modo, não será possível utilizar parâmetros pelas sub-rotas. Para isso, você precisa passar a opção `mergeParams` no construtor do Router.

```javascript
const router = express.Router({ mergeParams: true })
```
