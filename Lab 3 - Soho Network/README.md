# Laboratório de Redes SOHO - Cisco Packet Tracer

Laboratório prático desenvolvido no **Cisco Packet Tracer** para implementação e configuração de uma pequena rede **SOHO (Small Office/Home Office)**, utilizando um roteador wireless residencial como equipamento central da rede.

## 📌 Sobre o projeto

O laboratório simula a infraestrutura de rede de um pequeno escritório, com dispositivos conectados por meio de uma rede **cabeada e sem fio**.

O **WRT300N** atua como equipamento central da rede, desempenhando funções de **roteador, switch, ponto de acesso Wi-Fi e servidor DHCP**.

A prática permite aplicar conceitos de conectividade, endereçamento IPv4, DHCP, redes wireless, segurança Wi-Fi e testes de comunicação entre dispositivos.

## 🎯 Objetivos

- Compreender o funcionamento de uma rede SOHO;
- Configurar um roteador wireless residencial;
- Configurar uma rede Wi-Fi;
- Configurar segurança utilizando **WPA2-PSK**;
- Utilizar o serviço **DHCP** para atribuição automática de endereços;
- Conectar dispositivos por meio de rede cabeada e wireless;
- Realizar testes de conectividade utilizando o comando `ping`;
- Verificar a comunicação entre dispositivos da rede;
- Utilizar o **Cisco Packet Tracer** para simulação de redes.

## 🏗️ Estrutura e Dispositivos

- **Internet:** 1 Cloud-PT simulando o provedor;
- **Modem:** 1 Cable Modem;
- **Roteador:** 1 WRT300N;
- **Dispositivos cabeados:** 2 PCs e 1 impressora de rede;
- **Dispositivos sem fio:** 1 notebook e 1 smartphone.

### 🖧 Representação visual da topologia implementada

```text
                         Internet
                            │
                            ▼
                       Cloud-PT
                            │
                            ▼
                      Cable Modem
                            │
                            ▼
                    ┌─────────────────┐
                    │     WRT300N     │
                    │                 │
                    │ DHCP + Wi-Fi    │
                    │ + Switch        │
                    └─────────────────┘
                      │      │      │
              ┌───────┘      │      └───────┐
              ▼               ▼              ▼
             PC0             PC1         Impressora

                            )))))
                       Rede Wi-Fi
                         )))))

                    ┌───────────────┐
                    │   Notebook    │
                    └───────────────┘

                    ┌───────────────┐
                    │  Smartphone   │
                    └───────────────┘
```

## 🔌 Conectividade

A topologia utiliza diferentes meios de conexão:

- **Cloud-PT → Cable Modem:** cabo coaxial;
- **Cable Modem → WRT300N:** cabo direto;
- **PC0 → WRT300N:** cabo direto;
- **PC1 → WRT300N:** cabo direto;
- **Impressora → WRT300N:** cabo direto;
- **Notebook → WRT300N:** conexão Wi-Fi;
- **Smartphone → WRT300N:** conexão Wi-Fi.

## 📡 Configuração da Rede Wireless

O WRT300N foi configurado como **ponto de acesso wireless**, permitindo a conexão dos dispositivos móveis à rede.

A rede sem fio foi configurada utilizando:

- **SSID personalizado;**
- **WPA2 Personal;**
- **WPA2-PSK;**
- **Senha de acesso definida durante a configuração do laboratório.**

## 🌐 Configuração DHCP

O **WRT300N** atua como servidor **DHCP**, permitindo que os dispositivos conectados obtenham automaticamente suas configurações de rede.

Foram configurados para utilizar DHCP:

- PC0;
- PC1;
- Impressora;
- Notebook;
- Smartphone.

Dessa forma, não foi necessário configurar manualmente o endereço IP de cada dispositivo.

## 🧪 Teste de Conectividade

Após a configuração da rede, foi realizado um teste de comunicação entre o **PC0 e a impressora de rede** utilizando o comando `ping`.

No terminal do PC0, foi utilizado:

```bash
ipconfig
```

para verificar as configurações de rede atribuídas pelo DHCP.

Em seguida, foi utilizado o comando:

```bash
ping <ENDERECO_DA_IMPRESSORA>
```

O recebimento das respostas **ICMP** confirmou a comunicação entre os dispositivos conectados à rede local.

> 🔒 Os endereços utilizados durante a simulação não são registrados neste README.

## ✅ Resultado

A prática permitiu consolidar conceitos fundamentais de redes SOHO, incluindo **conectividade cabeada e wireless, DHCP, endereçamento IPv4, segurança Wi-Fi e testes de conectividade**.

O resultado final foi uma pequena rede de escritório funcional, com dispositivos cabeados e sem fio conectados ao roteador wireless e capazes de realizar comunicação dentro da rede local.
