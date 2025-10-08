- Locais físicos feitos por um ou mais datacenters.
- Um datacenter é um estabelecimento seguro que contem centenas de milhares de computadores.
- Cada região geralmente tem 3 zonas.
	- Nem todas as regiões tem 3 zonas e alguns usuários são limitadas a somente 2 zonas.

- É uma prática comum rodar *workloads* em , pelo menos, 3 AZs para assegurar que os serviços se mantenham disponíveis em caso de um ou dois datacenters falharem.
- AZs são representados pelo <mark style="background: #FFB86CA6;">Código da Região</mark>, seguido pela letra identificadora.
	- Exemplo: us-east-1**a**

## Detalhes sobre regiões e AZ

- Cada região foi desenhada para ser completamente isolada de outros regiões.
	- Isso serve para alcançar a maior tolerância a falhas e estabilidade.
- Cada AZ é isolado, mas as zonas de uma região estão conectadas por ligações de baixa latência.
- Cada Az é desenhada para ser uma <mark style="background: #FFB86CA6; color: white;">zona independente de falhas.</mark> 

## Subnets

- Uma subnet é associado com uma zona de disponibilidade.
- Você nunca escolhe quando subir recursos.
- Você escolhe a Subnet que é associado ao AZ.

### Zonas Locais (Local Zones)

- São datacenters localizados perto de áreas populares/densas para prover performance de baixa latência para aquela área.
- O propósito dos Local Zone é apoiar aplicações de alta demanda e sensíveis a latência como:
	- Mídia e Entretenimento
	- Automação de Design Eletrônico
	- Ad-Tech
	- Machine Learning

## AWS Zonas de *Wavelength*

- Te permite usar computação de ponta em redes 5G.
- Aplicações terão latência extremamente baixa estando o mais próximo possível dos usuários.