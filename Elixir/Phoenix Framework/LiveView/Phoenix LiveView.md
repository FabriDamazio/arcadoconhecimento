Phoenix LiveView funciona como uma biblioteca adicional que pode ser integrada aos projetos que utilizam [[Phoenix Framework]]. Ela adiciona funcionalidades de atualização das páginas em tempo real utilizando Websockets. A principal vantagem é um fluxo de desenvolvimento simplificado sem a forte dependência com o javascript.

## Como funciona uma LiveView?

Uma LiveView é inicialmente renderizada como uma página HTML estática por meio de um ciclo de requisição e resposta. Então, uma conexão WebSocket persistente é automaticamente aberta entre o navegador e um processo LiveView com estado que está rodando no servidor. Os eventos do usuário são então enviados pelo WebSocket para esse processo para alterar o estado da LiveView.
![[como funciona 1.png]]
![[como funciona 2.png]]
Em vez de renderizar a página inteira novamente, o LiveView apenas renderiza as partes da página que são afetadas. Essas diferenças de HTML são então enviadas de volta, e o LiveView inclui JavaScript que atualiza a DOM de forma eficiente. Assim, conforme o processo LiveView recebe eventos do usuário, muda o estado, retorna a diferença e renderiza novamente, tudo é automaticamente mantido sincronizado sem a necessidade de escrever qualquer JavaScript ou gerenciar WebSockets.

![[como funciona 3.png]]
Ao fazer isso, o LiveView nos libera para focar nos recursos dinâmicos interativos do nosso aplicativo, como ordenar e paginar , filtrar, adicionar e remover itens.

## Para saber mais

- [[LiveView Life Cycle]]
- [[Ilustrações sobre LiveView]]: todas as ilustrações mostradas sobre LiveView.