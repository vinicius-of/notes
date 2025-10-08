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