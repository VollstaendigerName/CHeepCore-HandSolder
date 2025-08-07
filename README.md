# CHeepCore-HandSolder
CHeepCore in a variant with larger footprints and TSSOP package for easier hand soldering.
A minimalist, ultra-low-cost RISC-V development board based on the CH32V003 series. Designed for embedded hobbyists, students, and low-cost prototyping.

<img src="https://github.com/VollstaendigerName/CHeepCore-HandSolder/blob/main/Images/Cheep.png" alt="CHeepCore Logo" width="300" height="300" />

---

## Project Information

- **Name:** CHeepCore-HandSolder  
- **Revision:** 0.0.1b  
- **Date:** 2025-08-06  
- **KiCad Version:** 9.0.3  
- **Target Audience:** Embedded hobbyists, students, low-cost prototyping  
- **Cost Goal:** Complete microcontroller board for under 0.50€  

---

## Key Features

- CH32V003F4U6 32-bit RISC-V microcontroller (20-pin QFN)  
- 16 GPIOs exposed on 2.54 mm headers (PC0–PC7, PD0–PD7)  
- External 24 MHz crystal with 22 pF load capacitors  
- USB-C power input (VBUS → 3.3 V LDO)  
- Configurable solder jumpers for:  
  - USB-VBUS disconnect  
  - 3.3 V / 5 V MCU supply  
- SWD/JTAG programming connectors (3-pin & 10-pin, WCH-LinkE compatible)  
- Breadboard-compatible PCB outline (18.288 × 32.004 mm)  

<img src="https://github.com/VollstaendigerName/CHeepCore-HandSolder/blob/main/Images/Screenshot%202025-08-07%20172010.png" alt="CHeepCore front" width="400" height="300" />

---

## Power Configuration

1. **USB-C Supply**  
   VBUS (5 V) feeds on-board LDO → 3.3 V rail  

2. **External Supply**  
   - Cut the USB-disconnect jumper (bottom side) to isolate VBUS  
   - Inject external 5 V or 3.3 V via header  

3. **MCU Voltage Selection**  
   - Default: 3.3 V  
   - For 5 V operation, cut the 3.3 V jumper (bottom side) and bridge the center pad to 5 V  

<img src="https://github.com/VollstaendigerName/CHeepCore-HandSolder/blob/main/Images/Screenshot%202025-08-07%20172043.png" alt="CHeepCore back" width="400" height="300" />

---

## Programming with WCH-LinkE

- Connect **3V3** and **GND** pins  
- Connect **SWDIO/TMS** to the middle pin of the 3-pin header  
- SWCLK/TCK and reset lines available on 10-pin header for full JTAG  

---

## Mechanical Dimensions

- **Width:** 29.489 mm  
- **Height:** 18.288 mm  
- Compatible with standard 2.54 mm breadboards  

---

## GPIO Pinout

| #   | Header Pin | Default Function            | Alternate Function                 |
| --- | ---------- | --------------------------- | ---------------------------------- |
| 0   | PD0        | T1CH1N / OPN1               | SDA / UTX                          |
| 1   | PD1        | SWIO / AETR2                | T1CH3N / SCL / URX                 |
| 2   | PD2        | A3 / T1CH1 / T2CH3          | T1CH2N                             |
| 3   | PD3        | A4 / T2CH2 / AETR           | UCTS / T1CH4                       |
| 4   | PD4        | A7 / UCK / T2CH1ETR         | OPO / T1CH4ETR                     |
| 5   | PD5        | A5 / UTX                    | T2CH4 / URX                        |
| 6   | PD6        | A6 / URX                    | T2CH3 / UTX                        |
| 7   | PD7        | NRST / T2CH4                | OPP1 / UCK                         |
| 8   | PC7        | MISO / T1CH2                | T2CH2 / URTS                       |
| 9   | PC6        | MOSI / T1CH1CH3N            | UCTS / SDA                         |
| 10  | PC5        | SCK / T1ETR / T2CH1ETR      | SCL / UCK / T1CH3                  |
| 11  | PC4        | A2 / T1CH4 / MCO            | T1CH1CH2N                          |
| 12  | PC3        | T1CH3 / T1CHIN              | UCTS                               |
| 13  | PC2        | SCL / URTS / T1BKIN         | AETR / T2CH2 / T1ETR               |
| 14  | PC1        | SDA / NSS / T2CH4           | T2CH1ETR / T1BKIN / URX            |
| 15  | PC0        | T2CH3 / UTX                 | NSS / T1CH3                        |

---
## Bill of Material (BoM)

| Reference     | Qty | Unit Price (€) | Description                                     |
|---------------|:---:|---------------:|-------------------------------------------------|
| C101          |  1  |        0.0020  | YAGEO CC0603KRX7R7BB104 (100 nF, 0603)          |
| C102, C103    |  2  |        0.0016  | YAGEO CC0603JRNPO9BN220 (22 pF, 0603)           |
| C301, C302    |  2  |        0.0033  | Samsung CL10A105KB8NNNC (1 µF, 0603)            |
| J301          |  1  |        0.0300  | SHOU HAN TYPE-C 16-PIN 2MD(073)                 |
| R301, R302    |  2  |        0.0004  | VO SCR0603J5K1 (5.1 kΩ, 0603)                   |
| U101          |  1  |        0.1349  | CH32V003F4P6 (32-bit RISC-V microcontroller)     |
| U301          |  1  |        0.0047  | Megain MG6206K3B-33 (3.3 V LDO)                  |
| Y101          |  1  |        0.0323  | TOGNJING XTM32024000DT00351001 (24 MHz crystal) |


---

## Author & License

   VollständigerName  GitHub: https://github.com/VollstaendigerName

   <small><span style="color:lightgrey;">
   This work is licensed under Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0). See LICENSE.txt for details.

   This hardware specification and documentation have been prepared to the best of the author’s knowledge, but are provided without any warranty. The author accepts no liability for malfunctions, consequential damages, or any claims arising from the use of this information, the design, or the implemented hardware. Any liability is expressly excluded.
   </span></small>

## Repository Contents

```text
/
├── CHeepCore/       # KiCad schematic and PCB files
├── Images/          # Images of the 3d Model
├── production/      # Gerber export for fabrication   
├── README.md        # This file  
└── LICENSE.txt      # CC BY-NC 4.0  
