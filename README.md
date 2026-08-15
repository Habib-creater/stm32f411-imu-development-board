# STM32F411 IMU Development Board

A compact STM32F411-based development board designed around an **STM32F411CEU6** microcontroller and **MPU-6050** 6-axis inertial measurement unit (IMU), with USB connectivity, 3.3 V regulation, SWD programming/debug access, GPIO expansion, and status indication.

> **Status:** Hardware design files and manufacturing outputs included. Validate the design and manufacturing outputs before production.

## Highlights

- **MCU:** STM32F411CEU6
- **IMU:** MPU-6050
- **USB:** Micro-USB connector
- **Power:** USB 5 V input with AMS1117-3.3 regulation
- **Programming / Debug:** SWD header
- **Expansion:** GPIO header
- **Clock:** 24 MHz crystal
- **PCB:** 2-layer Altium Designer layout
- **Manufacturing:** Gerber and drill outputs included
- **Documentation:** Schematic PDF, PCB renders, layer views, and BOM

## Repository Structure

```text
.
├── hardware/
│   ├── altium/                 # Native Altium project and design files
│   └── cam/                    # Altium CAM/CAMtastic files
├── manufacturing/
│   └── gerbers/                # Gerber + drill manufacturing outputs
├── bom/
│   └── STM32_PCB_BOM.csv       # Bill of materials
├── docs/
│   ├── schematics/
│   │   └── STM32_Schematics.pdf
│   └── images/                 # PCB layout and 3D renders
├── .github/
│   └── ISSUE_TEMPLATE/
├── .gitignore
├── CONTRIBUTING.md
└── README.md
```

## Hardware Architecture

The design is organized around four main functional areas:

1. **STM32F411CEU6 microcontroller** — main processing and control.
2. **MPU-6050 IMU** — accelerometer/gyroscope sensing connected through I²C.
3. **USB + power stage** — USB input, ferrite filtering, 5 V rail and AMS1117-3.3 regulation.
4. **Debug / expansion** — SWD interface and GPIO breakout for development and integration.

### Key Interfaces

| Interface | Purpose |
|---|---|
| USB | Power and USB data |
| SWD | Programming and debugging |
| I²C | MPU-6050 communication |
| GPIO | External expansion |
| NRST / BOOT0 | MCU reset and boot control |

## Design Files

The native Altium project is located in [`hardware/altium/`](hardware/altium/).

Main files include:

- `STM32_PCB.PrjPcb` — Altium project
- `STM32_PCB.PcbDoc` — PCB layout
- `STM32_Schematics.SchDoc` — schematic
- `STM32_PCB.OutJob` — output job configuration
- `STM32_PCB.BomDoc` — Altium BOM document
- `STM32_PCB.PrjPcbStructure` — project structure data

**Recommended Altium version:** Open the project in the same or a newer compatible Altium Designer release. If Altium reports conversion warnings, review them before saving changes.

## Manufacturing Outputs

The `manufacturing/gerbers/` directory contains the generated Gerber and drill files, including:

- Copper layers
- Solder mask
- Silkscreen / legend
- Paste layers
- Board profile
- Plated and non-plated drill files
- Assembly / component information

Before ordering PCBs, verify the Gerber package in an independent Gerber viewer and confirm the required stack-up, board thickness, copper weight, solder mask, surface finish, and fabrication tolerances with your PCB manufacturer.

## BOM

The current BOM export is available at [`bom/STM32_PCB_BOM.csv`](bom/STM32_PCB_BOM.csv).

Always cross-check component availability, footprints, ratings, lifecycle status, and approved substitutions before procurement.

## Preview

### 3D Board Render

![3D front render](docs/images/3d_1.png)

### PCB Layout

![PCB layout](docs/images/STM32_layout1.png)

### Layer View

![PCB layer view](docs/images/STM32_layout5.png)

More board views are available in [`docs/images/`](docs/images/).

## Schematic

The exported schematic PDF is available here:

[`STM32_Schematics.pdf`](docs/schematics/STM32_Schematics.pdf)

## Getting Started

### Open the Altium project

Open **`hardware/altium/STM32_PCB.PrjPcb`** in Altium Designer. The project source documents and CAMtastic files are intentionally kept beside the `.PrjPcb` file so Altium can resolve its project-relative document references on another machine.

The project file has also been cleaned of stale generated-output references and machine-specific absolute paths. Manufacturing Gerbers are provided separately under `manufacturing/gerbers/`, while the Altium Output Job uses repository-relative output locations.


### For hardware development

1. Install a compatible version of **Altium Designer**.
2. Clone this repository.
3. Open `hardware/altium/STM32_PCB.PrjPcb`.
4. Review the schematic and PCB rules.
5. Validate ERC/DRC and review all warnings.
6. Regenerate manufacturing outputs if the design is modified.

### For PCB fabrication

1. Use the files under `manufacturing/gerbers/`.
2. Open the Gerbers in an independent viewer.
3. Confirm the board outline and drill files.
4. Confirm layer order and fabrication specifications with your manufacturer.
5. Do not fabricate from modified files without first re-validating the design.

## Repository Conventions

- Keep native Altium source files under `hardware/altium/`.
- Keep generated manufacturing files under `manufacturing/`.
- Keep documentation and renders under `docs/`.
- Keep BOM exports under `bom/`.
- Avoid committing temporary Altium recovery, cache, autosave, or local user files.
- When making a hardware revision, document the change in the commit message and update the revision notes.

## Known Design Notes

The supplied schematic includes:

- STM32F411CEU6 MCU
- MPU-6050 IMU
- USB connector
- AMS1117-3.3 regulator
- 24 MHz crystal
- SWD interface
- GPIO expansion
- Reset / boot circuitry
- Status LED circuitry

This repository description is based on the supplied design files; component values and electrical behavior should be verified directly against the source schematic before production.

## License

No open-source license has been assigned yet. Until a license is added, assume the contents are **all rights reserved** by the copyright holder.

If you intend to publish the design for reuse, choose an appropriate hardware license before advertising the repository as open source.

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for contribution and revision guidelines.

## Suggested GitHub Topics

`stm32` `stm32f4` `stm32f411` `mpu6050` `imu` `embedded` `electronics` `pcb` `altium` `hardware` `swd` `usb` `gerber`
