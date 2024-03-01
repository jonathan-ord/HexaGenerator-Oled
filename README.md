# Generador de Código Hexadecimal para OLED SSD1306 🎨

Este recurso es un generador de código hexadecimal diseñado para facilitar la utilización de imágenes en pantallas OLED SSD1306 en proyectos con MicroPython, especialmente en Raspberry Pi Pico W.

<div align="center">
   <img src="https://i.postimg.cc/wBB9xw8D/Web.png" alt="Selección_003" width="500"/></td>
</div>

[*Ingresa a la web aquí*](https://jonathanord.pythonanywhere.com/)

## Funcionalidades Principales 🛠️

1. **Selección de Imagen:** Interfaz sencilla para elegir la imagen deseada.
   
2. **Procesamiento de la Imagen:** Conversión de la imagen seleccionada a código hexadecimal compatible.

3. **Visualización del Código:** Muestra el código generado para copiarlo fácilmente.

## Cómo Utilizar 📝

1. **Seleccionar Imagen:** Haz clic en "Seleccionar imagen" y elige la imagen.

2. **Generar Código:** Haz clic en "Generar" para obtener el código hexadecimal.

3. **Copiar Código:** Copia el código mostrado para utilizarlo en MicroPython.

## Ejemplo de Uso 🚀
    
```python
import time
import framebuf
from machine import Pin, I2C
import ssd1306

# Configuración de pines para la pantalla OLED
i2c = I2C(0, scl=Pin(9), sda=Pin(8))
oled = ssd1306.SSD1306_I2C(128, 64, i2c)

oled.invert(1)

# Ingresar código hexadecimal
buffer = bytearray(b"")

fb = framebuf.FrameBuffer(buffer, 128, 64, framebuf.MONO_HLSB)

while True:
    oled.fill(0)
    oled.blit(fb, 0, 0)
    oled.show()
    time.sleep_ms(1000)
```

## Requisitos 📋

- Raspberry Pi Pico W con MicroPython instalado.
- Pantalla OLED SSD1306 correctamente conectada.

## Notas ℹ️

- Este recurso es útil para proyectos que requieran la visualización de imágenes en pantallas OLED SSD1306 utilizando MicroPython.
- Asegúrese de seguir las instrucciones de conexión y configuración adecuadas para su Raspberry Pi Pico W y la pantalla OLED SSD1306.
