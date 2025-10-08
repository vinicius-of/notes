## *Data Residency*

- Um local físico onde os recursos de uma organização ou "nuvem" reside.
- Para permissão legal e alocação de espaço para estabelecer este local físico, é necessário ***Compliance Boundaries*** e **Data Sovereignty***.

- Para *workloads* que precisam obedecer o **Compliance Boundaries*** de forma restrita, é necessário definir a residência dos dados e os recursos da nuvem.
- A AWS tem recursos que ajudam com isso, sendo eles:

	- **AWS Outposts**
		- Uma grade de servidores físicos da AWS para colocar no seu datacenter.
		- Seus dados irão residir onde seu *outpost* residir.
		- Solução custosa.

	- **AWS Config**
		- É um serviço de politicas como serviço.
		- Você cria regras que faz checa de forma contínua as configurações de recursos do AWS.
		- Se eles se desviarem do que foi configurado, você será alertado.
		- Em alguns casos, a própria AWS remedia a anomalia.

	- **IAM Policies**
		- Politicas de acesso podem ser escritas para negar acesso à regiões específicas da AWS.
		- Um **Service Control Policy**(SCP) são permissões aplicadas a organização.

### O que é ***Compliance Boundaries***?

- Uma conformidade regulatória (requerimento legal) pelo governo or organização que descreve onde os dados e os recursos da nuvem estão permitidos em residir.

### O que é ***Data Sovereignty***?

- É um controle relativo à jurisdição ou autorização legal que pode confirmar sobre os dados de que sua localização está dentro dos limites legais.