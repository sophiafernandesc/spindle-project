#  Código Fonte - Spindle

Este diretório contém o firmware desenvolvido para o controle do robô-aranha quadrúpede.

## Tecnologias e Requisitos
* **Plataforma:** Arduino Nano
* **Linguagem:** C++ (Wiring)
* **Bibliotecas Necessárias:** * `Servo.h` (Nativa do Arduino)
    * `SoftwareSerial.h` (Para comunicação com o módulo Bluetooth HC-05)

## Lógica de Controle
O Spindle possui **8 servomotores**, organizados em 4 pernas. Cada perna utiliza:
1. **Servo de Coxa/Base:** Responsável pelo movimento de avanço e recuo (frente/trás).
2. **Servo de Joelho/Articulação:** Responsável pelo movimento de levantamento (cima/baixo).

O controle é processado pelo Arduino Nano, que recebe comandos via Bluetooth do aplicativo mobile e traduz esses caracteres em ângulos específicos para cada um dos 8 servos simultaneamente, garantindo estabilidade durante a caminhada.

##  Pinagem Sugerida
| Componente | Pino Arduino |
|------------|--------------|
| Bluetooth RX | D2 (via SoftwareSerial) |
| Bluetooth TX | D3 (via SoftwareSerial) |
| Servos Coxas | D4, D6, D8, D10 |
| Servos Joelhos| D5, D7, D9, D11 |

![Pinagem arduino nano](./assets/pinagemArduinoNano.jpeg)


##  Como carregar
1. Instale a [Arduino IDE](https://www.arduino.cc/en/software).
2. Conecte o Arduino Nano ao seu computador via USB.
3. Abra o arquivo `codigoArduino.ino`.
4. Selecione a placa **Arduino Nano** e o Processador **ATmega328P (Old Bootloader)** se necessário.
5. Clique em **Upload**.