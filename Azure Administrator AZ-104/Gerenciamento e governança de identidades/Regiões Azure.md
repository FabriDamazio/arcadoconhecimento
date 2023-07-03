
Uma região é uma área geográfica que possui um ou mais datacenters. Existem mais de 60 regiões que cobrem 140 países.

A maioria das regiões são emparelhadas com outra região próxima para criar um **par regional (regional pair)** que possui:

- **Isolamento físico:** possuem o mínimo de 300 milhas de distância se possível.
- **Replicação automática:** alguns serviços possuem replicação automática para a região par.
- **Ordem de recuperação:** em caso de falha é priorizada a recuperação de uma região de cada par.
- **Atualizações sequenciais:** são feitas em sequências nas regiões par e não ao mesmo tempo.