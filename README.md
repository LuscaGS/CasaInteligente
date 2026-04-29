# 🏠 Casa Inteligente — Automação Residencial com IoT

Sistema de automação residencial com controle e monitoramento de dispositivos em tempo real via interface web. Projeto que integra hardware e software para criar um ambiente doméstico inteligente e conectado.

---

## ✨ Funcionalidades

- 💡 Controle de iluminação remotamente
- 🌡️ Monitoramento de temperatura e umidade em tempo real
- 🔒 Controle de acesso e segurança
- 📊 Dashboard web para visualização dos dados dos sensores
- ⚡ Comunicação em tempo real entre dispositivos

---

## 🛠️ Tecnologias

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![MQTT](https://img.shields.io/badge/MQTT-660066?style=flat&logo=eclipse-mosquitto&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white)

---

## 🏗️ Arquitetura

```
Sensores / Atuadores (Hardware)
        ↕ (MQTT)
   Broker MQTT
        ↕
  Interface Web (Dashboard)
```

Os dispositivos publicam dados via protocolo MQTT. O broker distribui as mensagens para a interface web, que exibe as informações em tempo real e permite enviar comandos de volta aos dispositivos.

---

## 🚀 Como rodar

### Pré-requisitos
- Broker MQTT instalado (ex: Mosquitto)
- Dispositivo compatível (Arduino/ESP8266/ESP32)

### Interface web
```bash
# Clone o repositório
git clone https://github.com/LuscaGS/CasaInteligente.git

# Abra o index.html no navegador
open index.html
```

### Configuração do broker
```bash
# Instalar Mosquitto
sudo apt install mosquitto mosquitto-clients

# Iniciar o serviço
sudo systemctl start mosquitto
```

---

## 📡 Hardware utilizado

| Componente | Função |
|------------|--------|
| ESP8266 / ESP32 | Microcontrolador Wi-Fi principal |
| DHT11 / DHT22 | Sensor de temperatura e umidade |
| Relé | Controle de cargas elétricas |
| LED | Indicador de status |

---

## 👨‍💻 Autor

**Lucas Garcia Lima**
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/lucas-garcia-lima/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/LuscaGS)
