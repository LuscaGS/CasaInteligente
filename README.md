# 🏠 Casa Inteligente — Automação Residencial com ESP32

Sistema de automação residencial simulado no [Wokwi](https://wokwi.com/). Monitora sensores em tempo real, aciona dispositivos automaticamente e envia alertas via **Telegram**.

---

## ✨ Funcionalidades

- 🌡️ Monitoramento de temperatura e umidade (DHT22) — aciona ventilador automaticamente
- 💨 Detecção de gás/fumaça (MQ2) — alerta sonoro e notificação no Telegram
- 💡 Iluminação automática por presença + luminosidade (PIR + LDR)
- 📲 Notificações em tempo real via bot do Telegram
- 🌐 Controle remoto via MQTT (broker público Mosquitto)
- 🖥️ Servidor HTTP embarcado para controle local via rede
- 🔧 Motor de passo controlado via driver A4988

---

## 🛠️ Tecnologias

![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat&logo=espressif&logoColor=white)
![MQTT](https://img.shields.io/badge/MQTT-660066?style=flat&logo=eclipse-mosquitto&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram_Bot-26A5E4?style=flat&logo=telegram&logoColor=white)
![Wokwi](https://img.shields.io/badge/Simulado_no-Wokwi-7B2FBE?style=flat)

---

## 🔌 Hardware e Pinagem

| Componente | Pino ESP32 | Função |
|------------|------------|--------|
| DHT22 | GPIO 15 | Temperatura e umidade |
| Sensor de gás MQ2 | GPIO 34 | Detecção de gás/fumaça |
| LDR (fotoresistor) | GPIO 35 | Luminosidade ambiente |
| Sensor PIR | GPIO 14 | Detecção de presença |
| Relé Vermelho | GPIO 16 | Alarme de gás |
| LED Vermelho | GPIO 25 | Indicador de gás |
| Relé Azul | GPIO 17 | Ventilador |
| LED Azul | GPIO 26 | Indicador de temperatura |
| Relé Branco | GPIO 18 | Iluminação |
| LED Branco | GPIO 27 | Indicador de luz |
| Buzzer | GPIO 13 | Alerta sonoro |
| Motor de passo (STEP) | GPIO 33 | Controle de passo |
| Motor de passo (DIR) | GPIO 32 | Direção do motor |

> O circuito completo está no arquivo `diagram.json` — basta importar no Wokwi.

---

## 📡 Tópicos MQTT

| Tópico | Direção | Payload |
|--------|---------|---------|
| `casa/sensor/temperatura` | Publica | Valor em °C |
| `casa/sensor/gas` | Publica | `OK` ou `ALERT` |
| `casa/sensor/luz` | Publica | `DARK` ou `BRIGHT` |
| `casa/sensor/presenca` | Publica | `1` ou `0` |
| `casa/command/ventilador` | Recebe | `ON` / `OFF` |
| `casa/command/led_branco` | Recebe | `ON` / `OFF` |
| `casa/command/threshold/temp` | Recebe | Valor float (ex: `28.5`) |
| `casa/command/threshold/ldr` | Recebe | Valor inteiro (ex: `1500`) |
| `casa/command/bloqueio_sensor_luz` | Recebe | `ON` / `OFF` |
| `casa/command/bloqueio_sensor_temp` | Recebe | `ON` / `OFF` |

Broker utilizado: `test.mosquitto.org:1883` (público)

---

## 📂 Estrutura do projeto

```
CasaInteligente/
├── main.ino          ← Código principal do ESP32
├── diagram.json      ← Circuito completo para simulação no Wokwi
├── libraries.txt     ← Dependências do projeto
└── README.md
```

---

## ⚙️ Como rodar

### Simulação no Wokwi

1. Acesse [wokwi.com](https://wokwi.com) e crie um novo projeto **ESP32**
2. Substitua o `main.ino` e o `diagram.json` pelos arquivos deste repositório
3. Configure suas credenciais do Telegram no `main.ino` (veja abaixo)
4. Clique em ▶️ para simular

### Hardware real (Arduino IDE)

1. Instale as bibliotecas listadas em `libraries.txt`
2. Configure suas credenciais do Telegram no `main.ino`
3. Selecione a placa `ESP32 Dev Module` e grave

---

## 🔑 Configurando o Telegram

No arquivo `main.ino`, substitua os placeholders com seus dados:

```cpp
#define BOT_TOKEN "SEU_TOKEN_AQUI"
#define CHAT_ID_1 "SEU_CHAT_ID"
#define CHAT_ID_2 "CHAT_ID_OPCIONAL"
```

> 💡 **Token:** acesse [@BotFather](https://t.me/BotFather), envie `/newbot` e copie o token gerado.
>
> 💡 **Chat ID:** envie uma mensagem para [@userinfobot](https://t.me/userinfobot).

---

## 📦 Dependências (`libraries.txt`)

```
DHT sensor library
Adafruit GFX Library
Adafruit SSD1306
PubSubClient
```

Instale via **Arduino IDE → Library Manager** ou o Wokwi já carrega automaticamente ao usar o `libraries.txt`.

---

## 🔐 Segurança

> ⚠️ **Nunca suba seu `BOT_TOKEN` ou `CHAT_ID` reais para o GitHub.**
> O `main.ino` deste repositório contém apenas placeholders.
> Substitua localmente antes de simular ou gravar no dispositivo.

---

## 👨‍💻 Autor

**Lucas Garcia Lima**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/lucas-garcia-lima/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/LuscaGS)
