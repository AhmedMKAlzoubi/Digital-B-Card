# Digital Business Card (Digital-B-Card)

An ESP32-C3 based digital business card / badge with an e-paper display and NFC tap-to-share, designed as a custom PCB in a compact card/badge form factor.

## Overview

This project is a self-contained electronic business card. It combines a low-power microcontroller, an e-paper display for a persistent, battery-friendly visual, and an NFC tag for one-tap contact sharing on a phone. The board is designed to fit inside a 3D-printed badge case.

## Key Features

- **MCU:** ESP32-C3-MINI-1 (RISC-V, Wi-Fi/BLE) for control logic and future wireless updates.
- **Display:** 2.66" e-paper panel (GDEM0266T71WT) driven by the SSD1680 controller — low power, always-on readability.
- **NFC:** NXP NT3H2111/NT3H2211 NTAG I2C tag for tap-to-share contact info with any NFC-enabled phone.
- **Custom PCB:** Designed in KiCad, fabricated as a 2-layer card-format board.
- **Custom Case:** 3D-modeled badge enclosure (FreeCAD) with an optional 3D nameplate.

## Repository Structure

| Folder / File | Description |
|---|---|
| `PCB-Schem/` | KiCad schematic (`.kicad_sch`) and PCB layout (`.kicad_pcb`) source files. |
| `Gerber/` | Fabrication-ready Gerber files, drill files, job file, and a packaged `gerber.7z` for direct upload to a PCB manufacturer. |
| `BOM/` | Bill of materials for the board (`digital card-BOM.csv`). |
| `datasheets/` | Component datasheets and reference documents (see [Datasheets](#datasheets--spec-sheets) below). |
| `Case/` | FreeCAD badge case models (`Digital_Card_Case_3_BADGE.FCStd`), a backup revision, and a 3D nameplate (`case-nameplate.glb`). |
| `Digital_C-Case_Viewer.html` | Standalone browser-based 3D viewer for the case/nameplate model. |
| `DOC/` | Full project report (`Digital_Business_Card_Report.zip`) covering design decisions, testing, and build notes. |

## Bill of Materials (BOM)

The complete component list — part numbers, quantities, values, and package footprints — is maintained in [`BOM/digital card-BOM.csv`](./BOM/digital%20card-BOM.csv). Open it directly on GitHub or import it into a spreadsheet tool for sourcing and assembly.

## Datasheets & Spec Sheets

All component datasheets referenced by the design are collected in [`datasheets/`](./datasheets), including:

- **ESP32-C3-MINI-1** — [module datasheet](./datasheets/esp32-c3-mini-1_datasheet_en.pdf) and [hardware design guidelines](./datasheets/esp-hardware-design-guidelines-en-master-esp32c3.pdf).
- **SSD1680** — [e-paper display controller datasheet](./datasheets/SSD1680.pdf).
- **GDEM0266T71WT** — [2.66" e-paper panel datasheet](./datasheets/GDEM0266T71WT.pdf).
- **NT3H2111/NT3H2211** — [NFC/NTAG I2C datasheet](./datasheets/NT3H2111_2211.pdf).
- **Passives** — Samsung MLCC capacitor catalog and Uniroyal resistor catalog covering the passive components used on the board.
- [`all_datasheets_combined.md`](./datasheets/all_datasheets_combined.md) — a single combined reference of the key datasheet excerpts for quick lookup.
- Additional LCSC/JLCPCB component reference sheets (identified by their `C#####` part codes) for the remaining passives and connectors used in the BOM.

## Documentation

A full project report — covering the design rationale, schematic/PCB walkthrough, assembly notes, and testing — is available in [`DOC/Digital_Business_Card_Report.zip`](./DOC/Digital_Business_Card_Report.zip).

## Manufacturing

To fabricate the PCB, upload [`Gerber/gerber.7z`](./Gerber/gerber.7z) (or the individual Gerber/drill files) directly to your PCB manufacturer of choice, and reference the BOM for assembly/sourcing.

## Case & Enclosure

The badge enclosure is modeled in FreeCAD (`Case/Digital_Card_Case_3_BADGE.FCStd`). A 3D nameplate model (`case-nameplate.glb`) can be previewed directly in a browser using [`Digital_C-Case_Viewer.html`](./Digital_C-Case_Viewer.html).

## License
N/A
