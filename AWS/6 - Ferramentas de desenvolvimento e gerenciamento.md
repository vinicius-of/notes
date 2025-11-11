## AWS API

### O que é uma API?

- Uma [[API]] é um software que permite que duas aplicações/serviços se comuniquem entre si.
- O tipo mais comum é API via HTTP/s.

- Cada serviço da AWS tem seu próprio ***Service Endpoint*** que você pode enviar requisições.

![[Pasted image 20251005015320.png]]

- Para autorizar sua requisição para qualquer serviço, é necessário gerar uma requisição assinada.
- Para isto, deve ser feito uma requisição separada com suas credenciais da AWS e obter o token.

## AWS Management Console

- É um console unificado baseado em web para construir, gerenciar e monitorar tudo a partir de aplicações web "simples" para levantar estruturas complexas em nuvem.

- ![[Pasted image 20251005032834.png]]

### Service Consoles

- Cada serviço do AWS tem o próprio console. Você pode acessá-lo procurando pelo nome do serviço.
- Alguns serviços servem com um "guarda-chuva" contendo outras serviços como:
	- VPC Console
	- EC2 Console
	- System Manager Console
	- CloudWatch Console

## AWS Account ID

- Toda conta da AWS tem uma ID único da conta.
- Mantenha privado já que muitos componentes são atrelados a este ID.
- É composto por 12 dígitos.

## AWS Tools for Powershell

- PowerShell é um automatizador de tarefas e um framework de gerenciamento de configurações.
- Também pode ser descrito como um *command-line shell* e uma *scripting language*.

## Amazon Resource Name (ARNs)

- Trata-se da padronização da nomenclatura dos recursos da AWS.
- ARNs são requeridos para especificar um recurso de forma não ambígua dentro da AWS.

![[Pasted image 20251007031935.png]]

- Estes são alguns formatos usados pela AWS.

![[Pasted image 20251007031959.png]]

- É possível copiar o ARN a partir do AWS Management Console com um botão de copiar.
- Serviços globais não necessitam que as regiões sejam descritas.

## AWS Command Line Interface

- Permite que usuários interajam com as APIs da AWS via comandos em um shell ou terminal.
- Este serviço pode ser testado utilizando o AWS CloudShell no ambiente web ou dentro de um terminal do sistema operacional.

![[Pasted image 20251007182124.png]]

- Para executar o AWS CLI, é necessário ter Python instalado.
### O que é um Terminal?

- Um terminal é uma interface para o ambiente de IO que trabalha somente com texto.

### O que é um Console?

- É um computador físico para fisicamente dar entrada de informações em um terminal.

### O que é um Shell?

- É um programa de comandos em linha que os usuários interagem por meio de entrada de comandos.
	- Bash
	- Zsh
	- PowerShell

## AWS SDK

- Uma coleção de ferramentas para desenvolvimento de software (Software Development Kit) em um pacote instalável.
- É utilizado para operar com métodos de criar, modificar, interagir ou remover com os recursos da AWS.
- É oferecido em diversas linguagens.

![[Pasted image 20251012164145.png]]

## AWS CloudShell

- É um shell implementado no console de gerenciamento da AWS.
- Ele vem com diversas ferramentas instaladas gratuitamente.
- Você obtém 1GB de armazenamento gratuito para arquivos por região.
- Seus arquivos e configurações ficam salvos para futuras sessões na região.
- Pode trocar entre diversos ambientes de shell como:
	- Bash
	- PowerShell
	- Zsh

## Infrastructure as Code (IaC)

- *Infrastructure as Code* é um script de configuração para **automatizar** criação, atualização e desconstrução da infraestrutura em nuvem.
- IaC é como se fosse uma planta para sua infraestrutura.
- Este te permite facilmente compartilhar, versionar ou armazenar sua infraestrutura em nuvem.

- AWS te oferece duas opções para escrever IaC:
	- AWS CloudFormation (CFN)
	- AWS Cloud Development Kit (CDK)

- **AWS CloudFormation** é uma ferramenta <mark style="background: #FFB86CA6; color: white; font-weight:bold;">declarativa</mark> que permite construção da infraestrutura utilizando <mark style="background: #BBFABBA6;color: white;">JSON, YAML e XML</mark>.
	- Este é mais verboso, mas sua configuração é totalmente <mark style="background: #FF5582A6;color: white">explícita</mark>.
	- Com isso, não há como ocorrer erros de configurações por meios automatizados.

- **AWS Cloud Development Kit** é uma ferramenta <mark style="background: #FFB86CA6;color: white">imperativa</mark> que permite a construção da infraestrutura utilizando linguagens de programação como Python, JavaScript e outros.
	- Este já utiliza de métodos e funções para automatizar o processo de construção e dados necessários, então sua configuração ocorre de forma <mark style="background: #FF5582A6;color: white">implícita</mark>.
	- É menos verboso, mas é possível ocorrer configurações fora do esperado se não conhecer bem.

## CloudFormation

- AWS CloudFormation te permite escrever uma infraestrutura em formato de código declarativo tanto em JSON como em YAML.
- É uma ferramenta simples, mas que leva a grandes arquivos de configuração.
- É limitado em criar infraestrutura de forma dinâmica ou até repetidas comparado com CDK.
- CloudFormation pode ser mais fácil para engenheiros DevOps que não tenha conhecimento com linguagem de programação.

- Um detalhe importante é que CDK gera um CloudFormation, então é importante saber ler e entender CloudFormation caso seja necessário debuggar IaC *Stacks*

![[Pasted image 20251012171334.png]]

## Cloud Development Kit

- AWS CDK permite o usuário de utilizar sua linguagem escolhida para escrever IaC.
- CDK funciona utilizando CloudFormation por debaixo dos panos (Ele gera CFN templates).
- CDK tem seu próprio CLI.
- CDK Pipelines pode configurar rapidamente CI/CD pipelines para projetos CDK.
- CDK tem um framework de teste para unitários e para integrações.

>[!warning]
>É possível criar a infraestrutura também com o AWS SDK, mas a diferença é que CDK é idempotente de sua infraestrutura. Então ele sempre reproduzirá o mesmo resultado.

## AWS Toolkit for VSCode

- AWS Toolkit é um plugin open-source para VSCode para criar, analisar e levantar recursos AWS.

![[Pasted image 20251013232259.png]]

1. AWS Explorer
	1. Explorador sob os recursos da AWS ligados a sua conta configurada.

2. AWS CDK Explorer
	1. Permite o usuário explorar as *stacks* definidas pelo CDK.

3. Amazon Elastic Container Service
	1. Provê IntelliSense para definição para arquivos de tarefas ECS.

4. Serverless Applications
	1. Permite criar, analisar e levantar aplicações serverless via SAM e CFN.

## Access Keys

- Access Keys é um par de chave-segredo necessário para ter acesso programático aos recursos da AWS.
- Este é utilizando quando há interação entre AWS API fora do AWS Console Management.
- Também é chamado de <mark style="color:white; background: #BBFABBA6;">AWS Credentials</mark>.

![[Pasted image 20251013233510.png]]

- Um usuário deve receber o acesso para ter as credenciais.
- Um usuário pode ter duas chaves ativas.
- Essas chaves também podem ser desativadas.

![[Pasted image 20251013234641.png]]

### Coisas para não fazer

- Nunca compartilhar suas credenciais
- Nunca *commitar* a chave de acesso no código-fonte.

![[Pasted image 20251013234820.png]]

- Acima pode ser observado dois perfis de usuários para acesso ao recursos da AWS.
- Caso o desenvolvedor ou usuário não especifique qual perfil deverá ser usado na operação com o AWS CLI, será recorrido ao perfil *Default*.
- É possível também configurar utilizando o comando `aws configure` com o AWS CLI.
- AWS SDK irá automaticamente ler as credenciais e implementar no ambiente de desenvolvimento via variáveis de ambiente <mark style="color: white;background: #FF5582A6;">(Método mais seguro para utilizar as chaves dentro do código)</mark>.

## AWS Documentation

- É uma grande coleção de documentação técnica em como utilizar os serviços da AWS.
- AWS é muito boa em prover detalhes sobre todos os seus serviços.