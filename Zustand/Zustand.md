- Uma solução para gerenciamento de estados para o React.
- Zustand é uma API baseada em hooks.

![[Pasted image 20251016214823.png]]

- A imagem acima trata-se de uma *store* básica para o funcionamento.

![[Pasted image 20251016215024.png]]

- Para utilizar o novo hook, precisamos instanciá-lo dentro de outro componente.
- Na imagem acima, importamos o novo hook `useCounterStore` e selecionamos o seu seletor, neste caso, `count`.
- `count` é o valor retornado sempre que pedimos o retorno do valor ao `useCounterStore`.

![[Pasted image 20251016215557.png]]

![[Pasted image 20251016215634.png]]

- Para modificar o valor guardado dentro do *store*, é necessário utilizar o parâmetro `set`, um callback que retornará ou modificará os valores de acordo com a função declarada para esta variável.
- Neste caso, quando a função `increment` for chamada, a função `set` modificará o count para `1`, transformando em um novo estado.
- Isto vale também para o ``decrement``.

![[Pasted image 20251016220040.png]]

- Ambas as funções são chamadas dentro de um componente e são declaradas.
- Para utilizar a função, é necessário obter elas e atribuir a uma ação/evento.

![[Pasted image 20251016222236.png]]

- Você pode ter acesso direto ao estado da *store* chamando a função `getState`.

#### Best Practices

![[Pasted image 20251016222838.png]]
- Não *destruct* nenhum *store.* Busque os estados e seus atributos de forma específica por questões de performance. Já que se houver mais estados dentro do *store* e estamos desconstruindo o *store*, logo todos os componentes que instanciam o *store* desta forma serão afetados pela mudança.


- Sempre que definir seus *stores*, tente agrupá-los baseado no contexto.