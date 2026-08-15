# STM32F411 IMU Development Board

<p align="center">
  <img src="docs/images/3d_1.png" alt="STM32F411 IMU Development Board" width="750">
</p>

<p align="center">
  A compact 4-layer STM32F411 development board featuring an MPU-6050 6-axis IMU, USB connectivity, SWD debugging, GPIO expansion, and regulated 3.3 V power.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/MCU-STM32F411CEU6-blue" alt="STM32F411CEU6">
  <img src="https://img.shields.io/badge/IMU-MPU--6050-green" alt="MPU-6050">
  <img src="https://img.shields.io/badge/PCB-4--Layer-orange" alt="4 Layer PCB">
  <img src="https://img.shields.io/badge/CAD-Altium%20Designer-red" alt="Altium Designer">
  <img src="https://img.shields.io/badge/USB-Micro--USB-lightgrey" alt="Micro USB">
</p>

---

## Overview

The **STM32F411 IMU Development Board** is a compact embedded hardware platform built around the **STM32F411CEU6** microcontroller and **MPU-6050** 6-axis inertial measurement unit.

The board is designed for embedded development, motion sensing, firmware experimentation, sensor interfacing, and rapid prototyping.

The hardware includes USB connectivity, regulated 3.3 V power, SWD programming/debug access, GPIO expansion, reset and boot control, and status indication.

The PCB is designed as a **4-layer board using Altium Designer**, with complete design source files and manufacturing outputs included in this repository.

> **Design Status:** Hardware design files, documentation, BOM, and manufacturing outputs are included. Always validate the schematic, PCB, DRC/ERC results, component availability, and manufacturing files before production.

---

## Features

| Feature | Details |
|---|---|
| Microcontroller | STM32F411CEU6 |
| IMU | MPU-6050 6-axis accelerometer + gyroscope |
| USB | Micro-USB connector |
| Power Input | USB 5 V |
| Voltage Regulation | AMS1117-3.3 |
| Debug / Programming | SWD |
| Sensor Interface | I²C |
| Expansion | GPIO header |
| Clock | 24 MHz crystal |
| PCB | 4-layer PCB |
| PCB CAD | Altium Designer |
| Manufacturing | Gerber + drill files |
| Documentation | Schematic PDF, PCB views, BOM, manufacturing outputs |

---

## Hardware Architecture

The board is organized into four primary functional sections:

### 1. STM32F411CEU6 Microcontroller

The STM32F411CEU6 acts as the main processing and control device for the board.

It provides the processing resources required for firmware development, peripheral control, sensor communication, USB connectivity, and external GPIO interfacing.

### 2. MPU-6050 IMU

The MPU-6050 provides:

- 3-axis accelerometer
- 3-axis gyroscope
- I²C communication

The IMU is connected to the STM32F411 through the I²C interface.

### 3. USB and Power

The board accepts power through the Micro-USB connector.

The power section provides:

- USB 5 V input
- Power filtering
- 3.3 V regulation
- AMS1117-3.3 regulator

The regulated 3.3 V rail supplies the board's low-voltage circuitry.

### 4. Debug and Expansion

The board provides interfaces for development and external integration, including:

- SWD programming/debugging
- GPIO expansion
- NRST reset control
- BOOT0 boot configuration
- Status indication

---

## Key Interfaces

| Interface | Purpose |
|---|---|
| USB | Power and USB data |
| SWD | Programming and debugging |
| I²C | MPU-6050 communication |
| GPIO | External expansion |
| NRST | MCU reset |
| BOOT0 | MCU boot configuration |

---

## PCB Design

The board uses a **4-layer PCB architecture** designed in Altium Designer.

The repository includes the native Altium project together with the associated schematic, PCB layout, project configuration, CAM files, and manufacturing outputs.

### PCB Design Highlights

- 4-layer PCB
- STM32F411CEU6 MCU
- MPU-6050 IMU
- USB connectivity
- 3.3 V regulated power rail
- SWD programming/debug interface
- GPIO expansion
- Dedicated reset and boot circuitry
- Status LED circuitry
- 24 MHz crystal oscillator

---

## Repository Structure

```text
.
├── hardware/
│   ├── altium/                     # Native Altium project and design files
│   └── cam/                        # Altium CAM/CAMtastic files
│
├── manufacturing/
│   └── gerbers/                    # Gerber and drill manufacturing outputs
│
├── bom/
│   └── STM32_PCB_BOM.csv           # Bill of materials
│
├── docs/
│   ├── schematics/
│   │   └── STM32_Schematics.pdf    # Exported schematic
│   │
│   └── images/                     # PCB renders and layout images
│
├── .github/
│   └── ISSUE_TEMPLATE/             # GitHub issue templates
│
├── .gitignore
├── CONTRIBUTING.md
└── README.md
