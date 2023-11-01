## Azure DDoS Protection

O serviço de proteção contra DDoS do Azure foi projetado para ajudar a proteger seus aplicativos e servidores ao analisar o tráfego de rede e descartar qualquer coisa que pareça um ataque de DDoS.

- **Always-on traffic monitoring**: os padrões de tráfego de seus aplicativos são monitorados 24 horas por dia, 7 dias por semana, em busca de indicadores de ataques DDoS.
- **Adaptive real time tuning**: O perfil se ajusta conforme o tráfego é alterado ao longo do tempo.
- **DDoS Protection telemetry, monitoring, and alerting**: a Proteção contra DDoS do Azure expõe uma telemetria avançada por meio do Azure Monitor.

A Proteção contra DDoS do Azure dá suporte a dois tipos de camadas:

- **DDoS Network Protection:**  Se ajusta automaticamente para proteger os recursos específicos do Azure em uma rede virtual. É muito simples habilitar a proteção em qualquer rede virtual nova ou existente, e ela não exige nenhum aplicativo ou alterações de recursos.
- **DDoS IP Protection**:  A Proteção de IP contra DDoS contém os mesmos recursos principais de engenharia da Proteção de rede contra DDoS, mas difere por não incluir os serviços de valor agregado, como suporte de resposta rápida a DDoS, proteção de custos e descontos no Firewall de Aplicativo Web (WAF)

## Azure Firewall

O Firewall do Azure é um serviço de segurança de rede gerenciado e baseado em nuvem que fornece proteção contra ameaças para suas cargas de trabalho e recursos de nuvem executados no Azure.

Você pode implantar o Firewall do Azure em qualquer rede virtual, mas a melhor abordagem é usá-lo em uma rede virtual centralizada.

O Firewall do Azure é oferecido em três SKUs: Standard, Premium e Basic. A lista a seguir fornece uma lista de alguns dos principais recursos incluídos em todas as SKUs do Firewall do Azure:

- **Built-in high availability and availability zones:**  O Firewall do Azure pode ser configurado para abranger várias zonas de disponibilidade para aumentar a disponibilidade.
- **Network and application level filtering**:  use o endereço IP, a porta e o protocolo para dar suporte à filtragem de nome de domínio totalmente qualificado para o tráfego de HTTP(s) de saída e os controles de filtragem de rede.
- **Outbound SNAT and inbound DNAT to communicate with internet resources**: converter o endereço IP privado dos recursos de rede em um endereço IP público do Azure
- **Multiple public IP addresses**: esses endereços podem ser associados ao firewall do Azure.
- **Threat intelligence**: A filtragem contra ameaças baseada em inteligência pode ser habilitada para o seu firewall de forma a alertar e rejeitar o tráfego de/para endereços IP e domínios mal-intencionados.
- **Integration with Azure Monitor**

## Web Application Firewall (WAF)

O WAF (Firewall do Aplicativo Web) fornece proteção centralizada de seus aplicativos Web contra vulnerabilidades e explorações comuns. Um WAF centralizado ajuda a tornar o gerenciamento de segurança mais simples, aprimora o tempo de resposta a uma ameaça de segurança e permite a aplicação de patch a uma vulnerabilidade conhecida em um só lugar, em vez de proteger cada aplicativo Web individual.

## Azure Virtual Network

A VNet do Azure permite que as organizações segmentem sua rede. As organizações podem criar várias redes virtuais por região, por assinatura, e várias redes menores (sub-redes) podem ser criadas em cada rede virtual.

As VNets fornecem contenção em nível de rede dos recursos, sem tráfego permitido em VNets ou de entrada na VNet, por padrão. A comunicação precisa ser provisionada explicitamente. Isso permite mais controle sobre como os recursos do Azure em uma VNet se comunicam com outros recursos do Azure, com a Internet e com as redes locais.

## Azure Network Security Groups

Os NSGs (grupos de segurança de rede) permitem filtrar o tráfego de rede de e para os recursos do Azure em uma rede virtual do Azure; por exemplo, uma máquina virtual. Um NSG consiste em regras que definem como o tráfego é filtrado. Você pode associar apenas um grupo de segurança de rede a cada sub-rede e adaptador de rede de uma rede virtual em uma máquina virtual. Entretanto, o mesmo grupo de segurança de rede pode ser associado a quantas interfaces de rede e de sub-rede você desejar.

## Azure Bastion

O Azure Bastion é um serviço que ao ser implantado permite que você se conecte a uma máquina virtual usando seu navegador e o portal do Azure. O serviço do Azure Bastion é um serviço PaaS totalmente gerenciado por plataforma que pode ser provisionado dentro de sua rede virtual. O Azure Bastion fornece conectividade RDP e SSH segura e direta com suas máquinas virtuais diretamente do portal do Azure usando o protocolo TLS. Ao se conectar por meio do Azure Bastion, suas máquinas virtuais não precisarão de um endereço IP público, nem de um agente e tampouco de um software cliente especial.

## Azure Key Vault

O Azure Key Vault é serviço de nuvem para armazenar e acessar segredos de maneira segura. Um segredo é qualquer coisa a qual você queira controlar rigidamente o acesso, como chaves de API, senhas, certificados ou chaves criptográficas.