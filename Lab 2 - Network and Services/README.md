# Laboratório 2 - Serviços de Rede e Camada de Transporte

Laboratório prático desenvolvido no **Cisco Packet Tracer** para construção e configuração de uma rede local, com implementação de serviços de aplicação e análise do funcionamento da camada de transporte.

## 📌 Sobre o projeto

O laboratório simula uma pequena rede composta por um **PC-Cliente**, um **Servidor-Central** e um **switch**, permitindo configurar e testar serviços de **HTTP/HTTPS e DNS**.

A prática também possibilita observar, por meio do **Modo Simulation** do Cisco Packet Tracer, o funcionamento dos protocolos **DNS, TCP, HTTP e ICMP** durante a comunicação entre o cliente e o servidor.

## 🎯 Objetivos

- Construir uma rede local utilizando um switch;
- Configurar endereçamento IPv4;
- Configurar um servidor para disponibilizar serviços de rede;
- Configurar o serviço **HTTP/HTTPS**;
- Configurar o serviço **DNS**;
- Realizar testes de conectividade utilizando o comando `ping`;
- Testar a resolução de nomes utilizando o comando `nslookup`;
- Analisar os protocolos **DNS, TCP, HTTP e ICMP**;
- Compreender a comunicação entre as camadas de transporte e aplicação;
- Utilizar o **Modo Simulation** para visualizar o fluxo dos pacotes.

## 🏗️ Estrutura e Dispositivos

- **1 Switch Cisco 2960**
- **1 PC-Cliente**
- **1 Servidor-Central**

### 🖧 Representação visual da topologia implementada

```text
                 ┌──────────────────┐
                 │     Switch       │
                 │     Cisco 2960   │
                 └────────┬─────────┘
                          │
              ┌───────────┴───────────┐
              │                       │
              ▼                       ▼
       ┌─────────────┐        ┌─────────────────┐
       │ PC-Cliente  │        │ Servidor-Central│
       │             │        │                 │
       │   Cliente   │        │ DNS + HTTP/HTTPS│
       └─────────────┘        └─────────────────┘
```

## 🔌 Conectividade

Os dispositivos foram conectados ao switch utilizando **cabos Copper Straight-Through**.

- **PC-Cliente → Switch:** FastEthernet;
- **Servidor-Central → Switch:** FastEthernet.

A conexão permite que o PC-Cliente se comunique diretamente com o Servidor-Central através da rede local.

## 🌐 Endereçamento e Serviços

O laboratório utiliza endereçamento IPv4 configurado manualmente nos dispositivos.

O **Servidor-Central** é responsável por disponibilizar os serviços de:

- **HTTP**
- **HTTPS**
- **DNS**

O serviço DNS foi configurado para associar um **nome de domínio de laboratório** ao endereço do servidor, permitindo que o cliente acesse o serviço web utilizando um nome em vez de informar diretamente o endereço IP.

> 🔒 Os endereços IP utilizados na configuração não são registrados neste README.

## 🌎 Configuração do Servidor Web

O serviço **HTTP/HTTPS** foi habilitado no Servidor-Central.

A página inicial do servidor também foi personalizada para apresentar uma mensagem de boas-vindas relacionada ao laboratório.

Essa configuração permite que o **PC-Cliente** acesse a página hospedada pelo servidor através do navegador web.

## 📖 Configuração do DNS

O serviço **DNS** foi habilitado no Servidor-Central.

Foi criado um registro associando o domínio utilizado no laboratório ao endereço do servidor.

Dessa forma, o PC-Cliente consegue utilizar o nome configurado para localizar o servidor web.

## 🧪 Validação da Rede

Foram realizados testes no **PC-Cliente** utilizando o Prompt de Comando.

### Teste de conectividade

Foi utilizado o comando:

```bash
ping <ENDERECO_DO_SERVIDOR>
```

O recebimento das respostas confirmou a comunicação entre o PC-Cliente e o Servidor-Central.

### Teste de resolução de nomes

Também foi utilizado o comando:

```bash
nslookup <DOMINIO_CONFIGURADO>
```

O resultado permitiu verificar se o serviço DNS estava funcionando corretamente e associando o domínio ao servidor configurado.

## 🔬 Análise no Modo Simulation

O **Modo Simulation** do Cisco Packet Tracer foi utilizado para observar o comportamento dos protocolos durante uma requisição web.

Foram selecionados os protocolos:

- **DNS**
- **TCP**
- **HTTP**
- **ICMP**

Após acessar o domínio configurado pelo navegador do PC-Cliente, foi possível acompanhar o fluxo dos pacotes entre o cliente e o servidor.

A análise das informações das PDUs permite observar os protocolos envolvidos na comunicação e identificar informações relacionadas às diferentes camadas da rede.

### 📚 Protocolos analisados

| Protocolo | Função |
|---|---|
| **ICMP** | Utilizado no teste de conectividade com `ping` |
| **DNS** | Responsável pela resolução de nomes |
| **TCP** | Responsável pelo transporte confiável dos dados |
| **HTTP** | Responsável pela comunicação entre navegador e servidor web |

## 🎥 Demonstração

A prática demonstra a construção da rede, configuração dos serviços **DNS e HTTP/HTTPS**, realização dos testes de conectividade e análise do tráfego no **Modo Simulation** do Cisco Packet Tracer.

## ✅ Resultado

A prática permitiu consolidar conhecimentos sobre **endereçamento IPv4, comunicação em redes locais, DNS, HTTP/HTTPS, TCP e ICMP**.

O laboratório também possibilitou visualizar, de forma prática, o caminho percorrido pelos dados e a participação dos diferentes protocolos durante uma comunicação entre cliente e servidor.
