É um balanceador de carga para o tráfego da Web. 

Pontos importantes sobre o Gateway:

- Pode rotear tráfego para VMs, App Services e até para servidores on premise.
- Possui balanceamento de carga round robin (encaminha chamada para uma lista de servidores em sequência).
- Suporta sessão (session stickiness) para garantir que a chamada do mesmo cliente vá para o mesmo servidor.
- Suporte aos protocolos HTTP, HTTPS, HTTP/2 e WebSockets.
- Implementa firewall de aplicação web (opcional).
- Suporta Criptografia.
- Dimensionamento automático de carga.
- Necessário configurar os componentes: IP front-end, firewall (opcional), listeners, pools de back-end, health probes e regras de balanceamento.
- Utiliza a camada 7 de rede.


