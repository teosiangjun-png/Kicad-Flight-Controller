# Custom STM32F722 Flight Controller (Rev 1 Prototype)

A custom, bare-metal quadcopter flight controller engineered around the STMicroelectronics STM32F722 MCU running Betaflight.

This repository documents the KiCad schematics, PCB layout files, custom Betaflight target modifications, and a post-mortem technical analysis of bringing up a custom board through non-ideal hardware constraints and silicon-level clock workarounds.

---

## Technical Specifications

- **Microcontroller:** STM32F722RET6 / STM32F722 (ARM Cortex-M7 @ 216 MHz)
- **Target Firmware:** Betaflight (Custom fork derived from `BETAFPVF722`)
- **Physical Footprint:** 36 × 36 mm standard mounting pattern
- **Power Architecture:** Direct LiPo battery input with on-board buck/LDO stages for 5V and 3.3V rails
- **Peripheral Bus:** SPI for IMU communication, hardware UARTs for receiver and telemetry links

---

![](![alt text](pcb.png))

![](![alt text](sch.png))

---

## Repository Structure

```text
├── hardware/
│   ├── schematics/        # KiCad schematics (.kicad_sch)
│   ├── pcb/               # KiCad PCB layout and routing (.kicad_pcb)
│   └── gerbers/           # Fabrication and drill outputs
├── firmware/
│   ├── patches/           # Clock tree and pinout diffs against Betaflight master
│   └── target/            # Custom target configuration and pin mappings
└── docs/
    └── post-mortem.md     # Detailed engineering failure analysis and bring-up logs
```
