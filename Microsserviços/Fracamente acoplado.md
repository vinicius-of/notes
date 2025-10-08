- Há dois tipos de acoplamentos dentro de microsserviços:
	- Acoplamento no runtime
		- Influencia disponibilidade
	- Acoplamento no tempo de design
		- Influencia na velocidade de desenvolvimento

## Acoplamento no runtime

- Este tipo de acoplamento é o grau na qual a disponibilidade de um dos serviços é afetado pela disponibilidade de outro serviço.

![[Pasted image 20250925024117.png]]

- Como podemos ver, o endpoint `POST /orders` requisita n serviços para completar e retornar sua requisição. Isso aumenta o grau de acoplamento do `Orders Service` aos outros serviços.