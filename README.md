# DARA — Digital Business Card

> **A business card that closes the loop.**
> A custom circuit board with an e-paper panel and NFC, inside a 3D-printed shell you choose the colour of. Tap it to a phone and your details land instantly.

🌐 **Product Page:** [https://dara-shop.vercel.app/](https://dara-shop.vercel.app/)

---

## Overview

DARA is a smart, NFC-enabled digital business card built around a custom PCB. It features an e-paper display that holds its image with the power off, an NFC antenna for contactless sharing, and a USB-C rechargeable battery — all designed from scratch in KiCad.

The electronics stay constant across all variants. What changes is the printed shell around them.

---

## Hardware

| Component | Details |
|-----------|---------|
| MCU | ESP32-C3 |
| Display | E-paper panel (image persists without power) |
| Connectivity | NFC antenna |
| Power | USB-C charged battery |
| PCB Design | KiCad (designed from blank sheet) |

---

## Repository Structure

```
Digital-B-Card/
├── Case/               # 3D-printable shell files
├── Gerber/             # PCB manufacturing files
├── PCB-Schem/          # KiCad schematic and PCB layout
├── datasheets/         # Component datasheets
└── Digital_C-Case_Viewer.html  # Interactive 3D case viewer
```

---

## Available Bodies (Cases)

All three bodies share the same tray, cover, and four-screw pattern — a board bought today accepts any shell.

### The Card
The baseline body. 11 mm thin, back sealed as one unbroken surface. Lives in a wallet.
- **Footprint:** 104.6 × 69.6 mm — **Thickness:** 11.1 mm — **Mass:** 37.6 g

### The Nameplate
A desk stand version — leans 18° from vertical, putting the screen at 47.6 mm above the desk surface with USB-C on the top edge.
- **Standing:** 104.6 × 36.1 × 78.3 mm — **Mass:** 103 g

### The Badge
Includes an L-shaped flange with four obround lanyard slots. Can hang in landscape or portrait orientation.
- **Outline:** 114.6 × 79.6 mm — **Thickness:** 11.1 mm — **Mass:** 45.8 g

---

## PCB Design

The PCB was designed entirely in **KiCad** from a blank sheet. Gerber files for manufacturing are included in the `Gerber/` directory. Schematics and layout files are in `PCB-Schem/`.

---

## Getting Started

1. Browse the `PCB-Schem/` folder for schematics and layout files
2. Use the Gerber files in `Gerber/` to order PCB fabrication
3. Print a case from `Case/` in your colour of choice
4. Flash the ESP32-C3 firmware and configure your card details
5. Open `Digital_C-Case_Viewer.html` in a browser to preview the 3D case

---

## License

This project is open-source. See the repository for details.

---

*Designed & built in the UAE 🇦🇪*
