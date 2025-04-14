# Redes
---

# 🧠 Análises de Redes de Computadores

Este repositório reúne estudos, análises práticas e troubleshooting de redes de computadores realizados em ambientes reais e simulados. O foco principal é entender o comportamento dos protocolos, identificar problemas de conectividade e oferecer soluções técnicas com base em logs e pacotes capturados via **Wireshark**, configurações de **switches, firewalls (como Mikrotik)**, e dispositivos com **PoE (Power over Ethernet)**.

---

## 🔍 Objetivo

Registrar e compartilhar experiências com:

- Diagnóstico de problemas com **DHCP**
- Comportamentos anômalos no **tráfego de rede**
- Identificação de falhas por **sobrecarga de serviços**
- Investigação de **problemas com PoE**
- **Captura e análise de pacotes** para interpretação de falhas
- Estudo detalhado do ciclo de requisições DHCP
- Configurações e testes com ferramentas CLI em ambientes **Windows** e **Mikrotik**

---

## 📦 O que você vai encontrar aqui

- 📁 **/analises-pacotes**  
  Logs de tráfego coletados com Wireshark: pacotes DHCP Discover, Request, ACK, ARP, entre outros.

- 📁 **/topologias**  
  Modelos de topologias usadas para testes, como redes cabeadas, Wi-Fi e PoE.

- 📁 **/scripts-cli**  
  Comandos e scripts usados para diagnóstico via CLI (Windows e Mikrotik).

- 📁 **/documentacao**  
  Documentos explicando as causas prováveis dos problemas enfrentados, junto com prints e comentários sobre cada análise.

---

## 🔧 Casos investigados

### ⚙️ DHCP com comportamento irregular
Durante a análise, foram observados pacotes DHCP sem **Offer**, com **Discover duplicados**, e inconsistências no **Lease Time** (Discover com 90 dias, mas ACK com apenas 10 minutos).  
Além disso:

- **Option 50, 51, 54** analisados em detalhes
- Alguns pacotes com campos como "Your (Client)" e "Next Server IP" em 0.0.0.0
- Presença de requisições com **Source 0.0.0.0** e sem encaminhamento correto

### ⚡ PoE causando instabilidade
Foram detectadas quedas recorrentes nos dispositivos conectados via PoE. O motivo provável: **sobrecorrente em portas do switch**, impedindo o fornecimento de energia adequado para o roteador, resultando em reinicializações e perda de conectividade.

### 📶 Wi-Fi instável
Foi identificado que o Wi-Fi apresentava as maiores quedas, enquanto a rede cabeada se mantinha estável até certo ponto. As análises indicam possível **gargalo no firewall**, que também atua como servidor DHCP.

---

## 🔗 Ferramentas utilizadas

- [Wireshark](https://www.wireshark.org/)
- [Mikrotik CLI](https://wiki.mikrotik.com/)
- Switch Aruba
- Zabbix
- CMD / PowerShell (Windows)
- Packet Tracer (para testes simulados)
- Tracert / Ping / ARP tools

---

## 📚 Conceitos abordados

- Modelo OSI (foco nas camadas 2, 3 e 7)
- Endereçamento IP, ARP, DNS
- Funcionamento detalhado do protocolo DHCP
- ECN (Explicit Congestion Notification) em pacotes IP
- Diferença entre broadcast e unicast
- Failover e estratégias de contingência

---

## 🧪 Em andamento

- Implementação de failover na matriz
- Novas capturas de pacotes para análise mais profunda de DNS
- Validação do comportamento em ambientes com múltiplas VLANs

---

## 🤝 Contribuições

Este projeto é um repositório pessoal de aprendizado, mas sugestões e colaborações são bem-vindas. Se quiser compartilhar insights ou fazer um fork para adicionar análises próprias, fique à vontade!

---

## 🧠 Sobre o autor

Análises realizadas como parte de estudos e experiências práticas em redes corporativas. Todo o conteúdo está sendo postado com o máximo de cuidado para **preservar informações sensíveis** e simular cenários reais para fins educacionais. Parte dos conteúdos apresentados aqui fazem parte de experiências práticas em ambientes de produção e ambientes empresariais. 

