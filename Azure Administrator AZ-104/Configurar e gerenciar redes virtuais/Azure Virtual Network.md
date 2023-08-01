Rede Virtual do Azure é uma representação virtual da rede na nuvem. Algumas características importantes:

- É um isolamento lógico da Azure dedicada a sua assinatura.
- Pode ser usada para provisionar e gerencias VPNs.
- Tem o próprio bloco CIDR ( Classless Inter-Domain Routing) e pode ser vinculada a outras redes virtuais ou locais (quando os blocos CIDR não se sobrepõe).
- Tem as configurações do seu servidor DNS e a segmentação em sub-redes.
- Não é possível redefinir o espaço de endereços IP para uma rede depois que ela é criada.
- Para criar uma rede virtual, você precisa definir pelo menos uma sub-rede.

## Sub-redes

Divisões lógicas na rede virtual que são usadas para aprimorar segurança, desempenho ou facilitar o gerenciamento. Informações importantes sobre a sub-rede:

- Possui seu próprio intervalo de IP que se encaixar no espaço de endereço da rede virtual.
- O intervalo de endereços é exclusivo na rede virtual.
- O intervalo não pode sobrepor a outros intervalos de sub-rede da mesma rede virtual.
- O espaço de endereços ÌP tem que usar notação CIDR.
- Pode ter apenas um grupo de segurança associado.


### Endereços reservados

Para cada sub-rede, cinco endereços de IP são reservados (os quatro primeiros e o último):

- O primeiro identifica o endereço da rede virtual
- O segundo é configurado como gateway padrão.
- O terceiro e quarto, a Azure mapeia esses endereços IP do DNS do Azure para o espaço de rede virtual.
- O ultimo é o endereço de broadcast da rede virtual.

## Peering (emparelhamento)

Permite conectar redes virtuais para que possam comunicar entre si. Após emparelhadas elas funcionam como uma única rede em termos de conectividade.

Vantagens:
- **Tráfego privado entre as redes**
- **Tráfego é roteado por meio da rede da Azure**
- **Baixa latência (maior desempenho)**
- **Comunicação simplificada entre as redes**
- **Sem tempo de inatividade**

Pontos importantes:
- Somente as redes virtuais diretamente emparelhadas podem se comunicar entre si. Redes virtuais não podem se comunicar com pares de seus pares.
- Os espaços de endereço IP das redes conectadas no Azure, entre o Azure e o on premise, não podem se sobrepor. Isso também se aplica às redes virtuais emparelhadas.

### Azure VPN Gateway

Quando as redes virtuais são emparelhadas, você pode configurar o Gateway de VPN do Azure na rede virtual emparelhada como um _ponto de trânsito_. Pode ser usado para enviar tráfego criptografado entre Azure e on-premise pela internet ou entre redes Azure. Uma rede virtual pode ter apenas um gateway de VPN.

## System routes (rotas do sistema)

O Azure usa _rotas de sistema_ para direcionar o tráfego de rede entre máquinas virtuais, redes locais e a Internet. As informações sobre as rotas do sistema são registradas em uma _tabela de rotas_.

### Rotas definidas pelo usuário (UDR)

O Azure lida automaticamente com todo o roteamento de tráfego de rede, mas, em alguns casos, uma configuração personalizada é preferível usando rotas definidas pelo usuário (UDRs). - Semelhante às rotas do sistema, as UDRs também acessam tabelas de rotas.

## Service Endpoints (pontos de extremidade de serviço)

Podem estender sua identidade de rede virtual para seus recursos e isso permite adicionar regras da rede virtual (para restringir acesso pela internet por exemplo).

## Azure Private Links

Simplifica a arquitetura de rede e protege a conexão entre endpoints no Azure ao eliminar a exposição de dados para a Internet pública mantendo todo o tráfego na rede global da Microsoft.

## Network Virtual Appliance (NVA)

Uma NVA (solução de virtualização de rede) é uma solução de virtualização que consiste em várias camadas, tais como: firewall, otimizador de WAN, roteadores, load balancers, etc.

Você pode implantar NVAs escolhidos de provedores no Azure Marketplace. Tais provedores incluem Cisco, Check Point, Barracuda, Sophos, WatchGuard e SonicWall. Você pode usar uma NVA para filtrar o tráfego de entrada para uma rede virtual e bloquear solicitações mal-intencionadas ou solicitações feitas de recursos inesperados.