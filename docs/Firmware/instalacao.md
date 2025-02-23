# 🛠️ Instalação e Compilação

Esta seção fornece um guia passo a passo para configurar, compilar e carregar o firmware **BR SmartGuia** no **Raspberry Pi Pico**.

## 📥 Pré-requisitos

Antes de começar, certifique-se de que possui os seguintes itens instalados:

| Requisito                      | Descrição |
|--------------------------------|------------------------------------------------|
| **Raspberry Pi Pico SDK**     | Biblioteca necessária para desenvolver no RP2040. |
| **CMake**                     | Ferramenta para gerar os arquivos de build. |
| **GNU Arm Embedded Toolchain** | Compilador para ARM. |
| **VS Code (Opcional)**        | Editor de código recomendado. |

## 🚀 Passos para Compilar o Firmware

### 1️⃣ Clonar o Repositório

```bash
git clone <seu-repositorio>
cd <seu-repositorio>
```

### 2️⃣ Configurar o SDK do Pico

```bash
export PICO_SDK_PATH=~/pico-sdk
```
> 💡 **Dica:** Adicione essa linha ao `~/.bashrc` para evitar reconfigurar a cada sessão.

### 3️⃣ Criar o Diretório de Build

```bash
mkdir build
cd build
```

### 4️⃣ Gerar os Arquivos de Compilação

```bash
cmake ..
```

### 5️⃣ Compilar o Código

```bash
make -j$(nproc)
```

Após a conclusão, o firmware compilado estará disponível no arquivo `.uf2` dentro da pasta `build`.

## 🔄 Carregar o Firmware no Raspberry Pi Pico

1. Conecte o Raspberry Pi Pico ao seu computador enquanto segura o botão **BOOTSEL**.
2. Ele aparecerá como um dispositivo de armazenamento USB.
3. Copie o arquivo `.uf2` gerado para esse dispositivo:

   ```bash
   cp firmware.uf2 /media/$USER/RPI-RP2/
   ```

4. O Pico será reiniciado automaticamente e o firmware estará rodando! 🎉

## 📟 Testando o Firmware

Para verificar a saída serial do Raspberry Pi Pico:

```bash
minicom -b 115200 -o -D /dev/ttyUSB0
```

Ou, no Windows, utilize **PuTTY** e conecte à porta COM correta com baud rate **115200**.

---

Agora que o firmware está instalado, siga para os exemplos práticos! 📖

[➡️ Exemplos Práticos](exemplos.md)