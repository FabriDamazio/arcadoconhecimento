É um serviço que permite criar e gerenciar políticas de controle e auditoria de recursos. Podem ser criadas politicas de conformidade como quais recursos e localizações podem ser usadas.

## Grupos de gerenciamento

Oferecem um nível de escopo e controle acima das assinaturas e é usado para gerenciar políticas de acesso delas.

- Por padrão todas assinaturas são colocadas em um grupo de gerenciamento padrão (raiz).
- Todas assinaturas dentro de um grupo herdam automaticamente as configurações do grupo.
- Uma árvore de grupos de gerenciamento pode possuir até seis níveis.
- Controle de acesso por role (função) não esta habilitada por padrão 

## Criação de políticas

Uma **política (policy)** expressa uma condições e as ações a serem realizadas quando é atendida. Ela pode ser criada ou uma pré-pronta (build-in) pode ser utilizada.

Uma **iniciativa (initiative)** é um conjunto de **políticas (policy)** para ajudar a controlar a conformidade dos recursos para atender uma meta maior. Você pode **delimitar o escopo** dela a grupos de gerenciamento, assinaturas ou grupo de recursos específicos.

Após criar as políticas e iniciativas com escopo delimitado você pode avaliar seu estado usando o recurso de **Conformidade (Compliance)**.







