# Indoor 3D Mapping Drone — Software & Hardware

This repository hosts both the **flight-control software** and the **hardware design** used in our UWA ELEC5550 project *Indoor 3D Mapping Drone System*.  
We keep frozen tags for reproducibility and provide downloadable ZIPs so reviewers can access everything easily.

---

## Quick Links

- **Repository home:** https://github.com/zhangzilin121-netizen/indoor-3d-mapping-drone  
- **Software snapshot (tag):** `v0.1-initial-ano-import`  
  https://github.com/zhangzilin121-netizen/indoor-3d-mapping-drone/releases/tag/v0.1-initial-ano-import
- **Hardware baseline (tag):** `v0.2-hardware-baseline` *(Assets include the Altium source ZIP)*  
  https://github.com/zhangzilin121-netizen/indoor-3d-mapping-drone/releases/tag/v0.2-hardware-baseline
- **Root ZIPs in this repo:**  
  - `ANO_PioneerPro-088.zip` (software project)  
  - `STM32F407-Flight Control Hardware-sch,pcb.zip` (hardware sources)

---

## What’s Included

### Software (Flight Control)
- Based on the open-source **Ano Flight Control** (Pioneer Pro 0.88).
- **MCU:** STM32F407VG (Cortex-M4, 168 MHz, FPU).
- **Toolchain:** Keil MDK (project file: `ANO_Pioneer.uvprojx`).  
- **Core modules (paths inside the ZIP):**
  - PID core — `SRC/fc_general/Ano_Pid.c`
  - Attitude control (outer angle + inner rate) — `SRC/fc_specific/Ano_AttCtrl.c`
  - RC decoding & arming — `SRC/applications/Ano_RC.c`
  - Motor mixing & safety gating — `SRC/fc_specific/Ano_MotorCtrl.c`
  - Altitude/position control — `SRC/fc_specific/Ano_AltCtrl.c`, `SRC/fc_specific/Ano_LocCtrl.c`
  - IMU processing & filters — `SRC/fc_general/Ano_Imu.c`, `SRC/fc_general/Ano_Filter.c`

**Build (Keil MDK):**
1. Unzip `ANO_PioneerPro-088.zip` and open `ANO_Pioneer.uvprojx`.
2. Build to produce `.hex/.bin`, then flash via ST-Link to STM32F407.

### Hardware (Electronics)
- **EDA:** Altium (schematics `.SchDoc`, PCB `.PcbDoc`).
- **Sources:** attached to release **v0.2-hardware-baseline** *(Assets → hardware ZIP)* and also kept as a ZIP in the repo root.
- **Typical outputs (to be added as needed):** schematic PDF, board views (top/bottom), Gerbers/NC drill, BOM (`.csv`), pick-and-place (`.csv`).

---

## Project Status & Scope
- Public for educational/demo purposes. Sensitive assessment materials are intentionally excluded.
- Tags `v0.1` (software) and `v0.2` (hardware) are the baselines referenced in the report for V&V and reproducibility.

---

## How to Cite
- Repository: zhangzilin121-netizen, *indoor-3d-mapping-drone*, GitHub.  
- Software tag: **v0.1-initial-ano-import**; Hardware tag: **v0.2-hardware-baseline**.

---

## Credits
- Base algorithms/framework: **Ano Flight Control** project (Pioneer Pro 0.88).
