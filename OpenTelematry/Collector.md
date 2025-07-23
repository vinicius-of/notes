O OpenTelemetry Collector oferece uma implementação agnóstica do fornecedor de como receber, processar e exportar telemetria. Isso remove a necessidade de executar, operar e manter múltiplos agentes ou collectors.

- Isso melhora a escalabilidade e apoia o monitoramento open source, enviando para um ou mais backends.

## Quando utilizar um collector

- Recomendável utilizar um collector junto ao seu serviço, já que lhe permite descarregar dados rapidamente e o collector pode lidar com controles adicionais como *retries*, *batching* e encriptação.