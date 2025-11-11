- É um local intermediário entre uma região da AWS e o usuário final.
- Este local pode ser um **datacenter** ou uma coleção de *hardware*.

- Para AWS, um ponto de presença é um datacenter proprietário ou um parceiro confiável que é utilizado pelos serviços AWS em relação <mark style="background: #BBFABBA6; color: white;">a entrega de conteúdo ou upload de dados</mark>.

- Os recursos do PoP são:
	- [[#^ed036a|Edge Locations]] ^6b776b
	- [[#^e25b53|Caches Regionais Edge]]

![[Pasted image 20251001005958.png]]

### *Edge Locations*

^ed036a

- São datacenters que armazenam *cached* (cópias) dos arquivos mais populares (páginas web, images e vídeos) para que o entrega para o usuário final seja reduzida.

- *Edge Locations* podem agir de duas formas:
	- *On ramps*
	- *Off ramps*

- Tudo será trafegado pela **VPC Endpoints**, uma rede virtual privada da rede AWS para não trafegar pela internet pública.

### Locais Edge Regionais (Regional Edge Locations)

^e25b53
- São datacenters que armazenam caches maiores com arquivos menos populares para reduzir a distância percorrida pelos dados e os custos de transferência.

![[Pasted image 20251001010400.png]]

### Serviços que utilizam PoPs

- **Amazon CloudFront**
	- Um serviço de CDN (Content Delivery Network)
	- Você aponta seu website para o CloudFront para que ele roteie as requisições para o *Edge Location* mais próximo.
	- Te permite selecionar uma origem (como um web-server ou armazenamento) como a fonte daquilo que será cacheado.
	- Cacheia o retorno da origem e, assim, retornará para todos os *Edge Locations*.

- **Amazon S3 Transfer Acceleration**
	- Te permite gerar uma URL especial que pode ser usado por usuários finais para subir arquivos para um *Edge Location* próximo.
	- Uma vez que o arquivo tenha sido carregado, este pode mover muito mais rápido pela rede do AWS para alcançar o S3.

- **AWS Global Accelerator**
	- Permite encontrar um caminho optimum do usuário final para seus web-servers.
	- Global Accelerator é implantado dentro de uma borda, assim você enviar tráfego do usuário para uma borda em vez de diretamente a sua aplicação.