Entender ciclo de vida de uma LiveView é essencial para entender seu funcionamento. O ciclo de vida possui 3 passos:

## 1. Requisição HTTP inicial (sem estado)

Ao acessar uma LiveView o servidor recebe uma request HTTP GET comum. O Router é responsável por rotear a requisição para a página certa. Após encontrar a LiveView a função mount e render são executadas como mostra o exemplo abaixo:

![[lifecycle1.png]]

## 2. Websocket (e processo LiveView com estado)

Ao carregar o HTML inicial da página, o arquivo app.js abre uma conexão websocket com o servidor. No servidor então é criado um processo que tem o estado da LiveView. Então a função mount e render são executados novamente como mostrado abaixo:

![[lifecycle2.png]]
## 3. Renderização dinâmica

Com a conexão websocket aberta agora é possível enviar eventos para o servidor para que ele processe e envie o resultado para a página ser atualizada como mostra abaixo:

![[lifecycle3.png]]