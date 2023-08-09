É a base do modelo IaaS. Fornece sistema operacional, armazenamento e recursos de rede próprios.

Resumo de características:
- Windows ou Linux
- Podem ser acessadas remotamente por RDP ou SSH
- Podem ser colocadas em VNET.
- Podem ser organizadas em Conjuntos de disponibilidade (availability sets).
- Podem ficar atrás de Load Balancers.
- Pode ser instalado qual software desejar.
- Um servidor é criado em minutos.
- Vários serviços usam VMs, como AKS, Service Fabric, Azure Batch, etc.

## Configurando

Checklist para configurar uma VM:

- **Comece com a rede:** VMs na mesma rede podem se acessar. Para acesso externo é necessário configuração.
- **Escolha um nome para a VM:** 15 caracteres para VM Windows e 64 para Linux.
- **Decida o local:** a localização pode limitar as opções disponíveis de hardware e seu preço.
- **Determine o tamanho:** importante lembrar que o  redimensionamento pode exigir uma reinicialização que pode causar uma interrupção temporária ou alterar as definições de configuração, como o endereço IP.
- **Examine o modelo de preços e estime seus custos:** é cobrado com base no consumo de computação. O armazenamento é cobrado separadamente. As VMs podem ser reservadas por um ou três anos para ter descontos.
- **Identifique qual Armazenamento do Azure usar:** com o Azure Managed Disks você especifica o tamanho do disco e o desempenho e o serviço cria e o gerencia.
- **Selecione um sistema operacional:** Windows ou Linux

## Armazenamento

Todas máquinas tem pelo menos dois discos: um para o sistema operacional e outro temporário. Tipos de discos:

- **Disco de Sistema Operacional:** é anexado na criação e registrado como SATA com rótulo C: por padrão.
- **Disco Temporário:** fornece armazenamento temporário para aplicativos e processos. Rotulado por D: por padrão.
- **Disco de dados:** registrado como SCSI e rotulados com a letra que for escolhida. O tamanho da VM determina quantos desses discos podem ser anexados e o tipo de armazenamento deles.

## Conectando a uma VM

Há diversas maneiras para acesso por meio do Azure Bastion diretamente, com os protocolos SSH e RDP e com Cloud Shell.

O Azure Bastion é um serviço PaaS totalmente gerenciado que oferece conectividade RDP/SSH por meio de SSL. Quando utilizado as VMs não precisam de um IP público.

## Disponibilidade

### Conjuntos de disponibilidade (availability sets)

Um conjunto de disponibilidade (availability sets) é um recurso lógico para implantar VMs em conjunto o que garante que nem todos sejam atualizados ao mesmo tempo devido a uma atualização do host. Eles podem ser criados através do portal, template ARM, scripts ou API.

Existe também o conceito de domínio de atualização (update domain), onde cada domínio consiste em um conjunto de hardware que pode ser atualizado e reiniciado ao mesmo tempo, e domínio de falha (fault domain), onde são agrupados VMs com hardware que compartilham um mesmo ponto de falha. 

Cada máquina virtual em um conjunto de disponibilidade é colocada em um domínio de atualização e falha.

## Conjuntos de Dimensionamento (scale sets)

Azure Virtual Machine Scale Sets é um recurso para implantar e gerenciar VMs idênticas. Por serem idênticas é possível ter o dimensionamento automático (autoscaling). Com um conjunto é possível usar o Azure Load Balancer. É suportado até mil VMs com imagem padrão ou 600 personalizadas.

## Extensões de VMs

São pequenos aplicativos que fornecem configuração e automação pós-implantação para as VMs. Instalação de antivirus ou rodar um script de configuração são alguns dos casos de uso. Os scripts possuem um tempo limite de 90 minutos para execução.

## Azure Automation State Configuration

É um serviço do Azure criado no PowerShell. Esse serviço permite que você implemente, monitore com confiabilidade e atualize automaticamente o estado desejado de todos os seus recursos. A Automação do Azure fornece ferramentas para definir configurações e aplicá-las a máquinas reais e virtuais.

