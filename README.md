📡 Monitoramento Inteligente com IoT (ESP32 + MQTT + Node-RED)
👥Integrantes
João Victor Caetano, RM: 562074
João Victor Bueno, RM: 564115
Andrei de paiva, RM: 563061

Descrição do Projeto

Este projeto tem como objetivo desenvolver uma solução de monitoramento em tempo real utilizando conceitos de Internet das Coisas (IoT).

A aplicação simula o monitoramento de um reservatório, coletando dados de sensores e integrando-os com serviços externos para visualização e análise.

🧠 Arquitetura da Solução

ESP32 → MQTT → Node-RED → MySQL → Dashboard
🔹 Fluxo:
ESP32 envia dados dos sensores via MQTT
Node-RED recebe e processa
Dados são armazenados no MySQL
Dashboard exibe em tempo real
API externa (OpenWeather) complementa os dados

Tecnologias Utilizadas
ESP32 (Arduino)
MQTT (HiveMQ)
Node-RED
MySQL
OpenWeather API
JavaScript (Function Nodes)

📊 Funcionalidades
📈 Monitoramento de nível do reservatório
🌡️ Monitoramento de temperatura
📏 Medição de distância
⚠️ Sistema de alertas
🌦️ Integração com API de clima externo
💾 Armazenamento em banco de dados
📊 Dashboard em tempo real
🗄️ Estrutura do Banco de Dados

Tabela: sensores
CREATE TABLE sensores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    valor FLOAT,
    tipo VARCHAR(50),
    data TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
Tabela: clima_externo
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

⚙️ Como Executar o Projeto

🔹 1. Instalar dependências do Node-RED
npm install -g node-red
cd ~/.node-red
npm install node-red-dashboard
npm install node-red-node-mysql
npm install node-red-node-openweathermap
🔹 2. Rodar Node-RED
node-red

Acesse:

http://localhost:1880

🔹 3. Configurar MySQL

Criar banco iot
Executar scripts SQL fornecidos
Configurar no Node-RED:
host: localhost
porta: 3306
user: root
senha: sua_senha
database: iot

🔹 4. Configurar MQTT

broker: broker.hivemq.com
porta: 1883
🔹 5. Dashboard

Acesse:

http://localhost:1880/ui
Demonstração

Vídeo demonstrativo: (adicione o link aqui)

Estrutura do Projeto
📦 projeto
 ┣ 📂 esp32
 ┣ 📂 node-red
 ┣ 📂 database
 ┣ 📜 README.md
📌 Considerações Finais
