---
aliases:
  - regiões
  - aws regiões
---
## Regiões

- Regiões são locais geográficos distintos consistindo de um ou mais Zonas Disponíveis.

![[Pasted image 20250930163047.png]]

- Toda região é fisicamente isolada e independente de outros regiões nos termos de <mark style="background: #FF5582A6;">local, energia, reserva de água.</mark>

- Cada região é geralmente tem 3 zonas de disponibilidade.
	- Novos usuários são limitados à 2 zonas.

- Novos serviços quase sempre estarão disponíveis primeiro na zona **US-EAST**.
- Nem todos os serviços estão disponíveis em outras regiões
- Todos as suas informações de custo estão no **US-EAST-1**.
- Os custos dos serviços da AWS variam entre regiões.

## Detalhes sobre regiões e AZ

- Cada região foi desenhada para ser completamente isolada de outros regiões.
	- Isso serve para alcançar a maior tolerância a falhas e estabilidade.
- Cada AZ é isolado, mas as zonas de uma região estão conectadas por ligações de baixa latência.
- Cada Az é desenhada para ser uma <mark style="background: #FFB86CA6; color: white;">zona independente de falhas.</mark> 