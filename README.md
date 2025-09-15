# Projeto de Rede SOHO - Cisco Packet Tracer

Repositório para a documentação e arquivo `.pkt` do projeto de simulação de uma rede SOHO (Small Office/Home Office), desenvolvido no Cisco Packet Tracer.

---

## 📜 Sumário

- [1. Introdução](#1-introdução)
- [2. Desenvolvimento](#2-desenvolvimento)
  - [2.1 Planejamento e Topologia da Rede](#21-planejamento-e-topologia-da-rede)
  - [2.2 Configuração do Roteador](#22-configuração-do-roteador)
  - [2.3 Configuração dos Dispositivos e Validação da Conectividade](#23-configuração-dos-dispositivos-e-validação-da-conectividade)
- [3. Conclusão](#3-conclusão)
- [Ferramentas e Autor](#ferramentas-e-autor)

---

## 1. Introdução

O objetivo principal desta atividade foi aplicar os conhecimentos teóricos de redes de computadores. Para isso, utilizei o software Cisco Packet Tracer para simular a criação de uma rede. Os objetivos específicos que tracei para esta atividade foram: validar a comunicação ponta a ponta entre todos os dispositivos da rede.

## 2. Desenvolvimento

Nesta seção, descrevo detalhadamente todas as fases do projeto, desde a montagem inicial até os testes finais. As capturas de tela são essenciais para mostrar o processo.

### 2.1 Planejamento e Topologia da Rede

A primeira etapa foi a montagem da infraestrutura de rede. Os componentes utilizados foram:

- **Roteador (1x WRT300N):** Atua como o cérebro da rede, interligando os segmentos com e sem fio.
- **Switch (1x Cisco 2960):** Utilizado para aumentar o número de portas disponíveis na rede, permitindo a conexão de múltiplos dispositivos.
- **Dispositivos com Fio (3x PCs, 1x Impressora):** Simulam as estações de trabalho e recursos de rede fixos.
- **Dispositivos Sem Fio (1x Laptop, 1x Smartphone):** Representam os dispositivos móveis que necessitam de flexibilidade.

Realizei a conexão física dos dispositivos com cabo direto (Copper Straight-Through), ligando os PCs e a impressora ao switch, e este, por sua vez, a uma das portas LAN do roteador.

*Insira aqui o seu print da topologia. Para isso, suba a imagem para o seu repositório GitHub e substitua `caminho/para/imagem_topologia.png` pelo link da imagem.*
![Topologia da Rede](caminho/para/imagem_topologia.png)

### 2.2 Configuração do Roteador

Com a rede fisicamente montada, o passo seguinte e mais crucial foi a configuração lógica do roteador.

#### Endereço do Gateway
Na seção "Network Setup", defini o endereço IP do roteador como `192.168.10.1`, com a máscara de sub-rede `255.255.255.0`. Este IP serve como o gateway padrão, ou seja, a "porta de saída" para todos os dispositivos que precisarem se comunicar com redes externas.

#### Servidor DHCP e Rede Sem Fio (WLAN)
Além do Gateway, configurei os seguintes serviços essenciais no roteador:
- **Servidor DHCP:** Habilitei o serviço para automatizar a atribuição de IPs na rede, configurando a faixa para iniciar em `192.168.10.100` com um limite de 50 usuários.
- **Segurança Wireless:** Criei uma rede Wi-Fi com o SSID "MinhaRedeSOHO" e a protegi com o protocolo de segurança WPA2 Personal.

*Insira aqui o seu print da tela de configuração do roteador. Substitua `caminho/para/imagem_config.png` pelo link.*
![Configuração do Roteador](caminho/para/imagem_config.png)

### 2.3 Configuração dos Dispositivos e Validação da Conectividade

Com o roteador configurado, o passo final foi garantir que os dispositivos finais (endpoints) recebessem as configurações e conseguissem se comunicar.

#### Obtenção de IP
Em todos os dispositivos finais (PCs, impressora, laptop e smartphone), acessei as configurações de rede e os configurei para obter um endereço IP via DHCP. A tabela abaixo resume os endereços recebidos:

| Dispositivo   | Endereço IP Recebido |
| :------------ | :------------------- |
| PC1           | `192.168.10.2/24`    |
| PC2           | `192.168.10.3/24`    |
| PC3           | `192.168.10.4/24`    |
| Laptop0       | `192.168.10.11/24`   |
| Smartphone0   | `192.168.10.12/24`   |
| Printer0      | `192.168.10.30/24`   |

#### Testes de Conectividade
Para validar a comunicação, utilizei a ferramenta `ping`. Um `ping` bem-sucedido confirma que há um caminho válido e que a comunicação na camada de rede (camada 3 do modelo OSI) está funcionando. Realizei múltiplos testes, como:

- **Teste 1 (Cabo -> Wi-Fi):** Um `ping` do `PC1 (192.168.10.2)` para o `Laptop0 (192.168.10.11)`.
- **Teste 2 (Wi-Fi -> Cabo):** Um `ping` do `Smartphone0 (192.168.10.12)` para a `Printer0 (192.168.10.30)`.
- **Teste 3 (Dispositivo -> Gateway):** Um `ping` de um dos PCs para o roteador (`192.168.10.1`).

Todos os testes retornaram com 100% de sucesso, confirmando que a rede estava totalmente operacional.

*Insira aqui o seu print de um teste de ping bem-sucedido. Substitua `caminho/para/imagem_ping.png` pelo link.*
![Teste de Ping](caminho/para/imagem_ping.png)

## 3. Conclusão

A execução desta atividade permitiu-me aplicar e consolidar de forma prática os conhecimentos teóricos sobre redes. A implementação da rede foi concluída com sucesso, atingindo todos os objetivos falados na introdução. A rede se mostrou estável, segura e funcional, com todos os dispositivos obtendo configurações de rede certa e se comunicando de forma transparente. Esta atividade reforçou minha compreensão sobre a importância do planejamento de rede e o papel central de um roteador.

---

## Ferramentas e Autor

- **Ferramenta Utilizada:** Cisco Packet Tracer 8.2
- **Autor:** [Seu Nome Completo]
  - **GitHub:** [Link para seu GitHub]
  - **LinkedIn:** [Link para seu LinkedIn]
