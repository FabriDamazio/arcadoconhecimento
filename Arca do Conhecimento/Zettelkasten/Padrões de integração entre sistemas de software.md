---
Criado: 2025-09-16T12:01
Atualizado: 2025-09-16T12:01
Estudado: 2025-09-16T12:01
Links:
  - "[[Arquitetura de Software]]"
---
---
# Padrões de integração entre sistemas de software

São estratégias recorrentes para conectar sistemas distintos, garantindo a troca de dados, consistência e comunicação confiável.

## Principais padrões de integração

- API: Um sistema expõe uma interface para que outros sistemas possam as invocar para realizar ações ou acessar dados. (ex. REST, GraphQL, gRPC).
- Banco de dados compartilhado: sistemas diferentes acessar e manipulam o mesmo banco de dados para trocar informações.
- Transferência de arquivos: sistemas trocar informações através da geração a leitura de arquivos.
- [[Sistema de Mensageria (Message Broker)]]: utiliza um software intermediário para enviar e receber mensagens de forma padronizada.
- Ponto a ponto: conexões diretas entre sistemas individuais usando lógica personalizada.


---
## References

FOWLER, Martin; HAERMANN, Gregor; et al. _Enterprise Integration Patterns_. Disponível em: [https://www.enterpriseintegrationpatterns.com/](https://www.enterpriseintegrationpatterns.com/?utm_source=chatgpt.com) Acesso em: 16 set. 2025.