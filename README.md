# Digital Business Card (Digital-B-Card)

An ESP32-C3 based digital business card / badge with an e-paper display and NFC tap-to-share, designed as a custom PCB in a compact card/badge form factor.

## Overview

This project is a self-contained electronic business card. It combines a low-power microcontroller, an e-paper display for a persistent, battery-friendly visual, and an NFC tag for one-tap contact sharing on any NFC-enabled phone. The board is designed to fit inside a 3D-printed badge enclosure.

## Key Features

- **MCU:** ESP32-C3-MINI-1 (RISC-V, Wi-Fi / BLE) for control logic and future OTA wireless updates.
- **Display:** 2.66″ e-paper panel (GDEM0266T71WT) driven by the SSD1680 controller — ultra-low power, always-on readability.
- **NFC:** NXP NT3H2111 NTAG I²C tag for tap-to-share contact info with any NFC-enabled phone.
- **Power:** MCP73871 LiPo charger + MAX17048 fuel gauge + AP2112K-3.3 LDO regulator — USB-C charging with battery monitoring.
- **Custom PCB:** Designed in KiCad, fabricated as a 2-layer card-format board.
- **Custom Case:** 3D-modeled badge enclosure (FreeCAD) with an optional 3D nameplate.

## Repository Structure

| Folder / File | Description |
|---|---|
| `PCB-Schem/` | KiCad schematic (`.kicad_sch`) and PCB layout (`.kicad_pcb`) source files. |
| `Gerber/` | Fabrication-ready Gerber files, drill files, job file, and `gerber.7z` for direct upload to a PCB manufacturer. |
| `BOM/` | Bill of materials (`digital card-BOM.csv`). |
| `datasheets/` | Component datasheets and reference documents (see [Datasheets & Spec Sheets](#datasheets--spec-sheets) below). |
| `Case/` | FreeCAD badge case models (`Digital_Card_Case_3_BADGE.FCStd`), a backup revision, and a 3D nameplate (`case-nameplate.glb`). |
| `Digital_C-Case_Viewer.html` | Standalone browser-based 3D viewer for the case / nameplate model. |
| `DOC/` | Full project report (`Digital_Business_Card_Report.zip`) covering design decisions, testing, and build notes. |

---

## Bill of Materials (BOM)

The complete component list is in [`BOM/digital card-BOM.csv`](./BOM/digital%20card-BOM.csv). The table below provides a human-readable summary for quick sourcing and assembly reference.

| # | Designator | Description / Value | Package | Qty | Part / LCSC # |
|---|---|---|---|---|---|
| 1 | AE1 | Loop NFC Antenna | NFC_Antenna_50x15_8T | 1 | — |
| 2 | C1, C3, C8, C24 | Decoupling capacitor 0.1 µF | 0805 | 4 | Samsung MLCC |
| 3 | C2, C11 | Bulk capacitor 10 µF | 0603 | 2 | Samsung MLCC |
| 4 | C4, C9, C10, C18 | Bypass capacitor 1 µF | 0805 | 4 | Samsung MLCC |
| 5 | C5, C6 | Capacitor (C) | 0603 | 2 | — |
| 6 | C7, C12 | Capacitor 4.7 µF | 0603 | 2 | Samsung MLCC |
| 7 | C13 | Capacitor 220 nF | 0603 | 1 | Samsung MLCC |
| 8 | C14 | Capacitor 21 pF | 0603 | 1 | Samsung MLCC |
| 9 | C15–C23 | Bypass capacitor 1 µF | 0603 | 8 | Samsung MLCC |
| 10 | D1, D5, D6 | Schottky diode MBR0530 | SOD-123 | 3 | [C2286](./datasheets/C2286.pdf) |
| 11 | D2, D3, D4 | LED | 0603 | 3 | [C2682616](./datasheets/C2682616.pdf) |
| 12 | J1 | USB Type-C receptacle (USB 2.0, 16P) | HRO TYPE-C-31-M-12 | 1 | [C165948](./datasheets/C165948%20(1).pdf) |
| 13 | J2 | JST PH 2-pin battery connector | JST PH S2B horizontal | 1 | [C295747](./datasheets/C295747.pdf) |
| 14 | J3 | 24-pin FPC/FFC connector | AFC07-S24ECA-00 | 1 | [C262643](./datasheets/C262643%20(2).pdf) |
| 15 | L1 | Inductor (boost/charger) | CDRH2D18 3.0×3.0 mm | 1 | [C5121473](./datasheets/C5121473.pdf) |
| 16 | Q2 | N-MOSFET (power switch) | SOT-323 | 1 | [C51118](./datasheets/C51118.pdf) |
| 17 | R1, R4, R5 | Zero-ohm jumper | 0603 | 3 | Uniroyal |
| 18 | R2, R3, R8, R12, R17–R19 | Pull-up resistor 10 kΩ | 0805 | 7 | Uniroyal |
| 19 | R6, R7 | CC resistor 5.1 kΩ (USB-C) | 0603 | 2 | Uniroyal |
| 20 | R9 | Resistor 10 kΩ | 0805 | 1 | Uniroyal |
| 21 | R10 | Resistor 3.3 kΩ | 0603 | 1 | Uniroyal |
| 22 | R11 | Resistor 24 kΩ | 0603 | 1 | Uniroyal |
| 23 | R13, R14, R15 | Current-limiting resistor 470 Ω | 0603 | 3 | Uniroyal |
| 24 | R16 | Sense resistor 2.2 Ω | 0805 | 1 | Uniroyal |
| 25 | SW1, SW2 | Tactile push button | SMD 3.9×3.0 mm | 2 | [C720477](./datasheets/C720477%20(1).pdf) |
| 26 | U1 | MCU — ESP32-C3-MINI-1 | ESP32-C3-MINI-1 | 1 | [Datasheet](./datasheets/esp32-c3-mini-1_datasheet_en.pdf) |
| 27 | U2 | Fuel gauge — MAX17048G | SON 2×2 mm | 1 | [C2454210](./datasheets/C2454210%20(1).pdf) |
| 28 | U3 | LDO 3.3 V — AP2112K-3.3 | SOT-23-5 | 1 | [C21189](./datasheets/C21189.pdf) |
| 29 | U4 | NFC tag — NT3H2111W0FHKH | QFN-8 | 1 | [NT3H2111_2211](./datasheets/NT3H2111_2211.pdf) |
| 30 | U7 | LiPo charger — MCP73871-2CC | QFN-20 | 1 | [C7419947](./datasheets/C7419947%20(1).pdf) |

> **Total unique line items:** 30 &nbsp;|&nbsp; Full CSV: [`BOM/digital card-BOM.csv`](./BOM/digital%20card-BOM.csv)

---

## Datasheets & Spec Sheets

All component datasheets are in the [`datasheets/`](./datasheets) directory. A single combined quick-reference is also available at [`datasheets/all_datasheets_combined.md`](./datasheets/all_datasheets_combined.md).

### ICs & Active Components

| Component | Description | Datasheet |
|---|---|---|
| ESP32-C3-MINI-1 | RISC-V SoC module, Wi-Fi + BLE | [esp32-c3-mini-1_datasheet_en.pdf](./datasheets/esp32-c3-mini-1_datasheet_en.pdf) |
| ESP32-C3 HW Guidelines | PCB layout and antenna design guide | [esp-hardware-design-guidelines-en-master-esp32c3.pdf](./datasheets/esp-hardware-design-guidelines-en-master-esp32c3.pdf) |
| SSD1680 | E-paper display controller | [SSD1680.pdf](./datasheets/SSD1680.pdf) |
| GDEM0266T71WT | 2.66″ tri-color e-paper panel | [GDEM0266T71WT.pdf](./datasheets/GDEM0266T71WT.pdf) |
| NT3H2111 / NT3H2211 | NXP NTAG I²C NFC tag | [NT3H2111_2211.pdf](./datasheets/NT3H2111_2211.pdf) |
| MAX17048G | 1–2 cell fuel gauge (I²C) | [C2454210 (1).pdf](./datasheets/C2454210%20(1).pdf) |
| AP2112K-3.3 | 600 mA LDO regulator | [C21189.pdf](./datasheets/C21189.pdf) |
| MCP73871-2CC | LiPo charge management IC | [C7419947 (1).pdf](./datasheets/C7419947%20(1).pdf) |

### Discrete Components (LCSC)

| LCSC # | Component | File |
|---|---|---|
| C165948 | USB Type-C receptacle | [C165948 (1).pdf](./datasheets/C165948%20(1).pdf) |
| C2286 | MBR0530 Schottky diode | [C2286.pdf](./datasheets/C2286.pdf) |
| C21189 | AP2112K-3.3 LDO | [C21189.pdf](./datasheets/C21189.pdf) |
| C2454210 | MAX17048 fuel gauge | [C2454210 (1).pdf](./datasheets/C2454210%20(1).pdf) |
| C262643 | AFC07-S24ECA FPC connector | [C262643 (2).pdf](./datasheets/C262643%20(2).pdf) |
| C2682616 | LED 0603 | [C2682616.pdf](./datasheets/C2682616.pdf) |
| C295747 | JST PH 2-pin connector | [C295747.pdf](./datasheets/C295747.pdf) |
| C51118 | N-MOSFET SOT-323 | [C51118.pdf](./datasheets/C51118.pdf) |
| C5121473 | Inductor CDRH2D18 | [C5121473.pdf](./datasheets/C5121473.pdf) |
| C720477 | Tactile push button | [C720477 (1).pdf](./datasheets/C720477%20(1).pdf) |
| C7419947 | MCP73871 charger IC | [C7419947 (1).pdf](./datasheets/C7419947%20(1).pdf) |
| C77336 | Component reference | [C77336 (1).pdf](./datasheets/C77336%20(1).pdf) |

### Catalog References

| Catalog | Covers | File |
|---|---|---|
| Samsung MLCC | C1653, C15849, C19666, C19702, C21120, C28233, C28323 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| Uniroyal Resistors | C17414, C17521, C22978, C23179, C23186, C23352 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |

---

## Documentation

The full project report — covering design rationale, schematic/PCB walkthrough, assembly notes, and testing — is available in [`DOC/Digital_Business_Card_Report.zip`](./DOC/Digital_Business_Card_Report.zip).

---

## Manufacturing

To fabricate the PCB, upload [`Gerber/gerber.7z`](./Gerber/gerber.7z) (or the individual Gerber/drill files) directly to your PCB manufacturer of choice (e.g. JLCPCB, PCBWay). Reference the [BOM table](#bill-of-materials-bom) above or the CSV file for assembly and sourcing.

---

## Case & Enclosure

The badge enclosure is modeled in FreeCAD (`Case/Digital_Card_Case_3_BADGE.FCStd`). A 3D nameplate model (`case-nameplate.glb`) can be previewed directly in a browser using [`Digital_C-Case_Viewer.html`](./Digital_C-Case_Viewer.html).

---

## License

N/A
