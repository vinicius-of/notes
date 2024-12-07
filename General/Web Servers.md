---
tags:
  - web
  - server
  - back-end
---
Fontes: 
[What are web servers and how do they work](https://www.youtube.com/watch?v=JhpUch6lWMw)
[Mozilla - O que é um servidor web (web server)?](https://developer.mozilla.org/pt-BR/docs/Learn/Common_questions/Web_mechanics/What_is_a_web_server)

### O que é um Web Server?
- Pode se referir ao software ou hardware.
- Sendo hardware, é uma máquina que armazena conteúdos web e os entrega para os dispositivos do usuário final (cliente).
- Este é conectado a uma rede e pode ser acessado por um [[DNS]].
- Sendo software, este inclui diversos componentes que controlam como os clientes acessam os arquivos hospedados.
- Usa o protocolo [[HTTP]] para estabelecer a conexão entre o servidor e o cliente.
- O cliente pode consumir conteúdos web estáticos e/ou dinâmicos.
- Usado para hospedar páginas web, blogs e construir [[APIs]].

![[Pasted image 20240919052338.png]]

- O cliente contém um IP dentro de uma rede, intranet ou internet.
- O provedor web (Web Server) está hospedado em uma máquina, onde o mesmo irá reservar a porta 80 (443 caso seja [[HTTPS]]) para prover conteúdos web.
- Neste exemplo, o cliente faz uma chamada [[HTTP]] para o Web server pedindo pelo arquivo/página [[HTML]] "*index*".
- O Web server vai prover para o cliente o arquivo que pediu caso esteja disponível.

### Servidor web estático
- Consiste em um computador com um servidor HTTP.
- Envia arquivos hospedados como estão armazenados na máquina.

### Servidor web dinâmico
- Consiste em um servidor web estático com software adicional.
- Um servidor de aplicações e um banco de dados.
- Os arquivos são atualizados/processados antes de enviar de retornar ao cliente.

### Exemplos de tipos de Webservers
- ***Block Single-Threaded***: Após uma requisição, o soquete [[TCP]] fica travado para outros usos até sua finalização. Caso aja outra requisição de outro cliente, então será criado um novo soquete TCP para lidar com a nova requisição (maximum connections ou threads).
- ***OTS***