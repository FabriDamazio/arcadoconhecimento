---
Criado: 2024-12-19T14:05
Atualizado: 2025-05-23T17:00
Estudado: 2025-06-04T10:47
Links:
  - "[[Elixir language]]"
  - "[[Behaviour]]"
  - "[[Protocol]]"
  - "[[Processos]]"
---
---
# Polimorfismo em Elixir

Em uma linguagem de programação que utiliza o paradigma orientado a objetos, podemos pensar em um objeto como sendo um acoplamento entre estado, comportamento e mutabilidade (ou tempo, em relação ao dado sendo alterado ao longo do tempo). Sempre que criamos um objeto, essas três dimensões estão presentes.

![[objectoop.png]]

Do ponto de vista do Elixir, estas três dimensões estão desacoplados. Comportamentos são definidos por módulos, estado pelos dados e a mutabilidade pelos processos.

![[objectsbyelixir.png]]

Sendo assim podemos ter polimorfismo em cada uma dessas dimensões separadamente:

- Na dimensão comportamento , implementando um `Behaviour` no módulo:

![[modulebehaviour.png]]

- Na dimensão estado, implementando um  `Protocol`:

![[dataprotocol.png]]

- Na dimensão mutabilidade, criando um processo:

![[polyproccess.png]]

---
## References

**VALIM, José.** _Keynote: Gang of None? Design Patterns in Elixir._ ElixirConf EU 2024, YouTube, 2024. Disponível em: [https://youtu.be/agkXUp0hCW8](https://youtu.be/agkXUp0hCW8). Acesso em: 19 dez. 2024.