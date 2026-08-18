# Laboratório 1 - Configuração de Servidor DHCP no Roteador

Laboratório prático desenvolvido no **Cisco Packet Tracer** para configuração de um roteador Cisco como **servidor DHCP**, permitindo a distribuição automática das configurações de rede para os computadores de uma rede local.

## 📌 Sobre o projeto

O laboratório simula uma pequena rede local composta por um **roteador Cisco 2911**, um **switch Cisco 2960** e dois computadores.

O roteador é configurado para atuar como **gateway da rede** e também como **servidor DHCP**, fornecendo automaticamente aos computadores as informações necessárias para sua comunicação na rede.

## 🎯 Objetivos

- Configurar uma interface de um roteador Cisco;
- Configurar o endereço IPv4 do gateway;
- Ativar uma interface de rede utilizando `no shutdown`;
- Configurar um servidor DHCP no roteador;
- Distribuir automaticamente endereços IP aos computadores;
- Configurar máscara de rede, gateway e servidor DNS via DHCP;
- Compreender os principais modos da CLI do Cisco IOS;
- Validar o funcionamento do DHCP em computadores clientes;
- Utilizar comandos básicos de configuração de roteadores Cisco.

## 🏗️ Estrutura e Dispositivos

- **1 Roteador Cisco 2911**
- **1 Switch Cisco 2960**
- **2 PCs**

### 🖧 Representação visual da topologia implementada

```text
                    ┌─────────────────┐
                    │  Roteador 2911  │
                    │                 │
                    │ Gateway + DHCP  │
                    └────────┬────────┘
                             │
                             │
                    ┌────────▼────────┐
                    │  Switch 2960    │
                    └───────┬─┬───────┘
                            │ │
                       ┌────┘ └────┐
                       ▼           ▼
                  ┌────────┐  ┌────────┐
                  │  PC0   │  │  PC1   │
                  │ Cliente│  │ Cliente│
                  └────────┘  └────────┘
```

## 🔌 Conectividade

Os dispositivos foram conectados utilizando **Copper Straight-Through**.

- **PC0 → Switch:** conexão FastEthernet;
- **PC1 → Switch:** conexão FastEthernet;
- **Switch → Roteador:** conexão entre uma porta FastEthernet do switch e uma interface GigabitEthernet do roteador.

A conexão permite que os computadores clientes se comuniquem com o roteador por meio do switch.

## ⚙️ Configuração do Roteador

O roteador foi configurado através da **CLI (Command Line Interface)** do Cisco IOS.

Durante a configuração foram utilizados diferentes níveis de acesso:

```text
Router>
Router#
Router(config)#
```

A interface utilizada para a rede local foi configurada como **gateway**, recebendo um endereço IPv4 e sendo ativada por meio do comando `no shutdown`.

Em seguida, foi criado um **DHCP Pool** para realizar a distribuição automática das configurações de rede aos computadores clientes.

O DHCP foi configurado para fornecer:

- Endereço IPv4;
- Máscara de rede;
- Gateway padrão;
- Servidor DNS.

## 🌐 Funcionamento do DHCP

Após a configuração do roteador, os computadores foram configurados para obter suas informações de rede automaticamente por meio de **DHCP**.

Ao selecionar a opção **DHCP** na configuração de IP dos computadores, o roteador fornece automaticamente as informações necessárias para a comunicação na rede.

Dessa forma, não é necessário configurar manualmente cada computador.

> 🔒 Os endereços IP, configurações específicas e demais valores utilizados na simulação não são registrados neste README.

## 🧪 Teste Final

Para validar o funcionamento do laboratório, os computadores foram configurados para utilizar **DHCP**.

Após a solicitação, cada computador recebeu automaticamente suas configurações de rede fornecidas pelo roteador.

O procedimento foi repetido nos dois computadores para verificar a distribuição automática dos endereços.

### ⚠️ Observação sobre o Cisco Packet Tracer

Em algumas situações, o simulador pode apresentar comportamento inesperado durante a atualização das configurações DHCP.

Caso as informações não sejam atualizadas automaticamente, pode ser necessário acessar a configuração do computador e ajustar a opção de obtenção do **Gateway** para **DHCP/automático**, realizando novamente o teste.

Após a configuração correta, as conexões da topologia devem apresentar os indicadores de conectividade em **verde**.

## 💻 Principais Comandos Utilizados

Durante a configuração do roteador foram utilizados comandos relacionados a:

- Acesso ao modo privilegiado;
- Acesso ao modo de configuração global;
- Configuração de interface;
- Configuração de endereço IPv4;
- Ativação da interface;
- Criação de pool DHCP;
- Configuração da rede DHCP;
- Definição do gateway;
- Definição do servidor DNS;
- Salvamento da configuração.

Exemplos de comandos utilizados:

```text
enable
configure terminal
interface GigabitEthernet0/0
ip address <ENDERECO> <MASCARA>
no shutdown
exit
ip dhcp pool <NOME_DO_POOL>
network <REDE> <MASCARA>
default-router <GATEWAY>
dns-server <SERVIDOR_DNS>
exit
write
```

> 🔒 Os valores específicos utilizados durante a configuração foram omitidos deste README.

## 🎥 Demonstração

A demonstração apresenta a configuração do roteador como servidor DHCP e a obtenção automática das configurações de rede pelos computadores clientes.

## ✅ Resultado

A prática permitiu consolidar conhecimentos sobre **configuração de roteadores Cisco, interfaces de rede, gateway, DHCP e endereçamento IPv4**.

O resultado final foi uma rede local funcional na qual os computadores clientes conseguem obter automaticamente suas configurações de rede por meio do **servidor DHCP configurado no roteador**.
