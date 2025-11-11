
## Introdução ao Modelo de responsabilidade compartilhada

Tradução: **Shared Responsibility Model**

- É um modelo de segurança em nuvem que define quais obrigações de segurança entre os clientes e os [[1- Conceitos de Cloud#^764685|CSPs]].
- Cada CSP tem uma variação deste modelo.

## AWS Shared Responsibility Model

![[Pasted image 20251016023016.png]]

- Este é o modelo de responsabilidade compartilhada entre o cliente (*Customer*) e a AWS.
- A responsabilidade entre o funcionamento do serviço é dividido entre o que fica responsável pelo cliente e pela AWS.
- De forma resumida, o cliente fica responsável pelas: 
	- Configurações dos serviços
	- Dados armazenados no serviço
	- Encriptação dos dados 
	- Configuração de acesso de usuários
	- Uso de chaves para acesso a serviços 
	- Configurações das plataformas utilizadas como sistema operacional, máquinas e firewall.
- Já a AWS fica responsável em lidar com a computação e a integridade e confiabilidade física do sistema.
	- A computação
	- Tecnologia de banco de dados
	- Tecnologia de armazenamento
	- Networking entre as máquinas físicas e o [[AWS Global Network]].
	- Regiões, [[Pontos de Presença (PoP)#^6b776b|Edge Locations]], Segurança física das máquinas e [[Zonas de Disponibilidade (AZ)]].

![[Pasted image 20251016024204.png]]

- <mark style="color: white;background: #FFB86CA6;">Os clientes são responsáveis pela segurança dentro da nuvem.</mark>
- <mark style="color: white;background: #FFB86CA6;">Enquanto a AWS é responsável pela segurança da nuvem.</mark>

## Tipos de Responsabilidades de computações em nuvem

![[Pasted image 20251016024904.png]]

#### On-Premise
- O cliente é responsável por todos os detalhes dentro e fora da infraestrutura.

#### Infrastructure as a Service
- Com o IaaS, o CSP toma conta de toda a questão de máquinas, computação e tecnologia para que o cliente foque somente na transmissão de dados e sua aplicação.

#### Platform as a Service
- Já aqui, temos a PaaS que provê uma plataforma para que o cliente trabalhe sem precisar se importar com transferência de dados, como será feito, acessos ou sistema operacional. Sua responsabilidade é de somente criar a aplicação e onde armazenar esses dados.

#### Software as a Service
- Aqui trata-se de um produto completo e feito para o usuário final, onde este não terá que lidar com nada técnico. Um exemplo disto é o Microsoft Word.

## Shared Responsibility Model - Compute

![[Pasted image 20251016025842.png]]

![[Pasted image 20251020225730.png]]

### Shared Responsibility Model Alternate

![[Pasted image 20251020231157.png]]

## SRM - Architecture

![[Pasted image 20251020231619.png]]

### Traditional / VMs

- *Global Workforce* é bastante familiar com este tipo de arquitetura e muitas documentações, *frameworks* e suporte.
- Elastic Beanstalk para PaaS
- EC2 para IaaS

### Microservices / Containers

- Uma mistura de linguagens e possibilidades, melhor utilização de recursos.
- AWS Fargate é um exemplo de alocação de containers sem servidores.
- AWS ECS para containers e AWS EKS para containers Kubernetes.

## Serverless / Functions

- Nenhum servidor, somente se preocupar com dados e código.
- Aqui como exemplo temos Amplify como framework serverless e Lambda para a arquitetura serverless.

