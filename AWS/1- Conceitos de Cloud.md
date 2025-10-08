## O que é a Amazon?

- Uma empresa multinacional de tecnologia computacional americana.
- Seu centro de operações é em Seattle, Washington.

## O que é o AWS?

- Amazon Web Services
- O primeiro serviço lançado pela AWS foi o [[SQS]] (Simple Queue Service) para uso público em 2004.
- Depois veio [[S3]] (Simple Storage Service) em março de 2006.
- [[EC2]] (Elastic Compute Cloud) em agosto de 2006.

## O que é um Provedor de Serviço de Nuvem (CSP)?

- É uma empresa que:
	- Provê múltiplos serviços em nuvem (exemplo como de 10 a 100 serviços)
	- Aqueles que provê serviços que podem trabalhar juntos para criar uma arquitetura em nuvem.
	- Serviços que podem ser acessados via uma API unificada.
	- Serviços que utilizam custos com medidas baseadas no uso por segundo ou por hora.
	- Serviços que tenham monitoramento rico *builtin* como o AWS CloudTrail.
	- Serviços que ofereçam uma Infraestrutura como um Serviço (IaaS).
	- E serviços que ofereçam automação via Infraestrutura como Código (IaC).

> [!warning] Observação
> Se uma empresa oferece múltiplos serviços sob uma única interface, mas não alcança a maioria dos requisitos acima, este é referenciado como um Cloud Platform (Twilio, HashiCorp, Databricks)

## Quais CSPs existem?

### Tier 1

- AWS
- Microsoft Azure
- Google Cloud Platform
- Alibaba Cloud

### Tier 2

- IBM Cloud
- Oracle Cloud
- Huawei Cloud
- Tencent Cloud

### Tier 3 (VPS)

- Vultr
- Digital Ocean
- Akamai Connected Cloud (Linode)

### Tier 4 (Private Tier)

- OpenStack
- Apache CloudStack
- Vmware vSphere

### Serviços comuns de nuvem

- Um CSP pode ter diversos serviços em nuvem que são agrupados em vários tipos de serviços

- Os quatro tipos mais comuns de serviços para IaaS são:
	- Compute
		- Virtualização de máquinas para executar códigos e rodar aplicações. ([[EC2]])
	- Networking
		- Imagine ter uma rede virtual que define conexões com a Internet ou isolamentos de redes entre serviços ou limitações para a Internet. ([[VPC]] - Private Cloud Network)
	- Storage
		- Um sistema virtual de arquivos para armazenamento. ([[EBS]])
	- Databases
		- Imagine um banco de dados virtual para armazenamento de dados, relatórios ou aplicações gerais. ([[RDS]] - SQL Databases)

### Overview de Tecnologias

- Máquina dedicada
- VMs
- Containers
- Functions
	- Gerenciado por VMs e containers
	- Conhecido também como *Serverless Compute*
	- Você sobe um pedaço de código, escolhe a quantidade de memória e duração.
	- Somente responsável pelo código e os dados.
	- Bem custo-benefício, você paga somente pelo tempo de execução do código. As VMs somente rodarão quando tiver código para ser executado.
	- *Cold-start* é um efeito colateral desta configuração, já que precisa iniciar a VM para executar o código inicialmente.

### Tipos de computação em nuvem

- **SaaS** (Software as a Service) (For Customers)
	- Um produto que pode ser executado e gerenciado pelo provedor do serviço.
	- Não é necessário saber como o serviço é mantido por parte do cliente.
	- Exemplos: Gmail, Salesforce e Office 365.

- **PaaS** (Platform as a Service) (For Developers)
	- Focado para hospedagem e gerenciamento de seus aplicativos.
- **IaaS** (Infrastructure as a Service) (For Admins)

### Modelos de hospedagem em computação em nuvem

#### *Public Cloud*

- Tudo é construído no CSP como AWS, também conhecido como *Cloud-First* ou *Cloud-Native*.
- O público que utiliza este modelo geralmente são empresas que estão iniciaram recentemente.
	- Startups
	- Ofertas de SaaS
	- Novos projetos e empresas

#### *Private Cloud*

^8ee138

- Tudo é construído dentro do *datacenters* da empresa. Conhecido também como *On-Premise*.
- A tecnologia poderia ser a **OpenStack**.
- O público deste modelo tende a ser empresas que não pode trabalhar com a nuvem por questões de restrições legais ou pelo puro tamanho da sua empresa.

#### *Hybrid Cloud*

- A infraestrutura é construída utilizando serviços de ambos os modelos acima.
- O público tende a ser empresas que já tinham sua própria infraestrutura, mas não pode fazer a migração completamente para a nuvem.
	- Bancos
	- FinTechs, Gerencias de investimentos
	- Produtos legados