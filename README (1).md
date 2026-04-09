# 🎛️ RP2040 Custom Development Board

<div align="center">

![PCB Version](https://img.shields.io/badge/PCB-v1.0-blue?style=for-the-badge)
![MCU](https://img.shields.io/badge/MCU-RP2040-red?style=for-the-badge&logo=raspberrypi&logoColor=white)
![EDA](https://img.shields.io/badge/EDA-EasyEDA-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

<br/>

> **A fully custom-designed Raspberry Pi RP2040 development board** — built from scratch with onboard flash, USB-C, SWD debug header, and a full GPIO breakout. Designed to be compact, breadboard-friendly, and maker-ready.

</div>

---

## 📸 Project Gallery

<div align="center">

<table>
  <tr>
    <td align="center"><b>🗺️ PCB Layout</b></td>
    <td align="center"><b>🔭 3D Top View</b></td>
  </tr>
  <tr>
    <td><img src="PCB_Layout.JPG" alt="PCB Layout" width="420"/></td>
    <td><img src="3D_Top_View.JPG" alt="3D Top View" width="420"/></td>
  </tr>
  <tr>
    <td align="center"><b>📐 3D Perspective</b></td>
    <td align="center"><b>📦 Enclosure View</b></td>
  </tr>
  <tr>
    <td><img src="3D_Perspective.JPG" alt="3D Perspective" width="420"/></td>
    <td><img src="Enclosure_View.JPG" alt="Enclosure View" width="420"/></td>
  </tr>
</table>

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Hardware Specifications](#-hardware-specifications)
- [Pin Mapping](#-pin-mapping)
- [Schematic & PCB](#-schematic--pcb)
- [Bill of Materials (BOM)](#-bill-of-materials-bom)
- [Getting Started](#-getting-started)
- [Programming the Board](#-programming-the-board)
- [Project Files](#-project-files)
- [3D Model & Enclosure](#-3d-model--enclosure)
- [Contributing](#-contributing)
- [Author](#-author)
- [License](#-license)

---

## 🔍 Overview

This project is a **custom-designed development board** centered around the **Raspberry Pi RP2040** dual-core ARM Cortex-M0+ microcontroller. It was designed entirely from scratch — from schematic to PCB layout — using **EasyEDA**, with a focus on:

- Clean power delivery with proper decoupling
- Full GPIO breakout with double-row headers
- USB-C for power and programming
- Onboard SWD debug interface
- Compact, professional form factor with optional 3D-printed enclosure

---

## ✨ Features

- ⚡ **RP2040** — Dual-core ARM Cortex-M0+ @ up to 133 MHz
- 🔌 **USB-C Connector** — For power input and UF2 firmware flashing
- 💾 **Onboard Flash** — SOIC-8 NOR Flash (W25Q16 or compatible) for program storage
- 🔋 **3.3V LDO Regulator** — Clean, stable 3.3V rail (SOT-23-4P package)
- 🧩 **Full GPIO Breakout** — All 29 GPIOs exposed via dual-row 2.54mm pin headers
- 🛠️ **SWD Debug Header** — 3-pin SWD (SWCLK, SWDIO, GND) for OpenOCD / Picoprobe
- 🔄 **BOOTSEL & RUN Buttons** — For easy firmware flashing and reset
- 🌀 **Crystal Oscillator** — Onboard 12 MHz crystal for accurate USB & clock timing
- 📐 **3D-Printable Enclosure** — Matching shell designed in 3D (STEP file included)
- 🏷️ **Silkscreen Labels** — Clear GPIO numbering and power rail markings

---

## 🔧 Hardware Specifications

| Parameter | Value |
|---|---|
| Microcontroller | Raspberry Pi RP2040 |
| CPU | Dual-core ARM Cortex-M0+ |
| Clock Speed | Up to 133 MHz |
| SRAM | 264 KB |
| Flash | External SPI NOR Flash (SOIC-8) |
| Supply Voltage | 5V via USB-C |
| I/O Voltage | 3.3V |
| GPIO Count | 29 (all broken out) |
| USB | USB 1.1 Full-speed (via USB-C) |
| Debug Interface | SWD (3-pin header) |
| Crystal | 12 MHz |
| PCB Layers | 2-Layer |
| PCB Dimensions | ~56mm × 42mm (approx.) |
| PCB Color | Blue |
| Header Pitch | 2.54mm |

---

## 📌 Pin Mapping

### Top Header (H4) — GPIOs 16–28 + GND

| Pin | Function |
|-----|----------|
| GND | Ground |
| 16  | GPIO16 |
| 17  | GPIO17 |
| 18  | GPIO18 |
| 19  | GPIO19 |
| 20  | GPIO20 |
| 21  | GPIO21 |
| 22  | GPIO22 |
| 23  | GPIO23 |
| 24  | GPIO24 |
| 25  | GPIO25 |
| 26  | GPIO26 (ADC0) |
| 27  | GPIO27 (ADC1) |
| 28  | GPIO28 (ADC2) |

### Bottom Header (H2) — GPIOs 0–15 + 3.3V + GND

| Pin | Function |
|-----|----------|
| 3.3V | Power Output |
| 0   | GPIO0 (UART0 TX / I2C0 SDA) |
| 1   | GPIO1 (UART0 RX / I2C0 SCL) |
| 2   | GPIO2 (SPI0 SCK / I2C1 SDA) |
| 3   | GPIO3 (SPI0 TX / I2C1 SCL) |
| 4   | GPIO4 (SPI0 RX) |
| 5   | GPIO5 (SPI0 CS) |
| 6   | GPIO6 |
| 7   | GPIO7 |
| 8   | GPIO8 |
| 9   | GPIO9 |
| 10  | GPIO10 |
| 11  | GPIO11 |
| 12  | GPIO12 |
| 13  | GPIO13 |
| 14  | GPIO14 |
| 15  | GPIO15 |
| GND | Ground |

### Debug Header (H5 / H6)

| Pin | Function |
|-----|----------|
| SWCLK | Serial Wire Clock |
| SWDIO | Serial Wire Data |
| GND  | Ground |
| RUN  | Reset (active low) |

---

## 📁 Schematic & PCB

The board was designed using **EasyEDA** (LCEDA). Design files are included in the repository:

```
├── Gerber_PCB1_RP2040/       # Gerber files for PCB fabrication
│   ├── Gerber_TopLayer.gbr
│   ├── Gerber_BottomLayer.gbr
│   ├── Gerber_BoardOutline.gbr
│   ├── Gerber_TopSilkLayer.gbr
│   └── ...
├── PickAndPlace_PCB1_        # Pick and place file for SMT assembly
├── BOM_RP2040_Dev_Board_PCB1 # Bill of Materials (Excel)
└── 3D_step_file.step         # 3D STEP model of the board
```

### 📦 Ordering PCBs

Upload the `Gerber_PCB1_RP2040.zip` to any PCB manufacturer:
- [JLCPCB](https://jlcpcb.com) *(recommended)*
- [PCBWay](https://pcbway.com)
- [OSH Park](https://oshpark.com)

**Recommended fabrication settings:**
| Setting | Value |
|---------|-------|
| Layers | 2 |
| Thickness | 1.6mm |
| Surface Finish | HASL (LeadFree) |
| Copper Weight | 1 oz |
| Color | Blue |

---

## 🧾 Bill of Materials (BOM)

> Full BOM is in `BOM_RP2040_Dev_Board_PCB1.xlsx`

| Ref | Component | Package | Value / Part No. |
|-----|-----------|---------|-----------------|
| U2  | RP2040 | QFN-56 | Raspberry Pi RP2040 |
| U3  | USB-C Connector | SMD | USB Type-C Receptacle |
| U4  | LDO Regulator | SOT-23-4P | e.g. ME6206 / XC6206 3.3V |
| U5  | Flash Memory | SOIC-8 | W25Q16JVSSIQ (2MB) |
| U6  | Crystal | SMD | 12 MHz Crystal |
| H1  | Header 1×2 | 2.54mm THT | Power/GND Breakout |
| H2  | Header 2×20 | 2.54mm THT | Bottom GPIO |
| H4  | Header 2×(n) | 2.54mm THT | Top GPIO |
| H5/H6 | Header 1×4 | 2.54mm THT | SWD Debug |
| C1–C16 | Decoupling Caps | 0402/0603 | 100nF / 10µF |
| R1–R7 | Resistors | 0402 | Various (1kΩ, 27Ω, etc.) |

---

## 🚀 Getting Started

### Prerequisites

- Soldering iron + solder
- PCB (ordered from Gerber files)
- All BOM components
- USB-C cable
- PC with [Raspberry Pi Pico SDK](https://github.com/raspberrypi/pico-sdk) or [MicroPython](https://micropython.org/download/rp2-pico/)

### Assembly Steps

1. **Solder SMD components first** — Start with ICs (U2 RP2040, U4, U5), then passives (capacitors, resistors)
2. **Solder the crystal** (U6) and USB-C connector (U3)
3. **Solder through-hole headers** last (H2, H4, H1, H5, H6)
4. **Inspect** all joints under magnification
5. **Power up** via USB-C and check 3.3V rail before connecting peripherals

---

## 💻 Programming the Board

### Method 1: UF2 Drag-and-Drop (Easiest)

1. Hold **BOOTSEL** button and plug in USB-C
2. The board appears as a mass storage device (`RPI-RP2`)
3. Drag and drop your `.uf2` firmware file
4. The board resets and runs your firmware

### Method 2: MicroPython

1. Download [MicroPython UF2 for RP2040](https://micropython.org/download/rp2-pico/)
2. Flash via UF2 method above
3. Use Thonny IDE or any serial terminal to interact

### Method 3: C/C++ SDK

```bash
# Install Pico SDK
git clone https://github.com/raspberrypi/pico-sdk
cd pico-sdk && git submodule update --init

# Build a project
mkdir build && cd build
cmake -DPICO_SDK_PATH=../../pico-sdk ..
make -j4
```

### Method 4: SWD Debug (OpenOCD)

Connect a Picoprobe or J-Link to the SWD header (H5/H6):

```bash
openocd -f interface/picoprobe.cfg -f target/rp2040.cfg
```

---

## 📂 Project Files

```
RP2040-Dev-Board/
│
├── 📁 Gerber_PCB1_RP2040/          # Gerber files for fabrication
├── 📄 BOM_RP2040_Dev_Board_PCB1.xlsx  # Bill of Materials
├── 📄 PickAndPlace_PCB1_.csv        # Pick & Place file for SMT
├── 📄 3D_step_file.step             # 3D STEP model
├── 📁 3DShell_PCB1/                 # 3D printable enclosure files
├── 🖼️  FW.JPG                        # PCB layout render
├── 🖼️  SW.JPG                        # 3D perspective render
├── 🖼️  TW.JPG                        # 3D top view render
├── 🖼️  SSV.JPG                       # Enclosure 3D view
└── 📄 README.md                     # This file
```

---

## 🏠 3D Model & Enclosure

A matching **3D-printed enclosure** was designed for this board. The shell exposes:
- USB-C port on the left side
- SWD/RUN header on the right side
- All GPIO pins through the top

**Files:** `3DShell_PCB1/` and `3D_step_file.step`

Print with **PLA or PETG**, 0.2mm layer height, 20% infill recommended.

---

## 🤝 Contributing

Contributions, issues and feature requests are welcome!

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/my-improvement`
3. Commit your changes: `git commit -m 'Add some improvement'`
4. Push to the branch: `git push origin feature/my-improvement`
5. Open a Pull Request

---

## 👨‍🎓 Author

<div align="center">

### Mohit Jagtap

**Electronics & Telecommunication Engineering**  
Dr. D. Y. Patil Institute of Engineering Management and Research  
Akurdi, Pune

[![Portfolio](https://img.shields.io/badge/Portfolio-mohitjagtap.netlify.app-blue?style=for-the-badge&logo=netlify)](https://mohitjagtap.netlify.app/)
[![GitHub](https://img.shields.io/badge/GitHub-itsmemohitjagtap-black?style=for-the-badge&logo=github)](https://github.com/itsmemohitjagtap)

</div>

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Mohit Jagtap

Permission is hereby granted, free of charge, to any person obtaining a copy
of this hardware design and associated documentation files, to use, copy, modify,
merge, distribute, sublicense, and/or sell copies of the design, subject to the
following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the design.
```

---

<div align="center">

**⭐ If this project helped you, please consider giving it a star! ⭐**

Made with ❤️ in Pune, India 🇮🇳

</div>
