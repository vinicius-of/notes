
## O que é o Node.js?

- Uma plataforma de código aberto para a realização de I/O de forma assíncrona.
- Composto pelo interpretador V8 da Google com a biblioteca libuv.
- Este consegue alcançar a entrada e saída de dados sem precisar bloquear o *thread*.

![[Pasted image 20250925004255.png]]
- Baseado no padrão Reactor e *Proactor*.
- O node.js processa tudo em uma única *thread*.
- *Single Threaded*
- Utilzia o chamado *Event Loop*
- Um executor que observa uma fila de tarefas para ser executado.
- O Event Loop não pode ser travada por uma requisição ou chamada assíncrona (depende de algum tipo de conexão ou chamada a outro servidor). Para isso, o Event Loop reserva a requisição ociosa e executa outra tarefa dentro da fila. E quando a resposta for retornada, o Event Loop vai resolver a primeira requisição.

## Como escalar uma aplicação Node.js?

- Por meio de múltiplos processos, podemos alcançar processamento em paralelo baseado na quantidade de cores disponíveis.
- A *Thread Pool* é responsável pelo processamento de I/O (libuv).

## Como é executado o código Javascript?

- Utilizando o V8, um interpretador de Javascript de alta performance criado pela Google.
- Junto a isso, existe todo um conjunto de módulos que permite trabalhar com Javascript na plataforma Node.js. (exemplos: fs, stream, buffer, crypto e etc.)

![[Pasted image 20250925005455.png]]

## Node.js Thread Pool

- Normalmente o Node.js opera sobre a arquitetura I/O assíncrono, permitindo que não haja bloqueios na execução de suas tarefas.
- Este alcança isso por meio do chamado *Thread Pool*, uma "lista" de tarefas que ficam em espera fora da *main thread* até receber uma resposta vinda da fonte requisitada. Como por exemplo, uma requisição de dados de outro serviço web.
- Quando recebido a resposta para a tarefa em espera, é feita um *callback* para a *main thread* do Node.
- Assim, a próxima iteração do *loop* resgatará a informação recebida e executará o *callback*.
- *DNS Lookup*, File I/O e tarefas específicas do usuário podem usar o *thread pool*.

## DNS Lookup Bottleneck

- Pode ocorrer que caso todas as threads disponíveis da thread pool estejam ocupadas, bloqueando a execução de alguma chamada ou File I/O.