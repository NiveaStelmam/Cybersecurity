
# Laboratório 5 - Configuração de LAN e ISP

Laboratório prático desenvolvido no **Cisco Packet Tracer** para implementação e configuração de uma rede local (**LAN**) conectada a um provedor de serviços de Internet simulado (**ISP**).

A atividade envolve a configuração de dispositivos de rede, endereçamento IPv4, comunicação entre redes, serviço DHCP, NAT e DNS, permitindo que um computador pertencente à rede local consiga acessar um servidor localizado em outra rede utilizando um nome de domínio.

## 📌 Sobre o projeto

O laboratório simula uma infraestrutura básica de rede composta por uma rede local de um cliente conectada a um provedor de Internet.

A rede local é formada por um computador conectado a um switch, que por sua vez está conectado ao roteador do cliente. O roteador do cliente estabelece uma conexão serial com o roteador do provedor (**ISP**), permitindo a comunicação com um servidor localizado na rede externa.

Além da conectividade entre as redes, foram configurados serviços importantes para o funcionamento da infraestrutura, como:

* Endereçamento IPv4;
* DHCP;
* NAT/PAT;
* DNS;
* Roteamento estático;
* Comunicação entre redes;
* Resolução de nomes de domínio.

## 🎯 Objetivos

* Compreender a comunicação entre uma rede LAN e um provedor ISP;
* Configurar interfaces de roteadores;
* Configurar endereçamento IPv4;
* Utilizar uma conexão serial entre roteadores;
* Implementar DHCP para atribuição automática de endereços IP;
* Configurar NAT/PAT para permitir a comunicação da rede privada com redes externas;
* Configurar um servidor DNS;
* Implementar rotas estáticas;
* Realizar testes de conectividade;
* Testar a resolução de nomes utilizando um navegador;
* Utilizar o **Cisco Packet Tracer** para simulação da infraestrutura.

## 🏗️ Estrutura e Dispositivos

A topologia foi composta pelos seguintes equipamentos:

* **1 Computador:** PC0;
* **1 Switch:** modelo Cisco 2960;
* **2 Roteadores:** modelo Cisco 1941;
* **1 Servidor:** utilizado para simular serviços do ISP.

Os roteadores foram equipados com o módulo **HWIC-2T**, necessário para disponibilizar interfaces seriais e permitir a conexão WAN entre o roteador do cliente e o roteador do provedor.

### ⚙️ Preparação dos roteadores

Como o modelo Cisco 1941 não possui interfaces seriais disponíveis por padrão, foi necessário instalar o módulo **HWIC-2T** nos dois roteadores.

O procedimento realizado foi:

1. Acessar a aba **Physical** do roteador;
2. Desligar o equipamento utilizando o **Power Switch**;
3. Selecionar o módulo **HWIC-2T**;
4. Inserir o módulo em um slot disponível;
5. Ligar novamente o roteador.

O procedimento foi realizado tanto no roteador do cliente quanto no roteador do ISP.

## 🖧 Representação visual da topologia implementada

```text
                        REDE ISP / INTERNET

                      ┌─────────────────┐
                      │   Server-ISP    │
                      │                 │
                      │   DNS + Web     │
                      └────────┬────────┘
                               │
                         Cabo Direto
                               │
                               ▼
                      ┌─────────────────┐
                      │   Router-ISP    │
                      │                 │
                      │   Roteador ISP  │
                      └────────┬────────┘
                               │
                         Conexão Serial
                               │
                               ▼
                      ┌─────────────────┐
                      │ Router-Cliente  │
                      │                 │
                      │ DHCP + NAT/PAT  │
                      └────────┬────────┘
                               │
                         Cabo Direto
                               │
                               ▼
                      ┌─────────────────┐
                      │    Switch-01    │
                      │    Cisco 2960   │
                      └────────┬────────┘
                               │
                         Cabo Direto
                               │
                               ▼
                      ┌─────────────────┐
                      │       PC0       │
                      │                 │
                      │ Cliente DHCP    │
                      └─────────────────┘
```

## 🔌 Conectividade

A topologia foi construída utilizando conexões Ethernet e uma conexão serial entre os roteadores.

As conexões utilizadas foram:

* **PC0 → Switch-01:** cabo direto;
* **Switch-01 → Router-Cliente:** cabo direto;
* **Router-Cliente → Router-ISP:** cabo serial;
* **Router-ISP → Server-ISP:** cabo direto.

A conexão serial representa uma ligação WAN entre a rede do cliente e a infraestrutura do provedor de Internet.

## 🌐 Configuração do Servidor

O servidor foi configurado com um endereço IP estático, permitindo que ele pudesse ser acessado pelos dispositivos localizados em outras redes.

Também foi configurado o gateway padrão, permitindo que o servidor pudesse responder a dispositivos externos à sua rede local.

### Configurações realizadas

* Endereço IPv4 estático;
* Máscara de sub-rede;
* Gateway padrão;
* Servidor DNS.

> 🔒 Os endereços específicos utilizados durante a simulação não são registrados neste README.

## 📡 Configuração do Serviço DNS

O servidor também foi configurado para atuar como um **servidor DNS**.

Foi criado um registro DNS associando um nome de domínio ao endereço IP do servidor.

Dessa forma, o computador da rede local não precisa conhecer diretamente o endereço IP do servidor para acessá-lo.

O funcionamento ocorre da seguinte forma:

```text
Usuário digita um domínio
          │
          ▼
PC envia consulta DNS
          │
          ▼
Servidor DNS resolve o nome
          │
          ▼
Retorna o endereço IP correspondente
          │
          ▼
PC estabelece comunicação com o servidor
```

## 🔀 Configuração do Roteador do ISP

O roteador do provedor foi responsável pela comunicação entre a conexão WAN e a rede onde está localizado o servidor.

Foram configurados:

* Endereçamento IP nas interfaces;
* Ativação das interfaces utilizando `no shutdown`;
* Interface Ethernet conectada ao servidor;
* Interface serial conectada ao roteador do cliente;
* Rota estática para permitir a comunicação entre as redes.

Após a configuração, as informações foram salvas na memória do equipamento.

## 🏠 Configuração da LAN do Cliente

O roteador do cliente foi configurado como o principal equipamento da rede local.

Ele desempenha diversas funções importantes na topologia:

* Gateway padrão da LAN;
* Servidor DHCP;
* Tradução de endereços utilizando NAT/PAT;
* Roteamento para redes externas.

A interface conectada à rede local foi configurada como:

```text
NAT Inside
```

Já a interface conectada ao ISP foi configurada como:

```text
NAT Outside
```

Essa configuração permite diferenciar o tráfego proveniente da rede interna do tráfego destinado à rede externa.

## 📥 Configuração do DHCP

O roteador do cliente foi configurado para atuar como servidor **DHCP**.

Dessa forma, os dispositivos da rede local podem receber automaticamente suas configurações de rede.

As configurações distribuídas pelo DHCP incluem:

* Endereço IPv4;
* Máscara de sub-rede;
* Gateway padrão;
* Servidor DNS.

Também foi definido um intervalo de endereços reservados para equipamentos de infraestrutura.

O funcionamento ocorre da seguinte forma:

```text
PC conectado à rede
        │
        ▼
Solicitação DHCP
        │
        ▼
Router-Cliente
        │
        ▼
Atribuição automática de:
IP + Máscara + Gateway + DNS
        │
        ▼
PC conectado à rede
```

Após configurar o computador para utilizar DHCP, o endereço IP foi obtido automaticamente.

## 🔄 Configuração do NAT/PAT

Foi configurado **NAT com overload**, também conhecido como **PAT (Port Address Translation)**.

Essa configuração permite que dispositivos da rede privada utilizem um endereço público da interface externa para se comunicar com redes externas.

O funcionamento pode ser representado da seguinte forma:

```text
Rede Privada
192.168.x.x
      │
      ▼
Router-Cliente
      │
      │ NAT/PAT
      ▼
Interface Externa
      │
      ▼
Router-ISP
      │
      ▼
Servidor / Internet
```

O NAT permite que endereços privados da LAN sejam traduzidos para um endereço válido na rede externa.

## 🛣️ Configuração de Roteamento

Para permitir a comunicação entre todas as redes da topologia, foram configuradas rotas estáticas.

No roteador do cliente, foi configurada uma **rota padrão**, direcionando o tráfego destinado a redes desconhecidas para o roteador do ISP.

O conceito pode ser representado da seguinte forma:

```text
PC0
 │
 ▼
Rede Local
 │
 ▼
Router-Cliente
 │
 │ Rota padrão
 ▼
Router-ISP
 │
 ▼
Rede do Servidor
```

Essa configuração permite que o computador da LAN consiga alcançar redes localizadas fora de sua sub-rede.

## 💻 Configuração do Computador

O computador foi configurado para obter suas informações de rede automaticamente utilizando **DHCP**.

Após selecionar a opção DHCP, o dispositivo recebeu automaticamente:

* Endereço IPv4;
* Máscara de sub-rede;
* Gateway padrão;
* Endereço do servidor DNS.

Isso demonstra o funcionamento do serviço DHCP configurado no roteador do cliente.

## 🧪 Teste de Conectividade

Após finalizar todas as configurações, foram realizados testes para verificar a comunicação entre os dispositivos.

Inicialmente, foi possível verificar as configurações recebidas pelo computador utilizando:

```bash
ipconfig
```

Esse comando permite visualizar informações como:

* Endereço IP;
* Máscara de sub-rede;
* Gateway padrão;
* Servidor DNS.

Em seguida, foram realizados testes de comunicação entre as redes.

O objetivo foi verificar se o computador localizado na LAN conseguia alcançar dispositivos localizados na rede externa.

## 🌎 Teste de DNS e Navegação

Para validar o funcionamento do DNS, foi utilizado o navegador disponível no computador dentro do Cisco Packet Tracer.

O processo realizado foi:

1. Abrir o **Web Browser**;
2. Digitar o nome de domínio configurado no servidor DNS;
3. Realizar a solicitação de acesso;
4. Aguardar a resolução do nome;
5. Verificar o carregamento da página hospedada no servidor.

O funcionamento da comunicação pode ser representado da seguinte forma:

```text
PC0
 │
 │ Solicita acesso ao domínio
 ▼
Router-Cliente
 │
 │ NAT/PAT
 ▼
Router-ISP
 │
 ▼
Server-ISP
 │
 │ Consulta DNS
 ▼
Nome convertido em endereço IP
 │
 ▼
Comunicação estabelecida
```

O acesso bem-sucedido confirmou o funcionamento integrado dos serviços configurados na topologia.

## 🔐 Conceitos Aplicados

Durante o desenvolvimento do laboratório foram utilizados os seguintes conceitos de redes:

* LAN (Local Area Network);
* WAN (Wide Area Network);
* ISP (Internet Service Provider);
* IPv4;
* Máscara de sub-rede;
* Gateway padrão;
* DHCP;
* DNS;
* NAT;
* PAT;
* ACL (Access Control List);
* Roteamento estático;
* Interface serial;
* Comunicação entre redes;
* Cliente e servidor.

## 📚 Principais Aprendizados

Este laboratório permitiu compreender como diferentes tecnologias trabalham juntas para permitir a comunicação entre uma rede local e uma rede externa.

Foi possível observar o funcionamento completo de uma infraestrutura básica, desde a atribuição automática de endereços IP até o acesso a um servidor utilizando um nome de domínio.

A atividade também demonstrou a importância do roteador como elemento central da comunicação entre redes, realizando funções como roteamento, NAT e DHCP.

## ✅ Resultado

O laboratório foi concluído com sucesso, resultando em uma infraestrutura funcional composta por uma **LAN conectada a um ISP simulado**.

O computador da rede local conseguiu receber automaticamente suas configurações de rede através do **DHCP**, comunicar-se com redes externas utilizando o roteamento configurado e acessar um servidor por meio de um nome de domínio utilizando o serviço **DNS**.

A implementação também permitiu aplicar conceitos importantes como **NAT/PAT, ACL, roteamento estático, DHCP, DNS e comunicação entre redes**, consolidando conhecimentos fundamentais sobre o funcionamento de redes corporativas e conexão entre redes privadas e provedores de Internet.

> 🔒 Por segurança e boas práticas, informações específicas de configuração utilizadas exclusivamente durante a simulação, como endereços IP detalhados e demais dados de infraestrutura, não são expostos neste README.
