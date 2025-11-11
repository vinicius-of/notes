- É um hook que permite ler e inscrever para o contexto do seu componente.
- Serve para guardar dados e poder acessar facilmente dentro da árvore do React.
- Não é necessário passar esses dados via `props`.
- Evita o problema de *Props Drilling*.

## createContext

- `createContext` espera um valor padrão como argumento, o estado inicial. 

## useContext

![[Pasted image 20251017140028.png]]

- Com o Provider instanciado, os dados do usuário é acessível via useContext.
- Isso elimina a necessidade de passar dados para baixo da árvore por meio de props.

## Context Provider

![[Pasted image 20251017135412.png]]

- O Provider é o elemento que provê os dados e o valor para os componentes abaixo.
- 


![[Pasted image 20251017135427.png]]
