# Sistema de Casa Inteligente (Smart Home)

Este projeto consiste no desenvolvimento de um sistema de automação residencial utilizando IoT (Internet das Coisas), com integração entre sensores, atuadores e aplicações de software.

O objetivo é monitorar e controlar um ambiente residencial de forma automatizada e remota, utilizando comunicação em tempo real.

---

## Funcionalidades

* Monitoramento de temperatura e umidade (sensor DHT22)
* Detecção de gás (sensor MQ-2)
* Detecção de presença (sensor PIR)
* Controle de iluminação (LEDs e relés)
* Controle de dispositivos elétricos
* Acionamento de alarme sonoro (buzzer)
* Controle de motor de passo
* Exibição de informações em display OLED
* Comunicação via protocolo MQTT
* Integração com servidor HTTP
* Notificações automatizadas

---

## Tecnologias Utilizadas

### Hardware

* ESP32
* Sensor DHT22
* Sensor MQ-2
* Sensor PIR
* LDR (sensor de luminosidade)
* Display OLED
* Motor de passo com driver A4988
* Relés, LEDs e buzzer

### Software

* C++ (Arduino/ESP32)
* Protocolo MQTT
* Servidor HTTP
* Broker público MQTT (test.mosquitto.org)
* Simulação no Wokwi

---

## Arquitetura do Sistema

O sistema é dividido em três partes principais:

* Dispositivo IoT (ESP32): responsável pela coleta de dados dos sensores e controle dos atuadores
* Broker MQTT: responsável pela comunicação entre os dispositivos
* Aplicações cliente: responsáveis pelo monitoramento e controle (web, mobile ou desktop)

---

## Objetivo

Este projeto tem como objetivo demonstrar na prática:

* Integração entre hardware e software
* Comunicação em tempo real com MQTT
* Automação de ambientes residenciais
* Desenvolvimento de sistemas distribuídos
* Uso de sensores e atuadores em projetos reais

---

## Execução do Projeto

1. Configurar o ambiente no Wokwi ou em hardware real com ESP32
2. Conectar os sensores e atuadores conforme o projeto
3. Configurar o broker MQTT
4. Executar o código no ESP32
5. Acompanhar os dados via cliente MQTT ou interface web

---

## Autor

Lucas Garcia
Desenvolvedor de Software Multiplataforma

---

## Observações

Este projeto foi desenvolvido como parte de atividades acadêmicas, com foco em integração IoT e sistemas inteligentes.
