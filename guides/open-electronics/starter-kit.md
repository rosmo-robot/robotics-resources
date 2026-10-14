This is a sketch of a completely open hardware kit for getting started with elecronics

| # | Module | Part | Price | Source files | CircuitPython (chip / projects) | MicroBlocks |
|---|---|---|---|---|---|---|
| B1 | Board | [ESP32-WROOM-32E development board](https://github.com/samuk/ESP32-WROOM-32E-development-board) | $10.00 | [Repo](https://github.com/samuk/ESP32-WROOM-32E-development-board) | [CircuitPython NeoPixel](https://learn.adafruit.com/circuitpython-essentials/circuitpython-neopixel) | Yes, NeoPixel library |
| 3 | LED button | [Crowtail Button 2.0](https://www.elecrow.com/crowtailbutton-p-122.html) (plain button, no LED) | from $1.00 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--button.html) | [Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out) | Yes, basic digital pin blocks |
| 4 | DHT11 | [Crowtail Temp & Humidity 2.0](https://www.elecrow.com/crowtail-temperature-humidity-sensor-p-1229.html) (DHT11, 3.3V to 5V) | $2.10 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--temperature26-humidity-sensor.html) | [Adafruit DHT guide](https://learn.adafruit.com/dht), [adafruit_dht docs](https://docs.circuitpython.org/projects/dht/en/latest/) | Yes, a Temperature and Humidity DHT11 library exists |
| 5 | Relay | [Grove Relay](https://www.seeedstudio.com/Grove-Relay.html) | $2.99 | [Eagle, PCB and schematic PDFs](https://github.com/SeeedDocument/Seeed-WiKi/blob/master/docs/Grove-Relay.md) | [Digital In & Out](https://learn.adafruit.com/circuitpython-essentials/circuitpython-digital-in-out) (relay is just a digital output) | Yes, set digital pin |
| 7 | Buzzer | [Crowtail Buzzer 2.0](https://www.elecrow.com/crowtail-buzzer-p-1223.html) (piezo; out of stock when fetched) | $1.20 | [Crowtail wiki](https://elecrow.com/wiki/crowtail--buzzer.html) | [CircuitPython PWM](https://learn.adafruit.com/circuitpython-essentials/circuitpython-pwm) (variable frequency section) | Yes, Tone library |
| 8 | LDR | [Crowtail Light Sensor 2.0](https://www.elecrow.com/crowtail-light-sensor-p-1244.html) (GL5516 LDR with LMV358 buffer) | $1.90 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--light-sensor.html) | [Analog In](https://learn.adafruit.com/circuitpython-essentials/circuitpython-analog-in) | Yes, read analog pin |
| 9 | Potentiometer | [Crowtail Rotary Angle Sensor 2.0](https://www.elecrow.com/crowtail-rotary-angle-sensor-p-1514.html) | $1.30 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--rotary-angle-sensor.html) | [Analog In](https://learn.adafruit.com/circuitpython-essentials/circuitpython-analog-in) | Yes, read analog pin |
| 10 | NeoPixel | [Grove RGB LED Stick (10x WS2813 Mini)](https://www.seeedstudio.com/Grove-RGB-LED-Stick-10-WS2813-Mini.html) | $5.40 | [Seeed wiki](https://wiki.seeedstudio.com/Grove-RGB_LED_Stick-10-WS2813_Mini/) (pinout, datasheet) | [CircuitPython NeoPixel](https://learn.adafruit.com/circuitpython-essentials/circuitpython-neopixel) | Yes, NeoPixel library (untested with WS2813) |
| 11 | OLED | [Grove OLED Display 0.96" (SSD1315)](https://www.seeedstudio.com/Grove-OLED-Display-0-96-SSD1315-p-4294.html) | $6.00 | [Datasheet, schematic and wiki via Switch Science listing](https://www.switch-science.com/collections/seeed/products/7002) | [adafruit_displayio_ssd1306 docs](https://docs.circuitpython.org/projects/displayio_ssd1306/en/latest/) (SSD1306 driver, used with this module by others) | [OLED Graphics library](https://wiki.microblocks.fun/extension_libraries/oled), not confirmed against SSD1315 |
| | **Total** | | **$31.89** | | | |


**Part 2 starter robot**

| # | Item | Price | Source files | Notes |
|---|---|---|---|---|
| 6 | [Zio 4 DC Motor Controller (Qwiic)](https://www.smart-prototyping.com/Zio/Zio-4-DC-Motor-Controller.html) | $9.90 | [Eagle files](https://github.com/ZIOCC/Qwiic_4-Ch_DC_Motor_Controller); PCA9685 and TB6612FNG datasheets on the product page | Two motors, I2C address 0x40 by default. The listing contradicts itself: the title says 1.2A continuous and 3.2A peak, the body says 1A per channel and 2.7 to 5.5V recommended, 15V max. The demo code needs the pull-up jumpers soldered. Qwiic only, no Grove. MicroPython and MicroBlocks support not checked. |

