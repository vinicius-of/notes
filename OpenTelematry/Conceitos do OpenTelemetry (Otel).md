---
tags:
  - telemetry
  - back-end
  - software-engineering
aliases: []
---

- Há três fundamentos principais para alcançar o objetivo que o Otel propõe.
	- Signals
	- Context
	- Semantic Conventions

## Signals

- Trata-se dos três métodos discutidos acima. Entretanto, esses fundamentos são inúteis sem o contexto.

## Context

- *Context* é o que provê as informações vitais sobre o ambiente e as condições sobre os sinais.
- Isso é o que responde as dúvidas sobre:
	- Quando aconteceu?
	- Onde aconteceu?
	- O que aconteceu?

- Somente o contexto e o sinais não é o suficiente para certificar a consistência e interoperabilidade. 

## Convenções Semânticas

- Trata-se de padrões estabelecidos de nomeação, atributos para o dados da telemetria e garantir que a informação coletada entre vários serviços pode ser correlaciona e analisada com confiança e integridade.