# HTTP (Hyper-Text Transfer Protocol)

Componentes da web:
- Uma linguagem de apresentação (HTML);
- Um esquema de endereçamento (URI/URL);
- Um protocolo de comunicação entre cliente e servidor (HTTP).

## Modelo OSI
Modelo de um sistema de comunicações em 7 camadas.

### Serviços
Um serviço representa um conjunto de funções oferecidas a um utilizador por um fornecedor.

### Protocolos
Define como é usado o serviço da camada inferior, os procedimentos usados no protocolo e como são codificadas as PDU.

### Modelo TCP/IP
Conjunto de protocolos de comunicação entre computadores em rede. É usado na Internet para possibilitar computadores a receber e a enviar dados. Assim, estabelece comunicação entre vários computadores.

## Protocolo HTTP
O HTTP é um protocolo da camada de aplicação que permite duas aplicações comunicarem entre si. Na maior parte das vezes uma das aplicações é um servidor web como o `Apache` e a outra é um browser como por exemplo o `Google Chrome` ou o `Firefox`.

Usa TCP como protocolo subjacente para a camada de transporte.

### HTML e HTTP
Enquanto que o HTML é uma linguagem que estrutura a informação, o HTTP é o protocolo que regula a transferência das páginas HTML entre o servidor web e o cliente (browser).

O que acontece quando o utilizador escreve um URL no seu browser?
- O browser extrai o nome do servidor (hostname), incluindo o número da porta (se estiver definido).
- Abre um socket TCP especificando o endereço do servidor.
- O browser escreve uma mensagem de pedido da página ao servidor, usando o socket TCP.
- A camada TCP aceita a mensagem e garante a entrega da mensagem ao servidor (automaticamente reenviando a informação se esta a perder).
- O servidor responde ao cliente fazendo um percurso idêntico na sua pilha protocolar e devolve a este a página ou o recurso solicitado.

### Protocolo TCP
A camada de aplicação. Este é usado na web. O protocolo TCP faz deteção e correção de erros. Garante a entrega de dados entre o cliente e servidor. Tem também algoritmos para fazer o controlo do fluxo da informação, garantido uma taxa de transmissão adequada.

### Protocolo IP
A camada de transporte, usando o TCP, invoca os serviços da camada de Internet e escolhe usar o protocolo IP. TCP e IP geralmente são o par escolhidos na web, pelo que se fala muito em TCP/IP.

- O protocolo IP é responsável por dividir a informação em packets e movê-los de uma rede para outra através de routers, gateways etc.
- O IP faz o seu melhor para entregar todos os pacotes ao seu destino mas não é garantido. Essa responsabilidade é do TCP.
- O protocolo IP requer que todos os dispositivos tenham um endereço, conhecidos como endereço IP.

### Protocolo Ethernet
Até agora todos os processos mencionados correm dentro de uma máquina mas em dado momento terão que deixar a máquina do cliente para ser enviados por um cabo, uma fibra ou canal sem fios (wi-fi ou satélite). A responsabilidade de transportar estes pacotes é da responsabilidade da camada de ligação de dados com o protocolo Ethernet.

### Protocolo HTTP
Diferentes tipos de mensagens

- GET — Pede um recurso
- PUT — Guarda um recurso
- DELETE — Remove um recurso
- POST — Atualiza um recurso
- HEAD — Pede os cabeçalhos ou os metadados para um recurso
  
O browser lança um mensagem GET sempre que pedir um recurso, tal como uma página, uma imagem ou vídeo.

A mensagem HTTP GET não altera nada no servidor portanto é considerada uma mensagem segura.

Podemos usar o GET num form HTML num contexto de procura, em que apenas queremos obter o resultado de uma busca.

A mensagem POST é usada quando temos dados para enviar para o servidor. Portanto não é uma mensagem segura, pois pode alterar alguma coisa no servidor.

Diferença entre GET e POST:
Em vez de passar os parâmetros do form no corpo da mensagem tal como acontece no POST, o GET passa-os através do URL.

A maior desvantagem do GET é que se podem ver os valores dos parâmetros do formulários no campo URL do browser.

Nunca se deve usar o método GET num formulário se os dados são sensíveis.

### Códigos de estado

- 100-199 — Informacional
- 200-299 — Bem sucedido
- 300-399 — Redirecionado
- 400-499 — Erro do cliente
- 500-599 — Erro do servidor

### Ligações Paralelas

Ligações paralelas são ligações em feitas em paralelo de modo a carregar esses recursos mais rapidamente.

É normal, hoje em dia, abrir seis ligações em simultâneo. Uma descarrega o HTML, outra o CSS, outra o JS e as restantes imagens etc.

Quantas mais ligações, mais se carrega em paralelo, tornando o servidor mais lento. A partir de determinada altura, o aumento de ligações pode tornar o descarregamento de uma página mais lento.

### Ligações Persistentes

Em vez de se fechar o socket a seguir à resposta ao primeiro pedido, mantem-no aberto durante vários pedidos/respostas. Durante quantos pedidos? Istto depende dos recursos de memória no servidor, da sua configuração e do desempenho pretendido. Quantos mais pedidos se fizerem numa ligação mais se degrada o desempenho do servidor.

A configuração do servidor deve limitar o número de ligações abertas em simultâneo por razões de segurança contra ataques de DoS (Denial of Service). Este ataque surge quando pessoas mal intencionadas mantêm abertas um grande número de ligações em simultâneo, de modo a que o servidor não possa servir os pedidos "reais" dos clientes e dessa maneira nega o serviço.

Limita-se também o tempo máximo que é permitido para cada ligação permanecer em aberto. Se o cliente não efetuar mais pedidos para aquele socket, o mesmo é encerrado.

### Ligações com pedidos em série (pipeline)

Espera-se que em futuras especificações do HTTP seja permitido fazer um conjunto de pedidos em "rajada", sem esperar pelo par "resposta" individual para cada um deles. O cliente pode assim fazer múltiplos pedidos mesmo antes de chegar a resposta ao primeiro pedido.

## Controlo do Estado no HTTP
Apesar do HTTP ser stateless (não mantém a informação do utilizador de umas ligações para outras), o comportamento mais usual na web é vermos o servidor "recordar-se" do utilizador durante um longo periodo de tempo.

As técnicas usadas nas aplicações web para manter o estado ou seja manter a ligação entre os clientes e o servidor mais tempo podem ser duas:

- Incluir a informação de estados em todas as mensagens. O servidor insere na sua resposta uma referência de estado que depois é usada nas transações seguintes para identificar este cliente e o serviço a que está a aceder.

- Outra solução é usar uma base de dados para armazenar a informação de estado no servidor. Isto é conhecido como sessão de utilizador.

### Como mantém o servidor o estado se o HTTP é stateless?

Através de cookies. Quando um utilizador usa um site pela primeira vez, o servidor envia-lhe uma cookie. A partir daí o browser inclui em todos os cabeçalhos dos pedidos subsequentes essa cookie de modo a que o servidor o reconheça. Se a cookie contiver um identificador único então o site sabe com quem está a interagir.

O servidor pode incluir nas cookies qualquer informação mas há uma limitação de 4kbytes.

Em PHP ou noutra linguagem para a web os dados da sessão são automaticamente guardados pelo servidor e podem ser acedidos através de um objeto. No caso de PHP é chamado $_SESSION.

### Cookies persistentes

Existem cookies que sobrevivem a uma sessão quando os browsers guardam-nas no disco do computador. Assim, o servidor sabe sempre quem é o cliente.

Podem surgir problemas de segurança. O domínio deve ser sempre definido ou corremos o risco desta cookie reencaminhar informação para outros sites e exponha a informação que contém a terceiros não autorizados.