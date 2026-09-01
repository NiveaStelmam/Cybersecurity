# Laboratório 4 - Redes Hierárquicas 

Laboratório prático desenvolvido no **Cisco Packet Tracer** para implementação e análise de uma rede corporativa baseada no modelo hierárquico de três camadas.

## 📌 Sobre o projeto

O laboratório simula uma arquitetura de rede composta pelas camadas de Acesso, Distribuição e Core, permitindo praticar conceitos fundamentais de infraestrutura e conectividade de redes.


## 🎯 Objetivos

- Compreender a arquitetura hierárquica de redes;
- Configurar endereçamento IPv4;
- Configurar uma interface de roteador;
- Realizar testes de conectividade;
- Utilizar o comando `ping`;
- Visualizar o tráfego ICMP no Cisco Packet Tracer.


## 🏗️  Estrutura e Dispositivos

- **Camada de Acesso:** 2 switches Cisco 2960
- **Camada de Distribuição:** 1 switch Cisco 3650
- **Camada Core:** 1 roteador Cisco 4331
- **Dispositivos finais:** 4 PCs


### 🖧 Representação visual da topologia implementada

```text
                Roteador Core
                     │
                     ▼
            Switch de Distribuição
                  /       \
                 /         \
                ▼           ▼
        Switch de Acesso  Switch de Acesso
             /   \            /   \
            PC   PC          PC   PC
```

## 🎥 Demonstração

O vídeo apresenta a implementação da topologia seguindo o modelo hierárquico de redes, dividindo os dispositivos nas camadas de **Acesso, Distribuição e Core**.


https://github.com/user-attachments/assets/f7d97306-71e9-49d1-a344-e924595f6082


## ✅ Resultado

A prática permitiu consolidar os conceitos teóricos do modelo de três camadas da Cisco. O resultado final foi uma rede totalmente integrada, com simulação de envio de pacotes validada e total compreensão do caminho que a informação percorre do acesso ao núcleo.
