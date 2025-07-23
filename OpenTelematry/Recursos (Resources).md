---
aliases:
  - recursos
  - resources
---
Um recurso representa uma entidade produzindo telemetria como atributos de recursos.

- Como exemplo, um processo produzindo telemetria dentro de um container no [[Kubernetes]] tem:
	- process name
	- pod name
	- namespace
	- deployment name
- Todos esses atributos podem ser incluídos no recurso

No seu backend de monitoramento, você pode usar as informações do recurso para investigar melhor o comportamento, como encontrar um container específico que esteja produzindo latência no fluxo.