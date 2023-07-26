É um recurso gerenciado de segurança de redes baseado na nuvem para proteger suas redes virtuais.

O firewall possui um IP público estático.

## Hub-spoke

A topologia recomendada para implementar um firewall é a **hub-spoke**. Nela o **hub** é uma rede virtual que atua como ponto principal de conectividade com a sua rede local. No **hub** é onde o firewall se encontra. Já os **spokes** são redes virtuais que se emparelham com o hub e podem ser usadas para isolamento de recursos.

Algumas possíveis vantagens dessa topologia:
- Economia de custos por centralizar recursos compartilhados.
- Separação de função entre SecOps/InfraOps e DevOps.
- Controle centralizado dos aspectos de segurança.

## Regras do Firewall

Todo o tráfego é negado por padrão. Para permitir tráfego para algum recurso é necessário a definição de regras. Existem três tipos de regras (**que são processadas na seguinte ordem**):  
- Rede (Qualquer tráfego não HTTP/S que tem permissão deve ter uma regra de rede).
- Aplicativos (Regras de aplicativo definem os FQDNs (nomes de domínio totalmente qualificados) que podem ser acessados por uma sub-rede).
- NAT (podem ser úteis são a publicação de aplicativos SSH, RDP ou não HTTP/S na Internet).

