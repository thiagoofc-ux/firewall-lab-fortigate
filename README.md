# 🔥 LAB de Firewall Fortigate – Segmentação, Regras, IPS e Testes Práticos

Este repositório apresenta um laboratório completo utilizando o **FortiGate (emulador FortiVM Free)**, com foco em segurança de rede aplicada, seguindo práticas exigidas em vagas de **Analista de Segurança da Informação Júnior**.

O projeto inclui:

- Criação da topologia virtual  
- Configuração da rede no Fortigate  
- Políticas de segmentação e controle de tráfego  
- Bloqueio de portas inseguras  
- Configuração de IPS/DoS Policy  
- Testes práticos usando Kali Linux e Metasploitable  
- Evidências reais (prints)  
- Documentação completa e organizada  

---

## 📌 Estrutura do projeto

### `/configuracao/`
Arquivos técnicos, passo a passo e regras:

- **configuracao.md** → Guia completo de configuração do ambiente  
- **regras.txt** → Todas as regras criadas no Fortigate  
- **topologia.png** → Desenho da topologia da rede  
- **testes.md** → Demonstração dos testes de segurança realizados  

### `/evidencias/`
Pasta destinada aos prints coletados do ambiente real:

- Telas do Fortigate  
- Regras criadas  
- Logs  
- Testes vindo do Kali  
- Validação final  

---

## 🏗 Tecnologias utilizadas

- **FortiGate FortiVM (Emulador Free)**
- **Kali Linux**
- **Metasploitable2**
- VirtualBox

---

## 🎯 Objetivo principal

Demonstrar na prática:

- Configuração de firewall corporativo  
- Entendimento de segmentação e fluxo LAN → WAN  
- Criação de políticas de bloqueio  
- Análise de logs  
- Testes de ataques e comportamento do IPS  
- Aplicação de boas práticas de hardening  

---

## 🧪 Testes realizados

Os testes estão documentados em `/configuracao/testes.md`, incluindo:

- SYN Flood (hping3)
- Port Scan (nmap)
- Bloqueio Telnet (porta 23)
- Bloqueio SMB (445)
- Bloqueio RPC (135)
- Detecção de ICMP Sweep
- Logs gerados pelo Fortigate

---

## 📸 Evidências

Todos os prints se encontram na pasta:

/evidencias/
