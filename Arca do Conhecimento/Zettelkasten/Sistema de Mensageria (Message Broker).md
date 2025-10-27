---
Criado: 2025-09-16T12:10
Atualizado: 2025-09-16T12:10
Estudado: 2025-09-16T12:10
Links:
  - "[[Padrões de integração entre sistemas de software]]"
tags:
  - dev
---
---
# Sistema de Mensageria (Message Broker)

Um Message Broker é um middleware que recebe, armazena e encaminha mensagens entre sistemas, promovendo desacoplamento, escalabilidade e comunicação assíncrona.

## Objetivos

- Desacoplamento: produtores e consumidores não precisam se conhecer diretamente.
- Entrega confiável: garante persistência, retries e dead-letter.
- Escalabilidade: distribui mensagens em múltiplos consumidores (paralelismo).
- Transformação/roteamento: pode adaptar ou redirecionar mensagens conforme regras.

## Padrões suportados

- Filas (Queue) → mensagens consumidas por apenas um consumidor.
- Tópicos (Pub/Sub) → mensagens entregues a múltiplos consumidores.
- Event Streaming → armazenamento e reprocessamento contínuo de eventos.

## Exemplos de tecnologias

- [[Apache Kafka]] → streaming distribuído, alta vazão, persistência longa.
- RabbitMQ → mensageria tradicional, com roteamento flexível.
- Apache Pulsar → suporta filas e tópicos nativamente, multi-tenancy.
- NATS JetStream → leve, rápido, com suporte a persistência.
- Serviços gerenciados: AWS SQS/SNS, Azure Event Hubs, Google Pub/Sub.

---
## References

WIKIPEDIA. _Message broker_. Wikipédia, a enciclopédia livre. Disponível em: https://en.wikipedia.org/wiki/Message_broker. Acesso em: 16 set. 2025. 