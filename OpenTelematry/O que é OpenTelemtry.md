---
tags:
  - software-engineering
  - back-end
aliases:
  - otel
  - open telemetry
---
Fonte: https://www.youtube.com/watch?v=LzLULxhyIpU

OpenTelemetry é um framework de observação para criar e gerenciar dados de telemetria incluindo rastros, métricas e logs.

> [!info]
> Possível unificar todos os dados em uma telemetria unificada para encontrar e resolver problemas de forma eficiente.

> [!warning]
Ele não é um back-end de observabilidade como Jaeger, Prometheus ou outras aplicações comerciais.

## O problema que resolve

- Imagine uma plataforma ou software que utiliza diversos serviços, como serviço de pagamento, de login, de usuários, de banco de dados e o próprio front-end e back-end.
- Você, como dono da aplicação, começa a receber vários e-mails de suporte reclamando sobre problemas no funcionamento do aplicativo.
- Como a engenharia do aplicativo está disperso entre vários serviços e nodos, o problema trata-se de encontrar o que e onde está acontecendo.

## Logs

^df9232

 - Esses são textos gravados que demarcam eventos úteis para ocorrências específicas, mas este não diz explica onde está o problema e como está a saúde do sistema.
	 - Exemplo seria seu sistema falhar por falta de memória RAM. O logs rastreariam esse evento, mas não é útil para prever esse tipo de informação.

## Metrics

- São dados numéricos no estado do sistema e uso de recursos.
- Útil para encontrar problemas em potencias e analisar padrões do sistema.
	- Usando o mesmo exemplo acima, poderíamos analisar em "tempo real" o uso de memória RAM e o analista poderia prever a situação acima. Com isso, seria possível reagir a tal situação sem esperar pelo evento ocorrer, o que não é possível com logs.
- Possível ativar funções como: alertar o uso, reiniciar os servidores ou escalar conforme o uso.

## Tracing

- *Tracing tracks* (rastrear o caminho) das requisições entre os serviços de uma forma mais detalhada e localizar a fonte do erro.