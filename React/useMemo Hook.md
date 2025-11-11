
![[Pasted image 20251017145314.png]]

- É um hook do React que permite o desenvolvedor armazenar (cache) o resultado de um calculo entre re-renderizações.
- O hook recebe dois argumentos:
	- ``calculateValue``: A função que calcula o valor que deseja cachear. Deve ser uma função pura e sem argumentos. Na primeira renderização, este será chamado inicialmente. Caso o valor das `dependecies` forem os mesmos retornados anteriormente, não haverá renderização extra.
	- `dependecies`: Uma lista de valores reativos referenciados dentro do `calculateValue`. Valores reativos podem ser `props`, estados, variáveis e funções declaradas dentro do componente.

## Caveats

- ``useMemo`` é um hook, então pode ser chamado somente no início do seu componente.
- Não pode ser utilizado dentro de loops ou condições.
- No modo `strict`, React vai chamar o calculo duas vezes para ajudar o desenvolvedor a encontrar impuridades acidentais. Isto é um comportamento somente em modo desenvolvimento.