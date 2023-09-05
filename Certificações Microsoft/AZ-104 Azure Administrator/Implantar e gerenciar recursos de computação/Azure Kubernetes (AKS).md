Uma maneira simplificada de implantar um cluster Kubernetes gerenciado.

Conceitos importantes do AKS:

- **Pools:** grupo de nodes de configurações iguais.
- **Nodes:** uma máquina virtual individual que roda containers.
- **Pods:** uma única instância de uma aplicação. Pode conter um ou mais containers.
- **Container:** uma imagem executável que contém a aplicação e todas suas dependências.
- **Deployment:** o conjunto de um ou mais pods gerenciado pelo Kubernetes.
- **Manifest:** arquivo YAML que descreve um deployment.

## Arquitetura de clusters e nodes

O cluster do AKS possui 2 componentes: nodes gerenciados pela Azure (azure-managed) e nodes gerenciado pelo cliente (costumer-managed). Cada cluster contem um ou mais nodes e também um ou mais node pools.

O kubelet é o agente do Kubernetes que processa a orquestração de requests no nó gerenciado pela Azure.

O kube-proxy é o componente que lida com a rede virtual em cada node roteando o trafico de rede e gerencia o IP dos serviços e pods.

## Configurando a rede

As redes virtuais são suportadas no Kubernetes da seguinte maneira:

- Os nodes são conectados a uma rede virtual que fornece conectividade de entrada e saída para os pods.
- O componente kube-proxy executa em cada node para fornecer funcionalidades de rede.
- Políticas de rede configuram segurança e filtro para os pods.
- [[Azure Load Balancer]] pode ser utilizado.
- Para roteamento de rede mais complexo pode ser usado Ingress Controllers.

## Armazenamento

Volumes de armazenamento podem ser criados manualmente e serem atribuídos aos pods ou serem criados automaticamente pelo Kubernetes. Os volumes podem usar Azure Disks (disponível apenas para um node) ou Azure Files (para compartilhar dados entre múltiplos nodes).

Os volumes podem fazer parte do lifecycle do pod e existir até ele ser excluído ou serem persistentes.

## Scaling

Os pods e nodes podem ser escalados manualmente ou de forma automática. O cluster pode ser escalado automaticamente.
