# Digital Business Card (Digital-B-Card)

An ESP32-C3 based digital business card / badge with an e-paper display and NFC tap-to-share, designed as a custom PCB in a compact card/badge form factor.

## Overview

This project is a self-contained electronic business card. It combines a low-power microcontroller, an e-paper display for a persistent, battery-friendly visual, and an NFC tag for one-tap contact sharing on any NFC-enabled phone. The board is designed to fit inside a 3D-printed badge enclosure.

## Key Features

- **MCU:** ESP32-C3-MINI-1-N4 (RISC-V, Wi-Fi / BLE, native USB) for control logic and OTA wireless updates.
- **Display:** 2.66" e-paper panel (GDEM0266T71WT) driven by the SSD1680 controller — ultra-low power, always-on readability.
- **NFC:** NXP NT3H2111 NTAG I²C tag + custom 8-turn PCB antenna for tap-to-share contact info with any NFC-enabled phone.
- **Power:** MCP73871-2CC power-path LiPo charger + MAX17048 fuel gauge + AP2112K-3.3 LDO — USB-C charging with seamless battery monitoring.
- **Custom PCB:** Designed in KiCad, fabricated as a 2-layer, single-sided 100 × 60 mm board.
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

## Specification Sheet

> Rev A — 2026-08-24. Values are marked **[V]** verified against a datasheet/layout/CAD, **[E]** estimated, or **[TBC]** to be confirmed on hardware.

### At a Glance

| Parameter | Value |
|---|---|
| Function | E-paper display with NFC tap-to-share and Wi-Fi / BLE connectivity |
| Modes | Desk nameplate / event badge / tap-to-share card (firmware-selected) |
| Outer dimensions | 104.6 × 69.6 × 11.1 mm **[V]** |
| Mass, assembled | ≈ 68 g **[E]** |
| Power | 1S Li-Po, USB-C rechargeable |
| Enclosure | Two-part 3D print, M2 screws |
| MCU | ESP32-C3-MINI-1-N4 (RISC-V, Wi-Fi + BLE, native USB) |
| Display | 2.66" e-paper, 152 × 296 px, SSD1680 driver (GDEM0266T71WT) |
| Connectivity | NFC (NT3H2111 + custom PCB antenna), Wi-Fi, BLE |
| Charging | USB-C, MCP73871-2CC power-path Li-Po charge management |
| Regulation | AP2112K-3.3 LDO |
| Fuel gauge | MAX17048 |
| Battery | 1S Li-Po, 500 mAh (Uxney 503035, 200–600 mAh range supported) |
| Design tool | KiCad |
| Manufacturing | JLCPCB, 2-layer, full SMT assembly |

### PCB Mechanical

| Parameter | Value |
|---|---|
| Outline | 100.0 × 60.0 mm **[V]** |
| Thickness | 1.6 mm **[V]** |
| Layers | 2 (F.Cu, B.Cu) **[V]** |
| Assembly | Single-sided — all components on B.Cu **[V]** |
| Mounting holes | 4 × Ø2.2 mm NPTH for M2, 2.75 mm from each corner **[V]** |
| Min track width | 0.25 mm signal / 0.40 mm power **[V]** |
| Min clearance | 0.20 mm (0.50 mm on HV class) **[V]** |
| Via / drill | 0.6 / 0.3 mm **[V]** |
| Surface finish | ENIG recommended |
| Placements | 59 across 27 orderable line items **[V]** |

### Enclosure

| Parameter | Value |
|---|---|
| Outer | 104.6 × 69.6 × 11.1 mm **[V]** |
| Wall / floor thickness | 2.0 mm **[V]** |
| PCB fit clearance | 0.3 mm per side **[V]** (may open to 0.4–0.5 mm **[TBC]**) |
| Split line | z = +1.6 mm — tray below, cover above **[V]** |
| Internal cavity | 100.6 × 65.6 × 5.5 mm deep **[V]** |
| Board support | 4 × Ø4.5 mm bosses with Ø1.7 mm pilot holes **[V]** |
| Fasteners | 4 × M2 self-tapping; nylon in the two holes nearest the NFC coil |
| USB-C opening | 12.6 × 6.2 mm **[V]** |
| Button access | 2 × Ø2.0 mm through tray floor **[V]** |

### Display

| Parameter | Value |
|---|---|
| Part | GDEM0266T71WT (Good Display) |
| Technology | E-paper, monochrome, bistable — zero power to hold image |
| Controller | SSD1680 (Solomon Systech) |
| Diagonal | 2.66" |
| Resolution | 152 × 296 px **[V]** |
| Active area | 30.704 × 60.088 mm **[V]** |
| Interface | 4-wire SPI, BS1 strapped low **[V]** |
| Connector | 24-pin 0.5 mm FPC, 14 mm tail **[V]** |
| Typical operating current | 4.5 mA **[V]** |
| Peak refresh current | 40 mA typ / 60 mA max **[V]** |

### Wireless

| Parameter | Value |
|---|---|
| MCU module | ESP32-C3-MINI-1-N4 (Espressif), RF pre-certified |
| Core | 32-bit RISC-V single core |
| Flash | 4 MB |
| Wi-Fi | 802.11 b/g/n, 2.4 GHz |
| Bluetooth | BLE 5 |
| Wi-Fi/BLE Antenna | Integrated module PCB antenna, overhanging board edge per Espressif guidance **[V]** |
| USB | Native USB (GPIO18/19) — programming and debug, no UART bridge |

### NFC

| Parameter | Value |
|---|---|
| Tag IC | NT3H2111W0FHKH (NXP NTAG I²C plus) |
| Standard | NFC Forum Type 2, 13.56 MHz |
| Host interface | I²C |
| Antenna | Custom PCB coil on F.Cu — 8 turns, 0.6 mm trace, 0.3 mm gap **[V]** |
| Coil area | 15 × 50 mm **[V]** |
| Coil inductance | ≈ 1.93 µH **[E]** |
| Chip capacitance | 50 pF **[V]** (datasheet §13.1) |
| Tuning capacitor | 22 pF C0G/NP0 **[V]** |
| Field-detect | FD → GPIO3, deep-sleep wake on tap **[V]** |
| Read range | **[TBC]** — C14 is the tuning point |

### Power

| Parameter | Value |
|---|---|
| Battery chemistry | Lithium polymer, 1 cell |
| Capacity | 500 mAh (200–600 mAh range supported) |
| Nominal / max voltage | 3.7 V / 4.2 V |
| Cell | Uxney 503035, 35 × 30 × 5 mm, integrated protection |
| Connector | JST-PH 2.0 mm, S2B-PH-SM4-TB horizontal SMT **[V]** |
| Regulation output | 3.3 V (AP2112K LDO, 600 mA rated) |
| LDO input source | Charger SYS/OUT rail — **not** VBAT |
| Charge IC | MCP73871-2CC, power-path topology |
| Charge voltage | 4.20 V **[V]** |
| Input current limit | 500 mA **[V]** |
| Charge current | ≈ 303 mA **[E]** |
| Termination current | ≈ 42 mA **[E]** |
| Safety timer | 6 h **[V]** |
| Worst-case dissipation | ≈ 0.4 W **[E]** |
| Fuel gauge | MAX17048, ModelGauge, 3 µA operating, I²C, ALRT → GPIO4 wake |

### Current Budget

| State | Estimate | Note |
|---|---|---|
| Deep sleep | ≈ 10–20 µA | MCU deep sleep + gauge 3 µA + leakage |
| Display holding image | 0 µA | Bistable — no power to retain |
| Display refresh | 40–60 mA for a few seconds | Panel datasheet §6.2 |
| Wi-Fi transmit | up to ≈ 350 mA peak | ESP32-C3 typical |
| NFC tap (harvested) | Field-powered | Tag responds without waking MCU |

### GPIO Pin Map

| GPIO | Net | Notes |
|---|---|---|
| 0 | I2C SDA | Shared bus — NFC + fuel gauge |
| 1 | I2C SCL | Shared bus |
| 2 | EPD RST | Strapping pin, 10 kΩ pull-up, idles high |
| 3 | NFC FD | Field detect; deep-sleep wake on tap (RTC-capable) |
| 4 | FUELGAUGE ALERT | MAX17048 ALRT; deep-sleep wake (RTC-capable) |
| 5 | EPD BUSY | Input |
| 6 | EPDCLK | E-paper SPI clock |
| 7 | EPDDATA | E-paper SPI data |
| 8 | STATUS LED | Strapping — must be high at boot, 10 kΩ pull-up |
| 9 | BOOT | Strapping, 10 kΩ pull-up + debounce cap, button to GND |
| 10 | EPD CS | E-paper chip select |
| 18 / 19 | USB D− / D+ | 0 Ω series to USB-C |
| 20 | EPD DC | Data/command |
| 21 | UART0 TX | Optional debug |
| EN | RESET | 10 kΩ pull-up + cap + RESET button |

### Manufacturing Summary

| Parameter | Value |
|---|---|
| Fabricator | JLCPCB |
| Process | 2-layer, full SMT assembly, single-sided |
| DRC | 0 violations, 12 documented exclusions **[V]** |
| ERC | Clean — one intentional informational note **[V]** |
| Gerber set | 9 files, Protel extensions, X2 attributes |
| BOM | 27 line items, 59 placements, LCSC part numbers on every row **[V]** |
| DNP | C5, C6 — USB ESD positions, deliberately unpopulated |
| Not in BOM | AE1 — antenna is etched copper |
| Enclosure | FDM, PLA, 2 parts, no supports required **[TBC]** |

---

## Bill of Materials (BOM)

The complete component list is in [`BOM/digital card-BOM.csv`](./BOM/digital%20card-BOM.csv). The table below is the authoritative human-readable BOM (27 orderable line items, 59 placements) with all LCSC part numbers.

> **Note:** C5 and C6 (USB ESD capacitor positions) are **DNP** (Do Not Populate). AE1 (NFC antenna) is etched copper — not a sourced component.

| Designator(s) | Value / Part | Package | LCSC # | Datasheet |
|---|---|---|---|---|
| U1 | ESP32-C3-MINI-1-N4 | Module | C2838502 | [esp32-c3-mini-1_datasheet_en.pdf](./datasheets/esp32-c3-mini-1_datasheet_en.pdf) |
| U2 | MAX17048G+T10 | TDFN-8 + EP | C2682616 | [C2682616.pdf](./datasheets/C2682616.pdf) |
| U3 | AP2112K-3.3 | SOT-23-5 | C51118 | [C51118.pdf](./datasheets/C51118.pdf) |
| U4 | NT3H2111W0FHKH | XQFN-8 | C710403 | [NT3H2111_2211.pdf](./datasheets/NT3H2111_2211.pdf) |
| U7 | MCP73871-2CC | QFN-20 + EP | C5121473 | [C5121473.pdf](./datasheets/C5121473.pdf) |
| J1 | USB-C TYPE-C-31-M-12 | 16P receptacle | C165948 | [C165948 (1).pdf](./datasheets/C165948%20(1).pdf) |
| J2 | JST S2B-PH-SM4-TB | PH 2.0 mm horiz. SMT | C295747 | [C295747.pdf](./datasheets/C295747.pdf) |
| J3 | AFC07-S24ECA-00 | 24P, 0.5 mm, top-contact | C262643 | [C262643 (2).pdf](./datasheets/C262643%20(2).pdf) |
| Q2 | SI1304BDL | SOT-323 | C7419947 | [C7419947 (1).pdf](./datasheets/C7419947%20(1).pdf) |
| L1 | 47 µH CDRH2D18 | SMD | C2454210 | [C2454210 (1).pdf](./datasheets/C2454210%20(1).pdf) |
| D1, D5, D6 | MBR0530 Schottky | SOD-123 | C77336 | [C77336 (1).pdf](./datasheets/C77336%20(1).pdf) |
| D2, D3, D4 | Red LED | 0603 | C2286 | [C2286.pdf](./datasheets/C2286.pdf) |
| SW1, SW2 | TS-1088-AR02016 tactile button | 4 × 3 mm SMD | C720477 | [C720477 (1).pdf](./datasheets/C720477%20(1).pdf) |
| R2, R3, R8, R9, R12, R17–R19 | 10 kΩ | 0805 | C17414 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |
| R1, R4, R5 | 0 Ω jumper | 0603 | C21189 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |
| R6, R7 | 5.1 kΩ (USB-C CC) | 0603 | C23186 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |
| R10 | 3.3 kΩ | 0603 | C22978 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |
| R11 | 24 kΩ | 0603 | C23352 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |
| R13, R14, R15 | 470 Ω | 0603 | C23179 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |
| R16 | 2.2 Ω sense resistor | 0805 | C17521 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |
| C1, C3, C8, C24 | 100 nF decoupling | 0805 | C28233 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| C2, C11 | 10 µF bulk | 0603 | C19702 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| C4, C9, C10, C18 | 1 µF 50 V X7R bypass | 0805 | C28323 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| C7, C12 | 4.7 µF | 0603 | C19666 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| C13 | 220 nF | 0603 | C21120 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| C14 | 22 pF C0G/NP0 (NFC tuning) | 0603 | C1653 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| C15–C17, C19–C23 | 1 µF 50 V X5R bypass | 0603 | C15849 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| C5, C6 | **DNP** — USB ESD positions | 0603 | — | — |
| AE1 | NFC coil (etched copper, 8T) | — | — | — |

> **Total:** 27 orderable line items / 59 placements. Raw CSV: [`BOM/digital card-BOM.csv`](./BOM/digital%20card-BOM.csv)

---

## Datasheets & Spec Sheets

All component datasheets are in the [`datasheets/`](./datasheets) directory. A single combined quick-reference is also available at [`datasheets/all_datasheets_combined.md`](./datasheets/all_datasheets_combined.md).

### ICs & Active Components

| Component | LCSC # | Description | Datasheet |
|---|---|---|---|
| ESP32-C3-MINI-1-N4 | C2838502 | RISC-V SoC module, Wi-Fi + BLE, native USB | [esp32-c3-mini-1_datasheet_en.pdf](./datasheets/esp32-c3-mini-1_datasheet_en.pdf) |
| ESP32-C3 HW Guidelines | — | PCB layout and antenna design guide | [esp-hardware-design-guidelines-en-master-esp32c3.pdf](./datasheets/esp-hardware-design-guidelines-en-master-esp32c3.pdf) |
| SSD1680 | — | E-paper display controller | [SSD1680.pdf](./datasheets/SSD1680.pdf) |
| GDEM0266T71WT | — | 2.66" e-paper panel | [GDEM0266T71WT.pdf](./datasheets/GDEM0266T71WT.pdf) |
| NT3H2111W0FHKH | C710403 | NXP NTAG I²C NFC tag | [NT3H2111_2211.pdf](./datasheets/NT3H2111_2211.pdf) |
| MAX17048G+T10 | C2682616 | 1–2 cell fuel gauge (I²C, ModelGauge) | [C2682616.pdf](./datasheets/C2682616.pdf) |
| AP2112K-3.3 | C51118 | 600 mA LDO regulator | [C51118.pdf](./datasheets/C51118.pdf) |
| MCP73871-2CC | C5121473 | LiPo power-path charge management | [C5121473.pdf](./datasheets/C5121473.pdf) |
| SI1304BDL (Q2) | C7419947 | N-MOSFET, boost converter switch | [C7419947 (1).pdf](./datasheets/C7419947%20(1).pdf) |

### Passive & Discrete Components (LCSC)

| LCSC # | Component | Designator(s) | File |
|---|---|---|---|
| C165948 | USB Type-C receptacle | J1 | [C165948 (1).pdf](./datasheets/C165948%20(1).pdf) |
| C295747 | JST S2B-PH-SM4-TB battery connector | J2 | [C295747.pdf](./datasheets/C295747.pdf) |
| C262643 | AFC07-S24ECA-00 FPC connector | J3 | [C262643 (2).pdf](./datasheets/C262643%20(2).pdf) |
| C2454210 | 47 µH CDRH2D18 inductor | L1 | [C2454210 (1).pdf](./datasheets/C2454210%20(1).pdf) |
| C77336 | MBR0530 Schottky diode | D1, D5, D6 | [C77336 (1).pdf](./datasheets/C77336%20(1).pdf) |
| C2286 | Red LED 0603 | D2, D3, D4 | [C2286.pdf](./datasheets/C2286.pdf) |
| C720477 | TS-1088-AR02016 tactile button | SW1, SW2 | [C720477 (1).pdf](./datasheets/C720477%20(1).pdf) |

### Catalog References

| Catalog | Covers (LCSC #s) | File |
|---|---|---|
| Samsung MLCC | C1653, C15849, C19666, C19702, C21120, C28233, C28323 | [Samsung_MLCC_catalog.pdf](./datasheets/Samsung_MLCC_catalog%20(C1653%20C15849%20C19666%20C19702%20C21120%20C28233%20C28323).pdf) |
| Uniroyal Resistors | C17414, C17521, C22978, C23179, C23186, C23352 | [Uniroyal_resistors.pdf](./datasheets/Uniroyal_resistors%20(C17414%20C17521%20C22978%20C23179%20C23186%20C23352).pdf) |

---

## Documentation

The full project report — covering design rationale, schematic/PCB walkthrough, assembly notes, and testing — is available in [`DOC/Digital_Business_Card_Report.zip`](./DOC/Digital_Business_Card_Report.zip).

---

## Manufacturing

To fabricate the PCB, upload [`Gerber/gerber.7z`](./Gerber/gerber.7z) (or the individual Gerber/drill files) to JLCPCB or your PCB manufacturer of choice with full SMT assembly. Reference the [BOM table](#bill-of-materials-bom) above or the CSV for component sourcing.

**Pre-order checklist:**
- Verify polarized-part orientations (Q2, U7, U2, U4, diodes, LEDs) in the JLCPCB assembly preview.
- Confirm BOM excludes DNP rows (C5/C6) and the etched antenna (AE1).
- Use nylon (not steel) M2 screws in the two mounting holes nearest the NFC coil.
- On battery arrival: verify lead polarity at J2 with a multimeter before first connection — JST-PH polarity is not standardized.

---

## Case & Enclosure

The badge enclosure is modeled in FreeCAD (`Case/Digital_Card_Case_3_BADGE.FCStd`). A 3D nameplate model (`case-nameplate.glb`) can be previewed directly in a browser using [`Digital_C-Case_Viewer.html`](./Digital_C-Case_Viewer.html).

---

## License

N/A
