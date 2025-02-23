# 🛠️ Depuração e Testes

Nesta seção, exploramos estratégias para identificar e corrigir problemas no firmware **BR SmartGuia**.

## 🔍 Métodos de Depuração

### 1️⃣ **Saída Serial (Debugging via UART)**

A saída serial é uma das maneiras mais eficazes de depuração. Utilize `printf` para exibir mensagens no terminal:

```c
#include "pico/stdlib.h"

int main() {
    stdio_init_all();
    printf("Iniciando depuração...\n");
    
    while (true) {
        printf("Firmware rodando...\n");
        sleep_ms(1000);
    }
}
```

Para visualizar a saída:

```bash
minicom -b 115200 -o -D /dev/ttyUSB0
```

### 2️⃣ **Verificação de Estado dos GPIOs**

Para garantir que os pinos GPIO estão funcionando corretamente:

```c
#include "hardware/gpio.h"

#define TEST_PIN 2

int main() {
    gpio_init(TEST_PIN);
    gpio_set_dir(TEST_PIN, GPIO_IN);
    
    while (true) {
        printf("Pino %d: %d\n", TEST_PIN, gpio_get(TEST_PIN));
        sleep_ms(500);
    }
}
```

### 3️⃣ **Teste de Sensores**

Se o sensor ultrassônico HC-SR04 não estiver medindo corretamente:

```c
float distancia = hcsr04_measure();
printf("Distância medida: %.2f cm\n", distancia);
```

Caso os valores estejam errados, verifique:
- Conexões dos pinos TRIGGER e ECHO.
- Se há interferência de ruído.

### 4️⃣ **Teste do Display OLED**

Se o display não exibir nada, tente desenhar um padrão simples:

```c
uint8_t buf[SSD1306_BUF_LEN];
memset(buf, 0xFF, SSD1306_BUF_LEN); // Preenche com pixels acesos
ssd1306_render(buf, &(struct render_area){0, SSD1306_WIDTH-1, 0, SSD1306_NUM_PAGES-1});
```

Se continuar sem exibição:
- Verifique a alimentação do display.
- Confirme os pinos SDA e SCL.
- Teste reduzir a taxa de clock do I2C.

---

## ✅ Checklist de Testes

| Componente              | Teste |
|-------------------------|------------------------------------------------|
| **Matriz de LEDs**      | LEDs acendem e respondem corretamente? |
| **Buzzer**              | O som do alarme é emitido corretamente? |
| **Sensor Ultrassônico** | A distância medida está precisa? |
| **Display OLED**        | O texto e os gráficos aparecem corretamente? |

Se algum teste falhar, revise as conexões e tente os métodos de depuração mencionados acima.

---

## 🎥 Teste de Bancada

Aqui está um vídeo demonstrando o funcionamento do firmware durante os testes de bancada:

<center>
  <video controls poster="../../assets/video/v1_thumb.jpeg" style="height: 300px;">
    <source src="../../assets/video/teste_bancada.mp4" type="video/mp4">
    Seu navegador não suporta a reprodução de vídeos.
  </video>
</center>