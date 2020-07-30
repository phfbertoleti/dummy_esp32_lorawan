# Projeto básico / dummy de LoRaWAN com ESP32

Este repositório contém um projeto básico / dummy de um end-device LoRaWAN (ABP) feito com ESP32, já preparado para se conectar a rede pública da ATC (American Tower Corporation). 
No quesito hardware, este projeto utiliza a placa de desenvolvimento Heltec WiFi LoRa v1 (alimentado a bateria ou via cabo USB). Esta placa de desenvolvimento conta com o SX1276 como rádio LoRa e o ESP32 como SoC.
Este projeto envia, de 30 em 30 minutos, um número aleatório (na forma textual / ASCII) para a nuvem via LoRaWAN.

# IMPORTANTE

1) Esse projeto faz uso da biblioteca "MCCI LoRaWAN LMIC Library". Este projeto foi testado com a versão 2.3.2 da mesma.
2) Antes de compilar, é preciso deixar o arquivo lmic_project_config.h (dentro na pasta da biblioteca: project_config/lmic_project_config.h) com o conteúdo conforme abaixo:
```
// project-specific definitions
//#define CFG_eu868 1
//#define CFG_us915 1
#define CFG_au921 1
//#define CFG_as923 1
// #define LMIC_COUNTRY_CODE LMIC_COUNTRY_CODE_JP      
//#define CFG_in866 1
#define CFG_sx1276_radio 1
//#define LMIC_USE_INTERRUPTS
```
3) Você precisará da network session key, application session key (definidos por você ou pela operadora da ATC) e do Device Address (fornecido pela operadora em caráter experimental ou adquirido por meios oficiais). Substitua estas informações no arquivo LORAWAN_defs.h.
Para obtenção das chaves e tudo mais em termos de conectividade 
LoRaWAN, entre em contato com uma das empresas credenciadas pela ATC:
 
https://iotopenlabs.io/home/catalogo-de-solucoes/conectividade-lorawan/