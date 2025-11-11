## Elastic Compute Cloud (EC2)

- AWS EC2 é um servidor altamente configurável onde você pode escolher a predefinições que afetam as configurações da máquina como:
	- A quantidade de CPUs e VCPUs.
	- A quantidade de memória RAM.
	- A quantidade de largura de banda (*Network Bandwidth*).
	- O sistema operacional (Windows 10, Ubuntu, Amazon Linux 2).
	- E utilizar múltiplos HDs virtuais para armazenamento com Elastic Block Store (EBS).

>[!warning]
>EC2 é também considerado a espinha dorsal da AWS, já que a maioria dos serviços da AWS estão utilizando EC2 como seus servidores de operações. (eg. S3, RDS, DynamoDB, Lambda).

### O que são máquinas virtuais (VMs)?

- É uma emulação de um computador físico usando somente software.
- O *Server Virtualization* permite ao usuário **criar, copiar, redimensionar e migrar** seu servidor com facilidade.
- Múltiplas VMs podem rodar utilizando o mesmo servidor físico, assim, permitindo que os custos do uso da máquina sejam divididos entre os clientes.

- Quando é lançado uma VM, ela é chamada de <mark style="background: #ABF7F7A6; color: white;">"instância"</mark>.

## VMs, Containers e Serverless

### Virtual Machines

- É uma emulação de um computador físico utilizando software.
- Temos os serviços EC2 e AWS LightSail como exemplo.
	- AWS LightSail é um serviço de gerenciamento de servidores virtuais.
	- <mark style="background: #FFB86CA6; color: white;"> Uma versão mais amigável do EC2</mark> para quem não tem muito conhecimento com a AWS.

### Containers

- São unidades executáveis de software que empacotam o código da aplicação juntamente com suas bibliotecas e dependências.
- Eles permitem que o código seja executado em qualquer ambiente de computação.
- Estes aproveitam uma forma de virtualização do sistema operacional para executar múltiplos *workloads* em uma única instância.
- **Tipicamente utilizado em arquiteturas de microsserviços**.

Entre os serviços, temos:

#### Elastic Container Service (ECS)

- É um <mark style="color: white; background: #FFB86CA6;">serviço de orquestração de containers</mark> que suporta <mark style="color: white; background: #FF5582A6;">containers Docker</mark>.
- Ele sobe um grupo de servidores em instâncias do EC2 com Docker instalado.

>[!warning]
>Com ECS, o usuário continua executando um servidor EC2 mesmo quando não estiver executando nenhum container. Para isso existe o ECS Fargate.

#### Elastic Container Registry (ECR)

- É um <mark style="color:white;background: #FFB86CA6;">repositório para imagens de containers</mark>.
- Para lançar um container, é necessário uma imagem.
	- Uma imagem dentro do contexto de container significa uma cópia salva do container.
- Um repositório significa um meio de armazenar com controle de versão.

#### Elastic Container Service Fargate (ECS Fargate)

- É um <mark style="color: white; background: #FFB86CA6;">serviço de orquestração de containers serverless</mark>.
- Funciona exatamente como ECS, mas o cliente paga somente pela demanda enquanto estiver executando algum container.
- AWS gerencia os servidores por baixo dos panos para que não seja necessário escalar ou melhorar manualmente o servidor EC2.

#### Elastic Kubernetes Service (EKS)

- É um serviço Kubernetes totalmente gerenciado.
- Kubernetes é um programa open-source de orquestração que foi criado pelo Google e geralmente é um padrão no mercado para gerenciar microsserviços.

### Serverless

- É quando os servidores são totalmente gerenciados pela AWS. O usuário não se preocupa com a configuração do servidor.

### AWS Lambda

- É um <mark style="color:white;background: #FFB86CA6;">serviço de funções serverless</mark>.
- O usuário pode executar código sem prover ou gerenciar servidores.
- O usuário sobe um pequeno pedaço de código, escolhe a quantidade de memória e por quanto tempo a função pode se manter em *standby* antes de desligar.
- O custo basea-se no <mark style="color:white;background: #FF5582A6;">tempo de execução das funções serverless aproximada do mais próximo 100ms</mark>.

## Higher Performance Computing Services

^2b859c

- Um grupo de centenas de milhares de servidores com rápida conexão entre eles com o propósito de aumentar a capacidade computacional.
- Quando é necessário um supercomputador para resolver problemas computacionais muito grandes ou que demoram demais para os computadores convencionais.
- Isso é alcançado pelo **The Nitro System.***

### Nitro System

- Uma combinação de hardware dedicado e um *hypervisor* leve, permitindo rápida inovação e melhor segurança.
- Todas os tipos de novas instâncias de EC2 utilizam o **Nitro System**.
- Este sistema é compost por:
	- **Nitro Cards**: Cartões que transferem e aceleram I/O para funções. Os principais cartões são VPC, EBS e *Instance Storage* e cartões de controle.

	- **Nitro Security Chips**: Protege os recursos do hardware com um chip integrado a placa-mãe.

	- **Nitro Hypervisor**: Um *hypervisor* leve para controle de memória e alocação de CPU. Performance comparada aos tipos *Bare Metal*.

	- **AWS Nitro Enclaves**: Permite que os clientes criem ambientes de computação isolados para proteger e processar com mais segurança.
	- Útil para processamento de dados altamente sensíveis como identificação pessoal, dados financeiros, informações de saúde e entre outros.

	- **NitroTPM**: Módulo de plataforma TPM 2.0. É um recurso de segurança e compatibilidade que facilita aos clientes o uso de aplicações de recursos do sistema operacional.

### Instâncias Bare Metal

- O usuário também pode subir uma instância de <mark style="color: white; background: #FF5582A6;">EC2 sem ter hypervisor</mark>, assim, permitindo executar *workloads* diretamente no hardware.
- Isso leva a maior performance e controle.
- Existem dois tipos de instâncias EC2 que rodam desta forma: **O M5 e o R5**.

### Bottlerocket

- É um sistema operacional open-source construído pela AWS com o propósito executar containers em máquinas virtuais ou hospedeiros *bare metal*.

### AWS ParallelCluster

- É uma ferramenta de gerenciamento de grupos que tem suporte a AWS e é open-source.
- Esta ferramenta facilita o levantamento e gerenciamento de computação de alta performance ([[#^2b859c|HPC]]) na AWS.

## Edge e Hybrid

### O que é *"Edge Computing"*?

- Quando você passa seu processamento computacional para fora de suas redes para executar mais próximo da localização do destinatário.
- Pode ser executado em celulares, dispositivos IoT ou servidores externos fora de sua rede cloud.

### O que é *"Hybrid Computing"*?

- Quando é possível executar processos computacionais em datacenter *[[1- Conceitos de Cloud#^8ee138|On-Premise]]* e em uma VPC (*Virtual Private Cloud*) da AWS.

### Serviços de *Edge Computing*

- [[AWS Outposts]]
- [[Zonas de Disponibilidade (AZ)#^8cfe3d| AWS Wavelength]]
- [[Zonas de Disponibilidade (AZ)#^a50543|AWS Local Zones]]

#### WMWare Cloud on AWS

- Permite gerenciar máquinas virtuais On-Premise usando o WMWare como instâncias EC2.
- O datacenter deve utilizar o WMWare para virtualização.

## Custo e Gerencia de Capacidade

- Como economizar dinheiro?
- Como suportar a demanda do tráfego e uso via adicionando ou melhorando servidores?
- Existe diversos serviços que permite ao usuário cortar custos desnecessários de forma automatizada.

### Serviços

### EC2 Spot Instances, Reserved Instances and Saving Plans

- Uma forma de economizar em computação, pagando o preço cheio ou parcialmente, se comprometendo a contratos anuais ou sendo flexível sobre disponibilidade e interrupções nos serviços computacionais.

### AWS Batch

- Planeja, agenda e executa seus processos computacionais em lotes, incluindo uma grande abrangência entre os serviços da AWS.
- Pode utilizar Spot Instance para economizar nos gastos.

### AWS Compute Optimizer

- Um serviço que sugere como reduzir custos e melhorar performance utilizando *machine learning* para analisar seu histórico de uso.

### EC2 Autoscaling Groups (ASGs)
^5f9d3c

- Este serviço permite adicionar ou remover automaticamente servidores EC2 para cobrir a demanda atual de tráfego.
- Sempre economizará gatos e cobrirá a demanda já que irá levantar somente a quantidade necessária de servidores.

### Elastic Load Balancer (ELB)

- Este serviço distribui o tráfego entre múltiplos serviços.
- Pode re-rotear tráfego de instâncias não-saudáveis para instâncias em funcionamento.
- Pode rotear tráfego para instâncias EC2 executando em uma [[Zonas de Disponibilidade (AZ)|AZ]] diferente.

### AWS Elastic Beanstalk (EB)

- Este serviço serve para levantar aplicações web facilmente sem os desenvolvedores terem que se preocupar sobre configurar ou entender os serviços da AWS.
- Similar ao Heroku.