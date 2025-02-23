# 🔌 API do Firmware

Esta seção documenta as principais funções disponíveis no firmware **BR SmartGuia**. Aqui você encontrará detalhes sobre os métodos para interação com os periféricos e funcionalidades do projeto.

## 📜 Visão Geral

A API do firmware está organizada conforme os componentes principais do sistema:

- **Matriz de LEDs WS2812B** 🎨
- **Display OLED SSD1306** 📟
- **Sensor Ultrassônico HC-SR04** 📡
- **Buzzers** 🔊
- **Botões físicos** 🎛️

---

## 🎨 Controle da Matriz de LEDs

```c
void ws2812b_init(uint pin);
```
**Descrição:** Inicializa a máquina de estado PIO para controlar a matriz de LEDs WS2812B.

```c
void ws2812b_setLED(uint index, uint8_t r, uint8_t g, uint8_t b, float brightness);
```
**Descrição:** Define a cor e o brilho de um LED específico na matriz.

```c
void ws2812b_clear();
```
**Descrição:** Desliga todos os LEDs da matriz.

```c
void ws2812b_write();
```
**Descrição:** Envia os dados para atualizar os LEDs da matriz.

---

## 📟 Controle do Display OLED SSD1306

```c
void ssd1306_init();
```
**Descrição:** Inicializa o display OLED via comunicação I2C.

```c
void ssd1306_render(uint8_t *buf, struct render_area *area);
```
**Descrição:** Atualiza uma área específica do display com um buffer de pixels.

```c
void ssd1306_writeString(uint8_t *buf, int16_t x, int16_t y, char *str);
```
**Descrição:** Escreve uma string na posição `(x, y)` da tela.

---

## 📡 Sensor Ultrassônico HC-SR04

```c
float hcsr04_measure();
```
**Descrição:** Mede a distância em centímetros usando um sensor ultrassônico HC-SR04.

---

## 🔊 Controle do Buzzer

```c
void buzzer_play_tone(int frequency, int duration, int buzzer_pin);
```
**Descrição:** Toca uma frequência específica no buzzer por um tempo determinado.

```c
void buzzer_playAlarm();
```
**Descrição:** Emite um som de alarme pré-definido no buzzer.

---

## 🎛️ Interação com Botões

```c
bool button_read(uint button_pin);
```
**Descrição:** Retorna `true` se um botão estiver pressionado.

---

Agora que entendemos a API do firmware, podemos seguir para a próxima seção sobre instalação e compilação! 🛠️

[➡️ Instalação e Compilação](instalacao.md)

