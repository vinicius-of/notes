## Tipos de serviços de armazenamento

### Elastic Block Store (EBS) - Block

![[Pasted image 20251027050209.png]]

- Permite criar volumes de armazenamento e os anexar à instâncias do Amazon EC2.
- Após conectado, é possível:
	- Criar um sistema de arquivos por cima desses volumes.
	- Executar um banco de dados.
	- Utilizar como armazenamento em blocos.

- Os volumes são inseridos em uma zona de disponibilidade específica.
- São automaticamente replicados para proteger de falhas em um único componente.

- Este serviço se diferencia por escalar rapidamente para processos de alta performance e com alto *throughput*.
- Utilizando em exemplos como produtos SAP, Oracle e Microsoft.

### AWS Elastic File Storage (EFS) - File

![[Pasted image 20251027050215.png]]

- Aumenta e diminui automaticamente conforme a manipulação de arquivos, sem necessidade de gerenciamento.
- Criar e configurar sistemas de arquivos compartilhados de forma simples para serviços de computação da AWS.

- Os arquivos são salvos com os dados e seus metadados.
- É possível ter múltiplas conexões via compartilhamento de rede.
- Suporta múltiplas leituras, mas trava ao escrever no arquivo.

- Serviço útil para quando é necessário compartilhar arquivos entre múltiplos usuários ou VMs dentro do mesmo *drive*.

### Amazon Simple Storage Service (S3) - Object

![[Pasted image 20251027050221.png]]

- Serviço de armazenamento de objetos.
- Um objeto é armazenado com os dados, metadados e ID única.
- Escala sem limite de arquivos ou de armazenamento.
- Suporta múltiplas leituras e escritas (sem travas).

- É perfeito para quando o usuário deseja subir um arquivo para nuvem sem se preocupar com a infraestrutura abaixo.
- Não é recomendado para altos IOPs.

## Introdução ao S3

### O que é armazenamento de objetos (Object-based Storage)?

- Uma arquitetura de armazenamento de dados onde que gerencia os dados como objetos diferente de outras arquiteturas de armazenamento.
- S3 providencia o usuário com armazenamento ilimitado.
- O usuário não precisa entender sobre o funcionamento da infraestrutura.
- O Console do S3 provê uma interface para subir e acessar os arquivos.

### S3 Object

- Objetos contêm seus dados.
- Eles funcionam como arquivos.
- Um objeto consiste de:
	- **Key**: Nome do objeto
	- **Value**: Os dados em si feitos de sequências de bytes.
	- **Version ID**: Quando o versionamento está habilitado, este define a versão do objeto.
	- **Metadata**: Informações adicionais do objeto.

### S3 Bucket

- *Buckets* é o que segura os objetos.
- Buckets pode também ter pastas que seguram os objetos.
- S3 é um nome universal, então cada bucket exige um nome único.

>[!warning]
>Você pode armazenar um objeto individual de 0 Bytes até 5 Terabytes de tamanho.

## Tipos de armazenamento S3

![[Pasted image 20251027051454.png]]

### S3 Standard

^775e74

- Rápido, 99.99% de disponibilidade e replicado em pelo menos três AZs.

### S3 Intelligent Tiering

- Usa *machine learning* para analisar o uso de objetos e determinar o tipo apropriado de armazenamento.
- Os dados são movidos para o nível de acesso mais custo-benefício.
- Não há impacto na performance ou mais complexidade.

### S3 Standard-IA (Infrequent Access)

^3b2912

- O acesso continua rápido.
- Barato para acesso ocasionais (menor que uma vez ao mês) de arquivos.
- Caso deseje retornar mais do que isso, será cobrado uma taxa de retorno.
- Custo reduzido em 50% comparado ao [[#^775e74|S3 Standard]].
- Disponibilidade reduzida.

### S3 One-Zone-IA

- O acesso continua rápido.
- O objeto existe somente em uma única zona.
- Disponibilidade de 99.5%.
- Mais barato que o [[#^3b2912|S3 Standard-IA]] em 20%.
- Disponibilidade reduzida.
- O risco deste modelo é que caso aconteça algo com o local de armazenamento onde o arquivo está, os dados podem ser destruídos.

### S3 Glacier

- Este modelo serve para armazenamento frio para longo prazo.
- O resgate dos dados pode demorar de minutos até horas.
- Sua vantagem é que seu custo é barato.

### S3 Glacier Deep Archive

- Este modelo é o mais barato dentro do S3.
- Diferente do S3 Glacier, este somente resgata os dados após 12 horas do pedido.

>[!warning]
>S3 Outposts tem seu próprio modelo de armazenamento.

## AWS Snow Family

- Este serviço <mark style="color: white;background: #BBFABBA6;">oferece armazenamento e dispositivos de computação usados para mover dados fisicamente para dentro ou fora da nuvem</mark>.
- Uma solução quando mover dados pela internet ou por conexões privadas é <mark style="color: white;background: #FF5582A6;">lento, custo e/ou difícil</mark>.
- Existe três serviços dentro da família.

![[Pasted image 20251028013002.png]]

### Snowcone

- Este modelo vem em dois tamanhos: 
	- 8TB de armazenamento em HDD.
	- 14TB de armazenamento em SSD.

### Snowball Edge

- Este é generalizado em dois formatos:
	- Optimizado para armazenamento com 80TB de espaço.
	- Optimizado para computação com 39.5TB de espaço.

### Snowmobile

- 100PB de armazenamento.

>[!warning]
>Todos os dados são entregues ao Amazon S3.

## Serviços de armazenamento

### Simple Storage Service (S3)

- É um serviço de armazenamento de objeto serveless.
- Não existe limite de tamanho individual por objeto.
- Não existe limite de quantidade de objetos no S3.
- O usuário paga somente pelo que é armazenado.
- O único limite é a quantidade de 100 buckets por infraestrutura.

### S3 Glacier

- É um serviço de armazenamento frio.
- Seu propósito é ser uma solução de baixo custo para arquivar ou backup de longo termo.
- Utiliza HDDs de gerações anteriores para alcançar o baixo custo.
- Altamente seguro e durável.

### Elastic Block Store (EBS)

- Um serviço de armazenamento persistente em blocos.
- É essencialmente um disco rígido virtual dentro da nuvem.
- O usuário pode integrar este disco virtual à instâncias EC2.
- Você pode escolher diversos tipos de discos rígidos:
	- SSD
	- IOPS SSD
	- *Throughput* HDD
	- *Cold* HDD
- Ótima solução quando é necessário alto desempenho, mais controle sobre a montagem do disco rígido e persistência para uma única instância.

### Elastic File Storage (EFS)

- É um serviço de sistema de arquivos [[NFS]] nativo da nuvem.
- Você pode montar armazenamentos de arquivos para múltiplas instâncias EC2 ao mesmo tempo.
- Cada sistema de arquivo pode ser criado com as seguintes características:
	- **O tipo de sistema de arquivo**: Regional ou One-Zone
	- **O modo de performance**: General Purpose ou Max I/O

	- **O modo** **Throughput**: Elastic, Provisioned ou Bursting
- É utilizando quando é necessário:
	- Compartilhar arquivos entre múltiplos servidores.
	- Armazenamento flexível para aplicações escaláveis.

#### Elastic Throughput

- A configuração padrão para EFS.
- Utilizado para problemas de processamento imprevisível.

#### Provisioned throughput

- Utilizado para quantidades de processamentos previsíveis.

#### Bursting throughput

- Utilizado para quando é necessário que o *throughput* escale junto ao armazenamento do sistema de arquivos.

### Storage Gateway

- Um serviço de armazenamento de nuvem híbrida que estende seu armazenamento local para a nuvem.
- Este funciona de 3 formas:
	- **File Gateway**: Estende seu armazenamento local para o S3.
	- **Volume Gateway**: Cacheia seus discos locais para o S3, útil para backup contínuo de arquivos locais.
	- **Tape Gateway**: Armazena seus arquivos locais em uma fita virtual. Útil para armazenamento à longo prazo e custo-benefício.

### AWS Backup

- Um serviço de backup gerenciável que torna fácil centralizar e automatizar o backup de dados através de vários serviços da AWS.
- Exemplo de serviços são: EC2, EBS, RDS, DynamoDB, EFS, Storage Gateway.
- Você cria os planos de backup.

### CloudEndure Disaster Recovey

- Um serviço que replica suas máquinas de forma contínua em uma área de baixo custo do seu alvo.

### AWS FSx

- É um serviço de sistema de arquivos de alta performance e rico em funcionalidades.
- Pode ser utilizado para Windows (SMB) ou Linux (Lustre).