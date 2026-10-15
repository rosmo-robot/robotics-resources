| # | Module | Part | Price | Source files | CircuitPython | MicroBlocks |
|---|---|---|---|---|---|---|
| B1 | Board | [Matouch3.2](https://www.makerfabs.com/esp32-3-2-inch-tft-touch-with-camera.html) | $14.00 | [Repo](https://github.com/Makerfabs/Project_Touch-Camera-ILI9341/tree/master/hardware/V1.1) | [CircuitPython](https://learn.adafruit.com/circuitpython-essentials) | [Get started](https://microblocks.fun/get-started) |
| B2 | Custom Shield | [Custom Base](https://github.com/rosmo-robot/Grove-UEXT-3.2screen-breakout/) | $TBC | []() | N/A | N/A |
| 3 | LED button | [Crowtail Button 2.0](https://www.elecrow.com/crowtailbutton-p-122.html) | from $1.00 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--button.html) | [Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out) | [Shutter controlled with buttons](https://learn.microblocks.fun/en/activities/citilab-course-10-en) |
| 4 | DHT11 | [Crowtail Temp & Humidity 2.0](https://www.elecrow.com/crowtail-temperature-humidity-sensor-p-1229.html) | $2.10 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--temperature26-humidity-sensor.html) | [Adafruit DHT guide](https://learn.adafruit.com/dht), [adafruit_dht docs](https://learn.adafruit.com/dht/dht-circuitpython-code) | [Basic sensor: light level and temperature](https://learn.microblocks.fun/en/activities/citilab-course-02-en) |
| 5 | Relay | [Crowtail Solid-State Relay 2.0](https://www.elecrow.com/crowtail-solid-state-relay.html) | $2.50 | [Product page](https://www.elecrow.com/crowtail-solid-state-relay.html) | [Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out) | [Libraries](https://wiki.microblocks.fun/libraries) |
| 7 | Buzzer | [Crowtail Buzzer 2.0](https://www.elecrow.com/crowtail-buzzer-p-1223.html) | $1.20 | [Crowtail wiki](https://elecrow.com/wiki/crowtail--buzzer.html) | [CircuitPython PWM](https://learn.adafruit.com/circuitpython-essentials/circuitpython-pwm) | [Theremin](https://learn.microblocks.fun/en/activities/citilab-course-09-en) |
| 8 | LDR | [Crowtail Light Sensor 2.0](https://www.elecrow.com/crowtail-light-sensor-p-1244.html) | $1.90 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--light-sensor.html) | [Analog In](https://learn.adafruit.com/circuitpython-essentials/circuitpython-analog-in) | [Shutter controlled with light](https://learn.microblocks.fun/en/activities/citilab-course-11-en) |
| 9 | Potentiometer | [Crowtail Rotary Angle Sensor 2.0](https://www.elecrow.com/crowtail-rotary-angle-sensor-p-1514.html) | $1.30 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--rotary-angle-sensor.html) | [Analog In](https://learn.adafruit.com/circuitpython-essentials/circuitpython-analog-in) | [Libraries](https://wiki.microblocks.fun/libraries) |
| 10 | NeoPixel | [Crowtail RGB-LED (4x WS2812B)](https://elecrow.com/wiki/crowtail--rgb-led.html) | ~$4 | [Crowtail wiki](https://elecrow.com/wiki/crowtail--rgb-led.html) | [CircuitPython NeoPixel](https://learn.adafruit.com/circuitpython-essentials/circuitpython-neopixel) | [Play with Neopixels](https://learn.microblocks.fun/en/activities/citilab-course-06-en) |
| | **Total** | | **~$28 US plus shield** | | | |

# Starter kit course: seven lessons, done twice

Part 1 builds each lesson in MicroBlocks. Part 2 repeats the same seven lessons in CircuitPython. The wiring is identical in both parts.

**Hardware:** Matouch 3.2 (ESP32, 3.3V) on the custom shield, with Crowtail modules. The screen is built into the board.

## Pin map (both parts)

| Part | GPIO | Note |
|---|---|---|
| Crowtail RGB-LED (4 pixels) | 13 | data pin |
| Crowtail Button 2.0 | 4 | digital input |
| Crowtail Solid-State Relay 2.0 | 5 | digital output |
| Crowtail Light Sensor 2.0 | 34 | analogue input |
| Crowtail Rotary Angle Sensor 2.0 | 35 | analogue input |
| Crowtail Buzzer 2.0 | 18 | PWM |
| Crowtail Temp & Humidity 2.0 (DHT11) | 15 | digital |
| TFT screen | n/a | on the board |

Use GPIO 32 to 39 for the analogue parts, because ADC2 pins stop working when WiFi is on. In CircuitPython the pins are written `board.IO13` and so on. In MicroBlocks you use the plain GPIO number.

**To check before printing:** this map has not been checked against the Matouch 3.2 schematic. The screen, touch, SD card and camera already use GPIOs on this board, so some of these will need to change.

**Safety:** use the relay with low-voltage loads only. No mains in the lessons.

---

# Part 1: MicroBlocks

## Lesson 0: Setup
[Get started](https://microblocks.fun/get-started). Connect the board in the browser IDE and install the firmware when it asks.

## Lesson 1: Hello NeoPixel
Light the stick red, then green, then blue.

[Play with Neopixels](https://learn.microblocks.fun/en/activities/citilab-course-06-en): load the NeoPixel library. Set all pixels to red, wait 1000 ms, then green, then blue.

If the pixels flicker, the 3.3V data signal may be too weak for the LEDs.

## Lesson 2: Button changes the light
Hold the button and the stick turns green.

[Shutter controlled with buttons](https://learn.microblocks.fun/en/activities/citilab-course-10-en): `forever`, `if (digital read pin 4)` set all pixels green, else off.

## Lesson 3: Press to toggle the relay
Each press flips the relay on or off. This lesson introduces remembering the previous state.

[Libraries](https://wiki.microblocks.fun/libraries): make a variable `was`. `forever`: if the button is pressed and `was` is false, set pin 5 to `not (digital read pin 5)`. Then set `was` to the button state.

## Lesson 4: Light meter
The brighter the room, the more pixels light up.

[Shutter controlled with light](https://learn.microblocks.fun/en/activities/citilab-course-11-en): set `n` to `((read analog pin 34) * 4) / 1023` (MicroBlocks reads 0 to 1023). Clear the pixels, then `for i = 1 to n` set pixel `i`.

Show the raw reading first. The Crowtail module may read higher or lower in bright light.

## Lesson 5: Dial a tone
The potentiometer sets the buzzer pitch.

[Theremin](https://learn.microblocks.fun/en/activities/citilab-course-09-en): load the Tone library. `forever`: play a tone at `200 + (read analog pin 35)` Hz for 20 ms.

This only works if the Crowtail buzzer is passive.

## Lesson 6: Weather display
Read temperature and humidity and show them on the screen.

[Basic sensor: light level and temperature](https://learn.microblocks.fun/en/activities/citilab-course-02-en): load the DHT11 library and the TFT library for the board's display. `forever`: clear the screen, write the temperature and humidity, wait 2000 ms.

## Lesson 7: Capstone, a thermostat
Combine lessons 1 to 6. The pot sets the target temperature, the screen shows both values, and the relay switches a fan or heater. The stick is green when the temperature is below target and red when above. The buzzer sounds 5 degrees over.

Build one custom block, `update thermostat`, holding all of the logic, and call it from `forever`. That keeps the script readable. See [Shutter controlled with light](https://learn.microblocks.fun/en/activities/citilab-course-11-en) for custom blocks.

---

# Part 2: CircuitPython

Same seven lessons as Part 1. Do each one again, now in code.

## Lesson 0: Setup
The ESP32 has no USB drive, so you flash over serial and edit over WiFi. Follow the [ESP32 quick start](https://learn.adafruit.com/circuitpython-with-esp32-quick-start) and the [firmware download](https://circuitpython.org/board/espressif_esp32_devkitc_v4_wroom_32e/). Then install the libraries `neopixel`, `adafruit_dht`, `adafruit_ili9341` and `adafruit_display_text` from the library bundle.

## Lesson 1: Hello NeoPixel
Light the stick red, then green, then blue. ([NeoPixel](https://learn.adafruit.com/circuitpython-essentials/circuitpython-neopixel))

```python
import board, neopixel, time

px = neopixel.NeoPixel(board.IO13, 4, brightness=0.2)
for colour in [(255, 0, 0), (0, 255, 0), (0, 0, 255)]:
    px.fill(colour)
    time.sleep(1)
```

## Lesson 2: Button changes the light
Hold the button and the stick turns green. ([Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out))

```python
import board, neopixel, digitalio

px = neopixel.NeoPixel(board.IO13, 4, brightness=0.2)
btn = digitalio.DigitalInOut(board.IO4)
btn.switch_to_input(pull=digitalio.Pull.DOWN)  # use UP if it reads inverted

while True:
    px.fill((0, 255, 0) if btn.value else (0, 0, 0))
```

## Lesson 3: Press to toggle the relay
Each press flips the relay on or off. ([Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out))

```python
import board, digitalio, time

btn = digitalio.DigitalInOut(board.IO4)
btn.switch_to_input(pull=digitalio.Pull.DOWN)
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

## Lesson 4: Light meter
The brighter the room, the more pixels light up. ([Analog In](https://learn.adafruit.com/circuitpython-essentials/circuitpython-analog-in))

```python
import board, neopixel, analogio, time

px = neopixel.NeoPixel(board.IO13, 4, brightness=0.2)
ldr = analogio.AnalogIn(board.IO34)

while True:
    n = ldr.value * 5 // 65536   # 0 to 4 pixels
    px.fill((0, 0, 0))
    for i in range(n):
        px[i] = (0, 80, 80)
    time.sleep(0.1)
```

Print `ldr.value` first to check which way the module reads.

## Lesson 5: Dial a tone
The potentiometer sets the buzzer pitch. ([PWM](https://learn.adafruit.com/circuitpython-essentials/circuitpython-pwm))

```python
import board, analogio, pwmio, time

pot = analogio.AnalogIn(board.IO35)
buzzer = pwmio.PWMOut(board.IO18, duty_cycle=2**15, variable_frequency=True)

while True:
    buzzer.frequency = 200 + pot.value // 32   # about 200 to 2250 Hz
    time.sleep(0.02)
```

## Lesson 6: Weather display
Read temperature and humidity and show them on the screen. ([Adafruit DHT guide](https://learn.adafruit.com/dht))

```python
import board, busio, displayio, terminalio, time
import fourwire, adafruit_ili9341, adafruit_dht
from adafruit_display_text import label

# Fill these in from the Matouch 3.2 schematic
TFT_SCK = None
TFT_MOSI = None
TFT_MISO = None
TFT_CS = None
TFT_DC = None
TFT_RST = None

displayio.release_displays()
spi = busio.SPI(clock=TFT_SCK, MOSI=TFT_MOSI, MISO=TFT_MISO)
bus = fourwire.FourWire(spi, command=TFT_DC, chip_select=TFT_CS, reset=TFT_RST)
display = adafruit_ili9341.ILI9341(bus, width=320, height=240)

text = label.Label(terminalio.FONT, text="starting", x=10, y=30, scale=3)
display.root_group = text

dht = adafruit_dht.DHT11(board.IO15)

while True:
    try:
        text.text = f"{dht.temperature} C\n{dht.humidity} %"
    except RuntimeError:
        pass  # DHT11 misreads are normal
    time.sleep(2)
```

CircuitPython 9 or later is assumed.

## Lesson 7: Capstone, a thermostat
Combine lessons 1 to 6. The pot sets the target temperature, the screen shows both values, and the relay switches a fan or heater. The stick is green when the temperature is below target and red when above. The buzzer sounds 5 degrees over.

```python
import board, neopixel, digitalio, analogio, pwmio, adafruit_dht, time
# display setup: copy from lesson 6 (imports, TFT pins, display, text label)

px = neopixel.NeoPixel(board.IO13, 4, brightness=0.2)
relay = digitalio.DigitalInOut(board.IO5)
relay.direction = digitalio.Direction.OUTPUT
pot = analogio.AnalogIn(board.IO35)
buzzer = pwmio.PWMOut(board.IO18, duty_cycle=0, frequency=1000)
dht = adafruit_dht.DHT11(board.IO15)

while True:
    try:
        t = dht.temperature
        target = 15 + pot.value * 20 // 65535      # 15 to 35 C
        hot = t > target
        relay.value = hot
        px.fill((255, 0, 0) if hot else (0, 255, 0))
        buzzer.duty_cycle = 2**15 if t > target + 5 else 0
        text.text = f"{t} C\nset {target} C"
    except RuntimeError:
        pass
    time.sleep(2)
```







**Part 2 starter robot**

| # | Module | Part | Price | Source files | CircuitPython | MicroBlocks |
|---|---|---|---|---|---|---|
| 6 | Motor controller | [Zio 4 DC Motor Controller Qwiic](https://www.smart-prototyping.com/Zio/Zio-4-DC-Motor-Controller.html) | $9.90 | [Eagle files](https://github.com/ZIOCC/Qwiic_4-Ch_DC_Motor_Controller) | [circuitpython-zio-4dc-motor](https://github.com/tykling/circuitpython-zio-4dc-motor) | [Zio Four Motor Controller library request](https://bitbucket.org/john_maloney/smallvm/issues/444/i2c-motor-controller) |
| 12 | Chassis | [XRP Holonomic Chassis](https://www.printables.com/model/1409157-xrp-holonomic-chassis/files) | Free (3D print) | [Printables files](https://www.printables.com/model/1409157-xrp-holonomic-chassis/files) | | |
| 13 | Motor | [Yahboom TT DC Gear Motor with Encoder](https://www.yahboom.store/collections/a-motor/products/encoder-tt-motor) | $6.40 each | [Yahboom product page](https://www.yahboom.store/collections/a-motor/products/encoder-tt-motor) | | |
| | **Total** | | **$9.90 + $6.40 per motor** | | | |

