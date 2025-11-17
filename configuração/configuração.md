Laboratório Firewall FortiGate – Segmentação, Bloqueios e Testes com Kali + Metasploitable

Autor: Thiago Alves
Objetivo: Demonstrar domínio prático em firewall, segmentação, bloqueio de portas perigosas, políticas de segurança e validação dos bloqueios usando Kali Linux e Metasploitable.

1. Topologia do Ambiente

port1 → LAN (192.168.10.1/24)
port2 → WAN (DHCP / NAT ativo)
Hosts internos utilizados no LAB:
Kali Linux → 192.168.10.x
Metasploitable → 192.168.10.x
Arquivo sugerido: imagens/topologia.png

2. Configuração das Interfaces
   
LAN – port1

IP: 192.168.10.1/24
Role: LAN
Administrative Access: HTTPS, PING, SSH (opcional)
DHCP Server: opcional
WAN – port2
Modo: DHCP Client
NAT habilitado

3. Objetos de Rede (Address Objects)

Menu: Policy & Objects → Addresses
LAN_Internal → 192.168.10.0/24

Hosts opcionais:
Kali_Host → 192.168.10.x
Metasploitable_Host → 192.168.10.x

4. Serviços Criados (Portas Perigosas)

Menu: Policy & Objects → Services → Create New
Serviço	Porta	Protocolo
SMB	TCP 445	TCP
TELNET	TCP 23	TCP
RPC	TCP 135	TCP
NETBIOS	TCP/UDP 137–139	TCP/UDP
Grupo de Serviços (opcional)
Portas_Perigosas
SMB
TELNET
RPC
NETBIOS

5. Política de Bloqueio (DENY)
Menu: Policy & Objects → IPv4 Policy → Create New
Nome: Bloqueio_Portas_Populares
Incoming Interface: port1
Outgoing Interface: Any
Source: LAN_Internal
Destination: All
Service: Portas_Perigosas
Action: DENY
Logging: Enabled
NAT: Off


6. Política de Acesso LAN → Internet

Nome: LAN_para_Internet
Incoming: port1
Outgoing: port2
Source: LAN_Internal
Destination: All
Service: ALL
Action: ACCEPT
NAT: On
Security Profiles:
IPS: IPS_Basic
(Opcional) AntiVirus, WebFilter


7. Testes Realizados

Internet acessível na LAN 
Portas 445, 23, 135 bloqueadas 
Logs aparecem em Log & Report → Forward Traffic 
IPS detectando tentativas anormais 
Comunicação Kali → Metasploitable funcionando 
Testes realizados com:
ping
hping3 (SYN Flood)
nmap (portas bloqueadas e scans)
