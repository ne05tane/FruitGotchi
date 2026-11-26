# FruitGotchi

Tamagotchi Style digital pet. It runs on an ESP32-C3 with a 0.69"  OLED display, has three tactile buttons, and a piezo buzzer. 
Two (or more) units can "meet" over 2.4 GHz RF with no router needed.

<img width="820" height="605" alt="3D_PCB_TopView" src="https://github.com/user-attachments/assets/856b4c3f-d5f5-4811-8e39-f24835bb9462" />
<img width="2160" height="1932" alt="3D_PCB_BottomView" src="https://github.com/user-attachments/assets/26743890-6fe4-44b4-9ce9-60c99314806a" />


## Why I made this

Cause it sounded fun to make :/ 
<br><br>
I also initially planned to build this for a friend. The pets are fruits and each one has a representative fruit that they'd have to take care of similarly
to the original toy. However I wanted an "off-button", basically the MCU goes into sleep mode so you could turn it off whenever you wanted to. Therefore, 
my choice of microcontroller was naturally ESP-32.

There's also an advantage to it being in deep sleep because device to device linking is done through Wi-fi Radio, specifically the ESP-NOW Protocol which 
draws more power than an IR LED Pulse (Originally, connectivity was done through Infrared). You could keep the pet in deep sleep most times and only wake the radio 
to feed, play and check for peers periodically. 

PS. I haven't thought of firmware or how the whole thing operates in particular (what "needs" the pet can have, which fucntion goes to which button etc)


## PCB 

<img width="280" height="341" alt="PCB_Design" src="https://github.com/user-attachments/assets/8f84a2b5-1dae-4bde-b54b-7bbb1774ac19" />

## Wiring

<img width="822" height="451" alt="PCB_Schematic" src="https://github.com/user-attachments/assets/08899fb8-3dce-4e72-bece-80514793f372" />

## BOM

| No. | Quantity | Comment            | Designator  | Footprint                             | Value | Manufacturer Part  | Manufacturer   | Supplier Part | Supplier | LCSC Stock | JLCPCB Stock | JLCPCB Price | Layer | Mounting Style |
|-----|----------|--------------------|-------------|---------------------------------------|-------|--------------------|----------------|---------------|----------|------------|--------------|--------------|-------|----------------|
| 1   | 1        | 4kHz               | BUZZER1     | BUZ-TH_BD12.5-P6.50-D1.4              | 4kHz  | 1207-P6.5MM        | XHXDZ(兴华鑫)     | C49246964     | LCSC     |            | 3079         | 0.0049       | T     | DIP            |
| 2   | 1        | 1uF                | C1          | C0402                                 | 1uF   | CL05A105KP5NNNC    | SAMSUNG(三星)    | C14445        | LCSC     |            | 8156019      | 0.0005       | T     | SMT            |
| 3   | 1        | B2B-PH-K-S(LF)(SN) | CN1         | CONN-TH_B2B-PH-K-S                    |       | B2B-PH-K-S(LF)(SN) | JST            | C131337       | LCSC     |            | 331429       | 0.005        | T     | DIP            |
| 4   | 2        | 5.1kΩ              | R1,R2       | RES-TH_BD4.5-L11.5-P15.50-D0.7        | 5.1kΩ | MF1W-5.1KΩ±1%T     | 华星机电           | C714111       | LCSC     |            | 522          | 0.0059       | T     | DIP            |
| 5   | 2        | 10kΩ               | R3,R5       | R0402                                 | 10kΩ  | FRC0402F1002TS     | FOJAN(富捷)      | C2906861      | LCSC     |            | 39439841     | 0.0002       | T     | SMT            |
| 6   | 4        | 4.7kΩ              | R4,R6,R7,R8 | R0805                                 | 4.7kΩ | FRC0805J472 TS     | FOJAN(富捷)      | C2907326      | LCSC     |            | 2871719      | 0.0004       | T     | SMT            |
| 7   | 3        | TS-1088-AR02016    | SW1,SW2,SW3 | SW-SMD_L3.9-W3.0-P4.45                |       | TS-1088-AR02016    | XUNPU(讯普)      | C720477       | LCSC     |            | 711343       | 0.0076       | T     | SMT            |
| 8   | 1        | ESP32-C3-MINI-1-N4 | U3          | WIFIM-SMD_ESP32-C3-MINI-1             |       | ESP32-C3-MINI-1-N4 | ESPRESSIF(乐鑫)  | C2838502      | LCSC     |            | 22784        | 0.4701       | T     | SMT            |
| 9   | 1        | TP4054             | U4          | SOT-23-5_L2.9-W1.6-P0.95-LS2.8-BR     |       | TP4054             | JSMSEMI(杰盛微)   | C5381776      | LCSC     |            | 310460       | 0.0033       | T     | SMT            |
| 10  | 1        | XC6206-3.3V        | U5          | SOT-23-3_L2.9-W1.3-P0.95-LS2.4-BR     |       | XC6206-3.3V        | YONGYUTAI(永裕泰) | C3015484      | LCSC     |            | 30200        | 0.0046       | T     | SMT            |
| 11  | 1        | HS96L03W2C03       | U6          | OLED-TH_L27.8-W27.2-P2.54_C9900033791 |       | HS96L03W2C03       | HS(汉昇)         | C5248080      | LCSC     |            | 2115         | 0.332        | T     | DIP            |
| 12  | 1        | GT-USB-7010ASV     | U7          | USB-C-SMD_G-SWITCH_GT-USB-7010ASV     |       | GT-USB-7010ASV     | G-Switch(品赞)   | C2988369      | LCSC     |            | 37863        | 0.0126       | T     | DIP            |

## License - 

This project is released under the [MIT License](LICENSE). Use it, fork it, sell it, do whatever you want
