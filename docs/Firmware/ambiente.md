# 🛠️ Ambiente de Desenvolvimento

Esta seção detalha o ambiente necessário para desenvolver, compilar e testar o firmware do projeto **BR SmartGuia** no **Raspberry Pi Pico**.

## 📌 Requisitos

Antes de iniciar, certifique-se de que possui os seguintes itens:

### 🖥️ Hardware Necessário

| Componente              | Descrição |
|-------------------------|------------------------------------------------|
| **Raspberry Pi Pico W**   | Microcontrolador principal do projeto |
| **Cabo Micro-USB**      | Para alimentação e comunicação com o computador |
| **Display OLED SSD1306** | Comunicação via I2C para exibição de informações |
| **Matriz de LEDs WS2812B** | Controlada via PIO para sinalização visual |
| **Buzzer x2**           | Para alertas sonoros e música |
| **Sensor Ultrassônico HC-SR04** | Para medição de distância de obstáculos |
| **Botões físicos (A/B)** | Para controle manual da matriz de LEDs |

### 💻 Software Necessário

| Ferramenta                     | Descrição |
|---------------------------------|------------------------------------------------|
| **Sistema Operacional**        | Linux (recomendado) ou Windows com WSL |
| **SDK do Raspberry Pi Pico**   | Biblioteca e ferramentas para desenvolvimento |
| **CMake**                      | Gerenciador de build |
| **GNU Arm Embedded Toolchain**  | Compilador para ARM |
| **Visual Studio Code**          | Editor de código recomendado |
| **Extensão Pico SDK para VS Code** | Facilita a configuração do ambiente |
| **Minicom/PuTTY**               | Monitoramento de saída serial |

## 🔧 Configuração do Ambiente

### 1️⃣ Instalar Dependências (Linux)

```bash
sudo apt update && sudo apt install -y cmake gcc-arm-none-eabi libnewlib-arm-none-eabi build-essential
