# 📌 Introdução ao Firmware

Bem-vindo à documentação do firmware do projeto **BR SmartGuia**! 🎉

Este firmware foi desenvolvido para o **Raspberry Pi Pico**, utilizando diversos periféricos, como:

✅ **Matriz de LEDs WS2812B** - Controlada via PIO;

✅ **Display OLED SSD1306** - Comunicação via I2C;

✅ **Sensor Ultrassônico HC-SR04** - Para medição de distância;

✅ **Buzzers** - Para alarmes e reprodução de músicas;

✅ **Botões físicos** - Para interação com os LEDs.

A documentação desta sessão tem como objetivo fornecer um guia detalhado sobre a estrutura, funcionamento e desenvolvimento do firmware. Você encontrará informações sobre as bibliotecas utilizadas, API, instalação e compilação, além de exemplos práticos e estratégias de depuração e testes.

## 📂 Organização da Documentação

A documentação está organizada da seguinte forma:

| Seção                     | Descrição |
|---------------------------|--------------------------------------------------------------------------|
| [Ambiente de Desenvolvimento](ambiente.md) | Ferramentas e configurações necessárias para desenvolver o firmware. |
| [Estrutura do Código](estrutura.md) | Organização dos arquivos e principais componentes do código. |
| [Bibliotecas Utilizadas](bibliotecas.md) | Descrição das bibliotecas utilizadas no projeto. |
| [API do Firmware](api.md) | Funções principais disponíveis para uso e integração. |
| [Instalação e Compilação](instalacao.md) | Passos para compilar e rodar o firmware no Raspberry Pi Pico. |
| [Exemplos Práticos](exemplos.md) | Demonstrações e exemplos de uso do firmware. |
| [Depuração e Testes](depuracao.md) | Estratégias para identificar e corrigir problemas no firmware. |

## 🚀 Tecnologias Utilizadas

- **Linguagem**: C
- **Microcontrolador**: Raspberry Pi Pico
- **SDK**: Pico SDK
- **Gerenciador de Build**: CMake
- **Interfaces de Comunicação**:
  - I2C para o display OLED SSD1306
  - PIO para o controle da matriz de LEDs WS2812B
  - GPIO para sensores ultrassônicos e buzzers

## 🎯 Objetivos do Firmware

O firmware foi projetado para:

- Controlar eficientemente os periféricos conectados ao Raspberry Pi Pico.
- Garantir uma interface interativa e intuitiva através de botões físicos.
- Exibir informações relevantes no display OLED.
- Reproduzir sinais sonoros e músicas utilizando buzzers.
- Implementar um sistema responsivo para medição de distâncias.

---

Siga para a próxima seção para configurar o ambiente de desenvolvimento! 🛠️

[➡️ Ambiente de Desenvolvimento](ambiente.md)