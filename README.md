# Pedro Get Started

Welcome to the world of Pedro, the open-source robotics platform designed to make learning robotics, programming, and embedded electronics fun and accessible! Whether you’ve purchased a preassembled Pedro or you're building your own, here’s everything you need to get started.

<div align="center">
    <img src="img/pedro_kickstarter.png" width="80%">
</div>

---

## ✅ If You Purchased a Pre-Assembled Pedro:

When you buy a pre-assembled Pedro, it comes with the Pedro_Basic firmware already flashed. That means your robot is ready to use, plug & play. No setup required!

### Getting Started with Pedro

1- Turn on the robot using the ON/OFF button.

2- Use button A0 to select the part of the robot you want to control. The selection order (from bottom to top) is: Base -> Shoulder -> Elbow -> Gripper

3- Once selected, press A1 or A2 to move the chosen part.

<div align="left">
    <img src="img/pedro_parts.png" width="50%">
</div>

### Explore More Control Modes

Pedro also supports Radio, Bluetooth, and Wi-Fi control. The code for each mode is available on the Pedro GitHub page. Feel free to customize the code to match your needs and make Pedro truly yours! 🚀

<div align="left">
    <img src="img/dual-mode.gif" width="80%">
</div>

## ✅ If You Purchased a Pedro Full Kit or Are Building Pedro from scratch:

<div align="left">
    <img src="img/pedro_3d_print_parts.png" width="70%">
</div>

<br>

🛠️ What You Need:

- 3D-printed parts (STL files availables on [Pedro GitHub Page](https://github.com/almtzr/Pedro/tree/main/stl/kickstarter_version))
- Pedro Rev2 or Rev3 PCB (Gerber files available on [Pedro GitHub Page](https://github.com/almtzr/Pedro/tree/main/gerber))
- Servo motors (MG90S 360° not 180°)
- 7.4V DC Battery & charger
- Modules: NRF24L01, OLED 128x64, ESP8266-01 (only Rev3), Bluetooth HC-05 (only Rev3)
- Micro USB cable
- A PC with Arduino IDE installed

---

## 1. Programming the Pedro board

### Install Required Software

- Download [Arduino IDE](https://www.arduino.cc/en/software)
- Install the required libraries: Servo, Wire, Adafruit GFX, Adafruit SSD1306

### Flash the Bootloader on the microcontroller ATmega32u4 
(**This step is only necessary if you made the your own Pedro board from [Gerber file](https://github.com/almtzr/Pedro/tree/main/gerber), otherwise skip it.**)

If you built your own PCB, the microcontroller ATmega32u4 doesn’t have the correct bootloader yet, it's delivered with the factory bootloader. To make Pedro work with Arduino IDE, you first need to flash the Arduino Pro Micro bootloader into the Pedro board using the SPI pins.

🛠️ What You Need:

- your Pedro board (of course)
- an Arduino Pro Micro
- a Micro USB cable
- some wires

📌 How to do it?:

- Open Arduino IDE
- Connect the Arduino Pro Micro to the PC
- Upload the "Arduino as ISP" sketch to the Arduino Pro Micro
- Disconnect the Arduino Pro Micro from the PC
- Connect the SPI pins of the Pedro board to the Arduino Pro Micro as shown:
    - Pedro Board => Arduino Pro Micro
    - GND         =>      GND (black)
    - VCC         =>      VCC (red)
    - SCK         =>      15 (orange)
    - MI          =>      14 (purple)
    - MO          =>      16 (green)
    - RST         =>      10 (yellow)
- Re-Connect the Arduino Pro Micro to the PC
- Select Arduino Pro Micro (ATmega32U4) as the target board
- Go to Tools > Burn Bootloader

<div align="left">
    <img src="img/pedro_bootloader_wiring.png" width="80%">
</div>

🎯 Once done, disconnect the SPI wiring, plug the Pedro board to the PC and check in "Tools > Port" to ensure the board is recognized by Arduino IDE.

### Programming Board
 
- Download the code pedro_basic.ino from the [Pedro Github Page](https://github.com/almtzr/Pedro/tree/main/code/basic)
- Connect the Pedro Board to the PC
- Select Arduino Pro Micro (ATmega32U4) as the target board
- Upload the "pedro_basic.ino" sketch to the Pedro Board

## ⚙️ 2. Assembling Pedro

(If you have a preassembled Pedro, skip to Step 2)

| ![Pedro 1](img/pedro_how_to_build_1.png) | ![Pedro 2](img/pedro_how_to_build_2.png) |
|---------------------------------------|---------------------------------------|

| ![Pedro 3](img/pedro_how_to_build_3.gif)  | ![Pedro 4](img/pedro_how_to_build_4.png) |
|---------------------------------------|---------------------------------------|

| ![Pedro 5](img/pedro_how_to_build_5.png) | ![Pedro 6](img/pedro_how_to_build_6.png) | 
|---------------------------------------|---------------------------------------|

| ![Pedro 7](img/pedro_how_to_build_7.png) | ![Pedro 8](img/pedro_how_to_build_8.png) | 
|---------------------------------------|---------------------------------------|

| ![Pedro 9](img/pedro_how_to_build_9.png) | ![Pedro 10](img/pedro_how_to_build_10.png) |
|---------------------------------------|---------------------------------------|

| ![Pedro 11](img/pedro_how_to_build_11.png) | ![Pedro 12](img/pedro_how_to_build_12.png) |
|---------------------------------------|---------------------------------------|

| ![Pedro 11](img/pedro_how_to_build_13.png) | ![Pedro 12](img/pedro_how_to_build_14.png) |
|---------------------------------------|---------------------------------------|

<div align="center">
    <img src="img/pedro_how_to_build_15.png" width="50%">
</div>

## 3. Control Modes

Pedro can be controlled in three different ways:

- WiFi (ESP8266-01) – Control Pedro via a web or mobile app
- Bluetooth (HC-05) – Use an Android/iOS app
- Radio (NRF24L01) – Connect Pedro to another microcontroller

📌 Examples and code available on the [Pedro GitHub Page](https://github.com/almtzr/Pedro/tree/main/code)

<div align="center">
    <img src="img/bluetooth_mode.gif" width="60%">
</div>


## 4. Resources & Community

🔍 Full Documentation → Pedro GitHub
🚀 Need help or want to improve Pedro? → Open an issue on GitHub

Pedro is 100% open-source, meaning you’re free to explore, modify, and share your own improvements!

🎉 Have fun & keep building awesome robots! 🤖

---

This version keeps the content engaging, easy to read, and informative. Let me know if you need any adjustments! 🚀

## Mapping Pedro Board & Arduino

| Pedro Board         | Arduino Pin | Function                  |
|---------------------|-------------|---------------------------|
| Servo 1             | D5          | PWM Signal                |
| Servo 2             | D6          | PWM Signal                |
| Servo 3             | D9          | PWM Signal                |
| Servo 4             | D10         | PWM Signal                |
| Button 1  (Up)      | A0          | Select Servo              |
| Button 2 (Right)    | A1          | Servo Rotation (forward)  |
| Button 3 (Left)     | A2          | Servo Rotation (backward) |
| LED Servo 1         | D13         | Servo 1 Indicator         |
| LED Servo 2         | D11         | Servo 2 Indicator         |
| LED Servo 3         | D8          | Servo 3 Indicator         |
| LED Servo 4         | D7          | Servo 4 Indicator         |
| NRF24L01 CE         | D4          | SPI Enable (Radio)        |
| NRF24L01 CSN        | D12         | SPI Chip Select (Radio)   |
| OLED Display (SDA)  | D2          | I2C Data                  |
| OLED Display (SCL)  | D3          | I2C Clock                 |
| HC-05 TX (Rev3 Only)| D0          | UART RX (Bluetooth)       |
| HC-05 RX (Rev3 Only)| D1          | UART TX (Bluetooth)       |
| ESP8266 TX (Rev3 Only)| D0        | UART RX (WiFi)            |
| ESP8266 RX (Rev3 Only)| D1        | UART TX (WiFi)            |
| Switch 1 (Middle)   | N/A         | Select Mode Radio, Bluetooth, WiFi |
| Switch 2 (Left)     | N/A         | Select Mode AT (HC-05)    |
| Pin A3              | A3          | Free                      |
| Pin A4              | A4          | Free                      |
| Pin A5              | A5          | Free                      |
| Pin RX              | RX          | Free                      |
| Pin TX              | TX          | Free                      |

---
