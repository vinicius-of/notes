- Um serviço é empacotado como *deployable* ou como uma unidade executável.
- Exemplos disso incluí:
	- Arquivos JAR
	- Arquivos WAR
	- Executáveis de sistemas operacionais
	- Uma imagem de container Docker.

## Pronto para produção depois de ser testado em isolamento

- Uma definição seria um serviço que é empacotado como *deployable* ou como uma unidade executável **e** pronto para produção após testes isolados.
- Tal serviço tem que ter seu próprio repositório do código-fonte e *pipeline* de *deployment*.
- Se for necessário serviços de terceiros para testar a funcionalidade do seu serviço, ele não é *independently deployable*.

- O benefício de ter um serviço independente é que isso acelera a pipeline de deployment. Isto elimina as necessidades lentas e testes end-to-end complexos de múltiplos serviços.
- Além disso, elimina a necessidade dos times coordenarem.