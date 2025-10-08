
## O que é um Solutions Architect?

- Um Solutions Architect precisa sempre considerar os seguintes fatores para o negócio:
	- O quão seguro é essa solução?
	- O quanto essa solução irá custar?

## O que é um Cloud Architect?

- Um Cloud Architect precisa entender os seguintes termos e incorporá-los em sua arquitetura baseada nos requerimentos dos negócios:

%% Conhecido como ASEFODE %%

- Availability
	- Sua habilidade de assegurar que um serviço mantenha-se disponível.
- Scalability
	- Sua habilidade de crescer rapidamente de forma interrupta.
- Elasticity
	- Sua habilidade de diminuir e crescer para bater a demanda.
- Fault Tolerance
	- Sua habilidade de prevenir uma falha.
- Disaster Recovery
	- Sua habilidade de se recuperar de uma falha.

## High Availability (HA)

- Sua habilidade dos seus serviços se manterem disponíveis assegurando que \*<mark style="background: #FFB86CA6; color: white">não há pontos de falha</mark>.
- Ou assegurar <mark style="background: #BBFABBA6;color:white">um certo nível de performance</mark>.

![[Pasted image 20251003174648.png]]

- Como pode ver na imagem acima, por meio dos serviços da Amazon, é possível disponibilizar três zonas de disponibilidade para caso dois falhem, ainda teremos um terceiro funcionando.

### Elastic Load Balancer

- Um [[Load Balancer|load balancer]] que permite distribuir o tráfego para múltiplos servidores em um ou mais datacenters.
- Se um datacenter/servidores se tornar indisponível, o *load balancer* irá direcionar o tráfego para os servidores disponíveis.

## High Scalability

- Sua habilidade em aumentar sua capacidade baseada no aumento da demanda de tráfego, memória e poder computacional.

![[Pasted image 20251005001534.png]]

- **Vertical Scaling** (Scaling Up)
	- Melhorar o servidor para cima
	- Aumentar sua capacidade computacional melhorando suas configurações, mas aumentando também o tamanho do servidor.

- **Horizontal Scaling** (Scaling out)
	- Aumentar a quantidade de servidores do mesmo tamanho.

## High Elasticity

- Sua habilidade de **automaticamente** aumentar ou diminuir sua capacidade baseada na demanda atual de tráfego, memória e poder de computação.

![[Pasted image 20251005002932.png]]

- Não existe *"Scale Down"* para diminuir o tamanho verticalmente, não é algo usual para a arquitetura tradicional.
- Há um serviço chamado ***Auto Scaling Groups (ASG)*** que permite adicionar o remover servidores automaticamente baseado nas regras de escabilidade definidas e baseadas em métricas.

## Fault Tolerance

- Sua habilidade de assegurar que seus serviços não há nenhuma falha, <mark style="background: #FF5582A6; color: white">prevenindo chance de falha</mark>.
- ***Fail-overs*** é quando você tem um plano para <mark style="background: #FF5582A6; color: white">redirecionar o tráfego</mark> para um sistema redundante existente em caso do sistema primário falhar.

![[Pasted image 20251005003633.png]]

- Um exemplo clássico é ter um cópia (secundário) do seu banco de dados onde todas as mudanças são sincronizadas.
- Um sistema secundário não é utilizado até que um *fail-over* ocorra e se torna o sistema primário.

### RDS Multi-AZ

- Uma funcionalidade que executa uma duplicata de banco de dados em *standby* em outra [[Zonas de Disponibilidade (AZ)|zona de disponibilidade]] em caso do primeiro banco de dados falhar.

## High Durability

- Sua habilidade de se recuperar de um desastre e prevenir perdas de dados. 
- Soluções para recuperar de um desastre são conhecidos como <mark style="background: #BBFABBA6; color: white; font-weight: bold">Disaster Recovery (DR)</mark>.

- Alguns pontos para se pensar sobre recuperação de desastres são:
	- Você tem um backup?
	- O quão rápido você consegue restaurar a partir deste backup?
	- Seu backup ainda é funcional?
	- Como você assegura que mudanças de dados ao vivo não foram/estão corrompidas/perdidas?

- Uma solução da AWS é o serviço <mark style="background: #ABF7F7A6; color: white; font-weight: bold">CloudEndure Disaster Recovery</mark>, onde este replica de forma contínua suas máquinas em uma área de baixo custo dentro da conta-alvo AWS e na região preferida.
- Isto permite recuperações rápidas e seguras em casos de perda de servidores.

## Business Continuity Plan (BCP)

- Tradução: Plano de contingência dos negócios

![[Pasted image 20251005005418.png]]

- Um plano de contingência dos negócios (BCP) é um documento que descreve como um negócio deve <mark style="background: #FFB86CA6; color: white">operar durante uma interrupção dos serviços não planejada</mark>.

- ***Recovery Point Objective (RPO)*** 
	- A quantidade máxima de dados que podem ser perdidos após um incidente não planejado.
	- Este dado é expresso em <mark style="color: white; background: #FFB86CA6;">quantidade de tempo</mark>.
	- ![[Pasted image 20251005013554.png]]

- ***Recovery Time Objetive (RTO)***
	- A quantidade máxima tolerável de tempo de baixa dos negócios sem ocorrer uma perda financeira significativa.
	- ![[Pasted image 20251005011328.png]]

### Disaster Recovery Options

- Uma linha demonstrando as opções de recuperações de desastres desde a opção mais barata e que pode demorar (*Low*) até soluções que resolvem em tempo real (*High*).

![[Pasted image 20251005010041.png]]

- ***Backup & Restore***
	- Fazer backup dos dados e restaurá-los em uma nova infraestrutura.
	- Pode levar **horas** para ser completo.
	- Casos e serviços de baixa prioridade
	- Somente restaura os negócios após o ocorrido
	- Levanta recursos após o evento.
	- Custo $

- **Pilot Light**
	- Os dados são replicados para outra região com o mínimo de serviços em execução.
	- Pode levar até **10 minutos**.
	- Para serviços com RTO/RPO mais restrito
	- Somente os serviços principais estão prontos para uso.
	- Escala recursos após o evento.
	- Custo \$$

- ***Warm Standby***
	- Uma cópia inferior (*scaled down*) da sua infraestrutura já executada e pronta para *scale up*.
	- Pode levar **alguns minutos**.
	- Serve para serviços críticos para o negócio.
	- Este escala recursos após o evento.
	- Custa \$\$\$

-  ***Multi-site Active***
	- Uma cópia já levantada e *scaled up* de sua infraestrutura em outra região.
	- Este resolve o problema em tempo real (*downtime*)
	- Quase nenhuma perda financeira
	- Serve para serviços críticos.
	- Custa exatamente o mesmo dos serviços protegidos por esta opção.



