This is a sketch of a completely open hardware kit for getting started with electronics

| # | Module | Part | Price | Source files | CircuitPython | MicroBlocks |
|---|---|---|---|---|---|---|
| B1 | Board | [Adafruit Metro](https://www.digikey.co.uk/en/products/detail/adafruit-industries-llc/5500/24639111) | $24.00 | [Repo](https://github.com/samuk/ESP32-WROOM-32E-development-board) | [CircuitPython](https://learn.adafruit.com/circuitpython-essentials) | [Get started](https://microblocks.fun/get-started) |
| B2 | Shield | [Grove Base Shield V2.0 for Arduino](https://wiki.seeedstudio.com/Base_Shield_V2/) | $3.50| [Seeed wiki](https://wiki.seeedstudio.com/Base_Shield_V2/)  | N/A | N/A |
| 3 | LED button | [Crowtail Button 2.0](https://www.elecrow.com/crowtailbutton-p-122.html) | from $1.00 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--button.html) | [Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out) | [Shutter controlled with buttons](https://learn.microblocks.fun/en/activities/citilab-course-10-en) |
| 4 | DHT11 | [Crowtail Temp & Humidity 2.0](https://www.elecrow.com/crowtail-temperature-humidity-sensor-p-1229.html) | $2.10 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--temperature26-humidity-sensor.html) | [Adafruit DHT guide](https://learn.adafruit.com/dht), [adafruit_dht docs](https://learn.adafruit.com/dht/dht-circuitpython-code) | [Basic sensor: light level and temperature](https://learn.microblocks.fun/en/activities/citilab-course-02-en) |
| 5 | Relay | [Grove Relay](https://wiki.seeedstudio.com/Grove-Relay/) | $2.99 | [Seeed wiki](https://wiki.seeedstudio.com/Grove-Relay/) | [Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out) | [Libraries](https://wiki.microblocks.fun/libraries) |
| 7 | Buzzer | [Crowtail Buzzer 2.0](https://www.elecrow.com/crowtail-buzzer-p-1223.html) | $1.20 | [Crowtail wiki](https://elecrow.com/wiki/crowtail--buzzer.html) | [CircuitPython PWM](https://learn.adafruit.com/circuitpython-essentials/circuitpython-pwm) | [Theremin](https://learn.microblocks.fun/en/activities/citilab-course-09-en) |
| 8 | LDR | [Crowtail Light Sensor 2.0](https://www.elecrow.com/crowtail-light-sensor-p-1244.html) | $1.90 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--light-sensor.html) | [Analog In](https://learn.adafruit.com/circuitpython-essentials/circuitpython-analog-in) | [Shutter controlled with light](https://learn.microblocks.fun/en/activities/citilab-course-11-en) |
| 9 | Potentiometer | [Crowtail Rotary Angle Sensor 2.0](https://www.elecrow.com/crowtail-rotary-angle-sensor-p-1514.html) | $1.30 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--rotary-angle-sensor.html) | [Analog In](https://learn.adafruit.com/circuitpython-essentials/circuitpython-analog-in) | [Libraries](https://wiki.microblocks.fun/libraries) |
| 10 | NeoPixel | [Grove RGB 10x LED Stick ](https://wiki.seeedstudio.com/Grove-RGB_LED_Stick-10-WS2813_Mini/) | $5.40 | [Seeed wiki](https://wiki.seeedstudio.com/Grove-RGB_LED_Stick-10-WS2813_Mini/) | [CircuitPython NeoPixel](https://learn.adafruit.com/circuitpython-essentials/circuitpython-neopixel) | [Play with Neopixels](https://learn.microblocks.fun/en/activities/citilab-course-06-en) |
| 11 | OLED | [Grove OLED Display 0.96 SSD1315](https://wiki.seeedstudio.com/Grove-OLED-Display-0.96-SSD1315/) | $6.00 | [Seeed wiki](https://wiki.seeedstudio.com/Grove-OLED-Display-0.96-SSD1315/) | [adafruit_displayio_ssd1306 docs](https://docs.circuitpython.org/projects/displayio_ssd1306/en/latest/) | [OLED Graphics library](https://wiki.microblocks.fun/extension_libraries/oled) |
| | **Total** | | **~$50 US** | | | |


**Part 2 starter robot**

| # | Module | Part | Price | Source files | CircuitPython | MicroBlocks |
|---|---|---|---|---|---|---|
| 6 | Motor controller | [Zio 4 DC Motor Controller Qwiic](https://www.smart-prototyping.com/Zio/Zio-4-DC-Motor-Controller.html) | $9.90 | [Eagle files](https://github.com/ZIOCC/Qwiic_4-Ch_DC_Motor_Controller) | [circuitpython-zio-4dc-motor](https://github.com/tykling/circuitpython-zio-4dc-motor) | [Zio Four Motor Controller library request](https://bitbucket.org/john_maloney/smallvm/issues/444/i2c-motor-controller) |
| 12 | Chassis | [XRP Holonomic Chassis](https://www.printables.com/model/1409157-xrp-holonomic-chassis/files) | Free (3D print) | [Printables files](https://www.printables.com/model/1409157-xrp-holonomic-chassis/files) | | |
| 13 | Motor | [Yahboom TT DC Gear Motor with Encoder](https://www.yahboom.store/collections/a-motor/products/encoder-tt-motor) | $6.40 each | [Yahboom product page](https://www.yahboom.store/collections/a-motor/products/encoder-tt-motor) | | |
| | **Total** | | **$9.90 + $6.40 per motor** | | | |



# Part 1 course: seven lessons, each built in CircuitPython and MicroBlocks

**Pin map used throughout**

| Part | GPIO | Note |
|---|---|---|
| NeoPixel stick | 13 | data pin |
| Button | 4 | digital input |
| Relay | 5 | digital output |
| LDR | 34 | analogue input |
| Potentiometer | 35 | analogue input |
| Buzzer | 18 | PWM |
| DHT11 | 15 | digital |
| OLED | 21 (SDA), 22 (SCL) | I2C |

Use GPIO 32 to 39 for the analogue parts, because ADC2 pins stop working when WiFi is on. In CircuitPython the pins are written `board.IO13` and so on, assuming the DevKitC-V4 firmware pin names apply to your board. In MicroBlocks you use the plain GPIO number.

---

## Lesson 0: Setup

**CircuitPython:** The ESP32 has no USB drive, so you flash over serial and edit over WiFi. Follow the [ESP32 quick start](https://learn.adafruit.com/circuitpython-with-esp32-quick-start) and the [firmware download](https://circuitpython.org/board/espressif_esp32_devkitc_v4_wroom_32e/). Then install the libraries `neopixel`, `adafruit_dht`, `adafruit_displayio_ssd1306` and `adafruit_display_text` from the library bundle.

**MicroBlocks:** [Get started](https://microblocks.fun/get-started). Connect the board in the browser IDE and install the firmware when it asks.

## Lesson 1: Hello NeoPixel
Light the stick red, then green, then blue.

**CircuitPython** ([NeoPixel](https://learn.adafruit.com/circuitpython-essentials/circuitpython-neopixel))
```python
import board, neopixel, time
px = neopixel.NeoPixel(board.IO13, 10, brightness=0.2)
for colour in [(255, 0, 0), (0, 255, 0), (0, 0, 255)]:
    px.fill(colour)
    time.sleep(1)
```
**MicroBlocks** ([Play with Neopixels](https://learn.microblocks.fun/en/activities/citilab-course-06-en)): load the NeoPixel library. Set all pixels to red, wait 1000 ms, then green, then blue.

If the stick flickers, the 3.3V data signal may be too weak for the LEDs. I haven't tested this.

## Lesson 2: Button changes the light
Hold the button and the stick turns green.

**CircuitPython** ([Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out))
```python
import digitalio
btn = digitalio.DigitalInOut(board.IO4)
btn.switch_to_input(pull=digitalio.Pull.DOWN)  # use UP if it reads inverted
while True:
    px.fill((0, 255, 0) if btn.value else (0, 0, 0))
```
**MicroBlocks** ([Shutter controlled with buttons](https://learn.microblocks.fun/en/activities/citilab-course-10-en)): `forever`, `if (digital read pin 4)` set all pixels green, else off.

## Lesson 3: Press to toggle the relay
Each press flips the relay on or off. This lesson introduces remembering the previous state.

**CircuitPython** ([Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out))
```python
relay = digitalio.DigitalInOut(board.IO5)
relay.direction = digitalio.Direction.OUTPUT
was = False
while True:
    now = btn.value
    if now and not was:
        relay.value = not relay.value
    was = now
    time.sleep(0.02)
```
**MicroBlocks** ([Libraries](https://wiki.microblocks.fun/libraries)): a variable `was`. `forever`: if the button is pressed and `was` is false, set pin 5 to `not (digital read pin 5)`. Then set `was` to the button state.

Keep the relay on low-voltage loads only.

## Lesson 4: Light meter
The brighter the room, the more pixels light up.

**CircuitPython** ([Analog In](https://learn.adafruit.com/circuitpython-essentials/circuitpython-analog-in))
```python
import analogio
ldr = analogio.AnalogIn(board.IO34)
while True:
    n = ldr.value * 10 // 65536
    px.fill((0, 0, 0))
    for i in range(n):
        px[i] = (0, 80, 80)
    time.sleep(0.1)
```
**MicroBlocks** ([Shutter controlled with light](https://learn.microblocks.fun/en/activities/citilab-course-11-en)): set `n` to `(read analog pin 34) / 103` (MicroBlocks reads 0 to 1023). Clear the pixels, then `for i = 1 to n` set pixel `i`.

Print the raw value first. I don't know whether the Crowtail module reads higher or lower in bright light.

## Lesson 5: Dial a tone
The potentiometer sets the buzzer pitch.

**CircuitPython** ([PWM, variable frequency](https://learn.adafruit.com/circuitpython-essentials/circuitpython-pwm))
```python
import pwmio
pot = analogio.AnalogIn(board.IO35)
buzzer = pwmio.PWMOut(board.IO18, duty_cycle=2**15, variable_frequency=True)
while True:
    buzzer.frequency = 200 + pot.value // 32   # about 200 to 2250 Hz
    time.sleep(0.02)
```
**MicroBlocks** ([Theremin](https://learn.microblocks.fun/en/activities/citilab-course-09-en)): load the Tone library. `forever`: play a tone at `200 + (read analog pin 35)` Hz for 20 ms.

This only works if the Crowtail buzzer is passive. I haven't verified that.

## Lesson 6: Weather display
Read temperature and humidity and show them on the OLED.

**CircuitPython** ([Adafruit DHT guide](https://learn.adafruit.com/dht), [SSD1306 displayio docs](https://docs.circuitpython.org/projects/displayio_ssd1306/en/latest/))
```python
import displayio, terminalio, i2cdisplaybus, adafruit_dht
import adafruit_displayio_ssd1306
from adafruit_display_text import label

displayio.release_displays()
bus = i2cdisplaybus.I2CDisplayBus(board.I2C(), device_address=0x3C)
display = adafruit_displayio_ssd1306.SSD1306(bus, width=128, height=64)
text = label.Label(terminalio.FONT, text="starting", x=0, y=10, scale=2)
display.root_group = text

dht = adafruit_dht.DHT11(board.IO15)
while True:
    try:
        text.text = f"{dht.temperature} C\n{dht.humidity} %"
    except RuntimeError:
        pass  # DHT11 misreads are normal
    time.sleep(2)
```
**MicroBlocks** ([OLED Graphics library](https://wiki.microblocks.fun/extension_libraries/oled), [Basic sensor: light level and temperature](https://learn.microblocks.fun/en/activities/citilab-course-02-en)): load the DHT11 and OLED libraries. `forever`: clear the display, write the temperature and humidity, wait 2000 ms.

CircuitPython 9 and later is assumed. On older versions the OLED setup differs.

## Lesson 7: Capstone, a thermostat
Combine everything from lessons 1 to 6. The pot sets the target temperature, the OLED shows both values, and the relay switches a fan or heater. The stick is green when the temperature is below target, red when above, and the buzzer sounds 5 degrees over.

**CircuitPython** (reuse the setup from lessons 1 to 6)
```python
while True:
    try:
        t = dht.temperature
        target = 15 + pot.value * 20 // 65535        # 15 to 35 C
        hot = t > target
        relay.value = hot
        px.fill((255, 0, 0) if hot else (0, 255, 0))
        buzzer.duty_cycle = 2**15 if t > target + 5 else 0
        text.text = f"{t} C\nset {target} C"
    except RuntimeError:
        pass
    time.sleep(2)
```
**MicroBlocks** ([Shutter controlled with light](https://learn.microblocks.fun/en/activities/citilab-course-11-en), for custom blocks): same logic inside a custom block `update thermostat` that you call from `forever`. That pattern keeps the script readable.

---


