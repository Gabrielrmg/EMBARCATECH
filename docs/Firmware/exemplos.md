# 📖 Exemplos Práticos

Esta seção apresenta exemplos práticos de uso do firmware **BR SmartGuia** para facilitar o desenvolvimento e testes.

## 🟢 Acendendo a Matriz de LEDs

Este exemplo mostra como inicializar e configurar a matriz de LEDs WS2812B.

```c
#include "ws2818b.pio.h"

int main() {
    ws2812b_init(7); // Inicializa a matriz de LEDs no pino 7
    
    for (int i = 0; i < 25; i++) {
        ws2812b_setLED(i, 255, 0, 0, 0.5); // Acende os LEDs em vermelho
    }
    ws2812b_write(); // Atualiza a matriz de LEDs
    
    while (true);
}
```

## 📟 Exibindo Texto no Display OLED

Este exemplo exibe uma mensagem no display OLED SSD1306 via I2C.

```c
#include "ssd1306.h"

int main() {
    ssd1306_init();
    uint8_t buf[SSD1306_BUF_LEN];
    memset(buf, 0, SSD1306_BUF_LEN);
    
    ssd1306_writeString(buf, 5, 10, "Hello, BR SmartGuia!");
    ssd1306_render(buf, &(struct render_area){0, SSD1306_WIDTH-1, 0, SSD1306_NUM_PAGES-1});
    
    while (true);
}
```

## 📡 Medindo Distância com Sensor Ultrassônico

Este exemplo mostra como obter a distância medida pelo sensor ultrassônico HC-SR04.

```c
#include "hardware/gpio.h"
#include "pico/stdlib.h"

#define TRIGGER_PIN 4
#define ECHO_PIN 9

int main() {
    stdio_init_all();
    gpio_init(TRIGGER_PIN);
    gpio_set_dir(TRIGGER_PIN, GPIO_OUT);
    gpio_init(ECHO_PIN);
    gpio_set_dir(ECHO_PIN, GPIO_IN);
    
    while (true) {
        float distance = hcsr04_measure();
        printf("Distância: %.2f cm\n", distance);
        sleep_ms(500);
    }
}
```

## 🔊 Tocando um Alarme

Este exemplo ativa um som de alerta com o buzzer.

```c
#include "hardware/pwm.h"

#define BUZZER_PIN 10

int main() {
    buzzer_playAlarm();
    while (true);
}
```

---

Agora que você viu exemplos práticos, siga para a próxima seção sobre depuração e testes! 🛠️

[➡️ Depuração e Testes](depuracao.md)