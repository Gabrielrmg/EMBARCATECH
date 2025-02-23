# 📂 Estrutura do Código

Esta seção descreve a organização do código-fonte do firmware **BR SmartGuia**, explicando os principais arquivos e suas funções.

## 📌 Visão Geral

O código do firmware segue uma estrutura modular, facilitando a manutenção e a escalabilidade. Abaixo está a organização correta dos arquivos principais:

```
📁 Firmware/
├── 📂 build/                 # Diretório gerado após compilação
├── 📄 BatGuia.c              # Código principal do firmware
├── 📄 CMakeLists.txt         # Configuração do CMake para compilação
├── 📄 pico_sdk_import.cmake  # Importação do Pico SDK
├── 📄 ssd1306.h              # Header com funções do OLED
├── 📄 ssd1306_font.h         # Definições da fonte do display
├── 📄 ssd1306_i2c.c          # Implementação do driver do display OLED
├── 📄 ssd1306_i2c.h          # Header do driver do display OLED
├── 📄 ws2818b.pio.h          # Código para controle da matriz de LEDs WS2812B via PIO
├── 📄 ws2818b.pio            # Definição do programa PIO para controle dos LEDs
```

## 📝 Descrição dos Arquivos

| Arquivo                 | Descrição                                                                  |
| ----------------------- | -------------------------------------------------------------------------- |
| `CMakeLists.txt`        | Define a estrutura do projeto e os arquivos necessários para a compilação. |
| `pico_sdk_import.cmake` | Importa o SDK do Raspberry Pi Pico.                                        |
| `BatGuia.c`             | Arquivo principal, contendo a lógica do firmware.                          |
| `ssd1306_i2c.c`         | Implementação das funções para comunicação com o display OLED via I2C.     |
| `ssd1306_i2c.h`         | Header do driver do display OLED, definindo as funções e constantes.       |
| `ws2818b.pio.h`         | Configuração para o controle da matriz de LEDs WS2812B via PIO.            |
| `ws2818b.pio`           | Código PIO para controlar os LEDs de forma eficiente.                      |
| `ssd1306_font.h`        | Definições das fontes utilizadas no display OLED.                          |
| `ssd1306.h`             | Header com as principais funções de exibição para o OLED.                  |

## 🔄 Fluxo de Execução do Firmware

1. **Inicialização** 🚀

   - Configuração dos periféricos (I2C, GPIO, PIO, PWM).
   - Inicialização do display OLED e matriz de LEDs.
   - Configuração dos botões e sensores ultrassônicos HC-SR04.

2. **Loop Principal** 🔄

   - Leitura do sensor ultrassônico para medir distância.
   - Controle da matriz de LEDs com base na interação dos botões.
   - Exibição de informações no display OLED.
   - Emissão de sons de alerta via buzzer.

3. **Respostas a Eventos** 🎭

   - Se um botão for pressionado, a matriz de LEDs acende ou apaga.
   - Se a distância medida for menor que um valor crítico, o buzzer toca um alarme.
   - O display OLED exibe informações atualizadas continuamente.

---

Agora que você conhece a estrutura do código, siga para a próxima seção para explorar as bibliotecas utilizadas! 📚

[➡️ Bibliotecas Utilizadas](bibliotecas.md)