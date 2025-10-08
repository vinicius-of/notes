## O que é o Event Loop?

- Mecanismo que permite ao Node.js executar operações assíncronas sem interromper o fluxo principal da aplicação ou outras atividades pendentes.

- O Event loop é essencial para manter a eficiência para lidar com múltiplas operações simultaneamente.

- Sempre que uma operação assíncrona é iniciada, ela é enviada para fora do thread principal e um callback será registrado para essa operação.

- Quando a operação for concluída, o resultado é colocado na fila do Event Loop para ser executado assim que possível.