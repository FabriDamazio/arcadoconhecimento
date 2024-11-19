19/11/2024 - 09:30
Status: #idea
Tags: [[Phoenix Framework]]

# Phoenix LiveView

Uma LiveView é um processo que recebe eventos, atualiza seu estado e retorna as diferenças do HTML para atualizar uma página.

## Ciclo de vida

Uma LiveView inicia com uma chamada HTTP que retorna o HTML da página.

![[LiveView1.png]]

 Em seguida ele estabelece uma conexão via web socket para receber os eventos

![[LiveView2.png]]

Ao receber um evento, ele atualiza seu estado e responde o que deve ser atualizado no HTML da página. A página é atualizada através do Javascript do LiveView que já esta incluso.

![[LiveView3.png]]
---

# References