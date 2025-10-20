# Indoor 3D Mapping Drone – Flight Control

This repository hosts the flight-control firmware used in our UWA ELEC5550 project *Indoor 3D Mapping Drone System*.
The implementation is based on the open-source **Ano Flight Control** (Pioneer Pro 0.88) and runs on **STM32F407VG (Cortex-M4, 168 MHz)**.
We mainly performed parameter tuning, interface mapping, and safety gating for indoor flights and demonstrations.

## Repository Contents
- `ANO_PioneerPro-088.zip` — Upstream project snapshot used for our baseline build.
- (Planned) Selected core sources added as browsable files for transparency.

## Core Modules (paths inside the ZIP)
- PID: `SRC/fc_general/Ano_Pid.c`
- Attitude control (outer angle + inner rate): `SRC/fc_specific/Ano_AttCtrl.c`
- RC decoding & arming logic: `SRC/applications/Ano_RC.c`
- Motor control / output gating: `SRC/fc_specific/Ano_MotorCtrl.c`
- Altitude control: `SRC/fc_specific/Ano_AltCtrl.c`
- Position/local control: `SRC/fc_specific/Ano_LocCtrl.c`
- IMU processing & filters: `SRC/fc_general/Ano_Imu.c`, `SRC/fc_general/Ano_Filter.c`

## Build Environment
- Toolchain: **Keil MDK** (project file `ANO_Pioneer.uvprojx`)
- MCU: **STM32F407VGTx**, FPU, 168 MHz
- Libraries: `Libraries/CMSIS`, `Libraries/STM32F4xx_StdPeriph_Driver`, `Libraries/USBStack`
- Artifacts: `.elf`, `.hex`, `.bin` (not committed as plain files; see `.gitignore`)

## Notes
- The uploaded ZIP corresponds to the demo baseline. A tagged release is provided for reproducibility.
- Sensitive assessment documents are not included. This repo is for educational and demonstration purposes.

## Credits
- Base algorithms/framework: **Ano Flight Control** (Anonymous Tech).
