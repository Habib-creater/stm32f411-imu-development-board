# STM32F411 IMU Development Board

<p align="center">
  <img src="docs/images/3d_1.png" alt="STM32F411 IMU Development Board 3D Render" width="700">
</p>

<p align="center">
  <b>STM32F411CEU6 • MPU-6050 IMU • USB • SWD • 4-Layer PCB</b>
</p>

<p align="center">
  A compact STM32F4-based development board designed for embedded systems, motion sensing, firmware development, and hardware experimentation.
</p>

---

## Overview

The **STM32F411 IMU Development Board** is a custom 4-layer embedded development platform built around the **STM32F411CEU6** microcontroller and **MPU-6050 6-axis IMU**.

The board combines a high-performance STM32F4 MCU, motion sensing, USB connectivity, regulated 3.3 V power, SWD debugging, GPIO expansion, and a carefully organized 4-layer PCB design.

The complete hardware design package is included in this repository, including the native **Altium Designer project**, schematic, PCB layout, manufacturing Gerbers, drill files, BOM, and documentation renders.

> **Design Status:** Hardware design and manufacturing outputs are included for development and evaluation. Always validate the schematic, PCB, ERC/DRC results, and manufacturing outputs before production.

---

## Key Features

| Feature | Details |
|---|---|
| **Microcontroller** | STM32F411CEU6 |
| **IMU** | MPU-6050 6-axis accelerometer + gyroscope |
| **USB** | Micro-USB connectivity |
| **Power Input** | USB 5 V |
| **Voltage Regulation** | AMS1117-3.3 |
| **Programming / Debugging** | SWD |
| **IMU Interface** | I²C |
| **Expansion** | GPIO header |
| **Reset** | NRST |
| **Boot Control** | BOOT0 |
| **Clock** | 24 MHz crystal |
| **PCB** | 4-layer PCB |
| **EDA Software** | Altium Designer |
| **Manufacturing Data** | Gerber + drill files |
| **Documentation** | Schematic, PCB renders, layer views and BOM |

---

## Board Highlights

- **STM32F411CEU6** ARM Cortex-M4 microcontroller
- **MPU-6050** 6-axis inertial measurement unit
- **4-layer PCB** for improved routing, power distribution and signal integrity
- **Micro-USB** interface for power and USB communication
- **AMS1117-3.3** voltage regulation
- Dedicated **SWD programming/debugging interface**
- **GPIO expansion header**
- **NRST and BOOT0** control
- On-board status indication
- **24 MHz crystal oscillator**
- Complete **Altium Designer source files**
- Production-ready **Gerber and drill output package**
- Exported **schematic PDF**
- Component **BOM**
- PCB layout and 3D visualization images

---

## PCB Preview

### 3D Board Render

<p align="center">
  <img src="docs/images/3d_1.png" alt="STM32F411 IMU Board 3D Render" width="700">
</p>

### PCB Layout — Top View

<p align="center">
  <img src="docs/images/STM32_layout1.png" alt="STM32F411 PCB Layout Top View" width="700">
</p>

### PCB Layer View

<p align="center">
  <img src="docs/images/STM32_layout5.png" alt="STM32F411 PCB Layer View" width="700">
</p>

Additional PCB renders and layout views are available in:

[`docs/images/`](docs/images/)

---

## Hardware Architecture

The board is organized into four primary functional blocks:

### 1. STM32F411CEU6 MCU

The STM32F411CEU6 provides the main processing and control functionality of the board.

It is responsible for:

- Application firmware
- USB communication
- IMU data processing
- GPIO control
- External peripheral interfacing
- Debugging through SWD

### 2. MPU-6050 IMU

The MPU-6050 provides:

- 3-axis accelerometer
- 3-axis gyroscope
- I²C communication

This makes the board suitable for motion sensing, orientation experiments, robotics, embedded control systems, and IMU-based applications.

### 3. USB and Power

The board accepts power through the Micro-USB connector.

The power section includes:

- USB 5 V input
- Power filtering
- 3.3 V regulation
- AMS1117-3.3 regulator

The regulated 3.3 V rail supplies the MCU, IMU and other low-voltage circuitry.

### 4. Debug and Expansion

The board provides convenient access to:

- SWD programming/debugging
- GPIO
- NRST
- BOOT0
- I²C interface

This allows the board to be used as a development and experimentation platform rather than only as a standalone embedded controller.

---

## Interfaces

| Interface | Function |
|---|---|
| **USB** | Power and USB communication |
| **SWD** | Programming and debugging |
| **I²C** | MPU-6050 communication |
| **GPIO** | External peripheral expansion |
| **NRST** | MCU reset |
| **BOOT0** | Boot mode selection |

---

## PCB Design

The board uses a **4-layer PCB stack-up** designed to provide a more structured routing environment compared with a basic 2-layer board.

The 4-layer design provides dedicated routing and power/ground planes while helping keep the MCU, IMU, USB and supporting circuitry organized.

The PCB was designed using **Altium Designer**.

### PCB Design Characteristics

- 4-layer PCB
- Digital and power routing
- Dedicated ground/power plane structure
- Compact component placement
- USB interface routing
- MCU decoupling network
- IMU interface routing
- SWD programming interface
- GPIO expansion
- Through-hole and SMD components where applicable

> The exact fabrication stack-up, dielectric thickness, copper weight and impedance requirements should be confirmed with the PCB manufacturer before fabrication.

---

# Repository Structure

```text
.
├── .github/
│   └── ISSUE_TEMPLATE/
│
├── hardware/
│   ├── altium/
│   │   ├── STM32_PCB.PrjPcb
│   │   ├── STM32_PCB.PcbDoc
│   │   ├── STM32_Schematics.SchDoc
│   │   ├── STM32_PCB.OutJob
│   │   ├── STM32_PCB.BomDoc
│   │   └── ...
│   │
│   └── cam/
│       └── ...
│
├── manufacturing/
│   └── gerbers/
│       ├── Gerber files
│       ├── Drill files
│       └── Manufacturing outputs
│
├── bom/
│   └── STM32_PCB_BOM.csv
│
├── docs/
│   ├── schematics/
│   │   └── STM32_Schematics.pdf
│   │
│   └── images/
│       ├── 3d_1.png
│       ├── 3d_2.png
│       ├── 3d_3.png
│       ├── STM32_layout1.png
│       ├── STM32_layout2.png
│       ├── STM32_layout3.png
│       ├── STM32_layout4.png
│       └── STM32_layout5.png
│
├── .gitignore
├── CONTRIBUTING.md
└── README.md
