# 📚 Bibliotecas Utilizadas

O firmware **BR SmartGuia** faz uso de diversas bibliotecas para interagir com os periféricos e otimizar o desenvolvimento. Abaixo, detalhamos as principais bibliotecas utilizadas no projeto.

## 🔌 Bibliotecas do Raspberry Pi Pico SDK

O Raspberry Pi Pico SDK fornece suporte para a programação do microcontrolador RP2040.

| Biblioteca         | Descrição |
|-------------------|------------------------------------------------------------|
| `pico/stdlib.h`  | Fornece funções básicas para entrada/saída, temporização e controle de GPIO. |
| `pico/binary_info.h` | Permite armazenar metadados sobre o firmware, útil para depuração. |
| `hardware/gpio.h` | Controle dos pinos GPIO. |
| `hardware/i2c.h`  | Comunicação com dispositivos via protocolo I2C. |
| `hardware/pwm.h`  | Controle de PWM para os buzzers. |
| `hardware/pio.h`  | Configuração e controle da matriz de LEDs WS2812B. |
| `hardware/clocks.h` | Configuração e gerenciamento de clocks do sistema. |

## 📟 Bibliotecas para Periféricos

O firmware utiliza drivers customizados para interagir com os periféricos. Abaixo, listamos as bibliotecas específicas:

| Biblioteca           | Função |
|----------------------|------------------------------------------------|
| `ssd1306_i2c.h`     | Driver para controle do display OLED SSD1306 via I2C. |
| `ssd1306_font.h`    | Definições de fonte para exibição de caracteres no display. |
| `ws2812b.pio.h`     | Código PIO para controle da matriz de LEDs WS2812B. |

## 🔄 Dependências do Projeto

O projeto utiliza ferramentas externas para compilar e gerenciar o firmware:

| Ferramenta               | Descrição |
|--------------------------|--------------------------------------------------------------|
| **CMake**               | Gerenciador de build utilizado para compilar o código. |
| **GNU Arm Embedded Toolchain** | Toolchain para compilação de código C/C++ para o RP2040. |

## 📌 Como as Bibliotecas se Integram no Projeto

1. O **Pico SDK** é inicializado no `CMakeLists.txt`, garantindo que as bibliotecas essenciais estejam disponíveis.
2. As bibliotecas de hardware (`gpio`, `i2c`, `pwm`, `pio`) são usadas para interagir com os sensores e atuadores.
3. Os drivers personalizados para o **display OLED**, **matriz de LEDs** e **buzzers** garantem um controle eficiente dos periféricos.
4. O código principal realiza a integração entre essas bibliotecas, garantindo que os componentes trabalhem juntos de forma sincronizada.

---

Agora que conhecemos as bibliotecas utilizadas, siga para a próxima seção para entender melhor a API do firmware! 🔍

[➡️ API do Firmware](api.md)

