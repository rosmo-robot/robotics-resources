**Part 1 Basic Electronics**

| # | Module | Part | Price | Source files | MicroPython (chip / projects) | MicroBlocks |
|---|---|---|---|---|---|---|
| B1 | Board | [Adafruit QT Py ESP32-S3](https://www.adafruit.com/product/5426) (8 MB flash, no PSRAM) | $12.50 | [ESP32-S3 datasheet](https://cdn-shop.adafruit.com/product-files/5426/esp32-s3_datasheet_en.pdf), [Learn guide](https://learn.adafruit.com/adafruit-qt-py-esp32-s3). Board files not checked. | Not checked. The product page lists Arduino IDE and CircuitPython. | Not checked. MicroBlocks lists the XIAO ESP32-S3 and this board shares its pinout, but that is untested. |
| B2 | Board + onboard OLED, buzzer, button | [Seeed XIAO Expansion Base](https://www.seeedstudio.com/Seeeduino-XIAO-Expansion-board-p-4746.html) (no XIAO included) | $15.99 | [Wiki: schematic PDF, SCH and BRD files](https://wiki.seeedstudio.com/Seeeduino-XIAO-Expansion-Board/) | Not checked. The wiki covers CircuitPython. | MicroBlocks lists XIAO SAMD21, nRF52840, RP2040, RP2350, ESP32-C3 and ESP32-S3. Onboard OLED, buzzer and button: likely yes, untested. RTC and microSD: no library found. |
| 2 | RGB LED | [Grove RGB LED (WS2813 Mini)](https://www.seeedstudio.com/Grove-RGB-LED-WS2813-Mini-p-4269.html) | $4.40 | [WS2813-Mini datasheet](https://files.seeedstudio.com/wiki/Grove-RGB_LED_Ring-20-WS2813Mini/res/WS2813-Mini.pdf); [Eagle files on the stick's wiki](https://wiki.seeedstudio.com/Grove-RGB_LED_Stick-10-WS2813_Mini/) (same chip, not the single LED) | Built-in neopixel module (WS2812 timing). I found no WS2813-specific project. | Yes, NeoPixel library; set pin and LED count first |
| 3 | LED button | [Crowtail Button 2.0](https://www.elecrow.com/crowtailbutton-p-122.html) (plain button, no LED) | from $1.00 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--button.html) | No chip. Plain Pin in and out. | Yes, basic digital pin blocks |
| 4 | DHT11 | [Crowtail Temp & Humidity 2.0](https://www.elecrow.com/crowtail-temperature-humidity-sensor-p-1229.html) (DHT11, 3.3V to 5V) | $2.10 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--temperature26-humidity-sensor.html) | Built-in dht module (dht.DHT11) | Yes, a Temperature and Humidity DHT11 library exists |
| 5 | Relay | [Grove Relay](https://www.seeedstudio.com/Grove-Relay.html) | $2.99 | [Eagle, PCB and schematic PDFs](https://github.com/SeeedDocument/Seeed-WiKi/blob/master/docs/Grove-Relay.md) | No chip. Pin.value(). | Yes, set digital pin |
| 7 | Buzzer | [Crowtail Buzzer 2.0](https://www.elecrow.com/crowtail-buzzer-p-1223.html) (piezo; out of stock when fetched) | $1.20 | [Crowtail wiki](https://elecrow.com/wiki/crowtail--buzzer.html) | No chip. PWM on a pin. micropython-buzzer plays RTTTL and MIDI files (listed in [awesome-micropython](https://github.com/nasirxo/awesome-micropython)). | Yes, Tone library |
| 8 | LDR | [Crowtail Light Sensor 2.0](https://www.elecrow.com/crowtail-light-sensor-p-1244.html) (GL5516 LDR with LMV358 buffer) | $1.90 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--light-sensor.html) | No chip. ADC.read_u16() | Yes, read analog pin |
| 9 | Potentiometer | [Crowtail Rotary Angle Sensor 2.0](https://www.elecrow.com/crowtail-rotary-angle-sensor-p-1514.html) | $1.30 | [Crowtail wiki](https://www.elecrow.com/wiki/crowtail--rotary-angle-sensor.html) | No chip. ADC.read_u16() | Yes, read analog pin |
| | **Total, rows 2 to 9 (excludes the board)** | | **$14.89** | | | |

**Part 2 starter robot**

| # | Item | Price | Source files | Notes |
|---|---|---|---|---|
| 6 | [Zio 4 DC Motor Controller (Qwiic)](https://www.smart-prototyping.com/Zio/Zio-4-DC-Motor-Controller.html) | $9.90 | [Eagle files](https://github.com/ZIOCC/Qwiic_4-Ch_DC_Motor_Controller); PCA9685 and TB6612FNG datasheets on the product page | Two motors, I2C address 0x40 by default. The listing contradicts itself: the title says 1.2A continuous and 3.2A peak, the body says 1A per channel and 2.7 to 5.5V recommended, 15V max. The demo code needs the pull-up jumpers soldered. Qwiic only, no Grove. MicroPython and MicroBlocks support not checked. |

