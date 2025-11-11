
Fonte: [React Query - Complete Tutorial](https://www.youtube.com/watch?v=8K1N3fE-cDs)
[Overview](https://tanstack.com/query/v5/docs/framework/react/overview)


- TanStack Query é uma ferramenta para aplicações web que faz:
	- Fetching
	- Caching
	- Synch
	- Updating server state

- Enquanto a maioria das bibliotecas de gerenciamento de estados mais tradicionais são boas em lidar com o estado do lado do cliente, estes não lidam bem com os estados vindos do servidor.
- O estado do servidor é completamente diferente.
	- Necessita de chamadas assíncronas de API para resgatar ou atualizar dados.
	- Persiste remotamente em um local onde o lado do cliente pode não controlar.
	- Implica que os dados podem ser compartilhados e modificados a qualquer momento sem seu conhecimento.

```tsx
import {
  QueryClient,
  QueryClientProvider,
  useQuery,
} from '@tanstack/react-query'

const queryClient = new QueryClient()

export default function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <Example />
    </QueryClientProvider>
  )
}

function Example() {
  const { isPending, error, data } = useQuery({
    queryKey: ['repoData'],
    queryFn: () =>
      fetch('https://api.github.com/repos/TanStack/query').then((res) =>
        res.json(),
      ),
  })

  if (isPending) return 'Loading...'

  if (error) return 'An error has occurred: ' + error.message

  return (
    <div>
      <h1>{data.name}</h1>
      <p>{data.description}</p>
      <strong>👀 {data.subscribers_count}</strong>{' '}
      <strong>✨ {data.stargazers_count}</strong>{' '}
      <strong>🍴 {data.forks_count}</strong>
    </div>
  )
}
```

- TanStack Query funciona utilizando um Provider para que seu hook funcione dentro da aplicação que ele cobre.
- É necessário de um `queryClient` para adicionar ao Provider.
- A partir disso, seu hook `useQuery` pode ser chamado e configurado a qualquer momento.

![[Pasted image 20251016225222.png]]

- Para declarar o hook `useQuery`, ele leva dois argumentos principais: `queryFn` e `queryKey`
- `queryFn` é a função que fará a chamada para o serviço.
- `queryKey` é uma chave única para identificar a chamada dentro dos componentes.

## `useMutations`

![[Pasted image 20251016230109.png]]

- Esta função serve para fazer modificações aos dados. Ele funciona aparentemente com o `useQuery`.
- Ele tem dois objetivos:
	- De modificar/adicionar/remover os dados dependendo da operação feita no `mutationFn`.
	- Invalidar todas as queries com base no ``mutationKey``

![[Pasted image 20251016231022.png]]

- Caso deseje observar um estado para que o `useQuery` seja reativo, só é necessário adicionar o estado dentro do `queryKey`.

![[Pasted image 20251016231220.png]]
