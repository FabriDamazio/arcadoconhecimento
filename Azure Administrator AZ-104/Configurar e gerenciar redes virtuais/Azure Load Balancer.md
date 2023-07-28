Usado para distribuir com eficiência o tráfego que entra na rede entre servidores e recursos de back-end.

Pontos importantes sobre o Load Balancer:

- Pode ser usado tanto em entrada quanto em saída.
- Pode ser público ou privado.
- Necessário configurar quatro componentes: IP front-end, pools de back-end, health probes e regras de balanceamento.
- Ele escala verticalmente.
- O tipo padrão de distribuição utiliza um hash de cinco tuplas.
- As maquinas virtuais que utilizam o balanceador precisam estar na mesma rede virtual.
- Utiliza a camada 4 de rede.

