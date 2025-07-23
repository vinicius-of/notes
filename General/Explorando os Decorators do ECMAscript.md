
Fonte: https://medium.com/google-developers/exploring-es7-decorators-76ecb65fb841

## O padrão Decorator

- Em Python, os decorators provêm uma sintaxe simples para chamar funções de ordem maior ([[High-order functions]]).
- Esses Decorators são funções que levam outra função, estendendo o comportamento para a função posterior sem explicitamente modificá-la.

![[Pasted image 20250627164652.png]]

- O `@` indica para o *parser* sobre o uso do decorator, enquanto o *mydecorator* referencia a função pelo símbolo/nome.

- Ideal para envolver qualquer função com extra funcionalidade de forma prática e transparente.
- Isso inclui:
	- *[[Memoization]]*:
	- Exercer controle de acesso
	- Autenticação
	- Instrumentação
	- Funções temporizadores
	- *[[O que é OpenTelemtry#^df9232|Logging]]*
	- etc.

## Decorators no ES2016

- É uma expressão que retorna funções e pode marcar descritores *target*, nome e propriedade como argumentos.
- Podem ser definidos para classes e propriedades.

![[Pasted image 20250627165333.png]]

![[Pasted image 20250627165441.png]]

- Acima está a criação da class `Cat` que tem o atributo `meow`.
- Abaixo da definição da classe, tem a implementação do nome da propriedade `meow`.

![[Pasted image 20250627165609.png]]

- Acima está a definição de um decorator chamado `readonly`, onde o objetivo dele é marcar o atributo `meow` como somente para leitura, desabilitando a escrita sob o nome da propriedade.

![[Pasted image 20250627165730.png]]

- Um decorator é somente uma expressão que será avaliado e terá que retornar uma função.
- Isso também funciona para classes

## Decorators em classes

- O decorator marca o construtor da classe como alvo para modificar.

![[Pasted image 20250627170033.png]]