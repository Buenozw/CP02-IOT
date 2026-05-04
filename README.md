# 📡 Monitoramento Inteligente com IoT
> **ESP32 + MQTT + Node-RED + MySQL**[cite: 1]

Este projeto desenvolve uma solução completa de monitoramento em tempo real para reservatórios, integrando hardware, protocolos de comunicação de baixa latência e persistência de dados para análise técnica.[cite: 1]

---

## 👥 Integrantes
| Nome Completo | RM |
| :--- | :--- |
| **João Victor Caetano** | 562074 |[cite: 1]
| **João Victor Bueno** | 564115 |[cite: 1]
| **Andrei de Paiva** | 563061 |[cite: 1]

---

## 🧠 Arquitetura da Solução
O fluxo de dados segue a estrutura lógica de ponta a ponta, garantindo que a informação saia da ponta (sensor) e chegue tratada ao usuário final:[cite: 1]

**ESP32** ➔ **MQTT (HiveMQ)** ➔ **Node-RED** ➔ **MySQL** ➔ **Dashboard**[cite: 1]

### 🔹 Componentes do Fluxo:
*   **ESP32:** Responsável pela leitura dos sensores e publicação via MQTT.[cite: 1]
*   **MQTT:** Protocolo leve de mensageria para baixa latência.[cite: 1]
*   **Node-RED:** Motor de regras que processa dados e integra a API OpenWeather para enriquecimento de contexto.[cite: 1]
*   **MySQL:** Banco de dados relacional para persistência histórica.[cite: 1]
*   **Dashboard:** Interface intuitiva para exibição de métricas e alertas em tempo real.[cite: 1]

---

## 🛠️ Tecnologias Utilizadas
*   **Hardware:** ESP32 (Arduino)[cite: 1]
*   **Protocolo:** MQTT (Broker HiveMQ)[cite: 1]
*   **Orquestração:** Node-RED[cite: 1]
*   **Banco de Dados:** MySQL[cite: 1]
*   **API Externa:** OpenWeather (Dados climáticos)[cite: 1]
*   **Linguagens:** C++, SQL, JavaScript (Function Nodes)[cite: 1]

---

## 📊 Funcionalidades
- [x] **Nível do Reservatório:** Monitoramento volumétrico.[cite: 1]
- [x] **Climatização:** Temperatura e sensação térmica local.[cite: 1]
- [x] **Telemetria:** Medição precisa de distância via sensores.[cite: 1]
- [x] **Inteligência:** Sistema automático de alertas.[cite: 1]
- [x] **Histórico:** Armazenamento robusto para auditoria de dados.[cite: 1]

---

## 🗄️ Estrutura do Banco de Dados

```sql
-- Registro de telemetria dos sensores
CREATE TABLE sensores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    valor FLOAT,
    tipo VARCHAR(50),
    data TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Dados climáticos externos
CREATE TABLE clima_externo (
    id INT AUTO_INCREMENT PRIMARY KEY,
    cidade VARCHAR(100),
    temp_ext FLOAT,
    sensacao FLOAT,
    umidade FLOAT,
    descricao VARCHAR(255),
    vento_ms FLOAT,
    timestamp DATETIME DEFAULT CURRENT_TIMESTAMP
);
```[cite: 1]

---

## ⚙️ Como Executar o Projeto

### 1. Preparar o Ambiente Node-RED
No terminal, instale o core e as bibliotecas necessárias:
```bash
npm install -g node-red
cd ~/.node-red
npm install node-red-dashboard node-red-node-mysql node-red-node-openweathermap
```[cite: 1]

### 2. Configuração do Banco de Dados
1. Crie um banco de dados chamado `iot`.[cite: 1]
2. Execute os scripts SQL fornecidos acima.[cite: 1]
3. No Node-RED, configure o nó MySQL com suas credenciais locais (User: `root` | Porta: `3306`).[cite: 1]

### 3. Comunicação MQTT
O projeto utiliza o broker público da HiveMQ:
*   **Broker:** `broker.hivemq.com`[cite: 1]
*   **Porta:** `1883`[cite: 1]

---

## 📂 Estrutura de Pastas
```text
📦 projeto-iot
 ┣ 📂 esp32        # Código-fonte (.ino)
 ┣ 📂 node-red     # Fluxos exportados (JSON)
 ┣ 📂 database     # Scripts de criação e queries
 ┗ 📜 README.md    # Documentação
```[cite: 1]

---

## 🎬 Demonstração
📺 [Clique aqui para assistir ao vídeo do projeto](adicione_o_link_aqui)[cite: 1]

---
> **Status do Projeto:** 🚀 Finalizado / Acadêmico[cite: 1]
