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