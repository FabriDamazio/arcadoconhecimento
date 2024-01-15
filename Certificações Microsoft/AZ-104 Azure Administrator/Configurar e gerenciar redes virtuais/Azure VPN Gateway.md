Um gateway de VPN é um tipo de gateway de rede virtual. As instâncias do Gateway de VPN do Azure são implantadas em uma sub-rede dedicada da rede virtual e permitem a seguinte conectividade:

- Conecte datacenters locais a redes virtuais por meio de uma conexão site a site.
- Conecte dispositivos individuais a redes virtuais por meio de uma conexão ponto a site.
- Conecte redes virtuais a outras redes virtuais por meio de uma conexão rede a rede.

Todas as transferências de dados são criptografadas em um túnel privado à medida que atravessam a Internet. Você pode implantar apenas um gateway de VPN em cada rede virtual. Porém, você pode usar um gateway para se conectar a vários locais, incluindo outras redes virtuais ou datacenters locais.  

Ao configurar um gateway de VPN, você deve especificar o tipo de VPN: baseada em política ou baseada em rota. A principal distinção entre esses dois tipos é como eles determinam qual tráfego precisa de criptografia. No Azure, independentemente do tipo de VPN, o método de autenticação empregado é uma chave pré-compartilhada.