Permite limitar o tráfego de rede aos recursos de uma rede ou sub-rede. O grupo contém um conjunto de regras de segurança e ele pode ser associado a uma ou mais redes, sub-redes ou adaptador de redes.

## Regras de segurança

Permitem filtrar o tráfego de entrada e saída de rede.

Uma configuração de regra tem as seguintes informações:

- **Nome**
- **Prioridade** (as regras são processadas por esta ordem)
- **Porta**
- **Protocolo** (qualquer, TCP, UDP)
- **Origem** (qualquer, endereços IP, marca de serviço)
- **Destino** (qualquer, endereços IP, rede virtual)
- **Ação** (permitir ou negar)

Não é possível remover as regras de segurança padrão mas ela pode ser substituída por uma que tenha a prioridade mais alta.

As regras de ENTRADA padrão **negam todo o tráfego de entrada**, exceto o tráfego da rede virtual e dos [[Azure Load Balancer]].

As regras de SAÍDA padrão **só permitem o tráfego de saída** para a Internet e para a rede virtual.

## Zona desmilitarizada ou DMZ

Um cenário comum para aprimorar a segurança é criar uma sub-rede e associar um grupo de segurança para restringir o tráfico para os recursos que residem na sub-rede (cada sub-rede pode ter no máximo um grupo de segurança).



