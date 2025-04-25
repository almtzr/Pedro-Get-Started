# Pedro Get Started

<div align="center">
    <img src="img/pedro_kickstarter.png" width="50%">
</div> 

<br>

Welcome to the world of Pedro, the open-source robotics platform designed to make learning robotics, programming, and embedded electronics fun and accessible! Whether you’ve purchased a preassembled Pedro or you're building your own, here’s everything you need to get started. <br>
Whether you buy **a pre-assembled Pedro**, or **a full DIY kit**, or **a Pedro Board** it comes with the [**pedroDirectMode.ino**](https://github.com/almtzr/Pedro/tree/main/code/directMode) firmware already flashed. You can control it in **Direct Mode** using the button A0 to select an axis and the buttons A1 and A2 to rotate it.

<div align="left">
    <img src="img/pedro_direct_mode.gif" width="50%">
</div>

### How To Control Your Pedro In Direct Mode ?

1- Turn on the robot using the ON/OFF button on the board. <br>
2- Use button A0 to select the part of the robot you want to control. <br>
3- Once selected, press A1 or A2 to move the chosen part. <br>
(The selection order (from bottom to top) is: Base -> Shoulder -> Elbow -> Gripper)

<div align="left">
    <img src="img/pedro_parts.png" width="30%">
</div>

### Explore More Control Modes

Pedro also supports control modes: 
- Radio (NRF24L01)
- Bluetooth (HC-05)
- and Wi-Fi (ESP8266-01)

The code for each mode is available on the [Pedro GitHub page](https://github.com/almtzr/Pedro/tree/main/code). <br>
Feel free to customize the code to match your needs and make Pedro truly yours! 🚀

<div align="left">
    <img src="img/bluetooth_mode.gif" width="60%">
</div>

### Programming Pedro

- Download [Arduino IDE](https://www.arduino.cc/en/software)
- Install the required libraries: Servo, Wire, Adafruit GFX, Adafruit SSD1306
- Connect the Pedro Board to the PC
- Select Arduino Pro Micro (ATmega32U4) as the target board
- Upload your custom sketch to the Pedro Board or one of the sketch available on the [Pedro Github Page](https://github.com/almtzr/Pedro/tree/main/code/basic)
---

## ✅ 1. If You Purchased a Pre-Assembled Pedro

When you buy a pre-assembled Pedro, it comes with the pedroDirectMode.ino firmware already flashed. That means your robot is ready to use, plug & play. No setup required!

## ✅ 2. If You Purchased A Pedro Full Kit

With the Pedro Full DIY Kit, you get all the necessary components to build the robot, including electronics and 3D-printed parts. You can go straight to the section **5. Assembling Pedro**.

<div align="left">
    <img src="img/pedro_3d_print_parts.png" width="70%">
</div>

## ✅ 3. If You Purchased A Pedro Board Only

🛠️ To complete your robot, you’ll need:

<div align="left">
    <img src="img/pedro_print.png" width="70%">
</div>

- To print all the Pedro parts (STL files availables on [Pedro GitHub Page](https://github.com/almtzr/Pedro/tree/main/stl))
- 2 ball bearings 8 x 22 x 7 mm
- 7.4V DC battery with 2 pins JST XH2.54 connector
- 4x MS90 360° servo motors (not 180°)
- Micro USB cable
- (Options) Modules: NRF24L01 (Radio), HC-05 (Bluetooth), ESP8266-01 (WiFi), Screen OLED 128x64 0.96"

And then go to the section **5. Assembling Pedro**.

## ✅ 4. If You Are Building Pedro From Scratch (Board Rev2 Only):

Want to build Pedro from scratch? You can make your own Pedro Board by using Gerber files allows for the Rev2 board on the Pedro Github page. <br>
When you get your own PCB board, the microcontroller ATmega32u4 doesn’t have the correct bootloader yet, it's delivered with the factory bootloader. To make Pedro work with Arduino IDE, you first need to flash the Arduino Pro Micro bootloader into the Pedro board using the SPI pins as described below.

### How To Flash the Bootloader on the microcontroller ATmega32u4 ?
(**This step is only necessary if you made your own Pedro board from [Gerber file](https://github.com/almtzr/Pedro/tree/main/gerber), otherwise skip it.**)

🛠️ What You Need:

- Your Pedro board (of course)
- PC with Arduino IDE installed
- An Arduino Pro Micro
- A Micro USB cable
- Some wires

📌 How to do it?:

- Open Arduino IDE
- Connect the Arduino Pro Micro to the PC
- Select Arduino Pro Micro (ATmega32U4) as the target board
- Upload the "File" -> "Exemple" -> "Arduino as ISP" sketch to the Arduino Pro Micro
- When the upload is done disconnect the Arduino Pro Micro from the PC
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

🎯 Once done, disconnect the SPI wiring, plug the Pedro board to the PC and check in "Tools > Port" to ensure the board is recognized by Arduino IDE.

<div align="left">
    <img src="img/pedro_bootloader_wiring.png" width="80%">
</div>

## ⚙️ 5. Assembling Pedro

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

## 6. Resources & Community

🔍 Full Documentation → Pedro GitHub page <br>
🚀 Need help or want to improve Pedro? → Open an issue on GitHub or come to discuss with us on the [Pedro Discord](https://discord.gg/TxkWNPU3ES)

Pedro is 100% open-source, meaning you’re free to explore, modify, and share your own improvements!

🎉 Have fun & keep building awesome robots! 🤖

---

This version keeps the content engaging, easy to read, and informative. Let me know if you need any adjustments! 🚀

## 7. Mapping Pedro Board & Arduino

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

