# ESP32 Marauder DIY Detailed Instructions

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_19.jpeg" width="400"/>

## About

This guide will describe how to setup ESP32 Marauder on self made board/components. The below example will use these components:

* ESP32 [ESP32-WROOM-32D Microcontroller module](https://www.aliexpress.com/item/32864722159.html) 4,17eur
* [MicroSD Module](https://www.aliexpress.com/item/1005001861949506.html) 0,43eur
* [3.7V 103450 Polymer Lithium Battery](https://www.aliexpress.com/item/1005002734730431.html) 4,87eur
* [TP4056 Charging board](https://www.aliexpress.com/item/32467578996.html) 0,30eur
* [5x7cm Double Sided Board Sided Copper Green Breadboard](https://www.aliexpress.com/item/1005004267324732.html)  1,61eur
* [3.5 inch Raspberry Pi LCD TFT Touchscreen ILI9486](https://www.aliexpress.com/item/32609751923.html) 14eur
* [26 AWG 5 Meters Single Core Copper Wire](https://www.aliexpress.com/item/1005004635987651.html) 1,50eur
* Two [100k resistors](https://www.aliexpress.com/item/32847096736.html) 0,45eur
* [Soldering wire](https://www.aliexpress.com/item/1005004483998997.html) 3,20eur
* Soldering skills


Estimated project budget: 34,7eur

Estimated project time: 2 to 8 hours

## Pins

### TFT

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/tft_lcd_schema.png" width="400"/>


| TFT Module | ESP32 Board |
|------------|-------------|
| TFT 5V     | 5V          |
| TFT GND    | GND         |
| TFT MISO   | Pin 19      |
| TFT MOSI   | Pin 23      |
| TFT SCK    | Pin 18      |
| TFT CS     | Pin 16      |
| TFT DC     | Pin 2       |
| TFT RST    | Pin 4       |
| TFT T_CS   | Pin 21      |

### SD Card Module

| SD Card module | ESP32 Board          |
|----------------|----------------------|
| SD 3v3         | 3V3                  |
| SD GND         | GND                  |
| SD CS          | Pin 15               |
| SD SCK (clk)   | Pin 18 (same as TFT) |
| SD MOSI        | Pin 23 (same as TFT) |
| SD MISO        | Pin 19 (same as TFT) |

## Battery

* battery + -> 100k resistor -> ESP32 Pin 34
* battery - -> 100k resistor -> ESP32 Pin 34

## Building

### Prototype with the breadboard

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/prototype.jpg" width="400"/>

### Building mess

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_01.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_02.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_03.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_04.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_05.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_06.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_07.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_08.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_09.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_10.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_11.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_12.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_13.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_14.jpeg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_15.jpg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_16.jpeg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_17.jpeg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_18.jpeg" width="400"/>

<img src="https://github.com/e1z0/ESP32Marauder-DIY/raw/master/guide/pics/building_19.jpeg" width="400"/>

## 3D Case printing

```
Infill density: 45%
Layer height: 0,18mm
Raft: Yes
```
STL and SketchUp Files are [located here](https://github.com/e1z0/ESP32Marauder-DIY/tree/master/3d-print).

    
## Software flashing

### Prepare arduino

1. Install the [Arduino IDE](https://www.arduino.cc/en/main/software)
2. In the Arduino IDE, go to `File`>`Preferences`
3. Add the following URL to `Additional Boards Manager URLs:`
    - https://dl.espressif.com/dl/package_esp32_index.json
4. Go to `Tools`>`Board`>`Boards Manager`, search for `esp32` and install `esp32 by Espressif Systems`
5. Install Spacehuhn's [SimpleList](https://github.com/spacehuhn/SimpleList) library in your Arduino IDE
    - Download the SimpleList repo
    - In the Arduino IDE, go to `Sketch`>`Include Library`>`Add .ZIP Library...` and add the SimpleList-master.zip you just downloaded
<!---6. Install Bodmer's [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI) library in your Arduino IDE--->
6. Install Bodmer's [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI) library in your Arduino IDE
    - Download the TFT_eSPI repo
    - In the Arduino IDE, go to `Sketch`>`Include Library`>`Add .ZIP Library...` and add the TFT-eSPI-master.zip you just downloaded
7. Follow [these instructions](https://github.com/me-no-dev/arduino-esp32fs-plugin) for installing ESP32 Spiffs Tool
8. Set the compiler options in `C:\Users\<USERNAME>\AppDate\Local\Arduino15\packages\esp32\hardware\esp32\2.0.3\platform.txt` (Windows) or `/Users/<USERNAME>/Library/Arduino15/packages/esp32/hardware/esp32/2.0.5/platform.txt` (Mac), Add `-w` at the end of each line of:
    - `build.extra_flags.esp32`
    - `build.extra_flags.esp32s2`
    - `build.extra_flags.esp32s3`
    - `build.extra_flags.esp32c3`
9. Also add `-zmuldefs` to the following lines (at the end):
    - `compiler.c.elf.libs.esp32`
    - `compiler.c.elf.libs.esp32s2`
    - `compiler.c.elf.libs.esp32s3`
    - `compiler.c.elf.libs.esp32c3`
9. Install the [CH340 Drivers](https://github.com/justcallmekoko/ESP32Marauder/blob/master/Drivers/CH34x_Install_Windows_v3_4.EXE) (if you are running windows)

### Prepare code

1. Copy `User_Setup.h` from project root directory of repository to `~/Documents/Arduino/libraries/TFT_eSPI `, if you change any pins configuration you should change the definitions in this file too, as in project's `configs.h` either.
1. Download or clone this repository
2. Open `esp32_marauder/esp32_marauder.ino`
3. Plug your ESP32 into a USB port and select the COM port under `Tools`>`Port`
4. Select `LOLIN D32` under `Tools`>`Boards`
5. Select `Tools`>`Partition scheme`>`Minimal SPIFFS (Large APPS with OTA)`
6. Click `ESP32 Sketch Data Upload` and wait for the SPIFFS upload to finish
7. Click the upload button
8. When device resets, you should see boot logo on your TFT screen

For more information please read [official wiki](https://github.com/justcallmekoko/ESP32Marauder/wiki).
