# Digital Business Card — All Datasheets (Combined)

*Single merged reference: system datasheets (MCU, display) + all BOM part datasheets.
Merged 2026-08-01 from `datasheets_combined.md` and `part_datasheets_combined.md`, with J2 (C295747) added as §15 of Part II.*

---

# PART I — SYSTEM DATASHEETS

# Datasheets — Combined Reference

_Compiled 2026-07-31 from 4 source PDFs. Full-text extraction; the Good Display module was OCR-processed as it is image-based, so minor OCR artifacts may be present._

## Contents

1. [ESP32-C3-MINI-1 Datasheet](#1-esp32-c3-mini-1-datasheet) — Espressif Systems — ESP32-C3-MINI-1 / MINI-1U Wi-Fi + Bluetooth LE MCU module
2. [ESP32-C3 Hardware Design Guidelines](#2-esp32-c3-hardware-design-guidelines) — Espressif Systems — ESP32-C3 series hardware design guidelines
3. [SSD1680 Datasheet](#3-ssd1680-datasheet) — Solomon Systech — SSD1680 active matrix EPD display driver / controller
4. [GDEM0266T71WT Datasheet](#4-gdem0266t71wt-datasheet) — Good Display — GDEM0266T71WT 2.66" e-paper display module (OCR-extracted)


---

# 1. ESP32-C3-MINI-1 Datasheet

> **Source file:** `esp32-c3-mini-1_datasheet_en.pdf`  
> Espressif Systems — ESP32-C3-MINI-1 / MINI-1U Wi-Fi + Bluetooth LE MCU module

<!-- Page 1 -->

ESP32-C3-MINI-1
ESP32-C3-MINI-1U
Datasheet Version 2.2
Small-sized 2.4 GHz Wi-Fi (802.11b/g/n) and Bluetooth® 5 module
Built around ESP32-C3 series of SoCs, RISC-V single-core microprocessor
Up to 8 MB flash in chip package
15 GPIOs
On-board PCB antenna or external antenna connector
ESP32-C3-MINI-1
ESP32-C3-MINI-1U
www.espressif.com

<!-- Page 2 -->

1
Module Overview
1
Module Overview
Note:
Check the link or the QR code to make sure that you use the latest version of this document:
https://www.espressif.com/documentation/esp32-c3-mini-1_datasheet_en.pdf
1.1
Features
CPU and On-Chip Memory
• ESP32-C3FH4, ESP32-C3FH4X,
ESP32-C3FH8X, or ESP32-C3FH4AZ
embedded, 32-bit RISC-V single-core
processor, up to 160 MHz
• 384 KB ROM
• 400 KB SRAM (16 KB for cache)
• 8 KB SRAM in RTC
• Up to 8 MB flash in chip package
Wi-Fi
• IEEE 802.11 b/g/n-compliant
• Center frequency range of operating channel:
2412 ~ 2484 MHz
• Supports 20 MHz, 40 MHz bandwidth in 2.4
GHz band
• 1T1R mode with data rate up to 150 Mbps
• Wi-Fi Multimedia (WMM)
• TX/RX A-MPDU, TX/RX A-MSDU
• Immediate Block ACK
• Fragmentation and defragmentation
• Transmit opportunity (TXOP)
• Automatic Beacon monitoring (hardware TSF)
• 4 × virtual Wi-Fi interfaces
• Simultaneous support for Infrastructure BSS in
Station mode, SoftAP mode, Station + SoftAP
mode, and promiscuous mode
Note that when the chip scans in Station mode,
the SoftAP channel will change along with the
Station channel
• 802.11mc FTM
Bluetooth®
• Bluetooth LE: Bluetooth 5, Bluetooth mesh
• Speed: 125 Kbps, 500 Kbps, 1 Mbps, 2 Mbps
• Advertising extensions
• Multiple advertisement sets
• Channel selection algorithm #2
• Internal co-existence mechanism between Wi-Fi
and Bluetooth to share the same antenna
Peripherals
• Up to 15 GPIOs
– 3 strapping GPIOs
• SPI, UART, I2C, I2S, remote control peripheral,
LED PWM controller, general DMA controller,
TWAI® controller (compatible with ISO 11898-1,
i.e. CAN Specification 2.0), USB Serial/JTAG
controller, temperature sensor, SAR ADC,
general-purpose timers, watchdog timers
Note:
* Please refer to ESP32-C3 Series Datasheet for
detailed information about the module peripher-
als.
Integrated Components on Module
• 40 MHz crystal oscillator
Espressif Systems
2
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 3 -->

1
Module Overview
Antenna Options
• ESP32-C3-MINI-1: On-board PCB antenna
• ESP32-C3-MINI-1U: External antenna via a
connector
Operating Conditions
• Operating voltage/Power supply: 3.0 ~ 3.6 V
• Operating ambient temperature:
– 85 °C version module: –40 ~ 85 °C
– 105 °C version module: –40 ~ 105 °C
Certification
• RF certification: See certificates
• Green certification: RoHS/REACH
Test
• HTOL/HTSL/uHAST/TCT/ESD/Latch-up
1.2
Series Comparison
ESP32-C3-MINI-1 and ESP32-C3-MINI-1U are two general-purpose Wi-Fi and Bluetooth LE modules. The rich
set of peripherals and a small size make the two modules an ideal choice for smart homes, industrial
automation, health care, consumer electronics, etc.
ESP32-C3-MINI-1 comes with a PCB antenna. ESP32-C3-MINI-1U comes with an external antenna connector.
A wide selection of module variants are available as shown in Table 1-1 and 1-2.
The series comparison for the two modules is as follows:
Table 1-1. ESP32-C3-MINI-1 (ANT) Series Comparison1
Ambient Temp.2
Embedded
Size3
Part Number5
Flash4
(°C)
Chip Revision6
(mm)
ESP32-C3-MINI-1-N4X
(Recommended)
4 MB (Quad SPI)
–40 ∼85
v1.1
13.2 × 16.6 × 2.4
ESP32-C3-MINI-1-H4X
(Recommended)
–40 ∼105
v1.1
ESP32-C3-MINI-1-H8X
8 MB (Quad SPI)
–40 ∼105
v1.1
ESP32-C3-MINI-1-N4 (NRND)
4 MB (Quad SPI)
–40 ∼85
v0.4
ESP32-C3-MINI-1-H4 (NRND)
–40 ∼105
v0.4
ESP32-C3-MINI-1-H4-AZ (NRND)
–40 ∼105
v0.4
1 This table shares the same notes presented in Table 1-2 below.
Espressif Systems
3
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 4 -->

1
Module Overview
Table 1-2. ESP32-C3-MINI-1U (CONN) Series Comparison
Ambient Temp.2
Embedded
Size3
Part Number5
Flash4, 7
(°C)
Chip Revision 6
(mm)
ESP32-C3-MINI-1U-N4X
(Recommended)
4 MB (Quad SPI)
–40 ∼85
v1.1
13.2 × 12.5 × 2.4
ESP32-C3-MINI-1U-H4X
(Recommended)
–40 ∼105
v1.1
ESP32-C3-MINI-1U-N4 (NRND)
–40 ∼85
v0.4
ESP32-C3-MINI-1U-H4 (NRND)
–40 ∼105
v0.4
2 Ambient temperature specifies the recommended temperature range of the environment immediately outside the
Espressif module.
3 For details, refer to Section 10.1 Module Dimensions.
4 The flash is integrated in the chip’s package. For specifications, refer to Section 6.5 Memory Specifications.
5 All modules can be pre-programmed with AWS IoT ExpressLink firmware. Modules with such firmware have suffix ”-A”
in their part numbers, e.g. ESP32-C3-MINI-1-N4-A. Since AWS IoT ExpressLink firmware enables flash encryption
and secure boot, joint download boot mode will be disabled, and it will no longer be possible to program firmware
through the UART or USB port into the modules.
6 All chip revisions have the same SRAM size, but chip revision v1.1 has around 10 KB more available space for users
than chip revision v0.4. Chip revision v1.1 depends on specific ESP-IDF versions, as detailed in Compatibility Advisory
for ESP32-C3 Chip Revision v1.1. For how to identify chip revisions, please refer to ESP32-C3 Series SoC Errata.
7 By default, the SPI flash on the module operates at a maximum clock frequency of 80 MHz and does not support
the auto suspend feature. If you have a requirement for a higher flash clock frequency of 120 MHz or if you need
the flash auto suspend feature, please contact us.
Both ESP32-C3-MINI-1 and ESP32-C3-MINI-1U has two operating ambient temperature options: –40 ∼85 °C
variants and –40 ∼105 °C variants. These modules can be embedded with the following chips:
• ESP32-C3FH4: chip revision v0.4, 4 MB flash
• ESP32-C3FH4X: chip revision v1.1, 4 MB flash
• ESP32-C3FH8X: chip reivision v1.1, 8 MB
ESP32-C3-MINI-1 has one more variant: ESP32-C3-MINI-1-H4-AZ embedded with the ESP32-C3FH4AZ chip.
For this chip, SPI0/SPI1 pins for flash connection are not bonded.
For more information about the differences between chips embedded, please refer to Section Chip Series
Comparison in ESP32-C3 Series Datasheet.
1.3
Applications
• Smart Home
• Industrial Automation
• Health Care
• Consumer Electronics
• Smart Agriculture
• POS Machines
• Service Robot
• Audio Devices
• Generic Low-power IoT Sensor Hubs
• Generic Low-power IoT Data Loggers
Espressif Systems
4
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 5 -->

Contents
Contents
1
Module Overview
2
1.1
Features
2
1.2
Series Comparison
3
1.3
Applications
4
2
Block Diagram
9
3
Pin Definitions
10
3.1
Pin Layout
10
3.2
Pin Description
10
4
Boot Configurations
12
4.1
Chip Boot Mode Control
13
4.2
ROM Messages Printing Control
14
4.3
Chip Power-up and Reset
14
5
Peripherals
16
5.1
Peripheral Overview
16
5.2
Peripheral Description
16
5.2.1
Connectivity Interface
16
5.2.1.1
UART Controller
16
5.2.1.2
SPI Controller
16
5.2.1.3
I2C Controller
17
5.2.1.4
I2S Controller
18
5.2.1.5
USB Serial/JTAG Controller
18
5.2.1.6
Two-wire Automotive Interface
18
5.2.1.7
LED PWM Controller
19
5.2.1.8
Remote Control Peripheral
19
5.2.2
Analog Signal Processing
19
5.2.2.1
SAR ADC
20
5.2.2.2
Temperature Sensor
20
6
Electrical Characteristics
21
6.1
Absolute Maximum Ratings
21
6.2
Recommended Operating Conditions
21
6.3
DC Characteristics (3.3 V, 25 °C)
21
6.4
Current Consumption Characteristics
22
6.4.1
Current Consumption in Active Mode
22
6.4.2
Current Consumption in Other Modes
23
6.5
Memory Specifications
23
7
RF Characteristics
25
7.1
Wi-Fi Radio
25
Espressif Systems
5
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 6 -->

Contents
7.1.1
Wi-Fi RF Transmitter (TX) Characteristics
25
7.1.2
Wi-Fi RF Receiver (RX) Characteristics
26
7.2
Bluetooth 5 (LE) Radio
27
7.2.1
Bluetooth LE RF Transmitter (TX) Characteristics
27
7.2.2
Bluetooth LE RF Receiver (RX) Characteristics
29
8
Module Schematics
32
9
Peripheral Schematics
34
10 Physical Dimensions
35
10.1
Module Dimensions
35
10.2
Dimensions of External Antenna Connector
36
11
PCB Layout Recommendations
38
11.1
PCB Land Pattern
38
11.2
Module Placement for PCB Design
39
12 Product Handling
40
12.1
Storage Conditions
40
12.2
Electrostatic Discharge (ESD)
40
12.3
Reflow Profile
40
12.4
Ultrasonic Vibration
41
Datasheet Versioning
42
Related Documentation and Resources
43
Revision History
45
Espressif Systems
6
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 7 -->

List of Tables
List of Tables
1-1
ESP32-C3-MINI-1 (ANT) Series Comparison1
3
1-2
ESP32-C3-MINI-1U (CONN) Series Comparison
4
3-1
Pin Definitions
11
4-1
Default Configuration of Strapping Pins
12
4-2
Description of Timing Parameters for the Strapping Pins
13
4-3
Chip Boot Mode Control
13
4-4
UART0 ROM Message Printing Control
14
4-5
USB Serial/JTAG ROM Message Printing Control
14
4-6 Description of Timing Parameters for Power-up and Reset
15
6-1
Absolute Maximum Ratings
21
6-2 Recommended Operating Conditions
21
6-3 DC Characteristics (3.3 V, 25 °C)
21
6-4 Current Consumption for Wi-Fi (2.4 GHz) in Active Mode
22
6-5 Current Consumption for Bluetooth LE in Active Mode
22
6-6 Current Consumption in Modem-sleep Mode
23
6-7
Current Consumption in Low-Power Modes
23
6-8 Flash Specifications
23
7-1
Wi-Fi RF Characteristics
25
7-2
TX Power with Spectral Mask and EVM Meeting 802.11 Standards
25
7-3
TX EVM Test1
25
7-4
RX Sensitivity
26
7-5
Maximum RX Level
27
7-6
RX Adjacent Channel Rejection
27
7-7
Bluetooth LE RF Characteristics
27
7-8
Bluetooth LE - Transmitter Characteristics - 1 Mbps
28
7-9
Bluetooth LE - Transmitter Characteristics - 2 Mbps
28
7-10 Bluetooth LE - Transmitter Characteristics - 125 Kbps
28
7-11
Bluetooth LE - Transmitter Characteristics - 500 Kbps
29
7-12 Bluetooth LE - Receiver Characteristics - 1 Mbps
29
7-13 Bluetooth LE - Receiver Characteristics - 2 Mbps
30
7-14 Bluetooth LE - Receiver Characteristics - 125 Kbps
30
7-15 Bluetooth LE - Receiver Characteristics - 500 Kbps
31
Espressif Systems
7
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 8 -->

List of Figures
List of Figures
2-1
ESP32-C3-MINI-1 Block Diagram
9
2-2 ESP32-C3-MINI-1U Block Diagram
9
3-1
Pin Layout (Top View)
10
4-1
Visualization of Timing Parameters for the Strapping Pins
13
4-2
Visualization of Timing Parameters for Power-up and Reset
15
8-1
ESP32-C3-MINI-1 Schematics
32
8-2
ESP32-C3-MINI-1U Schematics
33
9-1
Peripheral Schematics
34
10-1 ESP32-C3-MINI-1 Physical Dimensions
35
10-2 ESP32-C3-MINI-1U Physical Dimensions
35
10-3 Dimensions of External Antenna Connector
36
11-1
ESP32-C3-MINI-1 Recommended PCB Land Pattern
38
11-2 ESP32-C3-MINI-1U Recommended PCB Land Pattern
39
12-1 Reflow Profile
40
Espressif Systems
8
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 9 -->

2
Block Diagram
2
Block Diagram
SPI Flash
RF Matching
40 MHz
Crystal
3V3
ESP32-C3-MINI-1
EN
GPIOs
Antenna
ESP32-C3FH4
Figure 2-1. ESP32-C3-MINI-1 Block Diagram
SPI Flash
40 MHz
Crystal
3V3
ESP32-C3-MINI-1U
EN
GPIOs
ESP32-C3FH4
RF Matching
Antenna
Figure 2-2. ESP32-C3-MINI-1U Block Diagram
Note:
For the pin mapping between the chip and the in-package flash, please refer to ESP32-C3 Series Datasheet > Table
Pin Mapping Between Chip and In-package Flash.
Espressif Systems
9
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 10 -->

3
Pin Definitions
3
Pin Definitions
3.1
Pin Layout
The pin diagram below shows the approximate location of pins on the module. For the actual diagram drawn to
scale, please refer to Figure 10.1 Module Dimensions.
Pin 49
GND
GND
GND
GND
GND
GND
GND
GND
GND
Pin 1
Pin 2
Pin 3
Pin 4
Pin 6
Pin 5
Pin 7
Pin 8
Pin 9
Pin 10
Pin 11
Pin 53
GND
Pin 52
GND
Pin 12
Pin 13
Pin 14
Pin 15
Pin 16
Pin 17
Pin 18
Pin 19
Pin 20
Pin 21
Pin 22
Pin 23
Pin 24
Pin 25
Pin 51
GND
Pin 26
Pin 27
Pin 28
Pin 29
Pin 30
Pin 31
Pin 32
Pin 33
Pin 34
Pin 35
Pin 50
GND
Pin 36
Pin 37
Pin 38
Pin 39
Pin 40
Pin 41
Pin 42
Pin 43
Pin 44
Pin 45
Pin 46
Pin 47
Pin 48
GND
GND
3V3
NC
IO2
IO3
NC
EN
NC
NC
GND
IO0
IO1
GND
NC
IO10
NC
IO4
IO5
IO6
IO7
IO8
IO9
NC
NC
IO18
IO19
NC
NC
RXD0
TXD0
NC
NC
NC
NC
GND
GND
GND
GND
GND
GND
GND
GND
GND
GND
GND
GND
GND
Keepout Zone
A
Figure 3-1. Pin Layout (Top View)
Note A:
The zone marked with dotted lines is the antenna keepout zone. The pin diagram is applicable to ESP32-C3-MINI-1
and ESP32-C3-MINI-1U, but the latter has no antenna keepout zone.
To learn more about the keepout zone for module’s antenna on the base board, please refer to
ESP32-C3 Hardware Design Guidelines > Section General Principles of PCB Layout for Modules.
3.2
Pin Description
The module has 53 pins. See pin definitions in Table 3-1 Pin Definitions.
For peripheral pin configurations, please refer to Section 5.2 Peripheral Description.
Espressif Systems
10
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 11 -->

3
Pin Definitions
Table 3-1. Pin Definitions
Name
No.
Type1
Function
GND
1, 2, 11, 14,
36-53
P
Ground
3V3
3
P
Power supply
NC
4, 7, 9, 10,
15, 17, 24,
25, 28, 29,
32-35
—
NC
IO2
5
I/O/T
GPIO2, ADC1_CH2, FSPIQ
IO3
6
I/O/T
GPIO3, ADC1_CH3
EN
8
I
High: on, enables the chip.
Low: off, the chip powers off.
Note: Do not leave the EN pin floating.
IO0
12
I/O/T
GPIO0, ADC1_CH0, XTAL_32K_P
IO1
13
I/O/T
GPIO1, ADC1_CH1, XTAL_32K_N
IO10
16
I/O/T
GPIO10, FSPICS0
IO4
18
I/O/T
GPIO4, ADC1_CH4, FSPIHD, MTMS
IO5
19
I/O/T
GPIO5, ADC2_CH0, FSPIWP, MTDI
IO6
20
I/O/T
GPIO6, FSPICLK, MTCK
IO7
21
I/O/T
GPIO7, FSPID, MTDO
IO8
22
I/O/T
GPIO8
IO9
23
I/O/T
GPIO9
IO18
26
I/O/T
GPIO18, USB_D-
IO19
27
I/O/T
GPIO19, USB_D+
RXD0
30
I/O/T
GPIO20, U0RXD
TXD0
31
I/O/T
GPIO21, U0TXD
1 P: power supply; I: input; O: output; T: high impedance.
Espressif Systems
11
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 12 -->

4
Boot Configurations
4
Boot Configurations
Note:
The content below is excerpted from ESP32-C3 Series Datasheet > Chapter Boot Configurations. For the strapping
pin mapping between the chip and modules, please refer to Chapter 8 Module Schematics.
The chip allows for configuring the following boot parameters through strapping pins and eFuse parameters at
power-up or a hardware reset, without microcontroller interaction.
• Chip boot mode
– Strapping pins: GPIO2, GPIO8, and GPIO9
• ROM message printing
– Strapping pin: GPIO8
– eFuse parameters: EFUSE_UART_PRINT_CONTROL and EFUSE_USB_PRINT_CHANNEL
The default values of all the above eFuse parameters are 0, which means that they are not burnt. Given that
eFuse is one-time programmable, once programmed to 1, it can never be reverted to 0. For how to program
eFuse parameters, please refer to ESP32-C3 Technical Reference Manual > Chapter eFuse Controller.
The default values of the strapping pins, namely the logic levels, are determined by pins’ internal weak
pull-up/pull-down resistors at reset if the pins are not connected to any circuit, or connected to an external
high-impedance circuit.
Table 4-1. Default Configuration of Strapping Pins
Strapping Pin
Default Configuration
Bit Value
GPIO2
Floating
–
GPIO8
Floating
–
GPIO9
Weak pull-up
1
To change the bit values, the strapping pins should be connected to external pull-down/pull-up resistances. If
the ESP32-C3 is used as a device by a host MCU, the strapping pin voltage levels can also be controlled by
the host MCU.
All strapping pins have latches. At Chip Reset, the latches sample the bit values of their respective strapping
pins and store them until the chip is powered down or shut down. The states of latches cannot be changed in
any other way. It makes the strapping pin values available during the entire chip operation, and the pins are
freed up to be used as regular IO pins after reset. For details on Chip Reset, see
ESP32-C3 Technical Reference Manual > Chapter Reset and Clock.
The timing of signals connected to the strapping pins should adhere to the setup time and hold time
specifications in Table 4-2 and Figure 4-1.
Espressif Systems
12
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 13 -->

4
Boot Configurations
Table 4-2. Description of Timing Parameters for the Strapping Pins
Parameter
Description
Min (ms)
tSU
Setup time is the time reserved for the power rails to stabilize be-
fore the CHIP_EN pin is pulled high to activate the chip.
0
tH
Hold time is the time reserved for the chip to read the strapping
pin values after CHIP_EN is already high and before these pins
start operating as regular IO pins.
3
Strapping pin
VIH_nRST
VIH
tSU
tH
CHIP_EN
Figure 4-1. Visualization of Timing Parameters for the Strapping Pins
4.1
Chip Boot Mode Control
GPIO2, GPIO8, and GPIO9 control the boot mode after the reset is released. See Table 4-3 Chip Boot Mode
Control.
Table 4-3. Chip Boot Mode Control
Boot Mode
GPIO2 2
GPIO8
GPIO9
SPI boot mode
1
Any value
1
Joint download boot mode 3
1
1
0
1 Bold marks the default value and configuration.
2 GPIO2 actually does not determine SPI Boot and Joint Down-
load Boot mode, but it is recommended to pull this pin up due
to glitches.
3 Joint Download Boot mode supports the following download
methods:
• USB-Serial-JTAG Download Boot
• UART Download Boot
In SPI Boot mode, the ROM bootloader loads and executes the program from SPI flash to boot the
system.
Espressif Systems
13
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 14 -->

4
Boot Configurations
In Joint Download Boot mode, users can download binary files into flash using UART0 or USB interface. It is
also possible to download binary files into SRAM and execute it from SRAM.
In addition to SPI Boot and Joint Download Boot modes, ESP32-C3 also supports SPI Download Boot mode.
For details, please see ESP32-C3 Technical Reference Manual > Chapter Chip Boot Control.
4.2
ROM Messages Printing Control
During the boot process, the messages by the ROM code can be printed to:
• (Default) UART0 and USB Serial/JTAG controller
• UART0
• USB Serial/JTAG controller
EFUSE_UART_PRINT_CONTROL and GPIO8 control ROM messages printing to UART0 as shown in Table 4-4
UART0 ROM Message Printing Control.
Table 4-4. UART0 ROM Message Printing Control
UART0 ROM Code Printing
EFUSE_UART_PRINT_CONTROL
GPIO8
Enabled
0
Ignored
1
0
2
1
Disabled
1
1
2
0
3
Ignored
1 Bold marks the default value and configuration.
EFUSE_USB_PRINT_CHANNEL controls the printing to USB Serial/JTAG controller as shown in Table 4-5 USB
Serial/JTAG ROM Message Printing Control.
Table 4-5. USB Serial/JTAG ROM Message Printing Control
USB Serial/JTAG
ROM Code Printing
EFUSE_DIS_USB_SERIAL_JTAG 2
EFUSE_USB_PRINT_CHANNEL
Enabled
0
0
Disabled
0
1
1
Ignored
1 Bold marks the default value and configuration.
2 EFUSE_DIS_USB_SERIAL_JTAG controls whether to disable USB Serial/JTAG.
4.3
Chip Power-up and Reset
Once the power is supplied to the chip, its power rails need a short time to stabilize. After that, CHIP_EN – the
pin used for power-up and reset – is pulled high to activate the chip. For information on CHIP_EN as well as
power-up and reset timing, see Figure 4-2 and Table 4-6.
Espressif Systems
14
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 15 -->

4
Boot Configurations
VIL_nRST
tST BL
tRST
2.8 V
VDDA,
VDD3P3,
VDD3P3_RTC,
VDD3P3_CPU
CHIP_EN
Figure 4-2. Visualization of Timing Parameters for Power-up and Reset
Table 4-6. Description of Timing Parameters for Power-up and Reset
Parameter
Description
Min (µs)
tST BL
Time
reserved
for
the
power
rails
of
VDDA,
VDD3P3,
VDD3P3_RTC, and VDD3P3_CPU to stabilize before the CHIP_EN
pin is pulled high to activate the chip
50
tRST
Time reserved for CHIP_EN to stay below VIL_nRST to reset the
chip (see Table 6-3)
50
Espressif Systems
15
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 16 -->

5
Peripherals
5
Peripherals
5.1
Peripheral Overview
ESP32-C3FH4 integrates a rich set of peripherals including SPI, UART, I2C, I2S, remote control peripheral, LED
PWM controller, TWAI® controller, USB Serial/JTAG controller, temperature sensor, SAR ADC.
To learn more about on-chip components, please refer to ESP32-C3 Series Datasheet > Section Functional
Description.
Note:
The content below is sourced from ESP32-C3 Series Datasheet > Section Peripherals. Some information may not be
applicable to ESP32-C3-MINI-1 and ESP32-C3-MINI-1U as not all the IO signals are exposed on the module.
To learn more about peripheral signals, please refer to ESP32-C3 Technical Reference Manual > Section Peripheral
Signal List.
5.2
Peripheral Description
This section describes the chip’s peripheral capabilities, covering connectivity interfaces and on-chip sensors
that extend its functionality.
5.2.1
Connectivity Interface
This subsection describes the connectivity interfaces on the chip that enable communication and interaction
with external devices and networks.
5.2.1.1
UART Controller
ESP32-C3 has two UART interfaces, i.e. UART0 and UART1, which support IrDA and asynchronous
communication (RS232 and RS485) at a speed of up to 5 Mbps. The UART controller provides hardware flow
control (CTS and RTS signals) and software flow control (XON and XOFF). Both UART interfaces connect to
GDMA via UHCI0, and can be accessed by the GDMA controller or directly by the CPU.
For details, see ESP32-C3 Technical Reference Manual > Chapter UART Controller (UART, LP_UART).
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.1.2
SPI Controller
ESP32-C3 has the following SPI interfaces:
• SPI0 used by ESP32-C3’s GDMA controller and cache to access in-package or off-package flash
• SPI1 used by the CPU to access in-package or off-package flash
• SPI2 is a general purpose SPI controller with access to a DMA channel allocated by the GDMA controller
Espressif Systems
16
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 17 -->

5
Peripherals
Features of SPI0 and SPI1
• Supports Single SPI, Dual SPI, and Quad SPI, QPI modes
• Configurable clock frequency with a maximum of 120 MHz in Single Transfer Rate (STR) mode
• Data transmission is in bytes
Features of SPI2
• Supports operation as a master or slave
• Connects to a DMA channel allocated by the GDMA controller
• Supports Single SPI, Dual SPI, and Quad SPI, QPI
• Configurable clock polarity (CPOL) and phase (CPHA)
• Configurable clock frequency
• Data transmission is in bytes
• Configurable read and write data bit order: most-significant bit (MSB) first, or least-significant bit (LSB)
first
• As a master
– Supports 2-line full-duplex communication with clock frequency up to 80 MHz
– Supports 1-, 2-, 4-line half-duplex communication with clock frequency up to 80 MHz
– Provides six SPI_CS pins for connection with six independent SPI slaves
– Configurable CS setup time and hold time
• As a slave
– Supports 2-line full-duplex communication with clock frequency up to 60 MHz
– Supports 1-, 2-, 4-line half-duplex communication with clock frequency up to 60 MHz
For details, see ESP32-C3 Technical Reference Manual > Chapter SPI Controller (SPI).
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.1.3
I2C Controller
ESP32-C3 has an I2C bus interface which is used for I2C master mode or slave mode, depending on your
configuration. The I2C interface supports:
• Standard mode (100 Kbit/s)
• Fast mode (400 Kbit/s)
• Up to 800 Kbit/s (constrained by SCL and SDA pull-up strength)
• 7-bit and 10-bit addressing mode
• Double addressing mode
Espressif Systems
17
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 18 -->

5
Peripherals
• 7-bit broadcast address
For details, see ESP32-C3 Technical Reference Manual > Chapter I2C Controller (I2C).
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.1.4
I2S Controller
ESP32-C3 includes a standard I2S interface. This interface can operate as a master or a slave in full-duplex
mode or half-duplex mode, and can be configured for 8-bit, 16-bit, 24-bit, or 32-bit serial communication. BCK
clock frequency, from 10 kHz up to 40 MHz, is supported.
The I2S interface connects to the GDMA controller. The interface supports TDM PCM, TDM MSB alignment,
TDM standard, and PDM standard.
For details, see ESP32-C3 Technical Reference Manual > Chapter I2S Controller (I2S).
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.1.5
USB Serial/JTAG Controller
ESP32-C3 integrates a USB Serial/JTAG controller. This controller has the following features:
• CDC-ACM virtual serial port and JTAG adapter functionality
• USB 2.0 full speed compliant, capable of up to 12 Mbit/s transfer speed (Note that this controller does
not support the faster 480 Mbit/s high-speed transfer mode)
• Programming in-package/off-package flash
• CPU debugging with compact JTAG instructions
• A full-speed USB PHY integrated in the chip
For details, see ESP32-C3 Technical Reference Manual > Chapter USB Serial/JTAG Controller
(USB_SERIAL_JTAG).
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.1.6
Two-wire Automotive Interface
ESP32-C3 has a TWAI® controller with the following features:
• Compatible with ISO 11898-1 protocol (CAN Specification 2.0)
• Standard frame format (11-bit ID) and extended frame format (29-bit ID)
• Bit rates from 1 Kbit/s to 1 Mbit/s
• Multiple modes of operation: Normal, Listen Only, and Self-Test (no acknowledgment required)
Espressif Systems
18
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 19 -->

5
Peripherals
• 64-byte receive FIFO
• Acceptance filter (single and dual filter modes)
• Error detection and handling: error counters, configurable error interrupt threshold, error code capture,
arbitration lost capture
For details, see ESP32-C3 Technical Reference Manual > Chapter Two-wire Automotive Interface.
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.1.7
LED PWM Controller
The LED PWM controller can generate independent digital waveform on six channels. The LED PWM
controller:
• Can generate digital waveform with configurable periods and duty cycle. The resolution of duty cycle
can be up to 14 bits.
• Has multiple clock sources, including APB clock and external main crystal clock.
• Can operate when the CPU is in Light-sleep mode.
• Supports gradual increase or decrease of duty cycle, which is useful for the LED RGB color-gradient
generator.
For details, see ESP32-C3 Technical Reference Manual > Chapter LED PWM Controller.
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.1.8
Remote Control Peripheral
The Remote Control Peripheral (RMT) supports two channels of infrared remote transmission and two
channels of infrared remote reception. By controlling pulse waveform through software, it supports various
infrared and other single wire protocols. All four channels share a 192 × 32-bit memory block to store transmit
or receive waveform.
For more details, see ESP32-C3 Technical Reference Manual > Chapter Remote Control Peripheral (RMT).
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.2
Analog Signal Processing
This subsection describes components on the chip that sense and process real-world data.
Espressif Systems
19
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 20 -->

5
Peripherals
5.2.2.1
SAR ADC
ESP32-C3 integrates two 12-bit SAR ADCs.
• ADC1 supports measurements on 5 channels, and is factory-calibrated.
• ADC2 supports measurements on 1 channel, and is not factory-calibrated.
Note:
ADC2 of some chip revisions is not operable. For details, please refer to ESP32-C3 Series SoC Errata.
For more details, see ESP32-C3 Technical Reference Manual > Chapter On-Chip Sensors and Analog Signal
Processing.
Pin Assignment
For details, see ESP32-C3 Series Datasheet > Section Peripheral Pin Assignment.
5.2.2.2
Temperature Sensor
The temperature sensor generates a voltage that varies with temperature. The voltage is internally converted
via an ADC into a digital value.
The temperature sensor has a range of –40 °C to 125 °C. It is designed primarily to sense the temperature
changes inside the chip. The temperature value depends on factors like microcontroller clock frequency or
I/O load. Generally, the chip’s internal temperature is higher than the operating ambient temperature.
For more details, see ESP32-C3 Technical Reference Manual > Chapter On-Chip Sensors and Analog Signal
Processing.
Espressif Systems
20
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 21 -->

6
Electrical Characteristics
6
Electrical Characteristics
6.1
Absolute Maximum Ratings
Stresses above those listed in Table 6-1 Absolute Maximum Ratings may cause permanent damage to the
device. These are stress ratings only and functional operation of the device at these or any other conditions
beyond those indicated under Table 6-2 Recommended Operating Conditions is not implied. Exposure to
absolute-maximum-rated conditions for extended periods may affect device reliability.
Table 6-1. Absolute Maximum Ratings
Symbol
Parameter
Min
Max
Unit
VDD33
Power supply voltage
–0.3
3.6
V
6.2
Recommended Operating Conditions
Table 6-2. Recommended Operating Conditions
Symbol
Parameter
Min
Typ
Max
Unit
VDD33
Power supply voltage
3.0
3.3
3.6
V
IV DD
Current delivered by external power supply
0.5
—
—
A
TA
Operating ambient temperature
85 °C version
–40
—
85
°C
105 °C version
105
6.3
DC Characteristics (3.3 V, 25 °C)
Table 6-3. DC Characteristics (3.3 V, 25 °C)
Parameter
Description
Min
Typ
Max
Unit
CIN
Pin capacitance
—
2
—
pF
VIH
High-level input voltage
0.75 × VDD 1
—
VDD 1 + 0.3
V
VIL
Low-level input voltage
–0.3
—
0.25 × VDD 1
V
IIH
High-level input current
—
—
50
nA
IIL
Low-level input current
—
—
50
nA
VOH 2
High-level output voltage
0.8 × VDD 1
—
—
V
VOL 2
Low-level output voltage
—
—
0.1 × VDD 1
V
IOH
High-level source current (VDD 1 = 3.3 V,
VOH >= 2.64 V, PAD_DRIVER = 3)
—
40
—
mA
IOL
Low-level sink current (VDD 1 = 3.3 V, VOL =
0.495 V, PAD_DRIVER = 3)
—
28
—
mA
RP U
Internal weak pull-up resistor
—
45
—
kΩ
RP D
Internal weak pull-down resistor
—
45
—
kΩ
VIH_nRST
Chip reset release voltage (CHIP_EN voltage
is within the specified range)
0.75 × VDD 1
—
VDD 1 + 0.3
V
Cont’d on next page
Espressif Systems
21
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 22 -->

6
Electrical Characteristics
Table 6-3 – cont’d from previous page
Parameter
Description
Min
Typ
Max
Unit
VIL_nRST
Chip reset voltage (CHIP_EN voltage is within
the specified range)
–0.3
—
0.25 × VDD 1
V
1 VDD – voltage from a power pin of a respective power domain.
2 VOH and VOL are measured using high-impedance load.
6.4
Current Consumption Characteristics
6.4.1
Current Consumption in Active Mode
The current consumption measurements are taken with a 3.3 V supply at 25 °C ambient temperature.
TX current consumption is rated at a 100% duty cycle.
RX current consumption is rated when the peripherals are disabled and the CPU idle.
Table 6-4. Current Consumption for Wi-Fi (2.4 GHz) in Active Mode
Work mode
Description
Peak (mA)
Active (RF working)
TX
802.11b, 1 Mbps, @20.5 dBm
350
802.11g, 54 Mbps, @18 dBm
295
802.11n, HT20, MCS7, @17.5 dBm
290
802.11n, HT40, MCS7, @17 dBm
290
RX
802.11b/g/n, HT20
82
802.11n, HT40
84
Table 6-5. Current Consumption for Bluetooth LE in Active Mode
Work Mode
RF Condition
Description
Peak (mA)
Active (RF working)
TX
Bluetooth LE @ 20.0 dBm
340
Bluetooth LE @ 9.0 dBm
190
Bluetooth LE @ 0 dBm
170
Bluetooth LE @ –15.0 dBm
100
RX
Bluetooth LE
86
Espressif Systems
22
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 23 -->

6
Electrical Characteristics
Note:
The content below is excerpted from Section Power Consumption in Other Modes in ESP32-C3 Series Datasheet.
6.4.2
Current Consumption in Other Modes
Table 6-6. Current Consumption in Modem-sleep Mode
Typ
Mode
CPU Frequency
(MHz)
Description
All Peripherals Clocks
Disabled (mA)
All Peripherals Clocks
Enabled (mA) 1
Modem-sleep 2,3
160
CPU is running
23
28
CPU is idle
16
21
80
CPU is running
17
22
CPU is idle
13
18
1 In practice, the current consumption might be different depending on which peripherals are enabled.
2 In Modem-sleep mode, Wi-Fi is clock gated.
3 In Modem-sleep mode, the consumption might be higher when accessing flash. For a flash rated at
80 Mbit/s, in SPI 2-line mode the consumption is 10 mA.
Table 6-7. Current Consumption in Low-Power Modes
Mode
Description
Typ (µA)
Light-sleep
VDD_SPI and Wi-Fi are powered down, and all GPIOs are high-impedance
130
Deep-sleep
RTC timer + RTC memory
5
Power off
CHIP_EN is set to low level, the chip is powered off
1
6.5
Memory Specifications
The data below is sourced from the memory vendor datasheet. These values are guaranteed through design
and/or characterization but are not fully tested in production. Devices are shipped with the memory
erased.
Table 6-8. Flash Specifications
Parameter
Description
Min
Typ
Max
Unit
VCC
Power supply voltage (1.8 V)
1.65
1.80
2.00
V
Power supply voltage (3.3 V)
2.7
3.3
3.6
V
FC
Maximum clock frequency
80
—
—
MHz
—
Program/erase cycles
100,000
—
—
cycles
TRET
Data retention time
20
—
—
years
TP P
Page program time
—
0.8
5
ms
TSE
Sector erase time (4 KB)
—
70
500
ms
TBE1
Block erase time (32 KB)
—
0.2
2
s
TBE2
Block erase time (64 KB)
—
0.3
3
s
Cont’d on next page
Espressif Systems
23
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 24 -->

6
Electrical Characteristics
Table 6-8 – cont’d from previous page
Parameter
Description
Min
Typ
Max
Unit
TCE
Chip erase time (16 Mb)
—
7
20
s
Chip erase time (32 Mb)
—
20
60
s
Chip erase time (64 Mb)
—
25
100
s
Chip erase time (128 Mb)
—
60
200
s
Chip erase time (256 Mb)
—
70
300
s
Espressif Systems
24
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 25 -->

7
RF Characteristics
7
RF Characteristics
This section contains tables with RF characteristics of the Espressif product.
The RF data is measured at the antenna port, where RF cable is connected, including the front-end loss. The
external antennas used for the tests on the modules with external antenna connectors have an impedance of
50 Ω.
Devices should operate in the center frequency range allocated by regional regulatory authorities. The target
center frequency range and the target transmit power are configurable by software. See ESP RF Test Tool and
Test Guide for instructions.
Unless otherwise stated, the RF tests are conducted with a 3.3 V (±5%) supply at 25 ºC ambient temperature.
7.1
Wi-Fi Radio
Table 7-1. Wi-Fi RF Characteristics
Name
Description
Center frequency range of operating channel
2412 ~ 2484 MHz
Wi-Fi wireless standard
IEEE 802.11b/g/n
7.1.1
Wi-Fi RF Transmitter (TX) Characteristics
Table 7-2. TX Power with Spectral Mask and EVM Meeting 802.11 Standards
Min
Typ
Max
Rate
(dBm)
(dBm)
(dBm)
802.11b, 1 Mbps
—
20.5
—
802.11b, 11 Mbps
—
20.5
—
802.11g, 6 Mbps
—
20.0
—
802.11g, 54 Mbps
—
18.0
—
802.11n, HT20, MCS0
—
19.0
—
802.11n, HT20, MCS7
—
17.5
—
802.11n, HT40, MCS0
—
18.5
—
802.11n, HT40, MCS7
—
17.0
—
Table 7-3. TX EVM Test1
Min
Typ
Limit
Rate
(dB)
(dB)
(dB)
802.11b, 1 Mbps, @20.5 dBm
—
–24.5
–10
802.11b, 11 Mbps, @20.5 dBm
—
–25.0
–10
802.11g, 6 Mbps, @20 dBm
—
–23.0
–5
802.11g, 54 Mbps, @18 dBm
—
–28.0
–25
Cont’d on next page
Espressif Systems
25
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 26 -->

7
RF Characteristics
Table 7-3 – cont’d from previous page
Min
Typ
Limit
Rate
(dB)
(dB)
(dB)
802.11n, HT20, MCS0, @19 dBm
—
–23.5
–5
802.11n, HT20, MCS7, @17.5 dBm
—
–30.5
–27
802.11n, HT40, MCS0, @18.5 dBm
—
–26.5
–5
802.11n, HT40, MCS7, @17 dBm
—
–30.5
–27
1 EVM is measured at the corresponding typical TX power provided
in Table 7-2 TX Power with Spectral Mask and EVM Meeting 802.11
Standards above.
7.1.2
Wi-Fi RF Receiver (RX) Characteristics
For RX tests, the PER (packet error rate) limit is 8% for 802.11b, and 10% for 802.11g/n.
Table 7-4. RX Sensitivity
Min
Typ
Max
Rate
(dBm)
(dBm)
(dBm)
802.11b, 1 Mbps
—
–98.0
—
802.11b, 2 Mbps
—
–96.0
—
802.11b, 5.5 Mbps
—
–93.0
—
802.11b, 11 Mbps
—
–88.6
—
802.11g, 6 Mbps
—
–92.8
—
802.11g, 9 Mbps
—
–91.8
—
802.11g, 12 Mbps
—
–90.8
—
802.11g, 18 Mbps
—
–88.4
—
802.11g, 24 Mbps
—
–85.4
—
802.11g, 36 Mbps
—
–82.0
—
802.11g, 48 Mbps
—
–77.8
—
802.11g, 54 Mbps
—
–76.2
—
802.11n, HT20, MCS0
—
–92.6
—
802.11n, HT20, MCS1
—
–90.6
—
802.11n, HT20, MCS2
—
–88.0
—
802.11n, HT20, MCS3
—
–84.8
—
802.11n, HT20, MCS4
—
–81.6
—
802.11n, HT20, MCS5
—
–77.4
—
802.11n, HT20, MCS6
—
–75.6
—
802.11n, HT20, MCS7
—
–74.4
—
802.11n, HT40, MCS0
—
–90.0
—
802.11n, HT40, MCS1
—
–87.6
—
802.11n, HT40, MCS2
—
–84.8
—
802.11n, HT40, MCS3
—
–81.8
—
802.11n, HT40, MCS4
—
–78.4
—
802.11n, HT40, MCS5
—
–74.2
—
Cont’d on next page
Espressif Systems
26
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 27 -->

7
RF Characteristics
Table 7-4 – cont’d from previous page
Min
Typ
Max
Rate
(dBm)
(dBm)
(dBm)
802.11n, HT40, MCS6
—
–72.6
—
802.11n, HT40, MCS7
—
–71.2
—
Table 7-5. Maximum RX Level
Min
Typ
Max
Rate
(dBm)
(dBm)
(dBm)
802.11b, 1 Mbps
—
5
—
802.11b, 11 Mbps
—
5
—
802.11g, 6 Mbps
—
5
—
802.11g, 54 Mbps
—
0
—
802.11n, HT20, MCS0
—
5
—
802.11n, HT20, MCS7
—
0
—
802.11n, HT40, MCS0
—
5
—
802.11n, HT40, MCS7
—
0
—
Table 7-6. RX Adjacent Channel Rejection
Min
Typ
Max
Rate
(dB)
(dB)
(dB)
802.11b, 1 Mbps
—
35
—
802.11b, 11 Mbps
—
35
—
802.11g, 6 Mbps
—
31
—
802.11g, 54 Mbps
—
14
—
802.11n, HT20, MCS0
—
31
—
802.11n, HT20, MCS7
—
13
—
802.11n, HT40, MCS0
—
19
—
802.11n, HT40, MCS7
—
8
—
7.2
Bluetooth 5 (LE) Radio
7.2.1
Bluetooth LE RF Transmitter (TX) Characteristics
Table 7-7. Bluetooth LE RF Characteristics
Name
Description
Center frequency range of operating channel
2402 ~ 2480 MHz
RF transmit power range
–24.0 ~ 20.0 dBm
Espressif Systems
27
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 28 -->

7
RF Characteristics
Table 7-8. Bluetooth LE - Transmitter Characteristics - 1 Mbps
Parameter
Description
Min
Typ
Max
Unit
In-band emissions
F = F0 ± 2 MHz
—
–37.62
—
dBm
F = F0 ± 3 MHz
—
–41.95
—
dBm
F = F0 ± > 3 MHz
—
–44.48
—
dBm
Modulation characteristics
∆f1avg
—
245.00
—
kHz
∆f2max
—
208.00
—
kHz
∆f2avg/∆f1avg
—
0.93
—
—
Carrier frequency offset
—
—
–9.00
—
kHz
Carrier frequency drift
|f0 −fn|n=2, 3, 4, ..k
—
1.17
—
kHz
|f1 −f0|
—
0.30
—
kHz
|fn −fn−5|n=6, 7, 8, ..k
—
4.90
—
kHz
Table 7-9. Bluetooth LE - Transmitter Characteristics - 2 Mbps
Parameter
Description
Min
Typ
Max
Unit
In-band emissions
F = F0 ± 4 MHz
—
–43.55
—
dBm
F = F0 ± 5 MHz
—
–45.26
—
dBm
F = F0 ± > 5 MHz
—
–47.00
—
dBm
Modulation characteristics
∆f1avg
—
497.00
—
kHz
∆f2max
—
398.00
—
kHz
∆f2avg/∆f1avg
—
0.95
—
—
Carrier frequency offset
—
—
–9.00
—
kHz
Carrier frequency drift
|f0 −fn|n=2, 3, 4, ..k
—
0.46
—
kHz
|f1 −f0|
—
0.70
—
kHz
|fn −fn−5|n=6, 7, 8, ..k
—
6.80
—
kHz
Table 7-10. Bluetooth LE - Transmitter Characteristics - 125 Kbps
Parameter
Description
Min
Typ
Max
Unit
In-band emissions
F = F0 ± 2 MHz
—
–37.90
—
dBm
F = F0 ± 3 MHz
—
–41.00
—
dBm
F = F0 ± > 3 MHz
—
–42.50
—
dBm
Modulation characteristics
∆f1avg
—
252.00
—
kHz
∆f1max
—
200.00
—
kHz
Carrier frequency offset
—
—
–13.70
—
kHz
Carrier frequency drift
|f0 −fn|n=1, 2, 3, ..k
—
1.52
—
kHz
|f0 −f3|
—
0.65
—
kHz
|fn −fn−3|n=7, 8, 9, ..k
—
0.70
—
kHz
Espressif Systems
28
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 29 -->

7
RF Characteristics
Table 7-11. Bluetooth LE - Transmitter Characteristics - 500 Kbps
Parameter
Description
Min
Typ
Max
Unit
In-band emissions
F = F0 ± 2 MHz
—
–37.90
—
dBm
F = F0 ± 3 MHz
—
–41.30
—
dBm
F = F0 ± > 3 MHz
—
–42.80
—
dBm
Modulation characteristics
∆f2avg
—
220.00
—
kHz
∆f2max
—
205.00
—
kHz
Carrier frequency offset
—
—
–11.90
—
kHz
Carrier frequency drift
|f0 −fn|n=1, 2, 3, ..k
—
1.37
—
kHz
|f0 −f3|
—
1.09
—
kHz
|fn −fn−3|n=7, 8, 9, ..k
—
0.51
—
kHz
7.2.2
Bluetooth LE RF Receiver (RX) Characteristics
Table 7-12. Bluetooth LE - Receiver Characteristics - 1 Mbps
Parameter
Description
Min
Typ
Max
Unit
Sensitivity @30.8% PER
—
—
–96
—
dBm
Maximum received signal @30.8% PER
—
—
10
—
dBm
Co-channel C/I
—
—
8
—
dB
Adjacent channel selectivity C/I
F = F0 + 1 MHz
—
–4
—
dB
F = F0 – 1 MHz
—
–3
—
dB
F = F0 + 2 MHz
—
–32
—
dB
F = F0 – 2 MHz
—
–36
—
dB
F ≥F0 + 3 MHz(1)
—
—
—
dB
F ≤F0 – 3 MHz
—
–39
—
dB
Image frequency
—
—
–29
—
dB
Adjacent channel to image frequency
F = Fimage + 1 MHz
—
–38
—
dB
F = Fimage – 1 MHz
—
–34
—
dB
Out-of-band blocking performance
30 MHz ~ 2000 MHz
—
–9
—
dBm
2003 MHz ~ 2399 MHz
—
–18
—
dBm
2484 MHz ~ 2997 MHz
—
–16
—
dBm
3000 MHz ~ 12.75 GHz
—
–6
—
dBm
Intermodulation
—
—
–44
—
dBm
1 Refer to the value of Adjacent channel to image frequency when F = Fimage – 1 MHz.
Espressif Systems
29
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 30 -->

7
RF Characteristics
Table 7-13. Bluetooth LE - Receiver Characteristics - 2 Mbps
Parameter
Description
Min
Typ
Max
Unit
Sensitivity @30.8% PER
—
—
–93
—
dBm
Maximum received signal @30.8% PER
—
—
0
—
dBm
Co-channel C/I
—
—
10
—
dB
Adjacent channel selectivity C/I
F = F0 + 2 MHz
—
–7
—
dB
F = F0 – 2 MHz
—
–7
—
dB
F = F0 + 4 MHz(1)
—
—
—
dB
F = F0 – 4 MHz
—
–34
—
dB
F ≥F0 + 6 MHz
—
–39
—
dB
F ≤F0 – 6 MHz
—
–39
—
dB
Image frequency
—
—
–27
—
dB
Adjacent channel to image frequency
F = Fimage + 2 MHz
—
–39
—
dB
F = Fimage – 2 MHz(2)
—
—
—
dB
Out-of-band blocking performance
30 MHz ~ 2000 MHz
—
–17
—
dBm
2003 MHz ~ 2399 MHz
—
–19
—
dBm
2484 MHz ~ 2997 MHz
—
–16
—
dBm
3000 MHz ~ 12.75 GHz
—
–22
—
dBm
Intermodulation
—
—
–40
—
dBm
1 Refer to the value of Image frequency.
2 Refer to the value of Adjacent channel selectivity C/I when F = F0 + 2 MHz.
Table 7-14. Bluetooth LE - Receiver Characteristics - 125 Kbps
Parameter
Description
Min
Typ
Max
Unit
Sensitivity @30.8% PER
—
—
–104
—
dBm
Maximum received signal @30.8% PER
—
—
10
—
dBm
Co-channel C/I
—
—
2
—
dB
Adjacent channel selectivity C/I
F = F0 + 1 MHz
—
–6
—
dB
F = F0 – 1 MHz
—
–5
—
dB
F = F0 + 2 MHz
—
–40
—
dB
F = F0 – 2 MHz
—
–42
—
dB
F ≥F0 + 3 MHz(1)
—
—
—
dB
F ≤F0 – 3 MHz
—
–46
—
dB
Image frequency
—
—
–34
—
dB
Adjacent channel to image frequency
F = Fimage + 1 MHz
—
–44
—
dB
F = Fimage – 1 MHz
—
–37
—
dB
1 Refer to the value of Adjacent channel to image frequency when F = Fimage – 1 MHz.
Espressif Systems
30
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 31 -->

7
RF Characteristics
Table 7-15. Bluetooth LE - Receiver Characteristics - 500 Kbps
Parameter
Description
Min
Typ
Max
Unit
Sensitivity @30.8% PER
—
—
–99
—
dBm
Maximum received signal @30.8% PER
—
—
10
—
dBm
Co-channel C/I
—
—
3
—
dB
Adjacent channel selectivity C/I
F = F0 + 1 MHz
—
–5
—
dB
F = F0 – 1 MHz
—
–7
—
dB
F = F0 + 2 MHz
—
–39
—
dB
F = F0 – 2 MHz
—
–40
—
dB
F ≥F0 + 3 MHz(1)
—
—
—
dB
F ≤F0 – 3 MHz
—
–40
—
dB
Image frequency
—
—
–34
—
dB
Adjacent channel to image frequency
F = Fimage + 1 MHz
—
–43
—
dB
F = Fimage – 1 MHz
—
–38
—
dB
1 Refer to the value of Adjacent channel to image frequency when F = Fimage – 1 MHz.
Espressif Systems
31
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 32 -->

8
Module Schematics
8
Module Schematics
This is the reference design of the module.
The values of C8, L2 and C9
vary with the actual PCB board.
The values of C1 and C2 vary with
the selection of the crystal.
The value of R1 varies with the
actual PCB board. R1 could be a
resistor or inductor, the initial
value is suggested to be 24 nH.
ESP32-C3-MINI-1(pin-out)
NC: No component.
50 ohm Impedance Control
GND
VDD33
GND
GND
GND
GND
GND
GND
GND
GND
VDD33
GND
GND
GND
VDD33
VDD33
GND
GND
GND
GND
VDD_SPI
VDD33
GND
GND
GND
VDD33
U2
ESP32-C3FH4
LNA_IN
1
VDD3P3
2
VDD3P3
3
XTAL_32K_P
4
XTAL_32K_N
5
GPIO2
6
CHIP_EN
7
MTMS
9
MTDI
10
VDD3P3_RTC
11
MTCK
12
MTDO
13
GPIO8
14
GPIO9
15
GPIO10
16
VDD3P3_CPU
17
VDD_SPI
18
SPIHD
19
SPIWP
20
SPICS0
21
SPICLK
22
SPID
23
SPIQ
24
U0RXD
27
U0TXD
28
XTAL_N
29
XTAL_P
30
GND
33
GPIO3
8
VDDA
32
VDDA
31
GPIO19
26
GPIO18
25
ESP32-C3-MINI-1
GND
1
3V3
3
IO9
23
NC
4
IO2
5
IO3
6
NC
7
NC
9
NC
10
NC
15
IO10
16
NC
17
IO4
18
IO5
19
NC
32
TXD0
31
RXD0
30
NC
34
NC
33
IO18
26
NC
29
NC
28
IO19
27
IO7
21
IO8
22
IO0
12
IO1
13
GND
52
IO6
20
NC
35
NC
24
EPAD
49
GND
2
GND
53
GND
51
GND
50
EN
8
GND
36
GND
37
GND
38
GND
39
GND
40
GND
41
GND
42
GND
43
GND
44
GND
45
GND
46
GND
47
GND
48
GND
14
GND
11
NC
25
C6
0.1uF
ANT1
PCB_ANT
1
2
C8
TBD
U1
40MHz(±10ppm)
XIN
1
GND
2
XOUT
3
GND
4
D1
ESD
C5
10uF
C11
1uF
R1
0
C7
0.1uF
C4
10nF
C2
TBD
L1
2.0nH
C3
1uF
C10
0.1uF
R2
499
L2
TBD
C12
0.1uF
C9
TBD
C1
TBD
R8
10K(NC)
GPIO19
CHIP_EN
GPIO4
GPIO5
GPIO6
GPIO7
GPIO8
U0RXD
GPIO18
LNA_IN
GPIO9
GPIO10
GPIO0
GPIO1
SPICS0
GPIO2
GPIO3
RF_ANT
U0TXD
GPIO2
GPIO3
CHIP_EN
GPIO1
GPIO0
GPIO10
GPIO6
GPIO7
GPIO8
GPIO9
GPIO18
GPIO19
U0RXD
U0TXD
GPIO4
GPIO5
Figure 8-1. ESP32-C3-MINI-1 Schematics
Espressif Systems
32
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 33 -->

8
Module Schematics
The values of C8, L2 and C9
vary with the actual PCB board.
The values of C1 and C2 vary with
the selection of the crystal.
The value of R1 varies with the
actual PCB board. R1 could be a
resistor or inductor, the initial
value is suggested to be 24 nH.
ESP32-C3-MINI-1U(pin-out)
NC: No component.
50 ohm Impedance Control
GND
VDD33
GND
GND
GND
GND
GND
GND
GND
GND
VDD33
GND
GND
VDD33
VDD33
GND
GND
GND
GND
VDD_SPI
VDD33
GND
GND
GND
GND
VDD33
C1
TBD
D1
ESD
C9
TBD
R8
10K(NC)
ANT1
CONN
1
4
2
3
ESP32-C3-MINI-1U
GND
1
3V3
3
IO9
23
NC
4
IO2
5
IO3
6
NC
7
NC
9
NC
10
NC
15
IO10
16
NC
17
IO4
18
IO5
19
NC
32
TXD0
31
RXD0
30
NC
34
NC
33
IO18
26
NC
29
NC
28
IO19
27
IO7
21
IO8
22
IO0
12
IO1
13
GND
52
IO6
20
NC
35
NC
24
EPAD
49
GND
2
GND
53
GND
51
GND
50
EN
8
GND
36
GND
37
GND
38
GND
39
GND
40
GND
41
GND
42
GND
43
GND
44
GND
45
GND
46
GND
47
GND
48
GND
14
GND
11
NC
25
R1
0
C12
0.1uF
C3
1uF
C10
0.1uF
R2
499
C8
TBD
C2
TBD
L1
2.0nH
C6
0.1uF
C5
10uF
L2
TBD
C7
0.1uF
C4
10nF
U2
ESP32-C3FH4
LNA_IN
1
VDD3P3
2
VDD3P3
3
XTAL_32K_P
4
XTAL_32K_N
5
GPIO2
6
CHIP_EN
7
MTMS
9
MTDI
10
VDD3P3_RTC
11
MTCK
12
MTDO
13
GPIO8
14
GPIO9
15
GPIO10
16
VDD3P3_CPU
17
VDD_SPI
18
SPIHD
19
SPIWP
20
SPICS0
21
SPICLK
22
SPID
23
SPIQ
24
U0RXD
27
U0TXD
28
XTAL_N
29
XTAL_P
30
GND
33
GPIO3
8
VDDA
32
VDDA
31
GPIO19
26
GPIO18
25
C11
1uF
U1
40MHz(±10ppm)
XIN
1
GND
2
XOUT
3
GND
4
GPIO19
CHIP_EN
GPIO4
GPIO5
GPIO6
GPIO7
GPIO8
U0RXD
GPIO18
LNA_IN
GPIO9
GPIO10
GPIO0
GPIO1
SPICS0
GPIO2
GPIO3
RF_ANT
U0TXD
GPIO2
GPIO3
CHIP_EN
GPIO1
GPIO0
GPIO10
GPIO6
GPIO7
GPIO8
GPIO9
GPIO18
GPIO19
U0RXD
U0TXD
GPIO4
GPIO5
Figure 8-2. ESP32-C3-MINI-1U Schematics
Espressif Systems
33
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 34 -->

9
Peripheral Schematics
9
Peripheral Schematics
This is the typical application circuit of the module connected with peripheral components (for example,
power supply, antenna, reset button, JTAG interface, and UART interface).
NC: No component.
ESP32-C3-MINI-1
ESP32-C3-MINI-1U
IO4
IO5
IO6
IO7
IO8
IO2
IO3
EN
IO9
IO0
IO1
IO10
RXD0
TXD0
EN
TMS
TDI
TCK
TDO
IO19
IO18
USB_D-
USB_D+
GND
VDD33
GND
GND
GND
GND
GND
VDD33
GND
GND
GND
GND
VDD33
GND
C3
TBD
R7
NC
C6
TBD
C4
0.1uF
R2
0
R9
10K
JP2
Boot Option
1
1
2
2
U1
GND
1
3V3
3
IO9
23
NC
4
IO2
5
IO3
6
NC
7
NC
9
NC
10
NC
15
IO10
16
NC
17
IO4
18
IO5
19
NC
32
TXD0
31
RXD0
30
NC
34
NC
33
IO18
26
NC
29
NC
28
IO19
27
IO7
21
IO8
22
IO0
12
IO1
13
GND
52
IO6
20
NC
35
NC
24
EPAD
49
GND
2
GND
53
GND
51
GND
50
EN
8
GND
36
GND
37
GND
38
GND
39
GND
40
GND
41
GND
42
GND
43
GND
44
GND
45
GND
46
GND
47
GND
48
GND
14
GND
11
NC
25
R6
0
JP3
USB
1
1
2
2
C1
10uF
C8
12pF(NC)
C2
0.1uF
C7
12pF(NC)
SW1
JP4
UART
1
1
2
2
3
3
4
4
X1
32.768kHz(NC)
1
2
JP1
JTAG
1
1
2
2
3
3
4
4
R6
0(NC)
R8
10K
R5
0(NC)
R1
TBD
R4
0
C5
TBD
Figure 9-1. Peripheral Schematics
• Soldering the EPAD to the ground of the base board is not a must, however, it can optimize thermal
performance. If you choose to solder it, please apply the correct amount of soldering paste. Too much
soldering paste may increase the gap between the module and the baseboard. As a result, the adhesion
between other pins and the baseboard may be poor.
• To ensure that the power supply to the ESP32-C3 chip is stable during power-up, it is advised to add an
RC delay circuit at the EN pin. The recommended setting for the RC delay circuit is usually R = 10 kΩand
C = 1 µF. However, specific parameters should be adjusted based on the power-up timing of the module
and the power-up and reset sequence timing of the chip. For ESP32-C3’s power-up and reset sequence
timing diagram, please refer Section 4.3 Chip Power-up and Reset.
• UART0 is used to download firmware and log output. When using the AT firmware, note that the UART
GPIO is already configured. It is recommended to use the default configuration. Please refer to
ESP-AT User Guide for ESP32-C3 > Section Hardware Connection.
Espressif Systems
34
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 35 -->

10
Physical Dimensions
10
Physical Dimensions
10.1
Module Dimensions
5.4
16.6±0.15
0.8
13.2±0.15
Top view
Side view
Bottom view
2.4±0.15
11.2
0.6
1.45
1.45
8.4
9.2
10
11.2
12.6
6.8
7.6
8.4
9
10.6
0.62
0.62
11.95
9.95
0.6
5.4
9.2
11
Ø0.5
Unit: mm
Figure 10-1. ESP32-C3-MINI-1 Physical Dimensions
5.4
12.5±0.15
0.8
13.2±0.15
Top view
Side view
Bottom view
0.6
1.45
1.45
8.4
9.2
10
11.2
12.6
6.8
7.6
8.4
9
10.6
12.25
0.6
5.4
9.2
11
Unit: mm
1.55
1.7
8.7
0.47
0.48
9.18
11.55
2.4±0.15
0.85
5.6
Figure 10-2. ESP32-C3-MINI-1U Physical Dimensions
Note:
For information about tape, reel, and product marking, please refer to ESP32-C3 Module Packaging Information.
Espressif Systems
35
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 36 -->

10
Physical Dimensions
10.2
Dimensions of External Antenna Connector
ESP32-C3-MINI-1U uses the third generation external antenna connector as shown in Figure 10-3 Dimensions
of External Antenna Connector. This connector is compatible with the following connectors:
• W.FL Series connector from Hirose
• MHF III connector from I-PEX
• AMC connector from Amphenol
SECTION: A-A
SCALE: 1:1
A
1.7
1.7
0.85
2.05±0.10
1.40
A
0.10
0.57
INSULATION RESISTANCE: 500MOHM Min.
DIELECTRIC WITHSTANDING VOLTAGE: 200V AC FOR 1MINUTE;
CONTACT MATERIAL: COPPER ALLOY, GOLD PLATED ALL OVER;
PERFORMANCE:
CONTACT RESISTANCE: 20mOHM Max.
HOUSING MATERIAL: THERMOPLASTIC, WHITE, UL 94V-0;
SHELL MATERIAL: COPPER ALLOY, GOLD PLATED ALL OVER;
CONTACT
GROUND CONTACT
2.00±0.10
Unit: mm
Tolerance: +/-0.1 mm
HOUSING
CONTACT
SHELL
Figure 10-3. Dimensions of External Antenna Connector
The external antenna used for ESP32-C3-MINI-1U during certification testing is the third generation monopole
antenna, with material code TFPD08H10060011.
The module does not include an external antenna upon shipment. If needed, select a suitable external
Espressif Systems
36
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 37 -->

10
Physical Dimensions
antenna based on the product’s usage environment and performance requirements.
It is recommended to select an antenna that meets the following requirements:
• 2.4 GHz band
• 50 Ωimpedance
• The maximum gain does not exceed 2.33 dBi, the gain of the antenna used for certification
• The connector matches the specifications shown in Figure 10-3 Dimensions of External Antenna
Connector
Note:
If you use an external antenna of a different type or gain, additional testing, such as EMC, may be required beyond the
existing antenna test reports for Espressif modules. Specific requirements depend on the certification type.
Espressif Systems
37
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 38 -->

11
PCB Layout Recommendations
11
PCB Layout Recommendations
11.1
PCB Land Pattern
This section provides the following resources for your reference:
• Figures for recommended PCB land patterns with all the dimensions needed for PCB design. See Figure
11-1 ESP32-C3-MINI-1 Recommended PCB Land Pattern and Figure 11-2 ESP32-C3-MINI-1U
Recommended PCB Land Pattern.
• Source files of recommended PCB land patterns to measure dimensions not covered in Figure 11-1 and
Figure 11-2. You can view the source files for ESP32-C3-MINI-1 and ESP32-C3-MINI-1U with Autodesk
Viewer.
• 3D models of ESP32-C3-MINI-1 and ESP32-C3-MINI-1U. Please make sure that you download the 3D
model file in .STEP format. Beware that some browsers might add .txt.
1.6
Antenna Area
Pin 1
11.2
0.6
9.9
5.4
11.9
1.6
13.2
16.6
1.45
5.4
1.45
0.6
11.8
9.8
Unit: mm
Pad
48 x 0.4
48 x 0.8
4 x 0.7
4 x 0.7
0.8
Via for thermal pad
Figure 11-1. ESP32-C3-MINI-1 Recommended PCB Land Pattern
Espressif Systems
38
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 39 -->

11
PCB Layout Recommendations
1.6
Pin 1
12.5
0.6
9.9
5.4
11.9
1.6
13.2
1.45
5.4
1.45
0.6
11.8
9.8
48 x 0.4
48 x 0.8
4 x 0.7
4 x 0.7
0.8
5.6
Unit: mm
Pad
Via for thermal pad
Figure 11-2. ESP32-C3-MINI-1U Recommended PCB Land Pattern
11.2
Module Placement for PCB Design
If module-on-board design is adopted, attention should be paid while positioning the module on the base
board. The interference of the base board on the module’s antenna performance should be minimized.
For details about module placement for PCB design, please refer to ESP32-C3 Hardware Design Guidelines >
Section General Principles of PCB Layout for Modules.
Espressif Systems
39
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 40 -->

12
Product Handling
12
Product Handling
12.1
Storage Conditions
The products sealed in moisture barrier bags (MBB) should be stored in a non-condensing atmospheric
environment of < 40 °C and 90%RH. The module is rated at the moisture sensitivity level (MSL) of 3.
After unpacking, the module must be soldered within 168 hours with the factory conditions 25±5 °C and
60%RH. If the above conditions are not met, the module needs to be baked.
12.2
Electrostatic Discharge (ESD)
• Human body model (HBM): ±2000 V
• Charged-device model (CDM): ±500 V
12.3
Reflow Profile
Solder the module in a single reflow.
50
100
0
150
200
250
200
100
50
150
250

Time (s)
217
25
Preheating
150 – 200 °C
60 – 120 s
Ramp-up
25 – 150 °C
60 – 90 s
1 – 3 °C/s
Soldering
＞ 217 °C
60 – 90 s
Peak temperature: 235 – 250 °C
Peak time: 30 – 70 s
Soldering time: ＞ 30 s
Solder: Sn-Ag-Cu (SAC305) lead-free solder
Temperature (°C)
180
230
Cooling
＜ 180 °C
–5 ~ –1 °C/s
Figure 12-1. Reflow Profile
Espressif Systems
40
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 41 -->

12
Product Handling
12.4
Ultrasonic Vibration
Avoid exposing Espressif modules to vibration from ultrasonic equipment, such as ultrasonic welders or
ultrasonic cleaners. This vibration may induce resonance in the in-module crystal and lead to its malfunction or
even failure. As a consequence, the module may stop working or its performance may deteriorate.
Espressif Systems
41
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 42 -->

Datasheet Versioning
Datasheet Versioning
Datasheet
Version
Status
Watermark
Definition
v0.1 ~ v0.5
(excluding v0.5)
Draft
Confidential
This datasheet is under development for products
in the design stage. Specifications may change
without prior notice.
v0.5 ~ v1.0
(excluding v1.0)
Preliminary
release
Preliminary
This datasheet is actively updated for products in
the verification stage. Specifications may change
before mass production, and the changes will be
documentation in the datasheet’s Revision History.
v1.0 and higher
Official release
—
This datasheet is publicly released for products in
mass production. Specifications are finalized, and
major changes will be communicated via Product
Change Notifications (PCN).
Any version
—
Not
Recommended
for New Design
(NRND)1
This datasheet is updated less frequently for
products not recommended for new designs.
Any version
—
End of Life
(EOL)2
This datasheet is no longer mtained for products
that have reached end of life.
1 Watermark will be added to the datasheet title page only when all the product variants covered by this
datasheet are not recommended for new designs.
2 Watermark will be added to the datasheet title page only when all the product variants covered by this
datasheet have reached end of life.
Espressif Systems
42
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 43 -->

Related Documentation and Resources
Related Documentation and Resources
Related Documentation
• ESP32-C3 Series Datasheet- Specifications of the ESP32-C3 hardware.
• ESP32-C3 Technical Reference Manual – Detailed information on how to use the ESP32-C3 memory and periph-
erals.
• ESP32-C3 Hardware Design Guidelines – Guidelines on how to integrate the ESP32-C3 into your hardware prod-
uct.
• ESP32-C3 Series SoC Errata – Descriptions of known errors in ESP32-C3 series of SoCs.
• Certificates
https://espressif.com/en/support/documents/certificates
• ESP32-C3 Product/Process Change Notifications (PCN)
https://espressif.com/en/support/documents/pcns?keys=ESP32-C3
• ESP32-C3 Advisories – Information on security, bugs, compatibility, component reliability.
https://espressif.com/en/support/documents/advisories?keys=ESP32-C3
• Documentation Updates and Update Notification Subscription
https://espressif.com/en/support/download/documents
Developer Zone
• ESP-IDF Programming Guide for ESP32-C3 – Extensive documentation for the ESP-IDF development framework.
• ESP-IDF and other development frameworks on GitHub.
https://github.com/espressif
• ESP32 BBS Forum – Engineer-to-Engineer (E2E) Community for Espressif products where you can post questions,
share knowledge, explore ideas, and help solve problems with fellow engineers.
https://esp32.com/
• ESP-FAQ – A summary document of frequently asked questions released by Espressif.
https://espressif.com/projects/esp-faq/en/latest/index.html
• The ESP Journal – Best Practices, Articles, and Notes from Espressif folks.
https://blog.espressif.com/
• See the tabs SDKs and Demos, Apps, Tools, AT Firmware.
https://espressif.com/en/support/download/sdks-demos
Products
• ESP32-C3 Series SoCs – Browse through all ESP32-C3 SoCs.
https://espressif.com/en/products/socs?id=ESP32-C3
• ESP32-C3 Series Modules – Browse through all ESP32-C3-based modules.
https://espressif.com/en/products/modules?id=ESP32-C3
• ESP32-C3 Series DevKits – Browse through all ESP32-C3-based devkits.
https://espressif.com/en/products/devkits?id=ESP32-C3
• ESP Product Selector – Find an Espressif hardware product suitable for your needs by comparing or applying filters.
https://products.espressif.com/#/product-selector?language=en
Espressif Systems
43
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 44 -->

Related Documentation and Resources
Contact Us
• See the tabs Sales Questions, Technical Enquiries, Circuit Schematic & PCB Design Review, Get Samples
(Online stores), Become Our Supplier, Comments & Suggestions.
https://espressif.com/en/contact-us/sales-questions
Espressif Systems
44
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 45 -->

Revision History
Revision History
Date
Version
Release notes
2026-05-06
v2.2
• Added ESP32-C3-MINI-1-H8X
• Table 1-1 ESP32-C3-MINI-1 (ANT) Series Comparison1 and Table 1-
2 ESP32-C3-MINI-1U (CONN) Series Comparison: Updated ”Ordering
Code” to ”Part Number”
2025-07-14
v2.1
• Added Section 4.3 Chip Power-up and Reset
• Added Section 6.5 Memory Specifications
• Section 9 Peripheral Schematics: Added a note about AT communication
using UART0
• Section 10.2 Dimensions of External Antenna Connector: Added the ex-
ternal antenna information for certification
• Added Datasheet Versioning
2025-04-14
v2.0
According to updates in Compatibility Advisory for ESP32-C3 Chip Revision v1.1,
updated SRAM space in note 6 for Table ESP32-C3-MINI-1U (CONN) Series
Comparison
2025-01-24
v1.9
Updated chip in ESP32-C3-MINI-1-N4 and ESP32-C3-MINI-1U-N4 from ESP32-
C3FN4 to ESP32-C3FH4
2024-11-20
v1.8
• Table 1-1 ESP32-C3-MINI-1 (ANT) Series Comparison1 and 1-2 ESP32-C3-
MINI-1U (CONN) Series Comparison:
– Added the ESP32-C3-MINI-1-N4X, ESP32-C3-MINI-1U-N4X, and
ESP32-C3-MINI-1U-H4X variants
– Marked the ESP32-C3-MINI-1U-N4 and ESP32-C3-MINI-1U-H4 vari-
ants as Not Recommended for New Designs (NRND)
• Added Table 6-5 Current Consumption for Bluetooth LE in Active Mode
2024-09-19
v1.7
• Table 1-2 ESP32-C3-MINI-1U (CONN) Series Comparison: Updated flash
program/erase cycles, data retention time (note 4) and maximum clock
frequency (note 7)
• Improved the wording and structure of following sections:
– Updated Section ”Strapping Pins” and renamed to 4 Boot Configu-
rations
– Added Chapter 5 Peripherals
– Updated Table ”Wi-Fi RF Standards” and renamed to ”Wi-Fi RF Char-
acteristics”
– Added Section 11.2 Module Placement for PCB Design
– Optimized Figure 12-1 Reflow Profile
Cont’d on next page
Espressif Systems
45
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 46 -->

Revision History
Cont’d from previous page
Date
Version
Release notes
2024-07-29
v1.6
Added Compatibility Advisory for ESP32-C3 Chip Revision v1.1 to the notes of
Table ESP32-C3-MINI-1U (CONN) Series Comparison
2024-06-05
v1.5
• Added new variant ESP32-C3-MINI-1-H4X
• Marked the ESP32-C3-MINI-1-N4, ESP32-C3-MINI-1-H4, and ESP32-C3-
MINI-1-H4-AZ variants as Not Recommended for New Designs (NRND)
2024-05-15
v1.4
• Updated note 5 of Table ESP32-C3-MINI-1 (ANT) Series Comparison1 and
Table ESP32-C3-MINI-1U (CONN) Series Comparison
• Updated the formatting of Section 4 Boot Configurations
• Updated the maximum value of ”RF power control range” to 20 dBm in
Table Bluetooth LE RF Characteristics
• Updated the note about solder paste in Section 9 Peripheral Schematics
• Updated the markings of dimensions and thermal pad vias in Section 11.1
PCB Land Pattern
2022-11-08
v1.3
• Added a new variant ESP32-C3-MINI-1-H4-AZ
• Changed Table Ordering Information to Table ESP32-C3-MINI-1 (ANT) Se-
ries Comparison1 and Table ESP32-C3-MINI-1U (CONN) Series Compari-
son
• Updated test condition descriptions and data in Section 6.4 Current Con-
sumption Characteristics
• Updated ”RF power control range” in Table Bluetooth LE RF Characteris-
tics
• Added descriptions in Section 11.1 PCB Land Pattern
2022-06-30
v1.2
Added Section 12.4 Ultrasonic Vibration
2022-05-16
v1.1
• Added a note under Table Ordering Information
• Updated Chapter 8 Module Schematics
2021-06-21
v1.0
• Updated module description on the title page
• Deleted Section ”About This Document”
• Restructured Section 1.1 Features
• Added ordering code in Table Ordering Information
• Added descriptions in Section 10.2 Dimensions of External Antenna Con-
nector
• Updated Section ”Learning Resources” and renamed to Related Docu-
mentation and Resources
• Replaced ”chip family” with ”chip series” following Espressif’s taxonomy
2021-04-16
v0.7
Added information about ESP32-C3-MINI-1U module
Cont’d on next page
Espressif Systems
46
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 47 -->

Revision History
Cont’d from previous page
Date
Version
Release notes
2021-02-22
v0.6
Updated the value of C7 to 0.1 µF in Chapter 8 Module Schematics
2021-02-05
v0.5
Preliminary release
Espressif Systems
47
Submit Documentation Feedback
ESP32-C3-MINI-1 & MINI-1U Datasheet v2.2

<!-- Page 48 -->

Disclaimer and Copyright Notice
Information in this document, including URL references, is subject to change without notice.
ALL THIRD PARTY’S INFORMATION IN THIS DOCUMENT IS PROVIDED AS IS WITH NO WARRANTIES TO ITS AUTHENTICITY AND
ACCURACY.
NO WARRANTY IS PROVIDED TO THIS DOCUMENT FOR ITS MERCHANTABILITY, NON-INFRINGEMENT, FITNESS FOR ANY PARTICULAR
PURPOSE, NOR DOES ANY WARRANTY OTHERWISE ARISING OUT OF ANY PROPOSAL, SPECIFICATION OR SAMPLE.
All liability, including liability for infringement of any proprietary rights, relating to use of information in this document is disclaimed. No
licenses express or implied, by estoppel or otherwise, to any intellectual property rights are granted herein.
The Wi-Fi Alliance Member logo is a trademark of the Wi-Fi Alliance. The Bluetooth logo is a registered trademark of Bluetooth SIG.
All trade names, trademarks and registered trademarks mentioned in this document are property of their respective owners, and are
hereby acknowledged.
Copyright © 2026 Espressif Systems (Shanghai) Co., Ltd. All rights reserved.
www.espressif.com


---

# 2. ESP32-C3 Hardware Design Guidelines

> **Source file:** `esp-hardware-design-guidelines-en-master-esp32c3.pdf`  
> Espressif Systems — ESP32-C3 series hardware design guidelines

<!-- Page 1 -->

ESP32-C3
Hardware Design Guidelines
Release master
Espressif Systems
Jul 06, 2026

<!-- Page 2 -->

Table of contents
Table of contents
i
1
Latest Version of This Document
3
1.1
About This Document
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3
1.1.1
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3
1.1.2
Latest Version of This Document . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3
1.2
Product Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
3
1.3
Schematic Checklist
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
4
1.3.1
Overview
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
4
1.3.2
Power Supply . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
5
1.3.3
Chip Power-up and Reset Timing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
6
1.3.4
Flash . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
7
1.3.5
Clock Source
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
7
1.3.6
RF . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
9
1.3.7
UART . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
11
1.3.8
SPI
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
11
1.3.9
Strapping Pins . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
11
1.3.10
GPIO
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
13
1.3.11
ADC . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
14
1.3.12
USB . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
14
1.4
PCB Layout Design . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
15
1.4.1
General Principles of PCB Layout for the Chip . . . . . . . . . . . . . . . . . . . . . . .
15
1.4.2
Power Supply . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
15
1.4.3
Crystal . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
17
1.4.4
RF . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
18
1.4.5
Flash . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
19
1.4.6
UART . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
20
1.4.7
General Principles of PCB Layout for Modules (Positioning a Module on a Base Board)
.
21
1.4.8
USB . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
22
1.4.9
Typical Layout Problems and Solutions . . . . . . . . . . . . . . . . . . . . . . . . . . .
22
1.5
Download Guidelines . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
23
1.6
Related Documentation and Resources . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
24
1.6.1
ESP32-C3 Modules . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
24
1.6.2
ESP32-C3 Development Boards
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
25
1.6.3
Other Related Documentation and Resources . . . . . . . . . . . . . . . . . . . . . . . .
25
1.7
Glossary
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
25
1.8
Revision History
. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
25
1.9
Disclaimer and Copyright Notice . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
26
i

<!-- Page 3 -->

ii

<!-- Page 4 -->

Table of contents
This document provides guidelines for the ESP32-C3 SoC.
Schematic Checklist
PCB Layout Design
Download Guidelines
Resources
Espressif Systems
1
Submit Document Feedback
Release master

<!-- Page 5 -->

Table of contents
Espressif Systems
2
Submit Document Feedback
Release master

<!-- Page 6 -->

Chapter 1
Latest Version of This Document
Check the link to make sure that you use the latest version of this document: https://docs.espressif.com/projects/
esp-hardware-design-guidelines/en/latest/esp32c3/index.html
1.1
About This Document
1.1.1
Introduction
The hardware design guidelines advise on how to integrate ESP32-C3 into a product. These guidelines will help to
achieve optimal performance of your product, ensuring technical accuracy and adherence to Espressif’s standards.
The guidelines are intended for hardware and application engineers.
The document assumes that you possess a certain level of familiarity with the ESP32-C3 SoC. In case you lack prior
knowledge, we recommend utilizing this document in conjunction with the ESP32-C3 Series Datasheet.
1.1.2
Latest Version of This Document
Check the link to make sure that you use the latest version of this document: https://docs.espressif.com/projects/
esp-hardware-design-guidelines/en/latest/esp32c3/index.html
1.2
Product Overview
ESP32-C3 is a system on a chip that integrates the following features:
• Wi-Fi (2.4 GHz band)
• Bluetooth® 5 (LE)
• High performance 32-bit RISC-V single-core processor
• Multiple peripherals
• Built-in security hardware
Powered by 40 nm technology, ESP32-C3 provides a robust, highly-integrated platform, which helps meet the con-
tinuous demands for efficient power usage, compact design, security, high performance, and reliability. Typical
application scenarios for ESP32-C3 include:
• Smart Home
3

<!-- Page 7 -->

Chapter 1. Latest Version of This Document
• Industrial Automation
• Health Care
• Consumer Electronics
• Smart Agriculture
• POS Machines
• Service Robot
• Audio Devices
• Generic Low-power IoT Sensor Hubs
• Generic Low-power IoT Data Loggers
For more information about ESP32-C3, please refer to ESP32-C3 Series Datasheet.
Note:
Unless otherwise specified, “ESP32-C3”used in this document refers to the series of chips, instead of a
specific chip variant.
1.3
Schematic Checklist
1.3.1
Overview
The integrated circuitry of ESP32-C3 requires only 20 electrical components (resistors, capacitors, and inductors)
and a crystal, as well as an SPI flash. The high integration of ESP32-C3 allows for simple peripheral circuit design.
This chapter details the schematic design of ESP32-C3.
The following figure shows a reference schematic design of ESP32-C3. It can be used as the basis of your schematic
design.
Fig. 1: ESP32-C3 Reference Schematic
Espressif Systems
4
Submit Document Feedback
Release master

<!-- Page 8 -->

Chapter 1. Latest Version of This Document
Any basic ESP32-C3 circuit design may be broken down into the following major building blocks:
• Power supply
• Chip power-up and reset timing
• Flash
• Clock source
• RF
• UART
• SPI
• Strapping pins
• GPIO
• ADC
• USB
The rest of this chapter details the specifics of circuit design for each of these sections.
1.3.2
Power Supply
The general recommendations for power supply design are:
• When using a single power supply, the recommended power supply voltage is 3.3 V and the output current is
no less than 500 mA.
• It is suggested to add an ESD protection diode and at least 10 μF capacitor at the main power entrance (where
the external power supply enters the PCB).
The power scheme is shown in ESP32-C3 Series Datasheet > Figure ESP32-C3 Power Scheme.
More information about power supply pins can be found in ESP32-C3 Series Datasheet > Section Power Supply.
Digital Power Supply
ESP32-C3 has pin17 VDD3P3_CPU as the digital power supply pin(s) working in a voltage range of 3.0 V ~ 3.6 V.
It is recommended to add an extra 0.1 μF decoupling capacitor close to the pin(s).
Pin VDD_SPI can serve as the power supply for the external device at 3.3 V (typical value), provided by
VDD3P3_CPU via RSPI. Therefore, there will be some voltage drop from VDD3P3_CPU. When the VDD_SPI
outputs 3.3 V, it is recommended that users add a 1 μF capacitor close to VDD_SPI.
VDD_SPI can be connected to and powered by an external power supply.
When not serving as a power supply pin, VDD_SPI can be used as a regular GPIO.
Attention: When using VDD_SPI as the power supply pin for the in-package flash or external 3.3 V flash, the
supply voltage should be 3.0 V or above, so as to meet the requirements of flash’s working voltage. In such
cases, VDD_SPI cannot be used as a regular GPIO.
Analog Power Supply
ESP32-C3’s VDDA and VDD3P3 pins are the analog power supply pins, working at 3.0 V ~ 3.6 V.
For VDD3P3, when ESP32-C3 is transmitting signals, there may be a sudden increase in the current draw, causing
power rail collapse. Therefore, it is highly recommended to add a 10 μF capacitor to the power rail, which can work
in conjunction with the 0.1 μF capacitor(s) or other capacitors.
It is suggested to add an extra 10 μF capacitor at the main power entrance. If the main power entrance is close to
VDD3P3, then the two 10 μF capacitors can be merged into one.
Espressif Systems
5
Submit Document Feedback
Release master

<!-- Page 9 -->

Chapter 1. Latest Version of This Document
Add an LC circuit to the VDD3P3 power rail to suppress high-frequency harmonics. The inductor’s rated current
is preferably 500 mA and above.
For the remaining capacitor circuits, please refer to ESP32-C3 Reference Schematic.
RTC Power Supply
ESP32-C3’s VDD3P3_RTC pin is the RTC and analog power pin. It is recommended to place a 0.1 μF decoupling
capacitor near this power pin in the circuit.
Note that this power supply cannot be used as a single backup power supply.
The schematic for the RTC power supply pin is shown in Figure ESP32-C3 Schematic for RTC Power Supply Pin.
Fig. 2: ESP32-C3 Schematic for RTC Power Supply Pin
1.3.3
Chip Power-up and Reset Timing
ESP32-C3’s CHIP_EN pin can enable the chip when it is high and reset the chip when it is low.
When ESP32-C3 uses a 3.3 V system power supply, the power rails need some time to stabilize before CHIP_EN
is pulled up and the chip is enabled. Therefore, CHIP_EN needs to be asserted high after the 3.3 V rails have been
brought up.
To reset the chip, keep the reset voltage VIL_nRST in the range of (–0.3 ~ 0.25 × VDD) V. To avoid reboots caused
by external interferences, make the CHIP_EN trace as short as possible.
Figure ESP32-C3 Power-up and Reset Timing shows the power-up and reset timing of ESP32-C3.
Fig. 3: ESP32-C3 Power-up and Reset Timing
Table Description of Timing Parameters for Power-up and Reset provides the specific timing requirements.
Espressif Systems
6
Submit Document Feedback
Release master

<!-- Page 10 -->

Chapter 1. Latest Version of This Document
Table 1: Description of Timing Parameters for Power-up and Reset
Parameter
Description
Minimum (µs)
tSTBL
Time reserved for the power rails to stabilize before the CHIP_EN
pin is pulled high to activate the chip
50
tRST
Time reserved for CHIP_EN to stay below VIL_nRST to reset the
chip
50
Attention:
• CHIP_EN must not be left floating.
• To ensure the correct power-up and reset timing, it is advised to add an RC delay circuit at the CHIP_EN
pin. The recommended setting for the RC delay circuit is usually R = 10 kΩand C = 1 μF. However, specific
parameters should be adjusted based on the characteristics of the actual power supply and the power-up
and reset timing of the chip.
• If the user application has one of the following scenarios:
– Slow power rise or fall, such as during battery charging.
– Frequent power on/off operations.
– Unstable power supply, such as in photovoltaic power generation.
Then, the RC circuit alone may not meet the timing requirements, which may prevent the chip from entering
normal operating mode or cause flash erase operations to occasionally fail to complete. In this case, please
reserve a power monitor chip to reset the chip when the power supply is abnormal, and the threshold of the
power monitor chip is recommended to be around 3.0 V.
1.3.4
Flash
ESP32-C3 can support up to 16 MB external flash, powered by VDD_SPI. It is recommended to add zero-ohm resistor
footprints in series on the SPI communication lines as shown in Figure ESP32-C3 Schematic for External Flash.
These footprints provide flexibility for future adjustments, such as tuning drive strength, mitigating RF interference,
correcting signal timing, and reducing noise, if needed.
For the ESP32-C3 variants with in-package SPI flash, the pins for flash communication cannot be used externally for
other purposes.
Fig. 4: ESP32-C3 Schematic for External Flash
1.3.5
Clock Source
ESP32-C3 supports two external clock sources:
Espressif Systems
7
Submit Document Feedback
Release master

<!-- Page 11 -->

Chapter 1. Latest Version of This Document
• External crystal clock source (Compulsory)
• RTC clock source (Optional)
External Crystal Clock Source (Compulsory)
The ESP32-C3 firmware only supports 40 MHz crystal.
The circuit for the crystal is shown in Figure ESP32-C3 Schematic for External Crystal. Note that the accuracy of the
selected crystal should be within ±10 ppm.
Fig. 5: ESP32-C3 Schematic for External Crystal
Please add a series component on the XTAL_P clock trace. Initially, it is suggested to use an inductor of 24 nH to
reduce the impact of high-frequency crystal harmonics on RF performance, and the value should be adjusted after an
overall test.
The initial values of external capacitors C1 and C2 can be determined according to the formula:
CL = C1 × C2
C1 + C2 + Cstray
where the value of CL (load capacitance) can be found in the crystal’s datasheet, and the value of Cstray refers to the
PCB’s stray capacitance. The values of C1 and C2 need to be further adjusted after an overall test as below:
1. Select TX tone mode using the Certification and Test Tool.
2. Observe the 2.4 GHz signal with a radio communication analyzer or a spectrum analyzer and demodulate it to
obtain the actual frequency offset.
3. Adjust the frequency offset to be within ±10 ppm (recommended) by adjusting the external load capacitance.
• When the center frequency offset is positive, it means that the equivalent load capacitance is small, and the
external load capacitance needs to be increased.
• When the center frequency offset is negative, it means the equivalent load capacitance is large, and the external
load capacitance needs to be reduced.
• External load capacitance at the two sides are usually equal, but in special cases, they may have slightly different
values.
Note:
• Defects in the manufacturing of crystal (for example, large frequency deviation of more than ±10 ppm, unstable
performance within the operating temperature range, etc) may lead to the malfunction of ESP32-C3, resulting
in a decrease of the RF performance.
• It is recommended that the amplitude of the crystal is greater than 500 mV.
• When Wi-Fi or Bluetooth connection fails, after ruling out software problems, you may follow the steps men-
tioned above to ensure that the frequency offset meets the requirements by adjusting capacitors at the two sides
of the crystal.
Espressif Systems
8
Submit Document Feedback
Release master

<!-- Page 12 -->

Chapter 1. Latest Version of This Document
RTC Clock Source (Optional)
ESP32-C3 supports an external 32.768 kHz crystal to act as the RTC clock. The external RTC clock source enhances
timing accuracy and consequently decreases average power consumption, without impacting functionality.
Figure ESP32-C3 Schematic for 32.768 kHz Crystal shows the schematic for the external 32.768 kHz crystal.
Fig. 6: ESP32-C3 Schematic for 32.768 kHz Crystal
Please note the requirements for the 32.768 kHz crystal:
• Equivalent series resistance (ESR) ≤70 kΩ.
• Load capacitance at both ends should be configured according to the crystal’s specification.
The parallel resistor R is used for biasing the crystal circuit (5 MΩ< R ≤10 MΩ).
In general, you do not need to populate the resistor.
If the RTC clock source is not required, then the pins for the 32.768 kHz crystal can be used as GPIOs.
1.3.6
RF
RF Circuit
ESP32-C3’s RF circuit is mainly composed of three parts, the RF traces on the PCB board, the chip matching
circuit, the antenna and the antenna matching circuit. Each part should meet the following requirements:
• For the RF traces on the PCB board, 50 Ωimpedance control is required.
• For the chip matching circuit, it must be placed close to the chip. A CLC structure is preferred.
– The CLC structure is mainly used to adjust the impedance point and suppress harmonics, and
a set of LC can be added if space permits.
– The RF matching circuit is shown in Figure ESP32-C3 Schematic for RF Matching.
• For the antenna and the antenna matching circuit, to ensure radiation performance, the antenna’s characteristic
impedance must be around 50 Ω. Adding a CLC matching circuit near the antenna is recommended to adjust
the antenna. However, if the available space is limited and the antenna impedance point can be guaranteed to
be 50 Ωby simulation, then there is no need to add a matching circuit near the antenna.
RF Tuning
The RF matching parameters vary with the board, so the ones used in Espressif modules could not be applied directly.
Follow the instructions below to do RF tuning.
Figure ESP32-C3 RF Tuning Diagram shows the general process of RF tuning.
In the matching circuit, define the port near the chip as Port 1 and the port near the antenna as Port 2. S11 describes
the ratio of the signal power reflected back from Port 1 to the input signal power, the transmission performance is
best if the matching impedance is conjugate to the chip impedance. S21 is used to describe the transmission loss of
Espressif Systems
9
Submit Document Feedback
Release master

<!-- Page 13 -->

Chapter 1. Latest Version of This Document
Fig. 7: ESP32-C3 Schematic for RF Matching
Fig. 8: ESP32-C3 RF Tuning Diagram
Espressif Systems
10
Submit Document Feedback
Release master

<!-- Page 14 -->

Chapter 1. Latest Version of This Document
signal from Port 1 to Port 2. If S11 is close to the chip conjugate point 35+j0 and S21 is less than -35 dB at 4.8 GHz
and 7.2 GHz, the matching circuit can satisfy transmission requirements.
Connect the two ends of the matching circuit to the network analyzer, and test its signal reflection parameter S11
and transmission parameter S21. Adjust the values of the components in the circuit until S11 and S21 meet the
requirements. If your PCB design of the chip strictly follows the PCB design stated in Chapter PCB Layout Design,
you can refer to the value ranges in Table Recommended Value Ranges for Components to debug the matching circuit.
Table 2: Recommended Value Ranges for Components
Reference Desig-
nator
Recommended Value Range
Serial No.
C11
1.2 ~ 1.8 pF
GRM0335C1H1RXBA01D
L2
2.0 ~ 3.0 nH
LQP03TN2NXB02D
C12
1.8 ~ 1.2 pF
GRM0335C1H1RXBA01D
Please use 0201 packages for RF matching components and add a stub to the first capacitor in the matching circuit
at the chip end.
Note:
If RF function is not required, it is recommended not to initialize the RF stack in firmware. In this case,
the RF pin can be left floating. However, if RF function is enabled, make sure an antenna is connected. Operation
without an antenna may result in unstable behavior or potential damage to the RF circuit.
1.3.7
UART
Usually, UART0 is used as the serial port for download and log printing. For instructions on download over UART0,
please refer to Section Download Guidelines. It is recommended to connect a 499 Ωseries resistor to the U0TXD
line to suppress harmonics.
For application communication, use UART interfaces other than UART0 if possible. Add a series resistor on the TX
line to suppress harmonics.
When using the AT firmware, please note that the UART GPIO is already configured (refer to Hardware Connection).
It is recommended to use the default configuration.
1.3.8
SPI
When using the SPI function, to improve EMC performance, add a series resistor (or ferrite bead) and a capacitor
to ground on the SPI_CLK trace. If space allows, it is recommended to also add a series resistor and capacitor to
ground on other SPI traces. Ensure that the RC/LC components are placed close to the pins of the chip or module.
1.3.9
Strapping Pins
At each startup or reset, a chip requires some initial configuration parameters, such as in which boot mode to load
the chip, etc. These parameters are passed over via the strapping pins. After reset, the strapping pins work as normal
function pins.
GPIO2, GPIO8, and GPIO9 are strapping pins.
All the information about strapping pins is covered in ESP32-C3 Series Datasheet > Chapter Boot Configurations.
In this section, we will mainly cover the strapping pins related to boot mode.
After chip reset is released, the combination of GPIO2, GPIO8, and GPIO9 controls the boot mode. See Table Boot
Mode Control.
Espressif Systems
11
Submit Document Feedback
Release master

<!-- Page 15 -->

Chapter 1. Latest Version of This Document
Table 3: Boot Mode Control
Boot Mode
GPIO2Page 12, 1
GPIO8
GPIO9
Default Config
–(Floating)
–(Floating)
1 (Pull-up)
SPI Boot (default)
1
Any value
1
Joint Download Boot2
1
1
0
Signals applied to the strapping pins should have specific setup time and hold time. For more information, see Figure
Setup and Hold Times for Strapping Pins and Table Description of Timing Parameters for Strapping Pins.
Fig. 9: Setup and Hold Times for Strapping Pins
Table 4: Description of Timing Parameters for Strapping Pins
Parameter
Description
Minimum (ms)
tSU
Time reserved for the power rails to stabilize before the chip enable
pin (CHIP_EN) is pulled high to activate the chip.
0
tH
Time reserved for the chip to read the strapping pin values after
CHIP_EN is already high and before these pins start operating as
regular IO pins.
3
Attention:
• It is recommended to place a pull-up resistor at the GPIO9 pin.
• Do not add high-value capacitors at GPIO9, or the chip may enter download mode.
1 GPIO2 actually does not determine SPI Boot and Joint Download Boot mode, but it is recommended to pull this pin up due to glitches.
2 Joint Download Boot mode supports the following download methods:
• USB-Serial-JTAG Download Boot
• UART Download Boot
Espressif Systems
12
Submit Document Feedback
Release master

<!-- Page 16 -->

Chapter 1. Latest Version of This Document
1.3.10
GPIO
The pins of ESP32-C3 can be configured via IO MUX or GPIO matrix. IO MUX provides the default pin configura-
tions (see ESP32-C3 Series Datasheet > Appendix ESP32-C3 Consolidated Pin Overview), whereas the GPIO matrix
is used to route signals from peripherals to GPIO pins. For more information about IO MUX and GPIO matrix,
please refer to ESP32-C3 Technical Reference Manual > Chapter IO MUX and GPIO Matrix.
Some peripheral signals have already been routed to certain GPIO pins, while some can be routed to any available
GPIO pins. For details, please refer to ESP32-C3 Series Datasheet > Section Peripherals.
When using GPIOs, please:
• Pay attention to the states of strapping pins during power-up.
• Pay attention to the default GPIO configurations after reset (see the table below). For unused pins in the high-
impedance state without an internal pull-up or pull-down, it is recommended to add a pull-up or pull-down
resistor or enable the internal pull during software initialization to avoid extra power consumption, selecting
the direction as required by the external circuit.
• Avoid using the pins already occupied by flash.
• Some pins will have glitches during power-up. Refer to Table Power-Up Glitches on Pins for details.
Table 5: IO MUX Pin Functions
Name
No.
Function 0
Function 1
Function 2
Reset
Notes
XTAL_32K_P
4
GPIO0
GPIO0
—
0
R
XTAL_32K_N
5
GPIO1
GPIO1
—
0
R
GPIO2
6
GPIO2
GPIO2
FSPIQ
1
R
GPIO3
8
GPIO3
GPIO3
—
1
R
MTMS
9
MTMS
GPIO4
FSPIHD
1
R
MTDI
10
MTDI
GPIO5
FSPIWP
1
R
MTCK
12
MTCK
GPIO6
FSPICLK
1*
G
MTDO
13
MTDO
GPIO7
FSPID
1
G
GPIO8
14
GPIO8
GPIO8
—
1
—
GPIO9
15
GPIO9
GPIO9
—
3
—
GPIO10
16
GPIO10
GPIO10
FSPICS0
1
G
VDD_SPI
18
GPIO11
GPIO11
—
0
—
SPIHD
19
SPIHD
GPIO12
—
3
—
SPIWP
20
SPIWP
GPIO13
—
3
—
SPICS0
21
SPICS0
GPIO14
—
3
—
SPICLK
22
SPICLK
GPIO15
—
3
—
SPID
23
SPID
GPIO16
—
3
—
SPIQ
24
SPIQ
GPIO17
—
3
—
GPIO18
25
GPIO18
GPIO18
—
0
USB, G
GPIO19
26
GPIO19
GPIO19
—
0*
USB
U0RXD
27
U0RXD
GPIO20
—
3
G
U0TXD
28
U0TXD
GPIO21
—
4
—
Reset
The default configuration of each pin after reset:
• 0 –input disabled, in high impedance state (IE = 0)
• 1 –input enabled, in high impedance state (IE = 1)
• 2 –input enabled, pull-down resistor enabled (IE = 1, WPD = 1)
• 3 –input enabled, pull-up resistor enabled (IE = 1, WPU = 1)
• 4 –output enabled, pull-up resistor enabled (OE = 1, WPU = 1)
• 0* –input disabled, pull-up resistor enabled (IE = 0, WPU = 0, USB_WPU = 1). See details in Notes
• 1* –When the value of eFuse bit EFUSE_DIS_PAD_JTAG is
– 0, input enabled, pull-up resistor enabled (IE = 1, WPU = 1)
Espressif Systems
13
Submit Document Feedback
Release master

<!-- Page 17 -->

Chapter 1. Latest Version of This Document
– 1, input enabled, in high impedance state (IE = 1)
Notes
• R –These pins have analog functions.
• USB –GPIO18 and GPIO19 are USB pins.
– By default,
the USB function is enabled for USB pins (i.e.,
GPIO18 and GPIO19),
and
the pin pull-up is decided by the USB pull-up resistor.
The USB pull-up resistor is
controlled by USB_SERIAL_JTAG_DP/DM_PULLUP and the pull-up value is controlled by
USB_SERIAL_JTAG_PULLUP_VALUE. For details, see ESP32-C3 Technical Reference Manual >
Chapter USB Serial/JTAG Controller.
– When the USB function is disabled, USB pins are used as regular GPIOs and the pin’s internal weak
pull-up and pull-down resistors are disabled by default (configurable by IO_MUX_FUN_WPU/WPD).
• G –These pins have glitches during power-up. See details in Table Power-Up Glitches on Pins.
Table 6: Power-Up Glitches on Pins
Pin
GlitchPage 14, 3
Typical Time (ns)
MTCK
Low-level glitch
5
MTDO
Low-level glitch
5
GPIO10
Low-level glitch
5
U0RXD
Low-level glitch
5
GPIO18
High-level glitch
50,000
1.3.11
ADC
Please add a 0.1 μF filter capacitor between ESP pins and ground when using the ADC function to improve accuracy.
It is recommend to use ADC1, given that ADC2 is not factory-calibrated, and ADC2 of some chip revisions is not
operable. For details, please refer to ESP32-C3 Series SoC Errata.
The calibrated ADC results after hardware calibration and software calibration are shown in the list below. For higher
accuracy, you may implement your own calibration methods.
• When ATTEN=0 and the effective measurement range is 0 ~ 750 mV, the total error is ±10 mV.
• When ATTEN=1 and the effective measurement range is 0 ~ 1050 mV, the total error is ±10 mV.
• When ATTEN=2 and the effective measurement range is 0 ~ 1300 mV, the total error is ±10 mV.
• When ATTEN=3 and the effective measurement range is 0 ~ 2500 mV, the total error is ±35 mV.
1.3.12
USB
ESP32-C3 integrates a USB Serial/JTAG controller that supports USB 2.0 full-speed device.
GPIO18 and GPIO19 can be used as D- and D+ of USB respectively. It is recommended to reserve series resistors
(initial value can be 22/33 Ω) and capacitors to ground on the traces (initially can be unpopulated), and place them
close to the chip.
Note that upon power-up, the USB_D+ signal will fluctuate between high and low states. The high-level signal is
relatively strong and requires a robust pull-down resistor to drive it low. Therefore, if you need a stable initial state,
adding an external pull-up resistor is recommended to ensure a consistent high-level output voltage at startup.
ESP32-C3 also supports download functions and log message printing via USB. For details please refer to Section
Download Guidelines.
3
• Low-level glitch: the pin is at a low level output status during the time period;
• High-level glitch: the pin is at a high level output status during the time period.
Espressif Systems
14
Submit Document Feedback
Release master

<!-- Page 18 -->

Chapter 1. Latest Version of This Document
1.4
PCB Layout Design
This chapter introduces the key points of how to design an ESP32-C3 PCB layout using an ESP32-C3 module (see
Figure ESP32-C3 Reference PCB Layout) as an example.
Fig. 10: ESP32-C3 Reference PCB Layout
1.4.1
General Principles of PCB Layout for the Chip
It is recommended to use a four-layer PCB design:
• Layer 1 (TOP): Signal traces and components.
• Layer 2 (GND): No signal traces here to ensure a complete GND plane.
• Layer 3 (POWER): GND plane should be applied to better isolate the RF and crystal. Route power traces and
a few signal traces on this layer, provided that there is a complete GND plane under the RF and crystal.
• Layer 4 (BOTTOM): Route a few signal traces here. It is not recommended to place any components on this
layer.
A two-layer PCB design can also be used:
• Layer 1 (TOP): Signal traces and components.
• Layer 2 (BOTTOM): Do not place any components on this layer and keep traces to a minimum. Please make
sure there is a complete GND plane for the chip, RF, and crystal.
1.4.2
Power Supply
Four-Layer PCB Design
Figure ESP32-C3 Power Traces in a Four-Layer PCB Design shows the power traces in a four-layer PCB design.
• A four-layer PCB design is recommended. Whenever possible, route the power traces on the inner layers (not
the ground layer) and connect them to the chip pins through vias. There should be at least two vias if the main
power traces need to cross layers. The drill diameter on other power traces should be no smaller than the width
of the power traces.
Espressif Systems
15
Submit Document Feedback
Release master

<!-- Page 19 -->

Chapter 1. Latest Version of This Document
Fig. 11: ESP32-C3 Power Traces in a Four-Layer PCB Design
• The yellow highlighted traces in Figure ESP32-C3 Power Traces in a Four-Layer PCB Design are the 3.3 V
power traces. The width of the main power traces should be no less than 25 mil. The width of VDD3P3 power
traces should be no less than 20 mil. The recommended width of other power traces is 10 mil. Ensure the
power traces are surrounded by ground copper.
• The red circles in ESP32-C3 Power Traces in a Four-Layer PCB Design show ESD protection diodes. Place
them close to the power input. Add a 10 µF capacitor before the power trace enters the chip. You can also
add a 0.1 µF or 1 µF capacitor in parallel. After that, the power trace can branch out in a star-shaped layout to
reduce coupling between different power pins.
• The power supply for pin2 and pin3 is RF related, so please place a 10 µF capacitor for each pin. You can also
add a 0.1 µF or 1 µF capacitor in parallel.
• Add a CLC/LC filter circuit near pin2 and pin3 to suppress high-frequency harmonics. The power trace can
be routed at a 45-degree angle to maintain distance from adjacent RF traces. Except for the 10 µF capacitor,
it is recommended to use 0201 components. This allows the filter circuit for pin2 and pin3 to be placed closer
to the pins, with a GND isolation layer separating them from surrounding RF and GPIO traces, while also
maximizing the placement of ground vias. Using 0201 components enables placing a via to the bottom layer at
the first capacitor near the chip, while maintaining a keep-out area on other layers, further reducing harmonic
interference. See Figure ESP32-C3 Power Traces in a Four-Layer PCB Design.
• In Figure ESP32-C3 Power Traces in a Four-Layer PCB Design, the 10 µF capacitor is shared by the analog
power supply VDD3P3, and the power entrance since the analog power is close to the chip power entrance.
If the chip power entrance is not near VDD3P3, it is recommended to add a 10 µF capacitor to both the chip
power entrance and VDD3P3.
• Place appropriate decoupling capacitors at the rest of the power pins. Ground vias should be added close to
the capacitor’s ground pad to ensure a short return path.
• The ground pad at the bottom of the chip should be connected to the ground plane through at least nine ground
vias.
• The ground pads of the chip and surrounding circuit components should make full contact with the ground
copper pour rather than being connected via traces.
• If you need to add a thermal pad EPAD under the chip on the bottom of the module, it is recommended to
employ a square grid on the EPAD, cover the gaps with solder paste, and place ground vias in the gaps, as
shown in Figure ESP32-C3 Power Traces in a Four-Layer PCB Design. This helps effectively reduce solder
leakage issues when soldering the module EPAD to the substrate.
• For optimal grounding, connect the EPAD to a large external ground area using wide traces or copper planes.
Two-Layer PCB Design
Figure ESP32 Power Traces in a Two-Layer PCB Design shows the power traces in a two-layer PCB design.
Espressif Systems
16
Submit Document Feedback
Release master

<!-- Page 20 -->

Chapter 1. Latest Version of This Document
Fig. 12: ESP32 Power Traces in a Two-Layer PCB Design
• For a two-layer design, ensure to provide a continuous reference ground for the chip, RF, and crystal oscillator,
as shown in the figure above.
• In the figure above, the trace VDD33 represents the 3.3 V power trace. Unlike a four-layer design, the power
trace should be routed on the top layer as much as possible. Therefore, the thermal pad in the center of the
chip should be reduced in size, allowing the power trace to pass between the signal pads and the thermal pad.
Vias to the bottom layer should only be used when absolutely necessary.
• Other layout considerations are the same as for a four-layer design.
• Note that there are no official two-layer modules. The figure above uses the ESP32 module as an example.
1.4.3
Crystal
Figure ESP32-C3 Crystal Layout (without Keep-out Area on Top Layer) shows the layout for the crystal that is con-
nected to the ground through vias but there is no keep-out area on the top layer for ground isolation.
The layout of the crystal should follow the guidelines below:
• Ensure a complete GND plane for the RF, crystal, and chip.
• The crystal should be placed far from the clock pin to avoid interference on the chip. The gap should be at least
2.0 mm. It is good practice to add high-density ground vias stitching around the clock trace for better isolation.
• There should be no vias for the clock input and output traces.
• Components in series to the crystal trace should be placed close to the chip side.
• The external matching capacitors should be placed on the two sides of the crystal, preferably at the end of the
clock trace, but not connected directly to the series components. This is to make sure the ground pad of the
capacitor is close to that of the crystal.
• Do not route high-frequency digital signal traces under the crystal. It is best not to route any signal trace under
the crystal. The vias on the power traces on both sides of the crystal clock trace should be placed as far away
from the clock trace as possible, and the two sides of the clock trace should be surrounded by ground copper.
• As the crystal is a sensitive component, do not place any magnetic components nearby that may cause interfer-
ence, for example large inductance component, and ensure that there is a clean large-area ground plane around
the crystal.
Espressif Systems
17
Submit Document Feedback
Release master

<!-- Page 21 -->

Chapter 1. Latest Version of This Document
Fig. 13: ESP32-C3 Crystal Layout (without Keep-out Area on Top Layer)
1.4.4
RF
The RF trace is routed as shown highlighted in pink in Figure ESP32-C3 RF Layout in a Four-layer PCB Design.
Fig. 14: ESP32-C3 RF Layout in a Four-layer PCB Design
The RF layout should meet the following guidelines:
• The RF trace should have a 50 Ω characteristic impedance. The reference plane is the layer next to the chip.
For designing the RF trace at 50 Ω impedance, you could refer to the PCB stack-up design shown below.
• A CLC matching circuit is required for chip tuning. Please use 0201 components and place them close to the
pin in a zigzag. In other words, the two capacitors should not be oriented in the same direction to minimize
interference.
• Add a stub on the ground pad of the grounding capacitor near the chip side in the matching circuit to suppress
the second harmonics. It is preferable to keep the stub length 15 mil, and determine the stub width according
to the PCB stack-up so that the characteristic impedance of the stub is 100 Ω± 10%. The reference plane
Espressif Systems
18
Submit Document Feedback
Release master

<!-- Page 22 -->

Chapter 1. Latest Version of This Document
Fig. 15: ESP32-C3 PCB Stack-up Design
is the third layer, so the area under the trace on the second layer should be cleared. The trace highlighted in
Figure ESP32-C3 Stub in a Four-layer PCB Design is the stub. Note that a stub is not required for package
types of 0402 and above.
• For PCB antennas, make sure to validate them through both simulation and real-world testing on a development
board. It is recommended to include an additional CLC matching circuit for antenna tuning. Place this circuit
as close to the antenna as possible.
• The RF trace should have a consistent width and not branch out. It should be as short as possible with dense
ground vias around for interference shielding.
• The RF trace should be routed on the outer layer without vias, i.e., should not cross layers. The RF trace should
be routed at a 135° angle, or with circular arcs if trace bends are required.
• The ground plane on the adjacent layer needs to be complete. Do not route any traces under the RF trace
whenever possible.
• There should be no high-frequency signal traces routed close to the RF trace. The RF antenna should be
placed away from high-frequency components, such as crystals, DDR SDRAM, high-frequency clocks, etc. In
addition, the USB port, USB-to-serial chip, UART signal lines (including traces, vias, test points, header pins,
etc.) must be as far away from the antenna as possible. The UART signal line should be surrounded by ground
copper and ground vias.
1.4.5
Flash
The layout for flash should follow the guidelines below:
• Place the zero-ohm resistors in series on the SPI lines close to ESP32-C3.
• Route the SPI traces on the inner layer (e.g., the third layer) whenever possible, and add ground copper and
ground vias around the clock and data traces of SPI separately.
Espressif Systems
19
Submit Document Feedback
Release master

<!-- Page 23 -->

Chapter 1. Latest Version of This Document
Fig. 16: ESP32-C3 Stub in a Four-layer PCB Design
• If the flash and PSRAM are located far from ESP32-C3, it is recommended to place appropriate decoupling
capacitors both at VDD_SPI and near the flash and PSRAM power supply.
Figure ESP32-C3 Quad SPI Flash Layout shows the quad SPI flash layout.
Fig. 17: ESP32-C3 Quad SPI Flash Layout
1.4.6
UART
Figure ESP32-C3 UART Layout shows the UART layout.
The UART layout should meet the following guidelines:
• The series resistor on the U0TXD trace needs to be placed close to the chip side and away from the crystal.
• The U0TXD and U0RXD traces on the top layer should be as short as possible.
Espressif Systems
20
Submit Document Feedback
Release master

<!-- Page 24 -->

Chapter 1. Latest Version of This Document
Fig. 18: ESP32-C3 UART Layout
• The UART trace should be surrounded by ground copper and ground vias stitching.
1.4.7
General Principles of PCB Layout for Modules (Positioning a Module on a Base
Board)
If module-on-board design is adopted, attention should be paid while positioning the module on the base board. The
interference of the baseboard on the module’s antenna performance should be minimized.
It is suggested to place the module’s on-board PCB antenna outside the base board, and the feed point of the
antenna close to the edge of the base board. In the following example figures, positions with mark ✓are strongly
recommended, while positions without a mark are not recommended.
Fig. 19: Placement of ESP32-C3 Modules on Base Board (antenna feed point on the right)
If the antenna cannot extend beyond the board edge, the feed point should still be placed as close to the board edge
as possible. Then cut off the base board on both sides of the antenna and below it to minimize the impact of the
base board material on the PCB antenna and provide a sufficiently large clearance area for the PCB antenna. Note
that the module should not be placed in the center of the board with clearance created by hollowing out on all four
Espressif Systems
21
Submit Document Feedback
Release master

<!-- Page 25 -->

Chapter 1. Latest Version of This Document
Fig. 20: Placement of ESP32-C3 Modules on Base Board (antenna feed point on the left)
sides. Figure Keepout Zone for ESP32-C3 Module’s Antenna (Antenna feed point on the Left) shows the suggested
clearance area. Please note that sufficient ground copper and dense ground vias should be placed on the base board
near the antenna.
After the base board is placed in the end product, please consider the impact of the housing on the antenna during
end-product design. Ensure that the PCB antenna on the base board also has a sufficiently large clearance area inside
the housing. A clearance of at least 15 mm is recommended in all directions.
Please note that the final end product should be tested for throughput and communication range to ensure RF perfor-
mance.
1.4.8
USB
The USB layout should meet the following guidelines:
• Reserve space for resistors and capacitors on the USB traces close to the chip side.
• Use differential pairs and route them in parallel at equal lengths. Maintain a differential pair impedance of 90
Ω with a tolerance of ±10%.
• USB differential traces should minimize via transitions as much as possible to ensure better impedance control
and avoid signal reflections. If vias are necessary, add a pair of ground return vias at each transition point.
• Ensure there is a continuous reference layer (a ground layer is recommended) beneath the USB traces.
• Surround the USB traces with ground copper.
1.4.9
Typical Layout Problems and Solutions
When ESP32-C3 sends data packages, the voltage ripple is small, but RF TX performance is poor.
Analysis: The RF TX performance can be affected not only by voltage ripples, but also by the crystal itself. Poor
quality and big frequency offsets of the crystal decrease the RF TX performance. The crystal clock may be corrupted
by other interfering signals, such as high-speed output or input signals. In addition, high-frequency signal traces,
such as the SDIO traces and UART traces under the crystal, could also result in the malfunction of the crystal.
Besides, sensitive components or radiating components, such as inductors and antennas, may also decrease the RF
performance.
Espressif Systems
22
Submit Document Feedback
Release master

<!-- Page 26 -->

Chapter 1. Latest Version of This Document
Fig. 21: Keepout Zone for ESP32-C3 Module’s Antenna (Antenna feed point on the Left)
Solution: This problem is caused by improper layout for the crystal and can be solved by re-layout. Please refer to
Section Crystal for details.
When ESP32-C3 sends data packages, the power value is much higher or lower than the target power value,
and the EVM is relatively poor.
Analysis: The disparity between the tested value and the target value may be due to signal reflection caused by
the impedance mismatch on the transmission line connecting the RF pin and the antenna. Besides, the impedance
mismatch will affect the working state of the internal PA, making the PA prematurely access the saturated region in
an abnormal way. The EVM becomes poor as the signal distortion happens.
Solution: Match the antenna’s impedance with the π-type circuit on the RF trace, so that the impedance of the
antenna as seen from the RF pin matches closely with that of the chip. This reduces reflections to the minimum.
TX performance is not bad, but the RX sensitivity is low.
Analysis: Good TX performance indicates proper RF impedance matching. Poor RX sensitivity may result from
external coupling to the antenna. For instance, the crystal signal harmonics could couple to the antenna. If the TX
and RX traces of UART cross over with RF trace, they will affect the RX performance, as well. If there are many
high-frequency interference sources on the board, signal integrity should be considered.
Solution: Keep the antenna away from crystals. Do not route high-frequency signal traces close to the RF trace.
Please refer to Section RF for details.
1.5
Download Guidelines
Espressif Systems
23
Submit Document Feedback
Release master

<!-- Page 27 -->

Chapter 1. Latest Version of This Document
You can download firmware to ESP32-C3 via UART and USB.
To download via UART:
1. Before the download, make sure to set the chip or module to Joint Download Boot mode, according to Table
Boot Mode Control.
2. Power up the chip or module and check the log via the UART0 serial port. If the log shows “waiting for
download”, the chip or module has entered Joint Download Boot mode.
3. Use the Flash Download Tool to flash firmware into flash via UART.
4. After the firmware has been downloaded, pull GPIO9 high or leave it floating to make sure that the chip or
module enters SPI Boot mode.
5. Power up the chip or module again. The chip will read and execute the new firmware during initialization.
To download via USB:
1. If the flash is empty, set the chip or module to Joint Download Boot mode, according to Table Boot Mode
Control.
2. Power up the chip or module and check the log via USB serial port. If the log shows “waiting for download”
, the chip or module has entered Joint Download Boot mode.
3. Use the Flash Download Tool to flash firmware into flash via USB.
4. After the firmware has been downloaded, pull GPIO9 high or leave it floating to make sure that the chip or
module enters SPI Boot mode.
5. Power up the chip or module again. The chip will read and execute the new firmware during initialization.
6. If the flash is not empty, start directly from Step 3.
Note:
• For firmware download instructions, see also ESP Product Firmware Download Instructions.
• For how to check serial port output, see also Establish Serial Connection with ESP32-C3.
• It is advised to download the firmware only after the “waiting for download”log shows via the serial port.
• Serial tools cannot be used simultaneously with the Flash Download Tool on one COM port.
• The USB auto-download will be disabled if the following conditions occur in the application, where it will be
necessary to set the chip or module to Joint Download Boot mode first by configuring the strapping pin.
– USB PHY is disabled by the application;
– USB is configured for other USB functions, e.g., USB host, USB standard device;
– USB IOs are configured to other peripherals, such as UART and LEDC.
• It is recommended that the user retains control of the strapping pins to avoid the USB download function not
being available in case of the above scenario.
• It is recommended to retain the UART download interface, as the current RF test firmware only supports the
UART interface.
1.6
Related Documentation and Resources
1.6.1
ESP32-C3 Modules
For a list of ESP32-C3 modules please check the Modules section on Espressif’s official website.
For module reference designs please refer to:
• Download links
Note: Use the following tools to open the files in module reference designs:
Espressif Systems
24
Submit Document Feedback
Release master

<!-- Page 28 -->

Chapter 1. Latest Version of This Document
• .DSN files: OrCAD Capture V16.6
• .pcb files: Pads Layout VX.2. If you cannot open the .pcb files, please try importing the .asc files into your
software to view the PCB layout.
1.6.2
ESP32-C3 Development Boards
For a list of the latest designs of ESP32-C3 boards please check the Development Boards section on Espressif’s
official website.
1.6.3
Other Related Documentation and Resources
• Chip Datasheet (PDF)
• Technical Reference Manual (PDF)
• Chip Errata
• ESP32-C3 Chip Variants
• Espressif KiCad Library
• ESP Product Selector
• Regulatory Certificates
• User Forum (Hardware)
• Technical Support
• ESP-FAQ
1.7
Glossary
The glossary contains terms and acronyms that are used in this document.
Term
Description
CLC
Capacitor-Inductor-Capacitor
DDR SDRAM
Double Data Rate Synchronous Dynamic Random-Access Memory
ESD
Electrostatic Discharge
LC
Inductor-Capacitor
PA
Power Amplifier
RC
Resistor-Capacitor
RTC
Real-Time Clock
Zero-ohm resistor
A zero-ohm resistor acts as a placeholder in the circuit, allowing for the replacement with
a higher-ohm resistor based on specific design requirements.
1.8
Revision History
Espressif Systems
25
Submit Document Feedback
Release master

<!-- Page 29 -->

Chapter 1. Latest Version of This Document
Table 7: Revision History
Date
Version
Release Notes
2025-06-05
v1.8
•PCB Layout Design
– Section USB: Updated descriptions about the USB layout
guidelines
2025-05-23
v1.7
•PCB Layout Design
– Section Crystal: Updated descriptions about the crystal layout
guidelines
2025-01-07
v1.6
•ESP32-C3 Modules：
– Added download links to module reference designs
2024-11-15
v1.5
•Schematic Checklist
– Section SPI: Newly added section
2024-10-15
v1.4
•Schematic Checklist
– Section UART: Updated the AT related description
2024-02-18
v1.3
•PCB Layout Design
– Section General Principles of PCB Layout for Modules (Posi-
tioning a Module on a Base Board): Updated Figure Placement
of ESP32-C3 Modules on Base Board (antenna feed point on
the right) and Figure Placement of ESP32-C3 Modules on Base
Board (antenna feed point on the left)
2024-01-09
v1.2
•Schematic Checklist
– Section RF Tuning: Updated RF matching description
2023-12-25
v1.1
•PCB Layout Design
– Section Crystal: Updated crystal PCB layout
2023-12-22
v1.0
Migrated ESP32-C3 Hardware Design Guidelines from PDF to HTML for-
mat. During the migration from PDF to HTML format, minor updates, im-
provements, and clarifications were made throughout the documentation. If
you would like to check previous versions of the document, please submit doc-
umentation feedback.
1.9
Disclaimer and Copyright Notice
Information in this document, including URL references, is subject to change without notice.
All third party’s information in this document is provided as is with no warranties to its authenticity and accuracy.
No warranty is provided to this document for its merchantability, non-infringement, fitness for any particular purpose,
nor does any warranty otherwise arising out of any proposal, specification or sample.
All liability, including liability for infringement of any proprietary rights, relating to use of information in this doc-
ument is disclaimed. No licenses express or implied, by estoppel or otherwise, to any intellectual property rights are
Espressif Systems
26
Submit Document Feedback
Release master

<!-- Page 30 -->

Chapter 1. Latest Version of This Document
granted herein.
The Wi-Fi Alliance Member logo is a trademark of the Wi-Fi Alliance. The Bluetooth logo is a registered trademark
of Bluetooth SIG.
All trade names, trademarks and registered trademarks mentioned in this document are property of their respective
owners, and are hereby acknowledged.
Espressif Systems
27
Submit Document Feedback
Release master


---

# 3. SSD1680 Datasheet

> **Source file:** `SSD1680.pdf`  
> Solomon Systech — SSD1680 active matrix EPD display driver / controller

<!-- Page 1 -->

SOLOMON SYSTECH
SEMICONDUCTOR TECHNICAL DATA
This document contains information on a product under development. Solomon Systech reserves the right to change
or discontinue this product without notice.
http://www.solomon-systech.com
SSD1680
Rev 0.14
P 1/46
Jun 2019
Copyright  2019 Solomon Systech Limited
SSD1680
Product Preview
176 Source x 296 Gate Red/Black/White
Active Matrix EPD Display Driver with Controller

<!-- Page 2 -->

SSD1680
Rev 0.14
P 2/46
Jun 2019
Solomon Systech
Appendix: IC Revision history of SSD1680 Specification
Version
Change Items
Effective Date
0.10
Initial Release
28-Feb-19
0.11
Updated Feature list
02-Apr-19
0.12
Updated AC Characteristics
Updated Component list
21-May-19
0.13
Updated Component list
24-May-19
0.14
Updated Component list, removed case size for C0 and C1.
5-Jun-19

<!-- Page 3 -->

SSD1680
Rev 0.14
P 3/46
Jun 2019
Solomon Systech
CONTENTS
1
GENERAL DESCRIPTION ....................................................................................................... 5
2
FEATURES ............................................................................................................................... 5
3
ORDERING INFORMATION..................................................................................................... 6
4
BLOCK DIAGRAM ................................................................................................................... 6
5
PIN DESCRIPTION ................................................................................................................... 7
6
FUNCTIONAL BLOCK DESCRIPTION .................................................................................. 10
6.1
MCU INTERFACE ........................................................................................................................... 10
6.1.1 MCU INTERFACE SELECTION.......................................................................................................... 10
6.1.2 MCU SERIAL INTERFACE (4-WIRE SPI) ........................................................................................... 10
6.1.3 MCU SERIAL PERIPHERAL INTERFACE (3-WIRE SPI) ....................................................................... 11
6.2
OSCILLATOR .............................................................................................................................. 12
6.3
BOOSTER & REGULATOR ......................................................................................................... 12
6.4
VCOM SENSING ......................................................................................................................... 12
6.5
RAM ............................................................................................................................................ 13
6.6
PROGRAMMABLE WAVEFORM FOR GATE, SOURCE AND VCOM ........................................................ 13
6.7
WAVEFORM SETTING ............................................................................................................... 15
6.8
TEMPERATURE SEARCHING............................................................................................................ 16
6.8.1 INTERNAL TEMPERATURE SENSOR ................................................................................................. 16
6.8.2 EXTERNAL TEMPERATURE SENSOR I2C SINGLE MASTER INTERFACE ............................................... 16
6.8.3 FORMAT OF TEMPERATURE VALUE .................................................................................................. 16
6.9
WAVEFORM SETTING SEARCHING MECHANISM ................................................................................ 17
6.10
ONE TIME PROGRAMMABLE (OTP) MEMORY ................................................................................... 18
6.11
THE FORMAT FOR TEMPERATURE RANGE (TR) ............................................................................... 18
6.12
CASCADE MODE ............................................................................................................................ 19
6.13
VCI DETECTION ............................................................................................................................ 19
6.14
HV READY DETECTION .................................................................................................................. 19
7
COMMAND TABLE ................................................................................................................ 20
8
COMMAND DESCRIPTION ................................................................................................... 34
8.1
DRIVER OUTPUT CONTROL (01H) ................................................................................................... 34
8.2
GATE SCAN START POSITION (0FH) ............................................................................................... 36
8.3
DATA ENTRY MODE SETTING (11H) ................................................................................................ 37
8.4
SET RAM X - ADDRESS START / END POSITION (44H) ..................................................................... 38
8.5
SET RAM Y - ADDRESS START / END POSITION (45H) ..................................................................... 38
8.6
SET RAM ADDRESS COUNTER (4EH-4FH) ...................................................................................... 38
9
OPERATION FLOW AND CODE SEQUENCE ...................................................................... 39
9.1
GENERAL OPERATION FLOW TO DRIVE DISPLAY PANEL ..................................................................... 39
10 ABSOLUTE MAXIMUM RATING ........................................................................................... 40
11 ELECTRICAL CHARACTERISTICS ...................................................................................... 40
12 AC CHARACTERISTICS ........................................................................................................ 42
12.1
SERIAL PERIPHERAL INTERFACE ..................................................................................................... 42
13 APPLICATION CIRCUIT ........................................................................................................ 43
14 PACKAGE INFORMATION .................................................................................................... 44
14.1
DIE TRAY DIMENSIONS FOR SSD1680Z ......................................................................................... 44
14.2
DIE TRAY DIMENSIONS FOR SSD1680Z8 ....................................................................................... 45

<!-- Page 4 -->

SSD1680
Rev 0.14
P 4/46
Jun 2019
Solomon Systech
TABLES
TABLE 3-1 : ORDERING INFORMATION .............................................................................................................. 6
TABLE 5-1: POWER SUPPLY PINS .................................................................................................................... 7
TABLE 5-2: INTERFACE LOGIC PINS .................................................................................................................. 8
TABLE 5-3: ANALOG PINS ................................................................................................................................ 9
TABLE 5-4: DRIVER OUTPUT PINS .................................................................................................................... 9
TABLE 5-5: MISCELLANEOUS PINS ................................................................................................................... 9
TABLE 6-1 : INTERFACE PINS ASSIGNMENT UNDER DIFFERENT MCU INTERFACE ............................................... 10
TABLE 6-2 : CONTROL PINS STATUS OF 4-WIRE SPI ........................................................................................ 10
TABLE 6-3 : CONTROL PINS STATUS OF 3-WIRE SPI ........................................................................................ 11
TABLE 6-4 : RAM BIT AND LUT MAPPING FOR 3-COLOR DISPLAY ...................................................................... 13
TABLE 6-5 : RAM BIT AND LUT MAPPING FOR BLACK/WHITE DISPLAY ............................................................... 13
TABLE 6-6 : VS[NX-LUTM] SETTINGS FOR SOURCE VOLTAGE AND VCOM VOLTAGE ......................................... 14
TABLE 6-7 : EXAMPLE OF 12-BIT BINARY TEMPERATURE SETTINGS FOR TEMPERATURE RANGES ........................ 16
TABLE 6-8 : EXAMPLE OF WAVEFORM SETTINGS SELECTION BASED ON TEMPERATURE RANGES. ........................ 17
TABLE 7-1: COMMAND TABLE ........................................................................................................................ 20
TABLE 10-1 : MAXIMUM RATINGS ................................................................................................................... 40
TABLE 11-1: DC CHARACTERISTICS ............................................................................................................... 40
TABLE 11-2: REGULATORS CHARACTERISTICS ............................................................................................... 41
TABLE 12-1 : SERIAL PERIPHERAL INTERFACE TIMING CHARACTERISTICS ........................................................ 42
TABLE 13-1: COMPONENT LIST FOR SSD1680 APPLICATION CIRCUIT ............................................................... 43
FIGURES
FIGURE 4-1 : SSD1680 BLOCK DIAGRAM ......................................................................................................... 6
FIGURE 6-1 : WRITE PROCEDURE IN 4-WIRE SPI MODE ................................................................................... 10
FIGURE 6-2 : READ PROCEDURE IN 4-WIRE SPI MODE ..................................................................................... 11
FIGURE 6-3 : WRITE PROCEDURE IN 3-WIRE SPI ............................................................................................. 11
FIGURE 6-4 : READ PROCEDURE IN 3-WIRE SPI MODE ..................................................................................... 12
FIGURE 6-5 : GATE WAVEFORM AND PROGRAMMABLE SOURCE AND VCOM WAVEFORM ILLUSTRATION .............. 13
FIGURE 6-6 : WAVEFORM SETTING MAPPING .................................................................................................. 15
FIGURE 6-7 : THE WAVEFORM SETTING MAPPING IN OTP FOR WAVEFORM SETTING AND TEMPERATURE RANGE . 18
FIGURE 6-8 : FORMAT OF TEMPERATURE RANGE (TR) IN OTP ........................................................................ 18
FIGURE 8-1: OUTPUT PIN ASSIGNMENT ON DIFFERENT SCAN MODE SETTING .................................................... 35
FIGURE 8-2: EXAMPLE OF SET DISPLAY START LINE WITH NO REMAPPING ....................................................... 36
FIGURE 9-1: OPERATION FLOW TO DRIVE DISPLAY PANEL ................................................................................ 39
FIGURE 12-1: SPI TIMING DIAGRAM ................................................................................................................ 42
FIGURE 13-1: SCHEMATIC OF SSD1680 APPLICATION CIRCUIT ........................................................................ 43
FIGURE 14-1 : SSD1680Z DIE TRAY INFORMATION (UNIT: MM) ......................................................................... 44
FIGURE 14-2 : SSD1680Z8 DIE TRAY INFORMATION (UNIT: MM) ....................................................................... 45

<!-- Page 5 -->

SSD1680
Rev 0.14
P 5/46
Jun 2019
Solomon Systech
1
GENERAL DESCRIPTION
SSD1680 is an Active Matrix EPD display driver with controller for Red/Black/White EPD displays.
It consists of 176 source outputs, 296 gate outputs, 1 VCOM and 1VBD (for border), which can support displays
with resolution up to 176x 296. In addition, SSD1680 has a cascade mode which provides two-chip solutions for
displays with higher resolution.
In the SSD1680, data and commands are sent from MCU through hardware selectable serial peripheral interface.
It has embedded booster, regulator and oscillator which is suitable for EPD display applications.
2
FEATURES
•
Design for dot matrix type active matrix EPD display, support Red/Black/White color
•
Resolution: 176 source outputs, 296 gate outputs, 1 VCOM and 1VBD (for border)
•
Power supply:
•
VCI:
2.2 to 3.7V
•
VDDIO: Connect to VCI
•
VDD:
1.8V, regulate from VCI supply
•
On chip display RAM
•
Mono B/W: 176x296 bits
•
Mono Red: 176x296 bits
•
On-chip booster and regulator for generating VCOM, Gate and Source driving voltage
•
Gate driving output voltage: 2-level outputs (VGH, VGL), Max 40Vp-p
•
VGH: 10V to 20V (Voltage adjustment step: 500mV)
•
VGL: -VGH (Voltage adjustment step: 500mV)
•
Source / VBD driving output voltage: 4-levels outputs (VSH1, VSH2, VSS and VSL)
•
VSH1/VSH2: 2.4V to 17V (Voltage adjustment step: 100mV for 2.4V to 8.8V, 200mV for 8.8V to
17V)
•
VSL: -5V to -17V (Voltage adjustment step: 500mV)
•
VCOM output voltage
•
DCVCOM: -3V to -0.2V in 100mV resolution
•
ACVCOM: 3-level outputs (VSH1+DCVCOM, DCVCOM, VSL+DCVCOM)
•
On-chip oscillator, adjustable frame rate from 25Hz to 200Hz
•
Programmable output Waveform Settings:
•
Individual setting of 5 LUT [LUT0~4]
-
VS: 2-bit per 4 phases
•
Common setting of 5 LUT
-
48 phases (4 phases/group, 12 groups with repeat and state repeat function)
-
TP: Max. 255 frame/phase
-
RP: 1 to 256 times for repeat count
-
SR: 1 to 256 times for state repeat count; state repeat count for phase A,B and 1 state
repeat count for phase C,D
-
FR: Selective Frame Rate for each group
-
XON: All Gate On Selection for each phase A,B and phase C,D
•
Embedded OTP to store the waveform settings and parameters:
•
36 sets of Waveform Settings (WS) including
-
waveform look up table (LUT),
-
Gate/Source voltage, VCOM value
-
Option for LUT end
•
36 sets of Temperature Range (TR)
•
Display mode selection
•
4-byte waveform version
•
10-byte User ID
•
Embedded OTP to store the init code setting
•
External or internal generated voltage for burning OTP
•
Built-in CRC checking method for RAM content and WS & TR in OTP
•
Panel break diagnostic
•
VCI low voltage detection
•
Driving voltage ready detection
•
Support display partial update

<!-- Page 6 -->

SSD1680
Rev 0.14
P 6/46
Jun 2019
Solomon Systech
•
Auto write RAM command for regular patterns
•
Internal Temperature Sensor of +/-2degC accuracy from -25degC to 50degC
•
I2C single master interface to communicate with external temperature sensor
•
MCU interface: 4-wire or 3-wire Serial peripheral interface (maximum SPI write speed 20MHz)
•
Cascade mode to support displays with higher resolution
•
Available in COG package
3
ORDERING INFORMATION
Table 3-1 : Ordering Information
Ordering Part Number
Package Form
Remark
SSD1680Z
Gold Bump Die
Bump Face Up
On Waffle pack
Die thickness: 300um
Bump height: 12um
SSD1680Z8
Gold Bump Die
Bump Face Down
On Waffle pack
Die thickness: 300um
Bump height: 12um
4
BLOCK DIAGRAM
Figure 4-1 : SSD1680 Block Diagram

<!-- Page 7 -->

SSD1680
Rev 0.14
P 7/46
Jun 2019
Solomon Systech
5
PIN DESCRIPTION
Key:
I = Input
O =Output
IO = Bi-directional (input/output)
P = Power pin
C = Capacitor Pin
NC = Not Connected
Table 5-1: Power Supply Pins
Name
Type
Connect to
Function
Description
When not
in use
VCI
P
Power
Supply
Power Supply
Power input pin for the chip.
-
VCIA
P
Power
Supply
Power Supply
Power input pin for the chip.
- Connect to VCI in the application circuit.
-
VDDIO
P
Power
Supply
Power for
interface logic
pins
Power input pin for the Interface.
- Connect to VCI in the application circuit.
-
VDD
P
Capacitor
Regulator
output
Core logic power pin
VDD can be regulated internally from VCI.
- For the single chip application, a capacitor
should be connected between VDD and VSS
under all circumstances.
- For the cascade mode application, a capacitor
should be connected between VDD and VSS in
the master chip under all circumstances.  For the
slave chip, the capacitor is not necessary as
VDD will be supplied from the cascade master
chip externally.
-
VSS
P
VSS
GND
Ground (Digital).
-
VSSA
P
VSS
GND
Ground (Analog)
- Connect to VSS in the application circuit.
-
VSSBG
P
VSS
GND
Ground (Reference) pin.
- Connect to VSS in the application circuit.
-
VSSGS
P
VSS
GND
Ground (Output) pin.
- Connect to VSS in the application circuit.
-
VPP
P
Power
Supply
OTP power
Power Supply for OTP Programming.
Open

<!-- Page 8 -->

SSD1680
Rev 0.14
P 8/46
Jun 2019
Solomon Systech
Table 5-2: Interface Logic Pins
Name
Type
Connect to
Function
Description
When not
in use
SCL
I
MPU
Data Bus
This pin is serial clock pin for interface.
Refer to MCU interface in Section 6.1.
-
SDA
I/O
MPU
Data Bus
This pin is serial data pin for interface.
Refer to MCU interface in Section 6.1.
-
CS#
I
MPU
Logic Control
This pin is the chip select input connecting to the
MCU. Refer to MCU interface in Section 6.1.
VDDIO or
VSS
D/C#
I
MPU
Logic Control
This pin is Data/Command control pin connecting
to the MCU. Refer to MCU interface in Section 6.1.
VDDIO or
VSS
RES#
I
MPU
System Reset
This pin is reset signal input.
Active Low.
-
BUSY
O
MPU
Device Busy
Signal
This pin is Busy state output pin.
When Busy is High, the operation of the chip
should not be interrupted, and command should
not be sent.
For example., The chip would output Busy pin as
High when
- Outputting display waveform; or
- Programming with OTP
- Communicating with digital temperature sensor
In the cascade mode, the BUSY pin of the slave
chip should be left open.
Open
M/S#
I
VDDIO/VSS
Cascade
Mode
Selection
This pin is Master and Slave selection pin.
- For the single chip application, the M/S# pin
should be connected to VDDIO.
- In the cascade mode:
For Master Chip, the M/S# pin should be
connected to VDDIO.
For Slave Chip, the M/S# pin should be
connected to VSS.  The oscillator, booster and
regulator circuits of the slave chip will be
disabled.  The corresponding pins including CL,
VDD, VDDIO, VGH, VGL, VSH1, VSH2, VSL
and VCOM must be connected to the master
chip.
-
CL
I/O
NC
Clock signal
This pin is the clock signal pin.
- For the single chip application, the CL pin should
be left open.
- In the cascade mode, the CL pin of the slave
chip should be connected to the CL pin of the
master chip.
Open
BS1
I
VDDIO/VSS
MCU Interface
Mode
Selection
This pin is for selecting 3-wire or 4-wire SPI bus.
BS1
MCU Interface
L
4-wire SPI
H
3-wire SPI (9-bit SPI)
-
TSDA
I/O
Temperature
sensor SDA
Interface to
Digital Temp.
Sensor
This pin is I2C Interface to digital temperature
sensor Data pin.
External pull up resistor is required when
connecting to I2C slave.
Open
TSCL
O
Temperature
sensor SCL
Interface to
Digital Temp.
Sensor
This pin is I2C Interface to digital temperature
sensor Clock pin.
External pull up resistor is required when
connecting to I2C slave.
Open

<!-- Page 9 -->

SSD1680
Rev 0.14
P 9/46
Jun 2019
Solomon Systech
Table 5-3: Analog Pins
Name
Type
Connect to
Function
Description
When not
in use
GDR
O
POWER
MOSFET
Driver
Control
VGH, VGL
Generation
This pin is N-Channel MOSFET gate drive control
pin.
-
RESE
I
Booster
Control
Input
This pin is Current sense input pin for the control
Loop.
-
VGH
C
Stabilizing
capacitor
This pin is Positive Gate driving voltage.
Connect a stabilizing capacitor between VGH and
VSS in the application circuit.
-
VGL
C
Stabilizing
capacitor
This pin is Negative Gate driving voltage.
Connect a stabilizing capacitor between VGL and
VSS in the application circuit.
-
VSH1
C
Stabilizing
capacitor
VSH1, VSH2,
VSL
Generation
This pin is Positive Source driving voltage, VSH1
Connect a stabilizing capacitor between VSH1 and
VSS in the application circuit.
-
VSH2
C
Stabilizing
capacitor
This pin is Positive Source driving voltage, VSH2
Connect a stabilizing capacitor between VSH2 and
VSS in the application circuit.
VSL
C
Stabilizing
capacitor
This pin is Negative Source driving voltage.
Connect a stabilizing capacitor between VSL and
VSS in the application circuit.
-
VCOM
C
Panel/
Stabilizing
capacitor
VCOM
Generation
This pins is VCOM driving voltage
Connect a stabilizing capacitor between VCOM
and VSS in the application circuit.
-
Table 5-4: Driver Output Pins
Name
Type
Connect to
Function
Description
When not
in use
S [175:0]
O
Panel
Source driving
signal
Source output pin.
Open
G [295:0]
O
Panel
Gate driving
signal
Gate output pin.
Open
VBD
O
Panel
Border driving
signal
Border output pin.
Open
Table 5-5: Miscellaneous Pins
Name
Type
Connect to
Function
Description
When not
in use
NC
NC
NC
Not Connected
This is dummy pin. It should not be connected with
other NC pins.
Open
RSV
NC
NC
Reserved
This is a reserved pin and should be kept open.
Open
TPA, TPB,
TPC, TPD,
TPF, FB
NC
NC
Reserved for
Testing
Reserved pins.
- Keep open.
- Do not connect to other NC pins and test pins
including TPA, TPB, TPC, TPD, TPE, TPF, TIN
and FB.
Open
TIN
I
NC
Reserved for
Testing
This is a reserved pin and should be kept open.
Open
TPE
O
NC
Reserved for
Testing
This is a reserved pin and should be kept open.
Open

<!-- Page 10 -->

SSD1680
Rev 0.14
P 10/46
Jun 2019
Solomon Systech
6
Functional Block Description
6.1 MCU Interface
6.1.1 MCU Interface selection
The SSD1680 can support 3-wire/4-wire serial peripheral. MCU interface is pin selectable by BS1
shown in Table 6-1.
Table 6-1 : Interface pins assignment under different MCU interface
Pin Name
MCU Interface
BS1
RES#
CS#
D/C#
SCL
SDA
4-wire serial peripheral
interface (SPI)
L
RES#
CS#
DC#
SCL
SDA
3-wire serial peripheral
interface (SPI) – 9 bits SPI
H
RES#
CS#
L
SCL
SDA
Note
(1) L is connected to VSS and H is connected to VDDIO
6.1.2 MCU Serial Interface (4-wire SPI)
The 4-wire SPI consists of serial clock SCL, serial data SDA, D/C# and CS#. The control pins status in
4-wire SPI in writing command/data is shown in Table 6-2 and the write procedure 4-wire SPI is shown
in Table 6-2
Table 6-2 : Control pins status of 4-wire SPI
Function
SCL pin
SDA pin
D/C# pin
CS# pin
Write command
↑
Command bit
L
L
Write data
↑
Data bit
H
L
Note:
(1) L is connected to VSS and H is connected to VDDIO
(2) ↑ stands for rising edge of signal
(3) SDA (Write Mode) is shifted into an 8-bit shift register on every rising edge of SCL in the order of
D7, D6, ... D0. The level of D/C# should be kept over the whole byte. The data byte in the shift
register is written to the Graphic Display Data RAM (RAM)/Data Byte register or command Byte
register according to D/C# pin.
Figure 6-1 : Write procedure in 4-wire SPI mode

<!-- Page 11 -->

SSD1680
Rev 0.14
P 11/46
Jun 2019
Solomon Systech
In the read operation (Command 0x1B, 0x27, 0x2D, 0x2E, 0x2F, 0x35). After CS# is pulled low, the
first byte sent is command byte, D/C# is pulled low.  After command byte sent, the following byte(s)
read are data byte(s), so D/C# bit is then pulled high.  An 8-bit data will be shifted out on every clock
falling edge.  The serial data SDA bit shifting sequence is D7, D6, to D0 bit. Figure 6-2 shows the read
procedure in 4-wire SPI.
Figure 6-2 : Read procedure in 4-wire SPI mode
6.1.3 MCU Serial Peripheral Interface (3-wire SPI)
The 3-wire SPI consists of serial clock SCL, serial data SDA and CS#. The operation is similar to 4-
wire SPI while D/C# pin is not used and it must be tied to LOW.  The control pins status in 3-wire SPI
is shown in Table 6-3.
In the write operation, a 9-bit data will be shifted into the shift register on every clock rising edge.  The
bit shifting sequence is D/C# bit, D7 bit, D6 bit to D0 bit.  The first bit is D/C# bit which determines the
following byte is command or data.  When D/C# bit is 0, the following byte is command.  When D/C#
bit is 1, the following byte is data. Table 6-3 shows the write procedure in 3-wire SPI
Table 6-3 : Control pins status of 3-wire SPI
Function
SCL pin
SDA pin
D/C# pin
CS# pin
Write command
↑
Command bit
Tie LOW
L
Write data
↑
Data bit
Tie LOW
L
Note:
(1)
L is connected to VSS and H is connected to VDDIO
(2)
↑ stands for rising edge of signal
Figure 6-3 : Write procedure in 3-wire SPI
SCL
SDA
(Read Mode)
SDA
(Write Mode)
D7
D6
D5
D4
D3
D2
D1
D0
D/C#
CS#
D7
D0

<!-- Page 12 -->

SSD1680
Rev 0.14
P 12/46
Jun 2019
Solomon Systech
In the read operation (Register 0x1B, 0x27, 0x2D, 0x2E, 0x2F, 0x35).  SDA data are transferred in the
unit of 9 bits. After CS# pull low, the first byte is command byte, the D/C# bit is as 0 and following with
the register byte.  After command byte send, the following byte(s) are data byte(s), with D/C# bit is 1.
After D/C# bit sending from MCU, an 8-bit data will be shifted out on every clock falling edge.  The serial
data SDA bit shifting sequence is D7, D6, to D0 bit. Figure 6-4 shows the read procedure in 3-wire SPI.
Figure 6-4 : Read procedure in 3-wire SPI mode
6.2 OSCILLATOR
The oscillator module generates the clock reference for waveform timing and analog operations.
6.3 BOOSTER & REGULATOR
A voltage generation system is included in the driver. It provides all necessary driving voltages required for an
AMEPD panel including VGH, VGL, VSH1, VSH2, VSL and VCOM.  External application circuit is needed to make
the on-chip booster & regulator circuit work properly.
6.4 VCOM SENSING
This functional block provides the scheme to select the optimal VCOM DC level. The sensed value can be
programmed into OTP.
The flow of VCOM sensing:
•
Active Gate is scanning during the VCOM sense Period.
•
Source are VSS.
•
VCOM pin used for sensing.
•
During Sensing period, BUSY is high.
•
After Sensing, Active Gate return to non-select stage.
C3
C2
GDR
C5
VSH1
VSH1
Generator
C4
VGL
C7
VSL
VSL
Generator
C8
VCOM
VCOM
Generator
C1
VDD
VDDIO
VCI
VSS
C0
RESE
VGH
L1
Q1
R1
D1
D2
D3
VGH & VGL
Generator
C6
VSH2
VSH2
Generator

<!-- Page 13 -->

SSD1680
Rev 0.14
P 13/46
Jun 2019
Solomon Systech
6.5 RAM
The On chip display RAM is holding the image data.
1 set of RAM is built for Mono B/W. The RAM size is 176x296 bits.
1 set of RAM is built for Mono Red. The RAM size is 176x296 bits.
Table 6-4 : RAM bit and LUT mapping for 3-color display
Data bit in R RAM
Data bit in B/W RAM
Image Color
LUT
0
0
Black
LUT 0 for driving Black
0
1
White
LUT 1 for driving White
1
0
Red
LUT 2 for driving Red
1
1
Red
LUT 3 = LUT2
Table 6-5 : RAM bit and LUT mapping for black/white display
Data bit in R RAM
Data bit in B/W RAM
Image Color
LUT
0
0
Black
LUT 0 for driving Black
0
1
White
LUT 1 for driving White
1
0
Black
LUT 2 = LUT0
1
1
White
LUT 3 = LUT1
6.6 Programmable Waveform for Gate, Source and VCOM
Figure 6-5 : Gate waveform and Programmable Source and VCOM waveform illustration
SR:repeat times between two Sub Groups from 1 to 256
RP:repeat times for Group from 1 to 256
RP[0]
RP[1]
RP[11]
SR[0AB]
SR[0CD]
SR[1AB]
SR[1CD]
SR[11AB]
SR[11CD]
VSH1
VSH2
VSS
……..
VSL
Option
for LUT
d
  Sub group C&D
group0
group1
group11
phase0A
phase0B
phase0C
phase0D
phase1A phase1B phase1C phase1D
phase11A phase11B phase11Cphase11D
  Sub group A&B
Source
Signal
end
VGH
……..
VGL
…
TP[0A]
TP[0B]
TP[0C]
TP[0D]
TP[1A]
TP[1B]
TP[1C]
TP[1D]
TP[11A]
TP[11B]
TP[11C]
…
…
…
…
…
TP[11D]
…
…
…
…
…
…
…
…
…
…
…
…
…
…
…
…
…
…
Gate
Signal
…
…
…
…
…
…
XON[11CD]
XON[0AB]
XON[0CD]
XON[1AB]
XON[1CD]
XON[11AB]
TP: time of phase length from 0 to 255* frames
0indicates phase skipped
XON: All Gate On selection for each nAB or nCD.
FR: Frame frequency selection for each group.
EOPT: Option for LUT end
FR[0]
FR[1]
FR[11]

<!-- Page 14 -->

SSD1680
Rev 0.14
P 14/46
Jun 2019
Solomon Systech
In the programmable waveform for Source and VCOM, there are 12 groups (Group0 to Group11) and each group
has 4 phases (Phase A to Phase D) and 2 state repeats (Phase A and B, Phase C and D).  Totally, there are 48
phases.  In addition, in each phase, the phase length (TP[nX]) can be set by number of frame from 0 to 255
frames.  Also, each group can be repeated with repeat counting number (RP[n]) from 1 to 256 times; each AB /
CD phases can be repeated with state repeat counting number (SR[nAB]/SR[nCD]) from 1 to 256 times.  For the
voltage, there is four levels for Source voltage (VSS, VSH1, VSH2, VSL) and three levels for VCOM voltage
(DCVCOM, VSH1+DCVCOM, VSL+DCVOM).
The description of each parameter is as follows.
1)
TP[nX] represents the phase length set by the number of frame.
•
The range of TP[nX] is from 0 to 255.
•
n represents the Group number from 0 to 11; X represents the phase number from A to D.
•
When TP[nX] = 0, the phase is skipped.  When TP[nX] = 1, the phase is 1 frame, and so on.  The
maximum phase length is 255 frame.
2)
RP[n] represents the repeat counting number for the Group.
•
The range of RP[n] is from 0 to 255.
•
n represents the Group number from 0 to 11.
•
RP[n] = 0 indicates that the repeat times =1, RP[n] = 1 indicates that the repeat times = 2, and so on.
The maximum repeat times is 256.
3)
SR[nAB] and SR[nCD] represent the state repeat counting number for Phase A & B and Phase C & D
respectively.
•
The range of SR[nXY] is from 0 to 255.
•
n represents the Group number from 0 to 11.
•
SR[nXY] = 0 indicates that the repeat times =1, SR[nXY] = 1 indicates that the repeat times = 2, and so
on.  The maximum repeat times is 256.
4)
VS[nX-LUTm] represents Source and VCOM voltage level which is used in each phase.  Table 6-6
shows the voltage settings for source voltage and VCOM voltage.
•
n represents the Group number from 0 to 11.
•
m represents the LUT number from 0-4.
Table 6-6 : VS[nX-LUTm] settings for Source voltage and VCOM voltage
VS[nX-LUTm]
Source voltage
VCOM voltage
00
VSS
DCVCOM
01
VSH1
VSH1 + DCVCOM
10
VSL
VSL + DCVCOM
11
VSH2
N/A
5)
FR[n] indicates the frame rate of group n
•
The range of FR [n] is from 0 to 7.
•
n represents the Group number from 0 to 11.
6)
XON[nAB] and XON[nCD], indicates the gate scan selection.
•
n represents the Group number from 0 to 11.
•
XON[nXY] = 0 indicates Normal gate scan in Phase[nX] & Phase[nY].
•
XON[nXY] = 1 indicates All gate on, that Gate keeps High until the phase for normal gate scan, in
Phase[nX] & Phase[nY].

<!-- Page 15 -->

SSD1680
Rev 0.14
P 15/46
Jun 2019
Solomon Systech
6.7 WAVEFORM SETTING
As described in Section 6.6, parameters VS[nX-LUTm], TP[nX], RP[n], SR[nXY], FR[n] and XON[nXY]  are used
to define the driving waveform. In the SSD1680, there are 159 bytes in the waveform setting to store LUT0, LUT1,
LUT2, LUT3 and LUT4, gate voltage, source voltage and frame rate.  The waveform LUT of a particular
temperature range can be loaded from OTP or written by MCU.
•
WS byte 0~152, the content of VS[nX-LUTm], TP[nX], RP[n], SR[nXY], FR[n] and XON[nXY]  are defined
by Register 0x32
•
WS byte 153, the content of Option for LUT end, is the parameter belonging to Register 0x3F.
•
WS byte 154, the content of gate level, is the parameter defined by Register 0x03.
•
WS byte 155~157, the content of source level, is the parameter defined by Register 0x04.
•
WS byte 158, the content of VCOM level, is the parameter defined by Register 0x2C.
The SSD1680 waveform setting is shown in Figure 6-6 : Waveform Setting mapping
Figure 6-6 : Waveform Setting mapping
addr.
D7
D6
D5
D4
D3
D2
D1
D0
addr.
D7
D6
D5
D4
D3
D2
D1
D0
0
81
1
82
2
83
3
84
4
85
5
86
6
87
7
88
8
89
9
90
10
91
11
92
12
93
13
94
14
95
15
96
16
97
17
98
18
99
19
100
20
101
21
102
22
103
23
104
24
105
25
106
26
107
27
108
28
109
29
110
30
111
31
112
32
113
33
114
34
115
35
116
36
117
37
118
38
119
39
120
40
121
41
122
42
123
43
124
44
125
45
126
46
127
47
128
48
129
49
130
50
131
51
132
52
133
53
134
54
135
55
136
56
137
57
138
58
139
59
140
60
141
61
142
62
143
63
144
64
145
65
146
66
147
67
148
68
149
69
150
XON[0AB]
XON[0CD]
XON[1AB]
XON[1CD]
XON[2AB]
XON[2CD]
XON[3AB]
XON[3CD]
70
151
XON[4AB]
XON[4CD]
XON[5AB]
XON[5CD]
XON[6AB]
XON[6CD]
XON[7AB]
XON[7CD]
71
152
XON[8AB]
XON[8CD]
XON[9AB]
XON[9CD] XON[10AB] XON[10CD] XON[11AB] XON[11CD]
72
153
73
154
74
155
75
156
76
157
77
158
78
79
80
EOPT
TP[11D]
SR[11CD]
RP[11]
FR[0]
FR[1]
SR[10CD]
RP[10]
TP[11A]
TP[11B]
SR[11AB]
TP[11C]
RP[9]
TP[10A]
TP[10B]
SR[10AB]
TP[10C]
TP[10D]
TP[9A]
TP[9B]
SR[9AB]
TP[9C]
TP[9D]
SR[9CD]
TP[7D]
SR[7CD]
RP[7]
TP[8A]
TP[8B]
SR[8AB]
SR[0AB]
SR[0CD]
TP[1A]
SR[1AB]
TP[1C]
RP[1]
VS[10A-L4]
VS[10B-L4]
VS[10C-L4]
VS[10D-L4]
VS[11A-L4]
VS[11B-L4]
VS[11C-L4]
VS[11D-L4]
VS[11C-L2]
VS[11D-L2]
VS[10A-L3]
VS[10B-L3]
VS[10C-L3]
VS[10D-L3]
VS[10A-L1]
VS[10B-L1]
VS[10C-L1]
VS[10D-L1]
VS[11A-L1]
VS[11B-L1]
VS[11C-L1]
VS[11D-L1]
VS[10A-L0]
VS[10B-L0]
VS[10C-L0]
VS[10D-L0]
VS[11A-L0]
VS[11B-L0]
VS[11C-L0]
VS[11D-L0]
VCOM
TP[8C]
TP[8D]
SR[8CD]
RP[8]
SR[7AB]
VGH
VSH1
VSH2
VSL
SR[2AB]
SR[2CD]
TP[3B]
TP[7C]
VS[8A-L4]
VS[8B-L4]
VS[8C-L4]
VS[8D-L4]
TP[7B]
VS[9A-L4]
VS[9B-L4]
VS[9C-L4]
VS[9D-L4]
RP[6]
VS[7A-L4]
VS[7B-L4]
VS[7C-L4]
VS[7D-L4]
TP[7A]
VS[11A-L3]
VS[11B-L3]
VS[11C-L3]
VS[11D-L3]
VS[5A-L4]
VS[5B-L4]
VS[5C-L4]
VS[5D-L4]
SR[6CD]
VS[6A-L4]
VS[6B-L4]
VS[6C-L4]
VS[6D-L4]
VS[3A-L4]
VS[3B-L4]
VS[3C-L4]
VS[3D-L4]
TP[6C]
VS[4A-L4]
VS[4B-L4]
VS[4C-L4]
VS[4D-L4]
VS[2A-L4]
VS[2B-L4]
VS[2C-L4]
VS[2D-L4]
SR[6AB]
TP[6D]
VS[0A-L4]
VS[0B-L4]
VS[0C-L4]
VS[0D-L4]
TP[6A]
VS[1A-L4]
VS[1B-L4]
VS[1C-L4]
VS[1D-L4]
VS[9A-L3]
VS[9B-L3]
VS[9C-L3]
VS[9D-L3]
RP[5]
TP[6B]
VS[7A-L3]
VS[7B-L3]
VS[7C-L3]
VS[7D-L3]
TP[5D]
VS[8A-L3]
VS[8B-L3]
VS[8C-L3]
VS[8D-L3]
VS[6A-L3]
VS[6B-L3]
VS[6C-L3]
VS[6D-L3]
TP[5C]
SR[5CD]
VS[4A-L3]
VS[4B-L3]
VS[4C-L3]
VS[4D-L3]
TP[5B]
VS[5A-L3]
VS[5B-L3]
VS[5C-L3]
VS[5D-L3]
VS[3A-L3]
VS[3B-L3]
VS[3C-L3]
VS[3D-L3]
TP[5A]
SR[5AB]
VS[10A-L2]
VS[10B-L2]
VS[10C-L2]
VS[1A-L3]
VS[1B-L3]
VS[1C-L3]
VS[1D-L3]
SR[4CD]
VS[2A-L3]
VS[2B-L3]
VS[2C-L3]
VS[2D-L3]
VS[0A-L3]
VS[0B-L3]
VS[0C-L3]
VS[0D-L3]
TP[4D]
RP[4]
VS[10D-L2]
VS[11A-L2]
VS[11B-L2]
VS[8A-L2]
VS[8B-L2]
VS[8C-L2]
VS[8D-L2]
SR[4AB]
VS[9A-L2]
VS[9B-L2]
VS[9C-L2]
VS[9D-L2]
VS[7A-L2]
VS[7B-L2]
VS[7C-L2]
VS[7D-L2]
TP[4B]
TP[4C]
VS[5A-L2]
VS[5B-L2]
VS[5C-L2]
VS[5D-L2]
RP[3]
VS[6A-L2]
VS[6B-L2]
VS[6C-L2]
VS[6D-L2]
VS[4A-L2]
VS[4B-L2]
VS[4C-L2]
VS[4D-L2]
SR[3CD]
TP[4A]
VS[2A-L2]
VS[2B-L2]
VS[2C-L2]
VS[2D-L2]
TP[3C]
VS[3A-L2]
VS[3B-L2]
VS[3C-L2]
VS[3D-L2]
VS[1A-L2]
VS[1B-L2]
VS[1C-L2]
VS[1D-L2]
SR[3AB]
TP[3D]
VS[9A-L1]
VS[9B-L1]
VS[9C-L1]
VS[9D-L1]
TP[3A]
VS[0A-L2]
VS[0B-L2]
VS[0C-L2]
VS[0D-L2]
VS[8A-L1]
VS[8B-L1]
VS[8C-L1]
VS[8D-L1]
RP[2]
FR[2]
FR[3]
FR[4]
VS[6A-L1]
VS[6B-L1]
VS[6C-L1]
VS[6D-L1]
TP[2D]
VS[7A-L1]
VS[7B-L1]
VS[7C-L1]
VS[7D-L1]
VS[5A-L1]
VS[5B-L1]
VS[5C-L1]
VS[5D-L1]
TP[2C]
FR[5]
FR[8]
FR[9]
VS[3A-L1]
VS[3B-L1]
VS[3C-L1]
VS[3D-L1]
TP[2B]
VS[4A-L1]
VS[4B-L1]
VS[4C-L1]
VS[4D-L1]
VS[2A-L1]
VS[2B-L1]
VS[2C-L1]
VS[2D-L1]
TP[2A]
VS[0A-L1]
VS[0B-L1]
VS[0C-L1]
VS[0D-L1]
SR[1CD]
VS[1A-L1]
VS[1B-L1]
VS[1C-L1]
VS[1D-L1]
VS[9A-L0]
VS[9B-L0]
VS[9C-L0]
VS[9D-L0]
TP[1D]
FR[6]
FR[7]
FR[10]
VS[7A-L0]
VS[7B-L0]
VS[7C-L0]
VS[7D-L0]
VS[8A-L0]
VS[8B-L0]
VS[8C-L0]
VS[8D-L0]
VS[6A-L0]
VS[6B-L0]
VS[6C-L0]
VS[6D-L0]
TP[1B]
FR[11]
VS[4C-L0]
VS[4D-L0]
RP[0]
VS[5A-L0]
VS[5B-L0]
VS[5C-L0]
VS[5D-L0]
VS[3A-L0]
VS[3B-L0]
VS[3C-L0]
VS[3D-L0]
TP[0D]
VS[4A-L0]
VS[4B-L0]
VS[1A-L0]
VS[1B-L0]
VS[1C-L0]
VS[1D-L0]
TP[0B]
VS[2A-L0]
VS[0A-L0]
VS[0B-L0]
VS[0C-L0]
VS[0D-L0]
TP[0A]
VS[2B-L0]
VS[2C-L0]
VS[2D-L0]
TP[0C]

<!-- Page 16 -->

SSD1680
Rev 0.14
P 16/46
Jun 2019
Solomon Systech
6.8 Temperature Searching
The SSD1680 has internal temperature sensor to detect the environment temperature or can communicate with
the external temperature sensor by I2C single master interface or can communicate with the external MCU to get
the temperature value through SPI.  In the SSD1680, there is a dedicated format for the temperature value so
that the driver IC can understand it.  The format of temperature value is described in Section 6.8.3.
6.8.1 Internal Temperature Sensor
The internal temperature sensor can be selected by command register. The accuracy of it is ±2degC from -
25degC to 50degC.
6.8.2 External Temperature Sensor I2C Single Master Interface
The driver IC can communicate with the external temperature sensor through I2C single master interface (TSDA
and TSCL). TSDA will be SDA and TSCL will be SCL. TSDA and TSCL are required to connect with external pull-
up resistor. Temperature register value of external temperature sensor can be read by command register.
6.8.3 Format of temperature value
The temperature value is defined by 12-bit binary.  The rules are shown as below.
•
If the Temperature value MSByte bit D11 = 0, then
the temperature is positive and value (DegC) = + (Temperature value) / 16
•
If the Temperature value MSByte bit D11 = 1, then
the temperature is negative and value (DegC) = - (2’s complement of Temperature value) / 16
Table 6-7 shows some examples of 12-bit binary temperature value:
Table 6-7 : Example of 12-bit binary temperature settings for temperature ranges
12-bit binary
(2's complement)
Hexadecimal
 Value
TR Value
[DegC]
0111 1111 1111
7FF
128
0111 1111 1111
7FF
127.9
0110 0100 0000
640
100
0101 0000 0000
500
80
0100 1011 0000
4B0
75
0011 0010 0000
320
50
0001 1001 0000
190
25
0000 0000 0100
004
0.25
0000 0000 0000
000
0
1111 1111 1100
FFC
-0.25
1110 0111 0000
E70
-25
1100 1001 0000
C90
-55

<!-- Page 17 -->

SSD1680
Rev 0.14
P 17/46
Jun 2019
Solomon Systech
6.9 Waveform Setting searching mechanism
As mentioned in Section 6.7, the SSD1680 OTP can store waveform setting and temperature range.  If waveform
setting and temperature range are programmed in OTP memory, corresponding waveform LUT can be selected
according to the sensed temperature to drive the display. The Waveform Setting searching mechanism by driver
IC is as follows.
1)
Read temperature value by command register in the format of 12-bit binary.
2)
According to read temperature and display mode selection, search LUT in OTP from TR0 to TR35 in
sequence.  The last match will be selected, then, the corresponding WS will be loaded in the LUT register
to drive the display.
Remark: Waveform LUT selection criteria is “Lower temperature bound < Sensed temperature ≤ Upper
temperature bound”.
Table 6-8 shows an example for the waveform LUT searching from OTP:
• If the read temperature is 25degC, then, WS4 will be selected.
• If the read temperature is 34degC, then, WS7 will be selected.  Although 34degC is also in the temperature
range TR6, according to searching mechanism, the last match should be selected. Therefore, WS7 is
selected.
Table 6-8 : Example of waveform settings selection based on temperature ranges.
Waveform
LUT in OTP
Temperature
Range in OTP
TR Lower Limit
[Hex]
TR Upper Limit
[Hex]
Temperature range in OTP
WS0
TR0
800
050
-128 DegC < Temperature ≤  5 DegC
WS1
TR1
050
0A0
5 DegC < Temperature ≤  10DegC
WS2
TR2
0A0
0F0
10 DegC < Temperature ≤  15DegC
WS3
TR3
0F0
140
15 DegC < Temperature ≤  20DegC
WS4
TR4
140
190
20 DegC < Temperature ≤  25DegC
WS5
TR5
190
1E0
25 DegC < Temperature ≤  30DegC
WS6
TR6
1E0
230
30 DegC < Temperature ≤  35DegC
WS7
TR7
210
7FF
33 DegC < Temperature ≤  127.9DegC
Others
Others
000
000
Precaution:
Please ensure the temperature range covers whole range of application temperatures, display will not be
updated if no suitable temperature range matches the sensed temperature.

<!-- Page 18 -->

SSD1680
Rev 0.14
P 18/46
Jun 2019
Solomon Systech
6.10 One Time Programmable (OTP) Memory
In the SSD1680, there is an embedded OTP memory which is designed to store the waveform settings of different
temperature range and some variables/parameters.  The OTP memory can store 36 sets of waveform LUT settings
(WS), 36 sets of temperature range (TR), VCOM value, display mode selection, waveform version and user ID.
Figure 6 7 shows the address mapping of the 36 waveform setting (WS0 to WS35) and temperature range (TR0 to
TR35).
Figure 6-7 : The Waveform setting mapping in OTP for waveform setting and temperature range
6.11 The Format for Temperature Range (TR)
The format of TR Lower limit and Upper limit as shown in Figure 6-8 which temp_L[11:0] is the lower limit and
temp_H[11:0] is the upper limit of the temperature range.  There has 36sets of TR for waveform LUT searching.
D7
D6
D5
D4
D3
D2
D1
D0
temp_L[7:0]
temp_H[3:0]
temp_L[11:8]
temp_H[11:4]
Figure 6-8 : Format of Temperature Range (TR) in OTP
addr.
D7
D6
D5
D4
D3
D2
D1
D0
0
…
158
159
…
317
318
…
476
477
…
635
636
…
794
5406
…
5564
5565
…
5723
5724
5725
5726
5727
5728
5729
5730
5731
5732
5733
5734
5735
5736
5737
5738
5826
5827
5828
5829
5830
5831
…
TR35
TR34
…
TR4
TR3
TR2
TR1
TR0
WS35
WS34
WS4
WS3
WS2
WS1
WS0

<!-- Page 19 -->

SSD1680
Rev 0.14
P 19/46
Jun 2019
Solomon Systech
6.12 Cascade Mode
SSD1680 has a cascade mode that can cascade 2 chips to achieve the display resolution up to 352 (sources) x 296
(gates).  The pin M/S# is used to configure the chip.  When M/S# is connected to VDDIO, the chip is configured as a
master chip.  When M/S# is connected to VSS, the chip is configured as a slave chip.
When the chip is configured as a master chip, it will be the same as a single chip application, ie, all circuit blocks will be
worked as usual.  When the chip is configured as a slave chip, its oscillator and booster & regulator circuit will be disabled.
The oscillator clock and all booster voltages will be come from the master chip.  Therefore, the corresponding pins
including CL, VDD, VGH, VGL, VSH1, VSH2, VSL, VGL and VCOM must be connected to the master chip.
6.13 VCI Detection
The VCI detection function is used to detect the VCI level when it is lower than Vlow, threshold voltage set by register.
In SSD1680, there is a command to execute the VCI detection function.  When the VCI detection command is issued,
the VCI detection will be executed.  During the detection period, BUSY output is at high level.  BUSY output is at low
level when the detection is completed.  Then, user can issue the Status Bit Read command to check the status bit for
the result of VCI, which 0 is normal, 1 is VCI<Vlow.
6.14 HV Ready Detection
The HV Ready detection function is used to detect whether the analog block is ready.
In SSD1680, there is a command to execute the HV Ready detection function.  When the HV Ready detection command
is issued, the HV Ready will be executed.  During the detection period, BUSY output is at high level.  BUSY output is at
low level when the detection is completed.  Then, user can issue the Status Bit Read command to check the status bit
for the result of HV Ready, which 0 is normal, 1 indicate HV is not ready.

<!-- Page 20 -->

SSD1680
Rev 0.14
P 20/46
Jun 2019
Solomon Systech
7
COMMAND TABLE
Table 7-1: Command Table
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
01
0
0
0
0
0
0
0
1
Driver Output control
Gate setting
A[8:0]= 127h [POR], 296 MUX
MUX Gate lines setting as (A[8:0] + 1).
B[2:0] = 000 [POR].
Gate scanning sequence and direction
B[2]: GD
Selects the 1st output Gate
GD=0 [POR],
G0 is the 1st gate output channel, gate
output sequence is G0,G1, G2, G3, …
GD=1,
G1 is the 1st gate output channel, gate
output sequence is G1, G0, G3, G2, …
B[1]: SM
Change scanning order of gate driver.
SM=0 [POR],
G0, G1, G2, G3…295 (left and right gate
interlaced)
SM=1,
G0, G2, G4  …G294, G1, G3,  …G295
B[0]: TB
TB = 0 [POR], scan from G0 to G295
TB = 1, scan from G295 to G0.
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
0
0
0
0
0
0
0
A8
0
1
0
0
0
0
0
B2
B1
B0
0
0
03
0
0
0
0
0
0
1
1
Gate Driving voltage
Control
Set Gate driving voltage
A[4:0] = 00h [POR]
VGH setting from 10V to 20V
A[4:0]
VGH
A[4:0]
VGH
00h
20
0Dh
15
03h
10
0Eh
15.5
04h
10.5
0Fh
16
05h
11
10h
16.5
06h
11.5
11h
17
07h
12
12h
17.5
08h
12.5
13h
18
07h
12
14h
18.5
08h
12.5
15h
19
09h
13
16h
19.5
0Ah
13.5
17h
20
0Bh
14
Other
NA
0Ch
14.5
0
1
0
0
0
A4
A3
A2
A1
A0

<!-- Page 21 -->

SSD1680
Rev 0.14
P 21/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
04
0
0
0
0
0
1
0
0
Source Driving voltage
Control
Set Source driving voltage
A[7:0] = 41h [POR], VSH1 at 15V
B[7:0] = A8h [POR], VSH2 at 5V.
C[7:0] = 32h [POR], VSL at -15V
Remark: VSH1>=VSH2
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
B7
B6
B5
B4
B3
B2
B1
B0
0
1
C7
C6
C5
C4
C3
C2
C1
C0
A[7]/B[7] = 1,
VSH1/VSH2 voltage setting from 2.4V
to 8.8V
A[7]/B[7] = 0,
VSH1/VSH2 voltage setting from 9V
to 17V
C[7] = 0,
VSL setting from -5V to -17V
0
0
08
0
0
0
0
1
0
0
0
Initial Code Setting
OTP Program
Program Initial Code Setting
The command required CLKEN=1.
Refer to Register 0x22 for detail.
BUSY pad will output high during
operation.
0
0
09
0
0
0
0
1
0
0
1
Write Register for Initial
Code Setting
Write Register for Initial Code Setting
Selection
A[7:0] ~ D[7:0]: Reserved
Details refer to Application Notes of Initial
Code Setting
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
B7
B6
B5
B4
B3
B2
B1
B0
0
1
C7
C6
C5
C4
C3
C2
C1
C0
0
1
D7
D6
D5
D4
D3
D2
D1
D0
0
0
0A
0
0
0
0
1
0
1
0
Read Register for Initial
Code Setting
Read Register for Initial Code Setting
A/B[7:0]
VSH1/VSH2
A/B[7:0]
VSH1/VSH2
8Eh
2.4
AFh
5.7
8Fh
2.5
B0h
5.8
90h
2.6
B1h
5.9
91h
2.7
B2h
6
92h
2.8
B3h
6.1
93h
2.9
B4h
6.2
94h
3
B5h
6.3
95h
3.1
B6h
6.4
96h
3.2
B7h
6.5
97h
3.3
B8h
6.6
98h
3.4
B9h
6.7
99h
3.5
BAh
6.8
9Ah
3.6
BBh
6.9
9Bh
3.7
BCh
7
9Ch
3.8
BDh
7.1
9Dh
3.9
BEh
7.2
9Eh
4
BFh
7.3
9Fh
4.1
C0h
7.4
A0h
4.2
C1h
7.5
A1h
4.3
C2h
7.6
A2h
4.4
C3h
7.7
A3h
4.5
C4h
7.8
A4h
4.6
C5h
7.9
A5h
4.7
C6h
8
A6h
4.8
C7h
8.1
A7h
4.9
C8h
8.2
A8h
5
C9h
8.3
A9h
5.1
CAh
8.4
AAh
5.2
CBh
8.5
ABh
5.3
CCh
8.6
ACh
5.4
CDh
8.7
ADh
5.5
CEh
8.8
AEh
5.6
Other
NA
A/B[7:0]
VSH1/VSH2
A/B[7:0]
VSH1/VSH2
23h
9
3Ch
14
24h
9.2
3Dh
14.2
25h
9.4
3Eh
14.4
26h
9.6
3Fh
14.6
27h
9.8
40h
14.8
28h
10
41h
15
29h
10.2
42h
15.2
2Ah
10.4
43h
15.4
2Bh
10.6
44h
15.6
2Ch
10.8
45h
15.8
2Dh
11
46h
16
2Eh
11.2
47h
16.2
2Fh
11.4
48h
16.4
30h
11.6
49h
16.6
31h
11.8
4Ah
16.8
32h
12
4Bh
17
33h
12.2
Other
NA
34h
12.4
35h
12.6
36h
12.8
37h
13
38h
13.2
39h
13.4
3Ah
13.6
3Bh
13.8
C[7:0]
VSL
0Ah
0Ch
-5.5
0Eh
-6
10h
-6.5
12h
-7
14h
-7.5
16h
-8
18h
-8.5
1Ah
-9
1Ch
-9.5
1Eh
-10
20h
-10.5
22h
-11
24h
-11.5
26h
-12
28h
-12.5
2Ah
-13
2Ch
-13.5
2Eh
-14
30h
-14.5
32h
-15
34h
-15.5
36h
-16
38h
-16.5
3Ah
-17
Other
NA

<!-- Page 22 -->

SSD1680
Rev 0.14
P 22/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
0C
0
0
0
0
1
1
0
0
Booster Soft start
Control
Booster Enable with Phase 1, Phase 2 and Phase 3
for soft start current and duration setting.
A[7:0] -> Soft start setting for Phase1
= 8Bh [POR]
B[7:0] -> Soft start setting for Phase2
= 9Ch [POR]
C[7:0] -> Soft start setting for Phase3
= 96h [POR]
D[7:0] -> Duration setting
= 0Fh [POR]
 Bit Description of each byte:
 A[6:0] / B[6:0] / C[6:0]:
Bit[6:4]
Driving Strength
Selection
000
1(Weakest)
001
2
010
3
011
4
100
5
101
6
110
7
111
8(Strongest)
Bit[3:0]
Min Off Time Setting of GDR
[ Time unit ]
0000
~
0011
NA
0100
2.6
0101
3.2
0110
3.9
0111
4.6
1000
5.4
1001
6.3
1010
7.3
1011
8.4
1100
9.8
1101
11.5
1110
13.8
1111
16.5
 D[5:0]: duration setting of phase
D[5:4]: duration setting of phase 3
D[3:2]: duration setting of phase 2
D[1:0]: duration setting of phase 1
Bit[1:0]
Duration of Phase
[Approximation]
00
10ms
01
20ms
10
30ms
11
40ms
0
1
1
A6
A5
A4
A3
A2
A1
A0
0
1
1
B6
B5
B4
B3
B2
B1
B0
0
1
1
C6
C5
C4
C3
C2
C1
C0
0
1
0
0
D5
D4
D3
D2
D1
D0

<!-- Page 23 -->

SSD1680
Rev 0.14
P 23/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
10
0
0
0
1
0
0
0
0
Deep Sleep mode
Deep Sleep mode Control:
A[1:0] :
Description
00
Normal Mode [POR]
01
Enter Deep Sleep Mode 1
11
Enter Deep Sleep Mode 2
After this command initiated, the chip will
enter Deep Sleep Mode, BUSY pad will
keep output high.
Remark:
To Exit Deep Sleep mode, User required
to send HWRESET to the driver
0
1
0
0
0
0
0
0
A1
A0
0
0
11
0
0
0
1
0
0
0
1
Data Entry mode setting Define data entry sequence
A[2:0] = 011 [POR]
A [1:0] = ID[1:0]
Address automatic increment / decrement
setting
The setting of incrementing or
decrementing of the address counter can
be made independently in each upper and
lower bit of the address.
00 –Y decrement, X decrement,
01 –Y decrement, X increment,
10 –Y increment, X decrement,
11 –Y increment, X increment [POR]
A[2] = AM
Set the direction in which the address
counter is updated automatically after data
are written to the RAM.
AM= 0, the address counter is updated in
the X direction. [POR]
AM = 1, the address counter is updated in
the Y direction.
0
1
0
0
0
0
0
A2
A1
A0
0
0
12
0
0
0
1
0
0
1
0
SW RESET
It resets the commands and parameters to
their S/W Reset default values except
R10h-Deep Sleep Mode
During operation, BUSY pad will output
high.
Note: RAM are unaffected by this
command.

<!-- Page 24 -->

SSD1680
Rev 0.14
P 24/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
14
0
0
0
1
0
1
0
0
HV Ready Detection
HV ready detection
A[7:0] = 00h [POR]
The command required CLKEN=1 and
ANALOGEN=1.
Refer to Register 0x22 for detail.
After this command initiated, HV Ready
detection starts.
BUSY pad will output high during
detection.
The detection result can be read from the
Status Bit Read (Command 0x2F).
0
1
0
A6
A5
A4
0
A2
A1
A0
A[6:4]=n for cool down duration:
10ms x (n+1)
A[2:0]=m for number of Cool Down Loop
to detect.
The max HV ready duration is
10ms x (n+1) x (m)
HV ready detection will be trigger after
each cool down time. The detection will be
completed when HV is ready.
For 1 shot HV ready detection, A[7:0] can
be set as 00h.
0
0
15
0
0
0
1
0
1
0
1
VCI Detection
VCI Detection
A[2:0] = 100 [POR] , Detect level at 2.3V
A[2:0] : VCI level Detect
A[2:0]
VCI level
011
2.2V
100
2.3V
101
2.4V
110
2.5V
111
2.6V
Other
NA
The command required CLKEN=1 and
ANALOGEN=1
Refer to Register 0x22 for detail.
After this command initiated, VCI
detection starts.
BUSY pad will output high during
detection.
The detection result can be read from the
Status Bit Read (Command 0x2F).
0
1
0
0
0
0
0
A2
A1
A0
0
0
18
0
0
0
1
1
0
0
0
Temperature Sensor
Control
Temperature Sensor Selection
A[7:0] = 48h [POR], external temperatrure
sensor
A[7:0] = 80h Internal temperature sensor
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
0
1A
0
0
0
1
1
0
1
0
Temperature Sensor
Control (Write to
temperature register)
Write to temperature register.
A[11:0] = 7FFh [POR]
0
1
A11 A10
A9
A8
A7
A6
A5
A4
0
1
A3
A2
A1
A0
0
0
0
0
0
0
1B
0
0
0
1
1
0
1
1
Temperature Sensor
Control (Read from
temperature register)
Read from temperature register.
1
1
A11 A10
A9
A8
A7
A6
A5
A4
1
1
A3
A2
A1
A0
0
0
0
0

<!-- Page 25 -->

SSD1680
Rev 0.14
P 25/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
1C
0
0
0
1
1
1
0
0
Temperature Sensor
Control (Write Command
to External temperature
sensor)
Write Command to External temperature
sensor.
A[7:0] = 00h [POR],
B[7:0] = 00h [POR],
C[7:0] = 00h [POR],
A[7:6]
A[7:6]
Select no of byte to be sent
00
Address + pointer
01
Address + pointer + 1st parameter
10
Address + pointer + 1st parameter +
2nd pointer
11
Address
A[5:0] – Pointer Setting
B[7:0] – 1st parameter
C[7:0] – 2nd parameter
The command required CLKEN=1.
Refer to Register 0x22 for detail.
After this command initiated, Write
Command to external temperature sensor
starts. BUSY pad will output high during
operation.
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
B7
B6
B5
B4
B3
B2
B1
B0
0
1
C7
C6
C5
C4
C3
C2
C1
C0
0
0
20
0
0
1
0
0
0
0
0
Master Activation
Activate Display Update Sequence
The Display Update Sequence Option is
located at R22h.
BUSY pad will output high during
operation. User should not interrupt this
operation to avoid corruption of panel
images.
0
0
21
0
0
1
0
0
0
0
1
Display Update Control
1
RAM content option for Display Update
A[7:0] = 00h [POR]
B[7:0] = 00h [POR]
A[7:4] Red RAM option
0000
Normal
0100
Bypass RAM content as 0
1000
Inverse RAM content
A[3:0] BW RAM option
0000
Normal
0100
Bypass RAM content as 0
1000
Inverse RAM content
B[7] Source Output Mode
0
Available Source from S0 to S175
1
Available Source from S8 to S167
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
B7
0
0
0
0
0
0
0

<!-- Page 26 -->

SSD1680
Rev 0.14
P 26/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
22
0
0
1
0
0
0
1
0
Display Update
Control 2
Display Update Sequence Option:
Enable the stage for Master Activation
A[7:0]= FFh (POR)
Operating sequence
Parameter
(in Hex)
Enable clock signal
80
Disable clock signal
01
Enable clock signal
 Enable Analog
C0
Disable Analog
 Disable clock signal
03
Enable clock signal
 Load LUT with DISPLAY Mode 1
 Disable clock signal
91
Enable clock signal
 Load LUT with DISPLAY Mode 2
 Disable clock signal
99
Enable clock signal
 Load temperature value
 Load LUT with DISPLAY Mode 1
 Disable clock signal
B1
Enable clock signal
 Load temperature value
 Load LUT with DISPLAY Mode 2
 Disable clock signal
B9
Enable clock signal
 Enable Analog
 Display with DISPLAY Mode 1
 Disable Analog
 Disable OSC
C7
Enable clock signal
 Enable Analog
 Display with DISPLAY Mode 2
 Disable Analog
Disable OSC
CF
Enable clock signal
Enable Analog
 Load temperature value
 DISPLAY with DISPLAY Mode 1
 Disable Analog
 Disable OSC
F7
Enable clock signal
Enable Analog
 Load temperature value
 DISPLAY with DISPLAY Mode 2
 Disable Analog
 Disable OSC
FF
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
0
24
0
0
1
0
0
1
0
0
Write RAM (Black White)
/ RAM 0x24
After this command, data entries will be
written into the BW RAM until another
command is written. Address pointers will
advance accordingly
For Write pixel:
  Content of Write RAM(BW) = 1
For Black pixel:
 Content of Write RAM(BW) = 0

<!-- Page 27 -->

SSD1680
Rev 0.14
P 27/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
26
0
0
1
0
0
1
1
0
Write RAM (RED)
/ RAM 0x26
After this command, data entries will be
written into the RED RAM until another
command is written. Address pointers will
advance accordingly.
For Red pixel:
  Content of Write RAM(RED) = 1
For non-Red pixel [Black or White]:
 Content of Write RAM(RED) = 0
0
0
27
0
0
1
0
0
1
1
1
Read RAM
After this command, data read on the
MCU bus will fetch data from RAM.
According to parameter of Register 41h to
select reading RAM0x24/ RAM0x26, until
another command is written. Address
pointers will advance accordingly.
The 1st byte of data read is dummy data.
0
0
28
0
0
1
0
1
0
0
0
VCOM Sense
Enter VCOM sensing conditions and hold
for duration defined in 29h before reading
VCOM value.
The sensed VCOM voltage is stored in
register
The command required CLKEN=1 and
ANALOGEN=1
Refer to Register 0x22 for detail.
BUSY pad will output high during
operation.
0
0
29
0
0
1
0
1
0
0
1
VCOM Sense Duration
Stabling time between entering VCOM
sensing mode and reading acquired.
A[3:0] = 9h, duration = 10s.
VCOM sense duration = (A[3:0]+1) sec
0
1
0
1
0
0
A3
A2
A1
A0
0
0
2A
0
0
1
0
1
0
1
0
Program VCOM OTP
Program VCOM register into OTP
The command required CLKEN=1.
Refer to Register 0x22 for detail.
BUSY pad will output high during
operation.
0
0
2B
0
0
1
0
1
0
1
1
Write Register for VCOM
Control
This command is used to reduce glitch
when ACVCOM toggle. Two data bytes
D04h and D63h should be set for this
command.
0
1
0
0
0
0
0
1
0
0
0
1
0
1
1
0
0
0
1
1

<!-- Page 28 -->

SSD1680
Rev 0.14
P 28/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
2C
0
0
1
0
1
1
0
0
Write VCOM register
Write VCOM register from MCU interface
A[7:0] = 00h [POR]
A[7:0]
VCOM
A[7:0]
VCOM
08h
-0.2
44h
-1.7
0Ch
-0.3
48h
-1.8
10h
-0.4
4Ch
-1.9
14h
-0.5
50h
-2
18h
-0.6
54h
-2.1
1Ch
-0.7
58h
-2.2
20h
-0.8
5Ch
-2.3
24h
-0.9
60h
-2.4
28h
-1
64h
-2.5
2Ch
-1.1
68h
-2.6
30h
-1.2
6Ch
-2.7
34h
-1.3
70h
-2.8
38h
-1.4
74h
-2.9
3Ch
-1.5
78h
-3
40h
-1.6
Other
NA
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
0
2D
0
0
1
0
1
1
0
1
OTP Register Read for
Display Option
Read Register for Display Option:
A[7:0]: VCOM OTP Selection
(Command 0x37, Byte A)
B[7:0]: VCOM Register
(Command 0x2C)
C[7:0]~G[7:0]: Display Mode
(Command 0x37, Byte B to Byte F)
[5 bytes]
H[7:0]~K[7:0]: Waveform Version
(Command 0x37, Byte G to Byte J)
[4 bytes]
1
1
A7
A6
A5
A4
A3
A2
A1
A0
1
1
B7
B6
B5
B4
B3
B2
B1
B0
1
1
C7
C6
C5
C4
C3
C2
C1
C0
1
1
D7
D6
D5
D4
D3
D2
D1
D0
1
1
E7
E6
E5
E4
E3
E2
E1
E0
1
1
F7
F6
F5
F4
F3
F2
F1
F0
1
1
G7
G6
G5
G4
G3
G2
G1
G0
1
1
H7
H6
H5
H4
H3
H2
H1
H0
1
1
I7
I6
I5
I4
I3
I2
I1
I0
1
1
J7
J6
J5
J4
J3
J2
J1
J0
1
1
K7
K6
K5
K4
K3
K2
K1
K0
0
0
2E
0
0
1
0
1
1
1
0
User ID Read
Read 10 Byte User ID  stored in OTP:
A[7:0]]~J[7:0]: UserID (R38, Byte A and
Byte J)  [10 bytes]
1
1
A7
A6
A5
A4
A3
A2
A1
A0
1
1
B7
B6
B5
B4
B3
B2
B1
B0
1
1
C7
C6
C5
C4
C3
C2
C1
C0
1
1
D7
D6
D5
D4
D3
D2
D1
D0
1
1
E7
E6
E5
E4
E3
E2
E1
E0
1
1
F7
F6
F5
F4
F3
F2
F1
F0
1
1
G7
G6
G5
G4
G3
G2
G1
G0
1
1
H7
H6
H5
H4
H3
H2
H1
H0
1
1
I7
I6
I5
I4
I3
I2
I1
I0
1
1
J7
J6
J5
J4
J3
J2
J1
J0

<!-- Page 29 -->

SSD1680
Rev 0.14
P 29/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
2F
0
0
1
0
1
1
1
1
Status Bit Read
Read IC status Bit [POR 0x01]
A[5]: HV Ready Detection flag [POR=0]
0: Ready
1: Not Ready
A[4]: VCI Detection flag [POR=0]
0: Normal
1: VCI lower than the Detect level
A[3]: [POR=0]
A[2]: Busy flag [POR=0]
0: Normal
1: BUSY
A[1:0]: Chip ID [POR=01]
Remark:
A[5] and A[4] status are not valid after
RESET, they need to be initiated by
command 0x14 and command 0x15
respectively.
1
1
0
0
A5
A4
0
0
A1
A0
0
0
30
0
0
1
1
0
0
0
0
Program WS OTP
Program OTP of Waveform Setting
The contents should be written into RAM
before sending this command.
The command required CLKEN=1.
Refer to Register 0x22 for detail.
BUSY pad will output high during
operation.
0
0
31
0
0
1
1
0
0
0
1
Load WS OTP
Load OTP of Waveform Setting
The command required CLKEN=1.
Refer to Register 0x22 for detail.
BUSY pad will output high during
operation.
0
0
32
0
0
1
1
0
0
1
0
Write LUT register
Write LUT register from MCU interface
[153 bytes], which contains the content of
VS[nX-LUTm], TP[nX], RP[n], SR[nXY],
FR[n] and XON[nXY]
Refer to Session 6.7 WAVEFORM
SETTING
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
B7
B6
B5
B4
B3
B2
B1
B0
0
1
:
:
:
:
:
:
:
:
0
1
.
..
.
.
.
.
.
.
0
0
34
0
0
1
1
0
1
0
0
CRC calculation
CRC calculation command
For details, please refer to SSD1680
application note.
BUSY pad will output high during
operation.
0
0
35
0
0
1
1
0
1
0
1
CRC Status Read
CRC Status Read
A[15:0] is the CRC read out value
1
1
A15 A14 A13 A12 A11 A10
A9
A8
1
1
A7
A6
A5
A4
A3
A2
A1
A0

<!-- Page 30 -->

SSD1680
Rev 0.14
P 30/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
36
0
0
1
1
0
1
1
0
Program OTP selection
Program OTP Selection according to the
OTP Selection Control [R37h and R38h]
The command required CLKEN=1.
Refer to Register 0x22 for detail.
BUSY pad will output high during
operation.
0
0
37
0
0
1
1
0
1
1
1
Write Register for Display
Option
Write Register for Display Option
A[7] Spare VCOM OTP selection
0: Default [POR]
1: Spare
B[7:0]  Display Mode for WS[7:0]
C[7:0]  Display Mode for WS[15:8]
D[7:0]  Display Mode for WS[23:16]
E[7:0]  Display Mode for WS[31:24]
F[3:0  Display Mode for WS[35:32]
0: Display Mode 1
1: Display Mode 2
F[6]:
PingPong for Display Mode 2
0: RAM Ping-Pong disable [POR]
1: RAM Ping-Pong enable
G[7:0]~J[7:0] module ID /waveform
version.
Remarks:
1) A[7:0]~J[7:0] can be stored in OTP
2) RAM Ping-Pong function is not support
for Display Mode 1
0
1
A7
0
0
0
0
0
0
0
0
1
B7
B6
B5
B4
B3
B2
B1
B0
0
1
C7
C6
C5
C4
C3
C2
C1
C0
0
1
D7
D6
D5
D4
D3
D2
D1
D0
0
1
E7
E6
E5
E4
E3
E2
E1
E0
0
1
0
F6
0
0
F3
F2
F1
F0
0
1
G7
G6
G5
G4
G3
G2
G1
G0
0
1
H7
H6
H5
H4
H3
H2
H1
H0
0
1
I7
I6
I5
I4
I3
I2
I1
I0
0
1
J7
J6
J5
J4
J3
J2
J1
J0
0
0
38
0
0
1
1
1
0
0
0
Write Register for User ID Write Register for User ID
A[7:0]]~J[7:0]: UserID [10 bytes]
Remarks: A[7:0]~J[7:0] can be stored in
OTP
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
B7
B6
B5
B4
B3
B2
B1
B0
0
1
C7
C6
C5
C4
C3
C2
C1
C0
0
1
D7
D6
D5
D4
D3
D2
D1
D0
0
1
E7
E6
E5
E4
E3
E2
E1
E0
0
1
F7
F6
F5
F4
F3
F2
F1
F0
0
1
G7
G6
G5
G4
G3
G2
G1
G0
0
1
H7
H6
H5
H4
H3
H2
H1
H0
0
1
I7
I6
I5
I4
I3
I2
I1
I0
0
1
J7
J6
J5
J4
J3
J2
J1
J0
0
0
39
0
0
1
1
1
0
0
1
OTP program mode
OTP program mode
A[1:0] = 00: Normal Mode [POR]
A[1:0] = 11: Internal generated OTP
programming voltage
Remark: User is required to EXACTLY
follow the reference code sequences
0
1
0
0
0
0
0
0
A1
A0

<!-- Page 31 -->

SSD1680
Rev 0.14
P 31/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
3C
0
0
1
1
1
1
0
0
Border Waveform Control Select border waveform for VBD
A[7:0] = C0h [POR], set VBD as HIZ.
A [7:6]  :Select VBD option
A[7:6]
Select VBD as
00
GS Transition,
Defined in A[2] and
A[1:0]
01
Fix Level,
Defined in  A[5:4]
10
VCOM
11[POR]
HiZ
A [5:4] Fix Level Setting for VBD
A[5:4]
VBD level
00
VSS
01
VSH1
10
VSL
11
VSH2
A[2] GS Transition control
A[2]
GS Transition control
0
Follow LUT
(Output VCOM @ RED)
1
Follow LUT
A [1:0] GS Transition setting for VBD
A[1:0]
VBD Transition
00
LUT0
01
LUT1
10
LUT2
11
LUT3
0
1
A7
A6
A5
A4
0
A2
A1 A0
0
0
3F
0
0
1
1
1
1
1
1
End Option (EOPT)
Option for LUT end
A[7:0]= 02h [POR]
22h
Normal.
07h
Source output level keep
previous output before power off
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
0
41
0
1
0
0
0
0
0
1
Read RAM Option
Read RAM Option
A[0]= 0 [POR]
0 : Read RAM corresponding to RAM0x24
1 : Read RAM corresponding to RAM0x26
0
1
0
0
0
0
0
0
0
A0
0
0
44
0
1
0
0
0
1
0
0
Set RAM X - address
Start / End position
Specify the start/end positions of the
window address in the X direction by an
address unit  for RAM
A[5:0]: XSA[5:0], XStart, POR = 00h
B[5:0]: XEA[5:0], XEnd,  POR = 15h
0
1
0
0
A5
A4
A3
A2
A1
A0
0
1
0
0
B5
B4
B3
B2
B1
B0
0
0
45
0
1
0
0
0
1
0
1
Set Ram Y- address
Start / End position
Specify the start/end positions of the
window address in the Y direction by an
address unit for RAM
A[8:0]: YSA[8:0], YStart, POR = 000h
B[8:0]: YEA[8:0], YEnd,  POR = 127h
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
0
0
0
0
0
0
0
A8
0
1
B7
B6
B5
B4
B3
B2
B1
B0
0
1
0
0
0
0
0
0
0
B8

<!-- Page 32 -->

SSD1680
Rev 0.14
P 32/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
46
0
1
0
0
0
1
1
0
Auto Write RED RAM for
Regular Pattern
Auto Write RED RAM for Regular Pattern
A[7:0] = 00h [POR]
A[7]: The 1st step value, POR = 0
A[6:4]: Step Height, POR= 000
Step of alter RAM in Y-direction according
to Gate
A[6:4]
Height
A[6:4]
Height
000
8
100
128
001
16
101
256
010
32
110
296
011
64
111
NA
A[2:0]: Step Width, POR= 000
Step of alter RAM in X-direction according
to Source
A[2:0]
Width
A[2:0]
Width
000
8
100
128
001
16
101
176
010
32
110
NA
011
64
111
NA
BUSY pad will output high during
operation.
0
1
A7
A6
A5
A4
0
A2
A1
A0
0
0
47
0
1
0
0
0
1
1
1
Auto Write B/W RAM for
Regular Pattern
Auto Write B/W RAM for Regular Pattern
A[7:0] = 00h [POR]
A[7]: The 1st step value, POR = 0
A[6:4]: Step Height, POR= 000
Step of alter RAM in Y-direction according
to Gate
A[6:4]
Height
A[6:4]
Height
000
8
100
128
001
16
101
256
010
32
110
296
011
64
111
NA
A[2:0]: Step Width, POR= 000
Step of alter RAM in X-direction according
to Source
A[2:0]
Width
A[2:0]
Width
000
8
100
128
001
16
101
176
010
32
110
NA
011
64
111
NA
During operation, BUSY pad will output
high.
0
1
A7
A6
A5
A4
0
A2
A1
A0

<!-- Page 33 -->

SSD1680
Rev 0.14
P 33/46
Jun 2019
Solomon Systech
Command Table
R/W# D/C# Hex
D7
D6
D5
D4
D3
D2
D1
D0 Command
Description
0
0
4E
0
1
0
0
1
1
1
0
Set RAM X address
counter
Make initial settings for the RAM X
address in the address counter (AC)
A[5:0]: 00h [POR].
0
1
0
0
A5
A4
A3
A2
A1
A0
0
0
4F
0
1
0
0
1
1
1
1
Set RAM Y address
counter
Make initial settings for the RAM Y
address in the address counter (AC)
A[8:0]: 000h [POR].
0
1
A7
A6
A5
A4
A3
A2
A1
A0
0
1
0
0
0
0
0
0
0
A8
0
0
7F
0
1
1
1
1
1
1
1
NOP
This command is an empty command; it
does not have any effect on the display
module.
However it can be used to terminate
Frame Memory Write or Read
Commands.

<!-- Page 34 -->

SSD1680
Rev 0.14
P 34/46
Jun 2019
Solomon Systech
8
COMMAND DESCRIPTION
8.1 Driver Output Control (01h)
This triple byte command has multiple configurations and each bit setting is described as follows:
R/W
DC
IB7
IB6
IB5
IB4
IB3
IB2
IB1
IB0
W
1
MUX7 MUX6 MUX5 MUX4 MUX3 MUX2 MUX1 MUX0
POR
0
0
1
1
1
1
1
1
W
1
MUX8
POR
1
W
1
GD
SM
TB
POR
0
0
0
MUX[8:0]: Specify number of lines for the driver: MUX[8:0] + 1. Multiplex ratio (MUX ratio) from 16 MUX to 296MUX.
GD: Selects the 1st output Gate
This bit is made to match the GATE layout connection on the panel. It defines the first scanning line.
SM: Change scanning order of gate driver.
When SM is set to 0, left and right interlaced is performed.
When SM is set to 1, no splitting odd / even of the GATE signal is performed,
Output pin assignment sequence is shown as below (for 296 MUX ratio):
SM=0
SM=0
SM=1
SM=1
Driver
GD=0
GD=1
GD=0
GD=1
G0
ROW0
ROW1
ROW0
ROW148
G1
ROW1
ROW0
ROW148
ROW0
G2
ROW2
ROW3
ROW1
ROW149
G3
ROW3
ROW2
ROW149
ROW1
:
:
:
:
:
G146
ROW146
ROW147
ROW73
ROW222
G147
ROW147
ROW146
ROW222
ROW73
G148
ROW148
ROW149
ROW74
ROW223
G149
ROW149
ROW148
ROW223
ROW74
:
:
:
:
:
G292
ROW292
ROW293
ROW146
ROW294
G293
ROW293
ROW292
ROW294
ROW146
G294
ROW294
ROW295
ROW147
ROW295
G295
ROW295
ROW294
ROW295
ROW147
See “Scan Mode Setting” on next page.
TB: Change scanning direction of gate driver.
This bit defines the scanning direction of the gate for flexible layout of signals in module either from up to down (TB
= 0) or from bottom to up (TB = 1).

<!-- Page 35 -->

SSD1680
Rev 0.14
P 35/46
Jun 2019
Solomon Systech
Figure 8-1: Output pin assignment on different Scan Mode Setting
SM = 0
SM = 1
GD = 0
GD = 1
Pad 1,2,3,…
Gold Bumps face up
ROW150
ROW151
...
ROW294
ROW295
ROW0
ROW1
...
ROW148
ROW149

Pad 1,2,3,…
Gold Bumps face up
ROW0
ROW1
...
...
ROW146
ROW147
ROW148
ROW149
...
...
...
ROW295
Pad 1, 2, 3,…
Gold Bumps face up
ROW148
ROW149
...
ROW294
ROW295
ROW0
ROW1
...
ROW146
ROW147

Pad 1,2,3,…
Gold Bumps face up
ROW0
ROW1
...
...
ROW146
ROW147
ROW148
ROW149
...
...
...
ROW295

<!-- Page 36 -->

SSD1680
Rev 0.14
P 36/46
Jun 2019
Solomon Systech
8.2 Gate Scan Start Position (0Fh)
R/W
DC
IB7
IB6
IB5
IB4
IB3
IB2
IB1
IB0
W
1
SCN7 SCN6 SCN5 SCN4 SCN3 SCN2 SCN1 SCN0
POR
0
0
0
0
0
0
0
0
W
1
0
0
0
0
0
0
0
SCN8
POR
0
0
0
0
0
0
0
0
This command is to set Gate Start Position for determining the starting gate of display RAM by selecting a value from 0
to 295. Figure 8-2 shows an example using this command of this command when MUX ratio= 295 and MUX ratio= 148.
“ROW” means the graphic display data RAM row.
Figure 8-2: Example of Set Display Start Line with no Remapping
MUX ratio (01h) = 127h
MUX ratio (01h) = 093h
MUX ratio (01h) = 095h
GATE Pin
Gate Start Position (0Fh)
= 000h
Gate Start Position (0Fh)
= 000h
Gate Start Position (0Fh)
= 04Ah
G0
ROW0
ROW0
-
G1
ROW1
ROW1
-
G2
ROW2
ROW2
-
G3
ROW3
ROW3
-
:
:
:
:
:
:
:
:
G72
:
:
-
G73
:
:
-
G74
:
:
ROW74
G75
:
:
ROW75
:
:
:
:
:
:
:
:
G146
ROW146
ROW146
:
G147
ROW147
ROW147
:
G148
ROW148
-
:
G149
ROW149
-
:
:
:
:
:
:
:
:
G220
:
:
:
G221
:
:
:
G222
:
:
ROW222
G223
:
:
ROW223
:
:
:
:
:
:
:
G292
ROW292
-
-
G293
ROW293
-
-
G294
ROW294
-
-
G295
ROW295
-
-
Display
Example

<!-- Page 37 -->

SSD1680
Rev 0.14
P 37/46
Jun 2019
Solomon Systech
8.3
Data Entry Mode Setting (11h)
This command has multiple configurations and each bit setting is described as follows:
R/W
DC
IB7
IB6
IB5
IB4
IB3
IB2
IB1
IB0
W
1
AM
ID1
ID0
POR
0
0
0
0
0
0
1
1
ID[1:0]: The address counter is automatically incremented by 1, after data is written to the RAM
when ID[1:0] = “01”. The address counter is automatically decremented by 1, after data is written
to the RAM when ID[1:0] = “00”. The setting of incrementing or decrementing of the address
counter can be made independently in each upper and lower bit of the address. The direction of
the address when data is written to the RAM is set by AM bits.
AM: Set the direction in which the address counter is updated automatically after data are written to
the RAM. When AM = “0”, the address counter is updated in the X direction. When AM = “1”, the
address counter is updated in the Y direction. When window addresses are selected, data are written
to the RAM area specified by the window addresses in the manner specified with ID[1:0] and AM
bits.
ID [1:0]="00”
X: decrement
Y: decrement
ID [1:0]="01”
X: increment
Y: decrement
ID [1:0]="10”
X: decrement
Y: increment
ID [1:0]="11”
X: increment
Y: increment
AM="0”
X-mode
AM="1”
Y-mode
The pixel sequence is defined by the ID [0],
ID[1:0]="00”
X: decrement
Y: decrement
ID[1:0]="01”
X: increment
Y: decrement
AM="0”
X-mode
00,00h
15,127h
4, 3, 2, 1
00,00h
15,127h
1, 2, 3, 4
00,00h
15,127h
00,00h
15, 127h
00,00h
15, 127h
00,00h
15, 127h
00,00h
15, 127h
00,00h
15, 127h
00,00h
15, 127h
00,00h
15, 127h

<!-- Page 38 -->

SSD1680
Rev 0.14
P 38/46
Jun 2019
Solomon Systech
8.4 Set RAM X - Address Start / End Position (44h)
R/W
DC
IB7
IB6
IB5
IB4
IB3
IB2
IB1
IB0
W
1
XSA4 XSA3 XSA2 XSA1 XSA0
POR
0
0
0
0
0
0
0
0
W
1
XEA4 XEA3 XEA2 XEA1 XEA0
POR
0
0
0
1
0
1
0
1
XSA[4:0]/XEA[4:0]: Specify the start/end positions of the window address in the X direction by 8 times address unit.
Data is written to the RAM within the area determined by the addresses specified by XSA [4:0] and XEA [4:0]. These
addresses must be set before the RAM write.
It allows on XEA [4:0] ≤ XSA [4:0]. The settings follow the condition on 00h ≤ XSA [4:0], XEA [4:0] ≤ 15h. The windows
is followed by the control setting of Data Entry Setting (R11h)
8.5 Set RAM Y - Address Start / End Position (45h)
R/W
DC
IB7
IB6
IB5
IB4
IB3
IB2
IB1
IB0
W
1
YSA7 YSA6 YSA5 YSA4 YSA3 YSA2 YSA1 YSA0
POR
0
0
0
0
0
0
0
0
W
1
0
0
0
0
0
0
0
YSA8
POR
0
0
0
0
0
0
0
0
W
1
YEA7 YEA6 YEA5 YEA4 YEA3 YEA2 YEA1 YEA0
POR
0
0
1
0
0
1
1
1
W
1
0
0
0
0
0
0
0
YEA8
POR
0
0
0
0
0
0
0
1
YSA[8:0]/YEA[8:0]: Specify the start/end positions of the window address in the Y direction by an address unit. Data is
written to the RAM within the area determined by the addresses specified by YSA [8:0] and YEA [8:0]. These addresses
must be set before the RAM write.
It allows YEA [8:0] ≤ YSA [8:0].  The settings follow the condition on 00h ≤ YSA [8:0], YEA [8:0] ≤ 127h.  The windows
is followed by the control setting of Data Entry Setting (R11h)
8.6 Set RAM Address Counter (4Eh-4Fh)
Reg#
R/W
DC
IB7
IB6
IB5
IB4
IB3
IB2
IB1
IB0
4Eh
W
1
XAD4
XAD3
XAD2
XAD1
XAD0
POR
0
0
0
0
0
0
0
0
4Fh
W
1
YAD7
YAD6
YAD5
YAD4
YAD3
YAD2
YAD1
YAD0
POR
0
0
0
0
0
0
0
0
W
1
YAD8
POR
0
XAD[4:0]: Make initial settings for the RAM X address in the address counter (AC).
YAD[8:0]: Make initial settings for the RAM Y address in the address counter (AC).
After RAM data is written, the address counter is automatically updated according to the settings with AM, ID bits and
setting for a new RAM address is not required in the address counter. Therefore, data is written consecutively without
setting an address. The address counter is not automatically updated when data is read out from the RAM. RAM address
setting cannot be made during the standby mode. The address setting should be made within the area designated with
window addresses which is controlled by the Data Entry Setting (R11h) {AM, ID[1:0]} ; RAM Address XStart / XEnd
Position (R44h) and RAM Address Ystart /Yend Position (R45h). Otherwise undesirable image will be displayed on the
Panel.

<!-- Page 39 -->

SSD1680
Rev 0.14
P 39/46
Jun 2019
Solomon Systech
9
Operation Flow and Code Sequence
9.1 General operation flow to drive display panel
.
START
2. Set Initial Configuration
•
Define SPI interface to communicate with MCU
•
HW Reset
•
SW Reset by Command 0x12
•
Wait 10ms
1. Power On
•
Supply VCI
•
Wait 10ms
4. Load Waveform LUT
•
Sense temperature by int/ext TS by Command 0x18
•
Load waveform LUT from OTP by Command 0x22, 0x20
or by MCU
•
Wait BUSY Low
5. Write Image and Drive Display Panel
•
Write image data in RAM by Command 0x4E, 0x4F,
0x24, 0x26
•
Set softstart setting by Command 0x0C
•
Drive display panel by Command 0x22, 0x20
•
Wait BUSY Low
END
6. Power Off
•
Deep sleep by Command 0x10
•
Power OFF
3. Send Initialization Code
•
Set gate driver output by Command 0x01
•
Set display RAM size by Command 0x11, 0x44, 0x45
•
Set panel border by Command 0x3C
Figure 9-1: Operation flow to drive display panel

<!-- Page 40 -->

SSD1680
Rev 0.14
P 40/46
Jun 2019
Solomon Systech
10 Absolute Maximum Rating
Table 10-1 : Maximum Ratings
Symbol
Parameter
Rating
Unit
VCI
Logic supply voltage
-0.5 to +6.0
V
VIN
Logic Input voltage
-0.5 to VDDIO+0.5
V
VOUT
Logic Output voltage
-0.5 to VDDIO+0.5
V
TOPR
Operation temperature range
-40 to +85
°C
TSTG
Storage temperature range
-65 to +150
°C
Maximum ratings are those values beyond which damages to the device may occur. Functional operation should be
restricted to the limits in the Electrical Characteristics tables or Pin Description section
This device contains circuitry to protect the inputs against damage due to high static voltages or electric fields;
however, it is advised that normal precautions be taken to avoid application of any voltage higher than maximum rated
voltages to this high impedance circuit. For proper operation it is recommended that VCI be constrained to the range
VSS < VCI. Reliability of operation is enhanced if unused input is connected to an appropriate logic voltage level (e.g.,
either VSS or VDDIO). Unused outputs must be left open. This device may be light sensitive. Caution should be taken to
avoid exposure of this device to any light source during normal operation. This device is not radiation protected.
11 Electrical Characteristics
The following specifications apply for:  VSS=0V, VCI=3.0V, VDD=1.8V, TOPR=25ºC.
Table 11-1: DC Characteristics
Symbol
Parameter
Applicable pin
Test Condition
Min.
Typ.
Max.
Unit
VCI
VCI operation voltage
VCI
2.2
3.0
3.7
V
VDD
VDD operation voltage
VDD
1.7
1.8
1.9
V
VCOM_DC
VCOM_DC output
voltage
VCOM
-3.0
-0.2
V
dVCOM_DC
VCOM_DC output
voltage deviation
VCOM
-200
200
mV
VCOM_AC
VCOM_AC output
voltage
VCOM
VSL +
VCOM_DC
VCOM_DC
VSH1+
VCOM_DC
V
VGATE
Gate output voltage
G0~G295
-20
+20
V
VGATE(p-p)
Gate output peak to
peak voltage
G0~G295
40
V
VSH1
Positive Source output
voltage
VSH1
+2.4
+15
+17
V
dVSH1
VSH1 output voltage
deviation
VSH1
From 2.4V to 8.8V
-100
100
mV
From 9.0V to 17V
-200
200
mV
VSH2
Positive Source output
voltage
VSH2
+2.4
+5
+17
V
dVSH2
VSH2 output voltage
deviation
VSH2
From 2.4V to 8.8V
-100
100
mV
From 9.0V to 17V
-200
200
mV
VSL
Negative Source output
voltage
VSL
-17
-15
-9
V
dVSL
VSL output voltage
deviation
VSL
-200
200
mV
VIH
High level input voltage
SDA, SCL, CS#,
D/C#, RES#, BS1,
M/S#, CL
0.8VDDIO
V
VIL
Low level input voltage
0.2VDDIO
V
VOH
High level output voltage SDA, BUSY, CL
IOH = -100uA
0.9VDDIO
V
VOL
Low level output voltage
IOL = 100uA
0.1VDDIO
V
VPP
OTP Program voltage
VPP
7.25
7.5
7.75
V

<!-- Page 41 -->

SSD1680
Rev 0.14
P 41/46
Jun 2019
Solomon Systech
Symbol
Parameter
Applicable pin
Test Condition
Min.
Typ.
Max.
Unit
Islp_VCI
Sleep mode current
VCI
- DC/DC off
- No clock
- No output load
- MCU interface
access
- RAM data access
20
35
uA
Idslp_VCI1
Current of deep sleep
mode 1
VCI
- DC/DC off
- No clock
- No output load
- No MCU interface
access
- Retain RAM data
but cannot access
the RAM
1
3
uA
Idslp_VCI2
Current of deep sleep
mode 2
VCI
- DC/DC off
- No clock
- No output load
- No MCU interface
access
- Cannot retain RAM
data
0.7
3
uA
Iopr_VCI
Operating Mode current
VCI
VCI=3.0V
Enable Clock and
Analog by Master
Activation Command
VGH=20V
VGL=-VGH
VSH1=15V
VSH2=5V
VSL=-15V
VCOM = -2V
No waveform
transitions.
No loading.
No RAM read/write
No OTP read /write
1000
uA
VGH
Operating Mode
Output Voltage
VGH
19.5
20
20.5
V
VSH1
VSH1
14.8
15
15.2
V
VSH2
VSH2
4.9
5
5.1
V
VSL
VSL
-15.2
-15
-14.8
V
VCOM
VCOM
-2.2
-2
-1.8
V
Table 11-2: Regulators Characteristics
Symbol
Parameter
Test Condition
Applicable pin
Min.
Typ.
Max.
Unit
IVSH
VSH1 current
VSH1 = +15V
VSH1
800
uA
IVSH1
VSH2 current
VSH2 = +5V
VSH2
800
uA
IVSL
VSL current
VSL = -15V
VSL
800
uA
IVCOM
VCOM current
VCOM = -2V
VCOM
100
uA

<!-- Page 42 -->

SSD1680
Rev 0.14
P 42/46
Jun 2019
Solomon Systech
12 AC Characteristics
12.1 Serial Peripheral Interface
The following specifications apply for: VDDIO - VSS = 2.2V to 3.7V, TOPR = 25°C, CL=20pF
Table 12-1 : Serial Peripheral Interface Timing Characteristics
Write mode
Symbol
Parameter
Min
Typ
Max
Unit
fSCL
SCL frequency (Write Mode)
20
MHz
tCSSU
Time CS# has to be low before the first rising edge of SCLK
60
ns
tCSHLD
Time CS# has to remain low after the last falling edge of SCLK
65
ns
tCSHIGH
Time CS# has to remain high between two transfers
100
ns
tSCLHIGH
Part of the clock period where SCL has to remain high
25
ns
tSCLLOW
Part of the clock period where SCL has to remain low
25
ns
tSISU
Time SI (SDA Write Mode) has to be stable before the next rising edge of SCL
10
ns
tSIHLD
Time SI (SDA Write Mode) has to remain stable after the rising edge of SCL
40
ns
Read mode
Symbol Parameter
Min
Typ
Max
Unit
fSCL
SCL frequency (Read Mode)
2.5
MHz
tCSSU
Time CS# has to be low before the first rising edge of SCLK
100
ns
tCSHLD
Time CS# has to remain low after the last falling edge of SCLK
50
ns
tCSHIGH
Time CS# has to remain high between two transfers
250
ns
tSCLHIGH Part of the clock period where SCL has to remain high
180
ns
tSCLLOW
Part of the clock period where SCL has to remain low
180
ns
tSOSU
Time SO(SDA Read Mode) will be stable before the next rising edge of SCL
50
ns
tSOHLD
Time SO (SDA Read Mode) will remain stable after the falling edge of SCL
0
ns
Note: All timings are based on 20% to 80% of VDDIO-VSS
Figure 12-1: SPI timing diagram

<!-- Page 43 -->

SSD1680
Rev 0.14
P 43/46
Jun 2019
Solomon Systech
13 Application Circuit
Figure 13-1: Schematic of SSD1680 application circuit
Table 13-1: Component list for SSD1680 application circuit
Part Name
Value
Requirements/Reference Part
C0-C1
1uF
X5R/X7R; Voltage Rating : 6V or 25V
C2-C7
1uF
0402/0603/0805; X5R/X7R; Voltage Rating : 25V
C8
0.47uF, 1uF
0603/0805; X7R; Voltage Rating : 25V
Note: Effective capacitance > 0.25uF @ 18V DC bias
R1
2.2 ohm
0402, 0603, 0805; 1% variation, ≥ 0.05W
D1-D3
Diode
MBR0530
1) Reverse DC voltage ≥ 30V
2) Io ≥ 500mA
3) Forward voltage ≤  430mV
Q1
NMOS
Si1304BDL/NX3008NBK
1)
Drain-Source breakdown voltage ≥ 30V
2)
Vgs(th) = 0.9V (Typ), 1.3V (Max)
3)
Rds on ≤ 2.1Ω @ Vgs = 2.5V
L1
47uH
CDRH2D18 / LDNP-470NC
Io= 500mA (Max)
U1
0.5mm ZIF socket
24pins, 0.5mm pitch
Remarks:
1)
The recommended component value and reference part in Table 13-1 is subject to change depending on panel
loading.
2)
Customer is required to review if the selected component value and part is suitable for their application.

<!-- Page 44 -->

SSD1680
Rev 0.14
P 44/46
Jun 2019
Solomon Systech
14 Package Information
14.1 Die Tray Dimensions for SSD1680Z
Figure 14-1 : SSD1680Z die tray information (unit: mm)

<!-- Page 45 -->

SSD1680
Rev 0.14
P 45/46
Jun 2019
Solomon Systech
14.2 Die Tray Dimensions for SSD1680Z8
Figure 14-2 : SSD1680Z8 die tray information (unit: mm)

<!-- Page 46 -->

SSD1680
Rev 0.14
P 46/46
Jun 2019
Solomon Systech
Solomon Systech reserves the right to make changes without notice to any products herein. Solomon Systech makes no warranty, representation
or guarantee regarding the suitability of its products for any particular purpose, nor does Solomon Systech assume any liability arising out of the
application or use of any product or circuit, and specifically disclaims any, and all, liability, including without limitation consequential or incidental
damages. “Typical” parameters can and do vary in different applications. All operating parameters, including “Typical” must be validated for each
customer application by the customer’s technical experts. Solomon Systech does not convey any license under its patent rights nor the rights of
others. Solomon Systech products are not designed, intended, or authorized for use as components in systems intended for surgical implant into
the body, or other applications intended to support or sustain life, or for any other application in which the failure of the Solomon Systech product
could create a situation where personal injury or death may occur. Should Buyer purchase or use Solomon Systech products for any such unintended
or unauthorized application, Buyer shall indemnify and hold Solomon Systech and its offices, employees, subsidiaries, affiliates, and distributors
harmless against all claims, costs, damages, and expenses, and reasonable attorney fees arising out of, directly or indirectly, any claim of personal
injury or death associated with such unintended or unauthorized use, even if such claim alleges that Solomon Systech was negligent regarding the
design or manufacture of the part.
The product(s) listed in this datasheet comply with Directive 2011/65/EU of the European Parliament and of the council of 8 June 2011 on the
restriction of the use of certain hazardous substances in electrical and electronic equipment and People’s Republic of China Electronic Industry
Standard GB/T 26572-2011 “Requirements for concentration limits for certain hazardous substances in electronic information products (电子电器产
品中限用物質的限用要求)”. Hazardous Substances test report is available upon request.
http://www.solomon-systech.com


---

# 4. GDEM0266T71WT Datasheet

> **Source file:** `GDEM0266T71WT.pdf`  
> Good Display — GDEM0266T71WT 2.66" e-paper display module (OCR-extracted)

<!-- Page 1 -->

2.66 inch
E-paper Display
GDEM0266T71WT 
 
Dalian Good Display Co., Ltd.
GOODISPLAY

<!-- Page 2 -->

GooDisplay GDEM0266T71WT

 

Product Specifications

BR BH

  

  

 

| Sunny c
Temperature ™ a
i wy

RB

ie il
Al alll

 

 

 

 

 

 

 

 

 

 

Customer Standard
Description 2.66” E-PAPER DISPLAY
Model Name GDEMO266T71WT
Date 2025/04/01
Revision 1.0
Design Engineering
Approval Check Design

 

ep ey Lay | ee

Zhongnan Building, No.18, Zhonghua West ST,Ganjingzi DST,Dalian, CHINA
Tel: +86-411-84619565
Email: info@good-display.com

 

Website: www.good-display.com

 

www.good-display.com 2/34 2.66 inch series

<!-- Page 3 -->

CONTENTS
7.
8.
9.
1.
Over View......................................................................................................................................
2.
Features ...........................................................................................................................................
3.
Mechanical Specification................................................................................................................
4.
Mechanical Drawing of EPD Module.............................................................................................
5.
Input/output Pin Assignment...........................................................................................................
6.
Electrical Characteristics.................................................................................................................
5
6
7
8
9
 
Command Table...............................................................................................................................
Block Diagram.................................................................................................................................
Typical Application Circuit with SPI Interface...............................................................................
6.1 Absolute Maximum Rating.......................................................................................................
6.2 Panel DC Characteristics...........................................................................................................
6.3 MCU Interface...........................................................................................................................
6.3.1 MCU Interface Selection........................................................................................................
6.3.2 MCU Serial Interface(4-wire SPI) .........................................................................................
6.3.3 MCU Serial Interface(3-wire SPI) ......................................................................................... 
6.3.4 Interface Timing.....................................................................................................................
10.
Typical Operating Sequence............................................................................................................
GDEM0266T71WT
www.good-display.com
3/34
2.66 inch series
9
5
14
16
24
25
26
12
11
11
11
10
GOODISPLAY

<!-- Page 4 -->

11.
Reliability Test................................................................................................................................
12.
Inspection Condition.......................................................................................................................
13.
Handling, Safety, and Environment Requirements.........................................................................
14.
Packaging........................................................................................................................................
28 
29 
33 
34 
GDEM0266T71WT
www.good-display.com
4/34
2.66 inch series
GOODISPLAY

<!-- Page 5 -->

GooDisplay GDEM0266T71WT

 

1. Over View

GDEM0266T71WT is an Active Matrix Electrophoretic Display (AM EPD), with interface and a
reference system design. The display is capable to display images at 1-bit white and black full display
capabilities. The 2.66 inch active area contains 152x296 pixels. The module is a TFT-array driving
electrophoresis display, with integrated circuits including gate driver, source driver, MCU interfece,
timing controller, oscillator, DC-DC, SRAM, LUT, VCOM. Module can be used in portable electronic
devices, such as Electronic Shelf Label (ESL) System.

2. Features

@ 152x296 pixels display

High contrast High reflectance

@ Ultra wide viewing angle Ultra low power consumption

Pure reflective mode

@Bi-stable display

@ Commercial temperature range

@ Landscape portrait modes

@ Hard-coat antiglare display surface

Ultra Low current deep sleep mode

On chip display RAM

@ Waveform can stored in On-chip OTP or written by MCU

Serial peripheral interface available

On-chip oscillator

On-chip booster and regulator control for generating VCOM, Gate and Source driving
voltage

2. "
1 C signal master interface to read external temperature sensor
Built-in temperature sensor

 

www.good-display.com 5/34 2.66 inch series

<!-- Page 6 -->

GooDisplay GDEM0266T71WT

 

3.Mechanical and Optical Specification

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

Parameter Specifications Unit Remark
Screen Size 2.66 Inch
Display Resolution 152(H)x296(V) Pixel DPI:125
Active Area 30.704*60.088 mm
Pixel Pitch 0.202 0.203 mm
Pixel Configuration Rectangle
Outline Dimension 36.30(H)*71.82 (V) x1.0(D) mm
Weight 4.740.5 g
Symbol | Parameter Conditions Min Typ. Max Units Notes
Black State L* value : 19 22 3-1
Black Ghosting AL : 1 : 3-1
ws White State L* value 66 67 = 3-1
White Ghosting AL - I - 3-1
R White Reflectivity White 30 34 - % 3-1
CR Contrast Ratio Indoor 15:1 20:1 - 3-1
3-2

 

GN 2Grey Level - - - -
A Temp:23 + 3°C
Life Humidity:55 + 10%RH

 

Syears 3-3

 

Notes: 3-1. Luminance meter: Eye-One Pro Spectrophotometer.
3-2. CR=Surface Reflectance with all white pixel/Surface Reflectance with all black pixels.
3-3. When the product is stored. The display screen should be kept white and face up.

 

www.good-display.com 6/34 2.66 inch series

<!-- Page 7 -->

GooDisplay GDEM0266T71WT

 

4.Mechanical Drawing of EPD Module

 

 

 

 

NOTE
1 DISPLAY NODULE 2. 66” ARRAY FOR EPD
, Sei 6807 EPD A 25.04.01
2 DRIVER IC:SSD168028 ANGLES:5"
3 RESOLUTION: 296gateX152source X=204mm
4 PIXEL SIZE: 0. 202mmX 0.203. mm Xx==0.20mm | GDEMO266T7INT mm 1/1

XXxX==0.20mm

 

www.good-display.com 7/34 2.66 inch series

<!-- Page 8 -->

GooDisplay GDEM0266T71WT

 

5. Input/output Pin Assignment

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

No. Name Vo Description Remark
1 NC Do not connect with other NC pins Keep Open
2 GDR O_ | N-Channel MOSFET Gate Drive Control
3 RESE I Current Sense Input for the Control Loop
4 NC NC | Do not connect with other NC pins Keep Open
5 VSH2 C_ | Positive Source driving voltage 2
6 TSCL O_ | I2C Interface to digital temperature sensor Clock pin Note 5-6
7 TSDA I/O | 12C Interface to digital temperature sensor Data pin Note 5-6
8 BSI I | Bus Interface selection pin Note 5-5
9 BUSY O | Busy state output pin Note 5-4
10 RES# I Reset signal input. Active Low. Note 5-3
ll D/C# I | Data /Command control pin Note 5-2
12 CS# I Chip select input pin Note 5-1
13 SCL I Serial Clock pin (SPI)

14 SDA VO _ | Serial Data pin (SPI)

 

Power Supply for interface logic pins It should be

Is VDDIO p connected with VCI

 

 

 

 

 

 

 

 

16 VCI P_ | Power Supply for the chip

17 VSS P| Ground
Core logic power pin VDD can be regulated internally

18 VDD C_ | from VCI. A capacitor should be connected between
VDD and VSS

19 VPP P |FOR TEST Keep Open

20 VSH1 C_ | Positive Source driving voltage

4 VGH Cc Power Supply pin for Positive Gate driving voltage and
VSH1

22 VSL C_ | Negative Source driving voltage

23 VGL c Power Supply pin for Negative Gate driving voltage

VCOM and VSL
24 VCOM C_ | VCOM driving voltage

 

 

 

www.good-display.com 8/34 2.66 inch series

<!-- Page 9 -->

GooDisplay GDEM0266T71WT

 

I= Input Pin, O =Output Pin, I/O = Bi-directional Pin (Input/output), P = Power Pin, C = Capacitor Pin

Note 5-1: This pin (CS#) is the chip select input connecting to the MCU. The chip is enabled for MCU
communication only when CS# is pulled LOW.

Note 5-2: This pin is (D/C#) Data/Command control pin connecting to the MCU in 4-wire SPI mode. When
the pin is pulled HIGH, the data at SDA will be interpreted as data. When the pin is pulled LOW,
the data at SDA will be interpreted as command.

Note 5-3: This pin (RES#) is reset signal input. The Reset is active low.

Note 5-4: This pin is Busy state output pin. When Busy is High, the operation of chip should not be
interrupted, command should not be sent. The chip would put Busy pin High when -Outputting
display waveform -Communicating with digital temperature sensor

Note 5-5: Bus interface selection pin.

 

 

 

BS1 State MCU Interface
L 4-lines serial peripheral interface(SPI) - 8 bits SPI
H 3- lines serial peripheral interface(SPI) - 9 bits SPI

 

6. Electrical Characteristics

6.1 Absolute Maximum Rating

 

 

 

 

 

 

 

 

 

Parameter Symbol Rating Unit
Logic supply voltage VCI -0.5 to +6.0 Vv
Logic Input voltage VIN -0.5 to VCI +0.5 Vv
Logic Output voltage VOUT -0.5 to VCI +0.5 Vv
Operating Temp range TOPR -25to +10 °C.
Operating Temp range max TOPRm -25 to +30 °C.
Storage Temp range TSTG -25 to+70 °C.
Optimal Storage Temp TSTGo 2343 °C.

Optimal Storage Humidity HSTGo 55410 %RH

 

Note:1. Maximum ratings are those values beyond which damages to the device may occur. Functional
operation should be restricted to the limits in the Panel DC Characteristics tables.

2. Due to the particle characteristics of FPL, we only guarantee that the bar code can be read from
10-30°C. The recommended operating temperature should be kept above -25-10°C.

 

www.good-display.com 9/34 2.66 inch series

<!-- Page 10 -->

GooDisplay GDEM0266T71WT

 

6.2 Panel DC Characteristics
The following specifications apply for: VSS=0V, VCI=3.0V, TOPR = -15°C.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

Parameter Symbol Condition opptcable Min. | Typ. | Max. | Unit
Single ground Vss - - 0 - Vv
Logic supply voltage Vel - VCI 2.2 3.0 3.7 Vv
Core logic voltage Vpp VDD 1.7 1.8 19 Vv
High level input voltage Vin - - 0.8 Ver - - Vv
Low level input voltage Vit - - - - 0.2 Ver Vv
High level output voltage Vou IOH = -100uA. - 0.9 Ver - - Vv
Low level output voltage VoL IOL = 100uA : : : 0.1 Ver Vv
Typical power Pryp Vai =3.0V - - 13.5 - mW
Deep sleep mode Pstpy Vai =3.0V - - 0.003 - mW
Typical operating current | lopr_VCI Vai =3.0V - - 45 : mA
Image update time : -15°C : : 30 : sec
Typical peak current Iopr_VCI 2.2~3.1V 40 60 mA

DC/DC off
Sleep mode current Islp_Ver No clock : b 20 uA
No input load
Ram data retain
DC/DC off
Deep sleep mode current | Idslp_Vcr No cloclg - - 1 5 uA

No input load
Ram data not retain
Notes: 1. The typical power is measured with following transition from horizontal 2 scale pattern to vertical

a

2. The deep sleep power is the consumed power when the panel controller is in deep sleep mode.

 

2 scale pattern.

3. The listed electrical characteristics are only guaranteed under the controller & waveform provided
by DKE.
4. Electrical measurement: Tektronix oscilloscope - MDO3024,

Tektronix current probe - TCP0030A.

 

www.good-display.com 10/34 2.66 inch series

<!-- Page 11 -->

GooDisplay GDEM0266T71WT

 

6.3 MCU Interface
6.3.1 MCU Interface Selection
The pin assignment at different interface mode is summarized in Table 6-3-1. Different MCU
mode can be set by hardware selection on BS1 pins. The display panel only supports 4-wire SPI or

3-wire SPI interface mode.

 

 

 

 

Pin Name Data/Command Interface Control Signal

Bus interface SDA SCL CS# D/C# RES#
BSI=L_ 4-wire SPI SDA SCL CS# D/C# RES#
BSI=H_ 3-wire SPI SDA SCL CS# L RES#

 

6.3.2 MCU Serial Interface (4-wire SPI)
The serial interface consists of serial clock SCL, serial data SDA, D/C#, CS#. This interface

supports Write mode and Read mode.

 

 

 

Function CS# D/C# SCL
Write command L L t
Write data L H t

 

Note: { stands for rising edge of signal

In the write mode SDA is shifted into an 8-bit shift register on every rising edge of SCL in the
order of D7, D6, ... DO. The level of D/C# should be kept over the whole byte . The data byte in the
shift register is written to the Graphic Display Data RAM /Data Byte register or command Byte
register according to D/C# pin.

| [
oo
= TU

& PRA@@EE@@00O0

Parameter

 

Figure 6-1: Write procedure in 4-wire SPI mode

 

www.good-display.com 11/34 2.66 inch series

<!-- Page 12 -->

GooDisplay GDEM0266T71WT

 

In the Read mode:
1. After driving CS# to low, MCU need to define the register to be read.
2. SDA is shifted into an 8-bit shift register on every rising edge of SCL in the order of D7,
D6, ... DO with D/C# keep low.
3. After SCL change to low for the last bit of register, D/C# need to drive to high.
4. SDA is shifted out an 8-bit data on every falling edge of SCL in the order of D7, D6, ... DO.
5. Depending on register type, more than 1 byte can be read out. After all byte are read, CS#

need to drive to high to stop the read operation.

2 r

‘ W
Register Parameter

SDA
onions |X KEK ™ KE AE A)

SDA
ecg i}

Figure 6-2: Read procedure in 4-wire SPI mode

6.3.3 MCU Serial Interface (3-wire SPI)

The 3-wire serial interface consists of serial clock SCL, serial data SDA and CS#. This
interface also supports Write mode and Read mode.

The operation is similar to 4-wire serial interface while D/C# pin is not used. There are
altogether 9-bits will be shifted into the shift register on every ninth clock in sequence: D/C# bit, D7
to DO bit. The D/C# bit (first bit of the sequential data) will determine the following data byte in
the shift register is written to the Display Data RAM (D/C# bit = 1) or the command register (D/C#
bit = 0).

 

 

 

Function CS# D/C# SCL
Write command L Tie t
Write data L Tie t

 

Note: { stands for rising edge of signal

 

www.good-display.com 12/34 2.66 inch series

<!-- Page 13 -->

GooDisplay GDEM0266T71WT

 

am | [

 

 

SCL
SDA
(Write 0 } D7} D6 } DS } D4} D3} D2} D1} DOX 1 } D7
Mode)
Register Parameter
Figure 6-3: Write procedure in 3-wire SPI mode
In the Read mode:

1. After driving CS# to low, MCU need to define the register to be read.

2. D/C=0 is shifted thru SDA with one rising edge of SCL

3. SDA is shifted into an 8-bit shift register on every rising edge of SCL in the order of D7,
D6, ... DO.

4. D/C=1 is shifted thru SDA with one rising edge of SCL

5. SDA is shifted out an 8-bit data on every falling edge of SCL in the order of D7, D6, ... DO.

6. Depending on register type, more than | byte can be read out. After all byte are read, CS#

need to drive to high to stop the read operation.

c# | if

& pDOooOooooo ey

‘
SDA i \
Read - D7
Mode) i ;
i i

Figure 6-4: Read procedure in 3-wire SPI mode

 

 

 

www.good-display.com 13/34 2.66 inch series

<!-- Page 14 -->

GooDisplay GDEM0266T71WT

 

6.3.4 Interface Timing
The following specifications apply for: VSS=0V, VCI=3.0V, Torr =-15°C.

 

 

 

 

 

Changed Diagram

Serial Interface Timing Characteristics

(VCI - VSS = 2.2V to 3.7V, TOPR = -15°C, CL=20pF)

 

 

 

 

 

 

 

 

 

Write mode

Symbol |Parameter (Min |Typ. |Max |Unit
fSCL SCL frequency (Write Mode) 20 | MHz
tCSSU Time CS# has to be low before the first rising edge of SCLK 60 ns
'tCSHLD —_|Time CS# has to remain low after the last falling edge of SCLK 65 ns
tCSHIGH |Time CS# has to remain high between two transfers 100 ns
itSCLHIGH |Part of the clock period where SCL has to remain high 25 ns
tSCLLOW |Part of the clock period where SCL has to remain low 25 ns
iSISU sre SI (SDA Write Mode) has to be stable before the next rising edge o 10 ns
tSIHLD sare SI (SDA Write Mode) has to remain stable after the rising edge o 40 ns

 

 

www.good-display.com 14/34 2.66 inch series

<!-- Page 15 -->

GooDisplay GDEM0266T71WT

 

 

 

 

 

 

 

 

 

 

Read mode

‘Symbol |Parameter (Min |Typ. |Max |Unit
fSCL ISCL frequency (Read Mode) 2.5 | MHz
tCSSU Time CS# has to be low before the first rising edge of SCLK 100 ns
tCSHLD — |Time CS# has to remain low after the last falling edge of SCLK 50 ns
tCSHIGH |Time CS# has to remain high between two transfers 250 ns
poLiiG Part of the clock period where SCL has to remain high 180 ns
tSCLLOW JPart of the clock period where SCL has to remain low 180 ns
tSOSU Time SO(SDA Read Mode) will be stable before the next rising edge of SCL 50 ns
tSOHLD |Time SO (SDA Read Mode) will remain stable after the falling edge of SCL 0 ns

 

 

www.good-display.com 15/34 2.66 inch series

<!-- Page 16 -->

GooDisplay GDEM0266T71WT

 

 

 

 

 

 

 

 

 

 

 

 

 

7.Command Table

R/W#|D/c#| Hex| D7 | D6 | D5 | D4 | D3 | 2 | D1 | Do cemman Description

0 0 |01;0{|0]0)04} 01} 0} 0 | 1 |Driver  |Gate setting

o|1 A7| A6| A5|A4| A3 | A2| Al | Ao [Output Set A[8:0]-0127h

0 1 ololololololo las control Set B[8:0]=00h

o|1 o{|o[0]0 | 0 |B2/B1/ Bo

0 0 {03} 0}]0}]0)0]0]0) 1 | 1 \Gate SetGate Driving voltage

ololo Driving |A[4:0]=17h[POR],VGH at 20V[POR]

ol 4 A4|A3|A2|A1| Ao [voltage |VGH setting from 10V to 20V
control

0 0 }04}0;0/0;)0;0)/ 1 0 | 0 |Source  |Set Source Driving voltage

old ‘A7/A6|A5/A4/A3|A2/ Al | Ao [Priving |A[7:0}= 41h[POR],VSHI at 15V
voltage :0]=A Ch[POR],VSH2 at 5.4V

oj B7 | B6 | BS | B4 | B3 | B2 | BI | BO | ontrol = 32h[POR], VSL at -15V

of c7| ce} cs | c4]}c3 | c2| c1 | co

 

Initial —_|Program Initial Code Setting

Code ‘The command required CLKEN=1.
0 0 |08]0}0}]0}0)] 1] 0 | 0 | 0 {Setting [Refer to Register 0x22 for detail.

OTP BUSY pad will output high during

Program joperation

0 0 |09;}/0;/0;,0/0} 140) 0] 1 |Write Write Register for Initial Code Setting

of 1 A7| A6| A5| A4] A3 | A2| AT | Ao [Register |Selection
for Initial |A[7:0] ~ D[7:0]: Reserved

 

 

 

 

 

 

 

 

9 1 B7 | B6 | BS | B4 | B3 | B2 | BI | BO Code Details refer to Application Notes of Initial
of 1 7] co | cs | C4] C3 [C2] C1 | CO|setting [Code Setting
0 1 D7 | D6 | DS | D4| D3 | D2 | DI | DO
Read Read Register for Initial Code Setting
OA Register
0 0 0} 0} 0 {0 1) 0} 1 | O |for Initial
Code
Setting
0 0 |10]0}0};,0{1/)]0{ 04 0 | 0 |Deep Deep Sleep mode Control:
0 1 o/o}o}o}]o}0)]0] Ao Sleep A[1:0]: Description

mode 00 ~Normal Mode [POR]
01 Enter Deep Sleep Mode 1
11 Enter Deep Sleep Mode 2
After this command initiated, the chip will
enter Deep Sleep Mode, BUSY pad will
keep output high.
Remark:
To Exit Deep Sleep mode, User required
to send HWRESET to the driver

 

 

www.good-display.com 16/34 2.66 inch series

<!-- Page 17 -->

GooDisplay GDEM0266T71WT

 

 

0 oO /1l1)0}/0)]0)]14]0/)] 0) 0) 1 JData Define data entry sequence
Entry — |A[2:0] = 011 [POR]
mode A [1:0] = ID[1:0]
setting  |Address automatic increment / decrement
setting
The setting of incrementing or
decrementing of the address counter can
be made independently in each upper and
0 1 0} 0] 0} 0] 0 | A>} Ai} Ao lower bit of the address.
00 - Y decrement, X decrement,
01 - Y decrement, X increment,
10 - Y increment, X decrement,
11 - Y increment, X increment [POR]
A[2]=AM
Set the direction in which the address
counter is updated automatically after data
are written to the RAM.
AM= 0, the address counter is updated in
the X direction. [POR]
AM = 1, the address counter is updated in
the Y direction

 

 

 

www.good-display.com 17/34 2.66 inch series

<!-- Page 18 -->

GooDisplay GDEM0266T71WT

 

 

0 0 }0oc;}0;0}0);0)} 1 1 | 0 | 0 |Booster |Booster Enable with Phase 1, Phase 2 and Phase 3
Soft start |for soft start current and duration setting.
‘Control |A[7:0] -> Soft start setting for Phasel

= 8Bh [POR]

B[7:0] -> Soft start setting for Phase2
= 9Ch [POR]

|C[7:0] -> Soft start setting for Phase3
= 96h [POR]

D[7:0] -> Duration setting

= OFh [POR]

Bit Description of each byte:
A[6:0] / B[6:0] / C[6:0]:
Bit[6:4]

Driving Strength

Selection

000 1(Weakest)

001 2

010 3

Oll 4

100 5

101 6

110 7

111 8(Strongest)

Bit[3:0]

‘Min Off Time Setting of GDR
[ Time unit ]

0000

(0011

NA

0100 2.6

0101 = 3.2

0110 3.9
0 1 1 | A6| A5 | A4| A3 | A2} Al | AO oll 46

0 1 1 | B6| BS | B4| B3 | B2| BI | BO 1000 5.4

7 ; 1001 6.3

0 1 1 | C6} C5 | C4) C3 | C2} C1 | CO 1010 73

0 1 0 | 0 | DS) D4} D3) D2) D1 | DO 1011 8.4

1100 9.8

1101 11.5

1110 13.8

1111 16.5

'D[5:0]: duration setting of phase
'D[5:4]: duration setting of phase 3
D[3:2]: duration setting of phase 2
D[1:0]: duration setting of phase 1
Bit[ 1:0]

Duration of Phase
[Approximation]

00 10ms

01 20ms

10 30ms

11 40ms

 

 

 

 

 

 

 

 

 

www.good-display.com 18/34 2.66 inch series

<!-- Page 19 -->

GooDisplay GDEM0266T71WT

 

 

0 0 |12/ 0/0] 0); 140] 0] 1 | 0 |SWRES It resets the commands and parameters to
ET their S/W Reset default values except
R10h-Deep Sleep Mode
During operation, BUSY pad will output

 

 

high.
Note: RAM are unaffected by this
command.
0 0 |18]| 0] 0} 0] 1 4} 1 | 0 | 0 | O |Temperat|/Temperature Sensor Selection
ure A[7:0] = 48h [POR], external temperature sensor
9 ! AT] A6) AS | A4) A3] A2) Al | AO Sensor |A[7:0] = 80h Internal temperature sensor
Control

 

0 0 {1A} 0/0 {0} 1} 1] 0} 1 | O |Temperat|Write to temperature register.

oo}. A7|A6| AS] A4] A3 | A2| Al | AO Jere A[11:0] = 7FFh [POR]
Sensor
0} 1 B7| Bo | B5|B4] 0 | 0 | 0 | O [Control
(Write to
temperat
ure
register)|

 

 

 

0 0 |20/ 0/0] 1 {040} 0] 0 | 0 |Master |Activate Display Update Sequence
Activatio |The Display Update Sequence Option is located at
in R22h
User should not interrupt this operation to avoid
corruption of panel images.

 

0 0 |21/ 0/0] 1{) 040] 0 | 0] 1 {Display |RAM content option for Display Update
o [1 A7/A6| A5| A4] a3] a2] Al] AO date 1 AT: =o IpoR

ontro!
0 1 B7}0}0/0/0/0/0)]0 Red RAM option
Normal
Bypass RAM content as 0
Inverse RAM content
A[3:0] BW RAM option
0000 Normal
0100 Bypass RAM content as 0
1000 Inverse RAM content
B[7] Source Output Mode
0 Available Source from SO to S175
1 Available Source from S8 to S167

 

 

 

  

 

 

www.good-display.com 19/34 2.66 inch series

<!-- Page 20 -->

GooDisplay GDEM0266T71WT

 

 

0 0 |22) 0] 0) 1 | 0] 0 | 0] 1 | O Display [Display Update Sequence Option:
Update [Enable the stage for Master Activation
Control 2|A[7:0]= FFh (POR)
Operating sequence
Parameter
(in Hex)
Enable clock signal 80
Disable clock signal 01
Enable clock signal
Enable Analog
co.
Disable Analog
Disable clock signal
03
Enable clock signal
Load LUT with DISPLAY Mode |
Disable clock signal

 

0 fl AT |A6 JAS |A4 |A3 |A2 |Al |AO

91
Enable clock signal
Load LUT with DISPLAY Mode 2
Disable clock signal
99
Enable clock signal
Load temperature value
Load LUT with DISPLAY Mode |
Disable clock signal
BL
Enable clock signal
Load temperature value
Load LUT with DISPLAY Mode 2
Disable clock signal
BS
Enable clock signal
Enable Analog
Display with DISPLAY Mode 1
Disable Analog
Disable OSC
C7
Enable clock signal
Enable Analog
Display with DISPLAY Mode 2
Disable Analog
Disable OSC
CF
Enable clock signal
Enable Analog
Load temperature value
DISPLAY with DISPLAY Mode 1
Disable Analog
Disable OSC
FT
Enable clock signal
Enable Analog
Load temperature value
DISPLAY with DISPLAY Mode 2

 

 

www.good-display.com 20/34 2.66 inch series

<!-- Page 21 -->

GooDisplay GDEM0266T71WT

 

 

0 0 |24}0]0 1)/0]0)]1) 04] 0 {Write After this command, data entries will be

RAM written into the BW RAM until another
(Black —|command is written. Address pointers will
White) jadvance accordingly
/ RAM _ |For Write pixel:
0x24 ‘Content of Write RAM(BW) = 1

For Black pixel:

‘Content of Write RAM(BW) = 0

0 0 |26)0)0}1)0]0)] 1) 1 | 0 Write After this command, data entries will be
RAM written into the RED RAM until another
(RED) —|command is written. Address pointers will
/ RAM _ jadvance accordingly.
0x26) For Red pixel:
Content of Write RAM(YELLOW) = |
For non-Red pixel [Black or White]:
Content of Write RAM(YELLOW) = 0

 

 

 

 

 

0 0 }2cC;0;/0};, 1/04 1 1 | 0 | 0 |Write Write VCOM register from MCU interface
0 1 'VCOM__|A[7:0] = 00h [POR]
AT|A6| AS | A4| A3 | A2| Al | AO register
0 0 |2D;0}0]1)04} 1) 1) 04 1 JOTP Read Register for Display Option:
1|a ATIA6|AS|A4|A3|A2/ Al | Ao [Register |A[7:0]: VCOM OTP Selection

 

Read for |(Command 0x37, Byte A)

 

 

 

 

 

 

 

! ! B7 | B6 | BS | B4 | B3 | B2 | BI | BO Display |B[7:0]: VCOM Register

1 1 C7 | C6 | CS | C4} C3 | C2 | Cl | CO |Option —|(Command 0x2C)

tid D7| D6 | Ds | D4] D3 | D2 | D1 | DO C[7:0]~G[7:0]: Display Mode

ifa £7 | £6 | £5 | £4 | £3 | £2 | £1 | EO Ca? Bate B to Byte F)
tes.

tj F7 | F6 | FS | Fa | F3 | F2 | FI | FO H[7:0]~K[7:0}: Waveform Version

1 fd G7 | G6 | G5 | G4| G3 | G2| G1 | Go (Command 0x37, Byte G to Byte J)

1 1 H7 | H6 | H5 | H4| H3 | H2 | H1 | HO [4 bytes]

1] 17] 16 | 15 | 14] 13 | 12 | 11 | 10

 

1 1 J7 | J6 | JS | J4 | J3-| J2 | Jl | JO
1 1 K7| K6| K5 | K4| K3 | K2| K1 | KO

 

 

0 0 |2F/0;}0}1/0;/1)1)1 1 {Status Read IC status Bit [POR 0x01]
Bit Read |A[5]: HV Ready Detection flag [POR=0]
0: Ready
1: Not Ready
A[4]: VCI Detection flag [POR=0]
0: Normal
1: VCI lower than the Detect level
A[3]: [POR=0]
A[2]: Busy flag [POR=0]
0: Normal
1: BUSY
A[1:0]: Chip ID [POR=01]
Remark:
A[5] and A[4] status are not valid after
RESET, they need to be initiated by
command 0x14 and command 0x15
respectively

 

 

www.good-display.com 21/34 2.66 inch series

<!-- Page 22 -->

GooDisplay GDEM0266T71WT

 

 

0 0 |30/ 0} 0} 141) 0] 0] 0 | O |Program |Program OTP of Waveform Setting
WS OTP |The contents should be written into RAM
before sending this command.
The command required CLKEN=1.
Refer to Register 0x22 for detail.
BUSY pad will output high during

 

 

 

 

 

 

 

operation
0 0 |32}/0}0}f1414)0/)] 07) 1 | O {Write Write LUT register from MCU interface
0 1 A7| A6| A5| A4| A3| A2!] Al | AO [LUT [153 bytes], which contains the content of
register |VS[nX-LUTm], TP[nX], RP[n], SR[nXY],
0 1 B7 | B6 | BS | B4 | B3 | B2 | B1 | BO FR{[n] and XON[nXY]
0 1 Peedi fete feted: Refer to Session 6.7 WAVEFORM
0 1 pfa fafa fs fs fry: SETTING
0 1
0 1

 

0 0 |}39/0/}0}]1)]1)1/)]0/)/ 04 1 jOTP OTP program mode
program |A[1:0] = 00: Normal Mode [POR]
mode A[1:0] = 11: Internal generated OTP
programming voltage
Remark: User is required to EXACTLY
follow the reference code sequences

 

0 0 }3C/0;}0)1)]1t}]1})1)0)0 Select border waveform for VBD
A[7:0] = COh [POR], set VBD as HIZ.

 

 

www.good-display.com 22/34 2.66 inch series

<!-- Page 23 -->

GooDisplay GDEM0266T71WT

 

 

0 1 Az| Ao | As | As} 0 | 0 | Ai | Ao A [7:6] :Select VBD option
A[7:6] Select VBD as
00 GS Transition,
Defined in A[2] and
A[1:0]
Ol Fix Level,
Defined in A[5:4]
10 VCOM
1[POR] HizZ
‘A [5:4] Fix Level Setting for VBD
A[5:4] VBD level
00 VSS
Ol VSHI
10 VSL
11 VSH2
A[2] GS Transition control
A[2] GS Transition control
0 Follow LUT
(Output VCOM @ RED)
1 Follow LUT
A [1:0] GS Transition setting for VBD
A[1:0] VBD Transition
00 ~LUTO
01 LUTI
10 LUT2
11 LUT3

0 0 |44| 0] 1/0) 0} 0] 1 | 0 | 0 |Set RAM|Specify the start/end positions of the window
0 1 0] 0] 0 | As! A3| Ao} Ar | Ao X- address in the X direction by an address unit
address |A[4:0]: XSA[4:0], X Start, POR = 01h

 

 

 

 

 

9)! 0 | 0 | 0 | Bs) Bs) Bo | Bi} Bo |cioty — |pl4:0}: XEA[4:0], X End, POR = 13h

End

position
0 0 |45/ 0] 1] 0 04} 0} 1 | 0 | 1 |SetRam Specify the start/end positions of the window
0 1 A7| Ao | As | Ay] As | Ao | Ai | Ao /¥> address in the Y direction by an address unit

 

address |A[8:0]: YSA[8:0], Y Start, POR = 0127h

 

 

 

 

 

 

 

oj O10} 0/0] 0] 0} 0 [Astcct/ — {Bp8:0]: YEA[8:0], Y End, POR = 0000h
0 1 Bz | Be | Bs | Ba | Bs | Bz | Bi | Bo [End
0 1 0] 0 | 0 | 0] 0 | 0 | O | Bs position
0 0 |4E;0};1]0)0] 1 1 1 | 0 |Set RAM |Make initial settings for the RAM X address in
0 1 0101] 0] As] As} Az} Ar | Ao * the address counter (AC) |
address |A[4:0]: XAD[4:0], POR is 01h
counter
0 0 |4F/ 0} 1 ]0]04 1} 1 4} 1 | 1 |SetRAM)Make initial settings for the RAM Y address in
0 1 A7| Ae] As | As| A3 | A2| Ar | Ao ya fe address counter (A) oth
0 1 olololololololas address |A[8:0]: YAD[8:0], POR is 7

counter

 

 

www.good-display.com 23/34 2.66 inch series

<!-- Page 24 -->

GooDisplay GDEM0266T71WT

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

8.Block Diagram
- 12C bus PREVGL
Temperature Data & control bus (SPI EPD
Senser — DC-DC
or MCU Circur aad
Circuit I2C bus me Circuit
(Optional) EPD - se
Capacitor | | Power Circuit

 

Circuit

 

 

 

www.good-display.com 24/34 2.66 inch series

<!-- Page 25 -->

GooDisplay GDEM0266T71WT

 

9. Typical Application Circuit with SPI Interface

Dt D2 Connectort"24 yy

 
  
    

oR

 

 

 

 

 

 

 

 

— , = i ul vsH2
vel hibit > VGH
xe D3
a4
GOR iB
= 3 4
Rt
Part Name Value Reference Part Requirements for spare part
C4C6 luF XS5R/X7R;Voltage Rating:6v or 25v
cl ba g C5 luF 0402/0603/0805; X5R/X7R: Voltage Rating:25v
co luF 0603/0805; X7R; Voltage Rating:25v
NOTE: Effective capacitance >0.25uF @18v DC bias
RI 2.20hm 0402/0603/0805; 1% variation, =0.05W

 

1)Reverse DC Voltage=30V
D1 D2 D3 Diode MBR0530 2)lo2500mA
3)Forward voltage <430mV
1)Drain-Source breakdown voltage =30v
Ql NMOS Sil304BDL/NX3008NBK | 2)Vgs(th)=0.9v(Typ), 1.3v(Max)
3)rds on<2.1 2 @ Vgs=2.5v

 

 

Ll 47UH CDRH2D18/LDNP-470NC | 1) lo=500mA(max)

 

 

www.good-display.com 25/34 2.66 inch series

<!-- Page 26 -->

GooDisplay GDEM0266T71WT

 

10.Typical Operating Sequence
10.1 OTP Operation Flow

 

Power On(Apply VCI)

(Apply VCI)

Reset the EPD driver

|

Turn on the oscillator clock and

 

 

 

 

 

DC/DC regulator to generate the

drive voltage

 

|

Load image data and update

|
|

Power Off Enter into deep sleep |

 

 

 

 

 

 

 

 

www.good-display.com 26/34 2.66 inch series

<!-- Page 27 -->

GooDisplay GDEM0266T71WT

 

10.2 OTP Operation Reference Program Code

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

ACTION [ VALUE/DATA [ COMMENT.
POWER ON
delay [ 10ms
PIN CONFIG
RESE# low Hardware reset
dela 200us
RESE# high
delay 200us
Read busy pin Wait for busy low
Command 0x12 [ Software reset
Read busy pin Wait for busy low
SET VOLTAGE AND LOAD LUT
LOAD IMAGE AND UPDATE
Command 0x24 5624b_tes Load ima_e_152/8*296 BW.
Command 0x20
Read busy pin Wait for busy low
Command 0x10 [ Data 0X01 Enter deep sleep mode
POWER OFF

 

 

www.good-display.com 27/34 2.66 inch series

<!-- Page 28 -->

GooDisplay GDEM0266T71WT

 

 

 

 

 

 

 

11. Reliability Test
NO Test items Test condition
| Low-Temperature T =-25°C, 240 h
Storage Test in white pattern
2 High-Temperature T=+70°C, RH=40%, 240h
Storage Test in white pattern
3 High-Temperature Operation T=+25°C, 240h
4 Low-Temperature Operation T=-25°C, 240h
5 _ | High Temperature, High T=60°C, RH=80%, 240h
Humidity Storage Test in white pattern

 

1 cycle:[-25°C 30min]—[+60 °C 30 min] : 50 cycles

6 Temperature Cycle Test in white pattern

 

Air+/-4KV;Contact+/-2KV
Contact+/-2KV(HBM C:100pF;R:1.5k ohm)
Contact+/-200V(MM C:200pF;R:0 ohm)

(Naked EPD display,including IC and FPC area)

7 ESD Gun

 

Note: 1. Stay white pattern for storage and non-operation test.
2. Operation is black-white pattern, the interval is 150s.

 

www.good-display.com 28/34 2.66 inch series

<!-- Page 29 -->

GooDisplay GDEM0266T71WT

 

12.Inspection condition
12.1 Environment

Temperature: 23+3°C
Humidity: 55+10%RH
12.2 Illuminance

Brightness: 1200~ 1500LUX;distance:20-30CM;Angle:Relate 45°surround.
12.3 Inspect method

 

TFT
12.4 Display area

Zone B

Zone A

 

 

Viewing area PPC

Ic

 

 

12.5 Ghosting test method
Two-color ghosting is measured with following transition from horizontal 2 scale pattern to vertical 2
scale pattern. The listed optical characteristics are only guaranteed under the controller & waveform

provided by DKE.

 

20min 24h

 

 

1) Measurement Instruments: X-rite ilPro

2) Ghosting formula:

W ghosting: AL= Max (4 L(W-W, B-W)) - Min (A L(W-W B-W))
K ghosting: AL= Max (A L(W-B, B-B)) - Min( A L(W-B, B-B))

 

www.good-display.com 29/34 2.66 inch series

<!-- Page 30 -->

GooDisplay GDEM0266T71WT

 

12.6 Inspection standard

12.6.1 Electric inspection standard

 

Defect

NO. Ttem Standard
level

Method Scope

 

Display complete
Display uniform

@
Black/White

2 spots Ds0.25mm, Allowed
0.25mm<D<0.4mm. Visual
N<4 allowable inspection
D=>0.4mm is not allowed

MI
el, Visual/

L<0.4mm,W<0.Imm Inspection card | Zone A
Show negligible
3 | BIW lines 0.4mm<L< 1.0mm
0.lmm<W<0.4mm
NS<4 allowable
L>1.0mm ,W>0.4mm is not
allowed

1 Display MA

 

 

 

Visual

4 Ghost image Allowed in switching process MI : .
inspection

 

Flash spots/ Flash spots in switching, Allowed

 

5 Lareer FPL size | EPL size larger than viewing area, MI Visual/ Zone A
8 Allowed Inspection card | Zone B
6 Display All appointed displays are showed
wrong/Missing | correct Visual
MA eee Zone A
inspection

 

Short circuit/
7 Circuit break/ | Not Allow
Display abnormal

 

 

www.good-display.com 30/34 2.66 inch series

<!-- Page 31 -->

GooDisplay GDEM0266T71WT

 

12.6.2 Appearance inspection standard

 

 

 

 

 

 

 

 

 

NO. Item Standard Defect Method Scope
level
a
)w
B/W spots /
Forcien bodies pees MI inspection Zone A
Dents DS0.25mm negligible Pr
0.25mm<D<0.4mm NS<4
allowable
D>0.4mm is not allowed
Zone A
2 Glass crack Not Allow MA Visual Zone B
; ; / Microscope Zone A.
3 Dirty Allowed if can be removed MI Zone B
vy
X<3mm,Y<0.5mm And without
affecting the electrode is permissible
4 Chips/Scratch/ MI Visual Zone A
Edge crown / Microscope | Zone B
2mm<X or 2mm<Y Not Allow
—~ iit
—
Leng
W<0.1mm,L<5mm, No harm to the
electrodes and NS2__ allow
7 Visual Zone A
5 TFT Cracks MA / Microscope
Zone B
Not Allow
Dirty/ foreign Visual Zone A/
body Allowed if can be removed/ allow MI / Microscope | Zone B

 

FPC broken/ Visual
isual
Goldfingers MA / Microscope Zone B

xidation/ scratch
Not Allow

 

 

www.good-display.com 31/34 2.66 inch series

<!-- Page 32 -->

GooDisplay GDEM0266T71WT

 

 

=r

L<1.0mm,W<0.15mm __ negligible

1.0mm<L<4.0mm Visual
0.15mm<W<0.S5mm MI /Ruler | 70neB
N<4 allowable

L>4.0mm ,W>0.5mm is not

allowed

8 B/W Line

 

TFT edge bulge | TFT edge bulge:
9 /TFT chromatic X<3mm, Y<0.3mm_ Allowed MI
aberration TFT chromatic aberration :Allowed
D<0.25mm, allow
: 0.25mm<D<0.4mm ,n<4 allow .
Electrostatic Visual

1 : i ve .
0 point D>0.4mm is not allowed MI | Microscope Zone A

Visual Zone A
/ Microscope | Zone B

 

(nS8 items are allowed within 5 mm
in diameter)

 

PCB (Circuit area) damaged Not

 

 

 

 

 

PCB damaged/ ATL
11 Poor welding/ ow .
Curl PCB Poor welding Not Allow
PCB Curls1%
Edge Adhesives H<PS surface MI Visual
(Including protect film) Edge / Ruler
| adhesives seep in<1/2 Margin width Zone B
12 | Edge glue height/ | [ ength excluding
Edge glue bubble | :dge adhesives bubble: bubble
Width
<1/2 Margin width; Length
<0.5mm. n<5
B Protect film A scratch but not effect protect Visual
function, Allowed Inspection
Thickness <PS surface(With protect film):
Full cover the IC;
A Shape: Visual
14 Silicon glue | The width on the FPC < 0.5mm (Front)| MI Inspection
The width on the FPC<1.0mm (Back)
smooth surface, No obvious raised.
FPL
Warp degree cs 4
1S | (TET substrate) | —S> t MI Ruler
TFT
t=10mm
Color difference
in COM area Visual
16 (Silver point Allowed Inspection

area)

 

 

www.good-display.com 32/34 2.66 inch series

<!-- Page 33 -->

GooDisplay GDEM0266171WT

 

13. Handling, Safety and Environment Requirements

 

Warning

 

The display glass may break when it is dropped or bumped on a hard surface. Handle with
care. Should the display break, do not touch the electrophoretic material. In case of contact with
electrophoretic material, wash with water and soap.

 

Caution

 

The display module should not be exposed to harmful gases, such as
aalkaligases,whichcorrodeelectronic components. Disassembling the display module.

Disassembling the display module can cause permanent damage and invalidates the warranty
agreements.

Observe general precautions that are‘common to handling delicate electronic components. The glass
can break and front surfaces can easily be damaged. Moreover the display is sensitive to static
electricity and other rough environmental conditions.

 

Data sheet status

 

Product specification This data sheet contains final product specifications.

 

Limiting values

 

Limiting values given are in accordance with the Absolute Maximum Rating System (IEC
134).Stress above one or more of the limiting values may cause permanent damage to the device.
These are stress ratings only and operation of the device at these or at any other conditions above
those given in the Characteristics sections of the specification is not implied. Exposure to limiting
values for extended periods may affect device reliability.

 

Application information

 

Where application information is given, it is advisory and does not form part of the specification.

 

 

www.good-display.com 33/34 2.66 inch series

<!-- Page 34 -->

GooDisplay GDEM0266T71WT

 

14. Packaging

EPD PACKING INSTRUCTION

DKE-QS. D-010

 

P/N Customer Code Ref. P/N Type | PKG Method | Marking Surface Marks Pull Tape
GLASS Blister BACK None YES:

 

 

 

Packing Materials List 18PCS/LAYER, 20LAYER/CTN, TOTAL 360PCS/CTN.
List Model Materials Q'ty Unie Pull tape:
Carton 7# 417%362#229 mm |corrugate’ 1 | Piece
Inner Carton 7#(INVER) 4008243 #95 nm corrugate) 2 | Piece a =
Blister PET 22 Piece
Thin foam | 270. 46%267.94"(TL. 5-1.8)mm — EPE 20 Piece
mnie 150959040. 075 2 | Piece
Foam board EPE 3 Piece
PULL TAPE 16#5%*T0. 05 360 Piece
Detail:
. . The blister box is rotated
Blister box for placement
Note: there are 20 layers of products, ba Mir ister 7 sisi
divided into 2 inner boxes, and an empty Thin foam = vacuum bag
blister box is placed on the top of each Blister €
inner box, so the number of blister boxes N YA
is 22 Pex boerd aed with rubber band
For 1 1sto 7e IER cARTON
(es ee ee OE INNER BOX LABEL A+
~ > Wa
a0 0007000 1 ( ¢ Va ance cao
$ a :

   
    

PUT THO 7H OER CARTON
Ifo Te carton

  

Cone
p00

Erni
ps

 

7 carton

Packing belt

oouo%

Ar rear

QUANTITY: 18PCS a>

 

 

 

 

 

www.good-display.com 34/34 2.66 inch series

---

# PART II — BOM PART DATASHEETS

# BOM Part Datasheets — Combined Reference

_Compiled 2026-07-31. Full-text extraction of the component (BOM) datasheets. Several JLCPCB part numbers share one generic manufacturer catalog (all resistors, all MLCCs) — these are deduplicated below and the covered parts are listed together. Files marked (OCR) were image-based and machine-read._

## Coverage vs. BOM table

| Part / role | JLCPCB | Value | Datasheet present? |
|---|---|---|---|
| MCU ESP32-C3-MINI-1-N4 | C2838502 | — | Yes — in first combined file (esp32-c3-mini-1) |
| Charger MCP73871-2CC | C5121473 | — | Yes |
| Gauge MAX17048G+T10 | C2682616 | — | Yes |
| USB-C TYPE-C-31-M-12 | C165948 | — | Yes (OCR) |
| FPC AFC07-S24ECA-00 | C262643 | — | Yes |
| Regulator AP2112K-3.3 | C51118 | — | Yes |
| NFC NT3H2111W0FHKH | C710403 | — | Yes (file named by part) |
| Resistor 10k | C17414 | 10k | Yes |
| Resistor 0 | C21189 | 0 | Yes |
| Resistor 5.1K | C23186 | 5.1K | **No separate file** — same Uniroyal catalog as C17414 |
| Resistor 3.3K | C22978 | 3.3K | **No separate file** — same Uniroyal catalog as C17414 |
| Resistor 24K | C23352 | 24K | Yes |
| Resistor 470 | C23179 | 470 | Yes |
| Resistor 2.2 | C17521 | 2.2 | Yes |
| Cap 0.1uF | C28233 | 0.1uF | Yes |
| Cap 10uF | C19702 | 10uF | Yes |
| Cap 1uF | C28323 | 1uF | Yes |
| Cap 4.7uF | C19666 | 4.7uF | Yes |
| Cap 220nF | C21120 | 220nF | Yes |
| Cap TBD (C14) | C1653 | TBD | Yes |
| Cap 1uF X5R | C15849 | 1uF X5R | Yes |
| LED red D2/D3/D4 | C2286 | RED | Yes |
| NMOS SI1304BDL | C7419947 | — | Yes (OCR) |
| Inductor CDRH2D18 | C2454210 | 47µH | Yes |
| Schottky MBR0530 (×3) | C77336 | — | Yes |
| Tactile SW-01/SW-02 | C720477 | — | Yes (OCR) |

**Missing files:** `C23186` (5.1K) and `C22978` (3.3K) — but both are the *same* Uniroyal thick-film chip-resistor catalog already included via C17414, so the datasheet content is effectively covered; you only lack the JLC-specific PDFs.

## Contents

1. MCP73871 — Li-Ion/Li-Po Charge Management + Load Sharing
2. MAX17048/MAX17049 — Fuel Gauge
3. AP2112 — 600mA CMOS LDO Regulator
4. NT3H2111/2211 — NTAG I2C plus (NFC)
5. AFC07-S24ECA-00 — 24-pin FPC Connector
6. TYPE-C-31-M-12 — USB-C Receptacle (OCR)
7. SI1304BDL — N-Channel MOSFET (OCR)
8. CDRH2D18/LD — SMD Power Inductor
9. MBR0530 — Schottky Barrier Diode
10. 0603 Red LED — Kuangtong (approval doc)
11. Tactile Switch SW-01/SW-02 (OCR)
12. Uniroyal Thick Film Chip Resistors (0805) — generic catalog
13. Uniroyal Thick Film Chip Resistors — 0-ohm jumper
14. MLCC Capacitor Catalog — generic (0805 X5R/X7R)


---

# 1. MCP73871 — Li-Ion/Li-Po Charge Management + Load Sharing

> **Role:** Charger — MCP73871-2CC  
> **Covers:** `C5121473` (Charger)

<!-- Page 1 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 1
MCP73871
Features
• Integrated System Load Sharing and Battery
Charge Management
- Simultaneously Power the System and
Charge the Li-Ion Battery
- Voltage Proportional Current Control (VPCC)
ensures system load has priority over Li-Ion
battery charge current
- Low-Loss Power-Path Management with
Ideal Diode Operation
• Complete Linear Charge Management Controller
- Integrated Pass Transistors
- Integrated Current Sense
- Integrated Reverse Discharge Protection
- Selectable Input Power Sources: USB Port or
AC-DC Wall Adapter
• Preset High Accuracy Charge Voltage Options:
- 4.10V, 4.20V, 4.35V or 4.40V
- ±0.5% Regulation Tolerance
• Constant Current/Constant Voltage (CC/CV)
Operation with Thermal Regulation
• Maximum 1.8A Total Input Current Control
• Resistor Programmable Fast Charge Current
Control: 50 mA to 1A
• Resistor Programmable Termination Set Point
• Selectable USB Input Current Control
- Absolute Maximum: 100 mA (L)/500 mA (H)
• Automatic Recharge
• Automatic End-of-Charge Control
• Safety Timer With Timer Enable/Disable Control
• 0.1C Preconditioning for Deeply Depleted Cells
• Battery Cell Temperature Monitor
• Undervoltage Lockout (UVLO)
• Low Battery Status Indicator (LBO)
• Power Good Status Indicator (PG)
• Charge Status and Fault Condition Indicators
• Numerous Selectable Options Available for a
Variety of Applications:
- Refer to Section 1.0 “Electrical
Characteristics” for Selectable Options
- Refer to the Product Identification System
for Standard Options
• Temperature Range: -40°C to +85°C
• Packaging: 20-Lead QFN (4 mm x 4 mm)
Applications
• GPSs/Navigators
• PDAs and Smart Phones
• Portable Media Players and MP3 Players
• Digital Cameras
• Bluetooth® Headsets
• Portable Medical Devices
• Charge Cradles/Docking Stations
• Toys
Description
The MCP73871 device is a fully integrated linear
solution for system load sharing and Li-Ion/Li-Polymer
battery charge management with AC-DC wall adapter
and USB port power sources selection. It is also
capable of autonomous power source selection
between input and battery. Along with its small physical
size, the low number of required external components
makes
the
device
ideally
suited
for
portable
applications.
The MCP73871 device automatically obtains power for
the system load from a single-cell Li-Ion battery or an
input power source (AC-DC wall adapter or USB port).
The MCP73871 device specifically adheres to the
current drawn limits governed by the USB specification.
With an AC-DC wall adapter providing power to the
system, an external resistor sets the magnitude of 1A
maximum charge current while supporting up to 1.8A
total current for system load and battery charge
current.
The
MCP73871
device
employs
a
constant
current/constant voltage (CC/CV) charge algorithm
with
selectable
charge
termination
point.
To
accommodate new and emerging battery charging
requirements, the constant voltage regulation is fixed
with four available options: 4.10V, 4.20V, 4.35V or
4.40V. The MCP73871 device also limits the charge
current based on the die temperature during high
power or high ambient conditions. This thermal
regulation optimizes the charge cycle time while
maintaining device reliability.
The MCP73871 device includes a low battery indicator,
a power good indicator and two charge status
indicators that allow for outputs with LEDs or
communication
with
host
microcontrollers.
The
MCP73871 device is fully specified over the ambient
temperature range of -40°C to +85°C.
Stand-Alone System Load Sharing and Li-Ion/Li-Polymer Battery Charge
Management Controller

<!-- Page 2 -->

MCP73871
DS20002090F-page 2
 2008-2022 Microchip Technology Inc. and its subsidiaries
Package Types
Typical Application Circuit
IN
 STAT1/LBO
PG
THERM
STAT2
PROG1
IN
OUT
OUT
CE
SEL
PROG3
TE
VBAT
VBAT
VPCC
VSS
VSS
VBAT_SENSE
2
EP
20
1
19 18 17
3
4
12
11
10
9
5
6
7
8
13
14
15
16
21
PROG2
MCP73871
20-Lead QFN*
* Includes Exposed Thermal Pad (EP); see Table 3-1.
STAT1
LBO
IN
OUT
PG
VBAT
Single-Cell
Li-Ion Battery
7
1, 20
8
18, 19
10 µF
10, 11, EP
AC-DC Adapter
         or
    USB Port
STAT2
THERM
VSS
PROG1
PROG3 12
13 RPROG1
6
5
14, 15, 16
470
470
470
2
4.7 µF
System
Load
SEL
TE
PROG2
Hi
Low
Hi
Low
Hi
Low
3
4
9
RPROG3
VPCC
NTC
10 k
Hi
Low
17 CE
4.7 µF
MCP73871 Typical Application

<!-- Page 3 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 3
MCP73871
Functional Block Diagram
STAT1
PROG1
VBAT
G = 0.001
VSS
Direction
Control
TERM
+
-
+
-
LTVT
+
-
HTVT
THERM
50 µA
UVLO,
REFERENCE,
CHARGE
CONTROL,
TIMER,
AND
STATUS
LOGIC
STAT2
PG
Direction
Control
PROG2
IN
+
-
CURRENT
LIMIT
VREF
+
-
CURRENT
LIMIT
VREF/2

PROG3
+
-
CA
VREF
PRECONDITION
+
-
VREF
+
-
VA
VREF
VREF
SEL
OUT
VREF
TE
0.2
0.2
Ideal
Diode,
Synchronous
Switch
CHRG
+
-
VREF
+
-
VREF
VPCC
CE
VBAT_SENSE
G = 0.001
G = 0.001
G = 0.001
VREF (1.21V)
361k
190k
7k
89k

<!-- Page 4 -->

MCP73871
DS20002090F-page 4
 2008-2022 Microchip Technology Inc. and its subsidiaries
1.0
ELECTRICAL CHARACTERISTICS
Absolute Maximum Ratings(†)
VIN.....................................................................................................................................................................................................7.0V
All Inputs and Outputs w.r.t. .................................................................................................................................VSS–0.3V to VDD+0.3V
(VDD = VIN or VBAT)
Maximum Junction Temperature, TJ ............................................................................................................................. Internally Limited
Storage temperature ..................................................................................................................................................... –65°C to +150°C
ESD protection on all pins
Human Body Model (1.5 k in Series with 100 pF)4 kV
Machine Model (200 pF, No Series Resistance)..............................................................................................................................300V
†
Notice: Stresses above those listed under “Maximum Ratings” may cause permanent damage to the
device. This is a stress rating only and functional operation of the device at those or any other conditions
above those indicated in the operational listings of this specification is not implied. Exposure to maximum
rating conditions for extended periods may affect device reliability.
DC CHARACTERISTICS
Electrical Specifications: Unless otherwise indicated, all limits apply for VIN = VREG + 0.3V to 6V, TA = -40°C to +85°C.
Typical values are at +25°C, VIN = [VREG (typical) + 1.0V]
Parameters
Sym
Min
Typ
Max
Units
Conditions
Supply Input
Supply Voltage
VIN
VREG + 0.3V
—
6
V
Supply Current
ISS
—
2500
3750
µA
Charging
—
260
350
µA
Charge Complete
—
180
300
µA
Standby
—
28
50
µA
Shutdown
(VDD < VBAT – 100 mV or
VDD < VSTOP)
UVLO Start Threshold
VSTART
VREG + 0.05V
VREG + 0.15V
VREG + 0.25V
V
VDD = Low-to-High
UVLO Stop Threshold
VSTOP
VREG – 0.07V
VREG + 0.07V
VREG + 0.17V
V
VDD = High-to-Low
UVLO Hysteresis
VHYS
—
90
—
mV
Voltage Regulation (Constant Voltage Mode)
Regulated
Charge Voltage
VREG
4.080
4.10
4.121
V
VDD = [VREG(typical) + 1V]
IOUT = 10 mA
TA = -5°C to +55°C
4.179
4.20
4.221
V
4.328
4.35
4.372
V
4.378
4.40
4.422
V
Regulated Charge
Voltage Tolerance
VRTOL
–0.5
—
+0.5
%
TA = +25°C
–0.75
—
+0.75
%
TA = -5°C to +55°C
Line Regulation
VBAT/VBAT)
/
VDD|
—
0.08
0.20
%/V
VDD = [VREG(typical) + 1V] to 6V
IOUT = 10 mA
Load Regulation
VBAT/VBAT|
—
0.08
0.18
%
IOUT = 10 mA to 150 mA
VDD = [VREG(typical) + 1V]
Supply Ripple
Attenuation
PSRR
—
-47
—
dB
IOUT = 10 mA, 1 kHz
—
-40
—
dB
IOUT = 10 mA, 10 kHz
Note
1:
The value is ensured by design and not production tested.
2:
The maximum available charge current is also limited by the value set at PROG1 input.

<!-- Page 5 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 5
MCP73871
Current Regulation (Fast Charge Constant Current Mode)
AC-Adapter
Fast Charge
Current
IREG
90
100
110
mA
PROG1 = 10 k
TA = -5°C to +55°C, SEL = High
900
1000
1100
mA
PROG1 = 1 k
TA = -5°C to +55°C, SEL = High
USB Fast Charge
Current
IREG
80
90
100
mA
PROG2 = Low, SEL = Low,
(Note 2)
TA = -5°C to +55°C
400
450
500
mA
PROG2 = High, SEL = Low,
(Note 2)
TA = -5°C to +55°C
Input Current Limit Control (ICLC)
USB-Port Supply
Current Limit
ILIMIT_USB
80
90
100
mA
PROG2 = Low, SEL = Low
TA = -5°C to +55°C
400
450
500
mA
PROG2 = High, SEL = Low
TA = -5°C to +55°C
AC-DC Adapter Current
Limit
ILIMIT_AC
1500
1650
1800
mA
SEL = High, TA = -5°C to +55°C
Voltage Proportional Charge Control (VPCC - Input Voltage Regulation)
VPCC Input Threshold
VVPCC
—
1.23
—
V
IOUT = 10 mA
TA = -5°C to +55°C
VPCC Input Threshold
Tolerance
VRTOL
–3
—
+3
%
Input Leakage Current
ILK
—
0.01
1
µA
VVPCC = VDD
Precondition Current Regulation (Trickle Charge Constant Current Mode)
Precondition Current
Ratio
IPREG/IREG
7.5
10
12.5
%
PROG1 = 1.0 k to 10 k
TA = -5°C to +55°C
Precondition Current
Threshold Ratio
VPTH/VREG
69
72
75
%
VBAT Low-to-High
Precondition Hysteresis
VPHYS
—
105
—
mV
VBAT High-to-Low
Automatic Charge Termination Set Point
Charge Termination
Current Ratio
ITERM
75
100
125
mA
PROG3 = 10 k
TA = -5°C to +55°C
7.5
10
12.5
mA
PROG3 = 100 k
TA = -5°C to +55°C
Automatic Recharge
Recharge Voltage
Threshold Ratio
VRTH
VREG – 0.21V
VREG – 0.15V
VREG – 0.09V
V
VBAT High-to-Low
IN-to-OUT Pass Transistor ON-Resistance
ON-Resistance
RDS_ON
—
200
—
m
VDD = 4.5V, TJ = 105°C
Charge Transistor ON-Resistance
DC CHARACTERISTICS (CONTINUED)
Electrical Specifications: Unless otherwise indicated, all limits apply for VIN = VREG + 0.3V to 6V, TA = -40°C to +85°C.
Typical values are at +25°C, VIN = [VREG (typical) + 1.0V]
Parameters
Sym
Min
Typ
Max
Units
Conditions
Note
1:
The value is ensured by design and not production tested.
2:
The maximum available charge current is also limited by the value set at PROG1 input.

<!-- Page 6 -->

MCP73871
DS20002090F-page 6
 2008-2022 Microchip Technology Inc. and its subsidiaries
ON-Resistance
RDSON_
—
200
—
m
VDD = 4.5V, TJ = 105°C
BAT-to-OUT Pass Transistor ON-Resistance
ON-Resistance
RDS_ON
—
200
—
m
VDD = 4.5V, TJ = 105°C
Battery Discharge Current
Output Reverse
Leakage Current
IDISCHARGE
—
30
40
µA
Shutdown
(VBAT < VDD < VUVLO)
—
30
40
µA
Shutdown (0 < VDD < VBAT)
—
30
40
µA
VBAT = Power Out, No Load
—
–6
–13
µA
Charge Complete
Status Indicators - STAT1 (LBO), STAT2, PG
Sink Current
ISINK
—
16
35
mA
Low Output Voltage
VOL
—
0.4
1
V
ISINK = 4 mA
Input Leakage Current
ILK
—
0.01
1
µA
High Impedance, VDD on pin
Low Battery Indicator (LBO)
Low Battery Detection
Threshold
VLBO
—
Disable
—
VBAT > VIN, PG = High-Z
TA = -5°C to +55°C
2.85
3.0
3.15
V
2.95
3.1
3.25
V
3.05
3.2
3.35
V
Low Battery Detection
Hysteresis
VLBO_HYS
—
150
—
mV
VBAT Low-to-High
PROG1 Input (PROG1)
Charge Impedance
Range
RPROG
1
—
20
k
PROG3 Input (PROG3)
Termination Impedance
Range
RPROG
5
—
100
k
PROG2 Input (PROG2)
Input High Voltage Level
VIH
1.8
—
—
V
Input Low Voltage Level
VIL
—
—
0.8
V
Input Leakage Current
ILK
—
0.01
1
µA
VPROG2 = VDD
Timer Enable (TE)
Input High Voltage Level
VIH
1.8
—
—
V
Note 1
Input Low Voltage Level
VIL
—
—
0.8
V
Note 1
Input Leakage Current
ILK
—
0.01
1
µA
VTE = VDD
DC CHARACTERISTICS (CONTINUED)
Electrical Specifications: Unless otherwise indicated, all limits apply for VIN = VREG + 0.3V to 6V, TA = -40°C to +85°C.
Typical values are at +25°C, VIN = [VREG (typical) + 1.0V]
Parameters
Sym
Min
Typ
Max
Units
Conditions
Note
1:
The value is ensured by design and not production tested.
2:
The maximum available charge current is also limited by the value set at PROG1 input.

<!-- Page 7 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 7
MCP73871
Chip Enable (CE)
Input High Voltage Level
VIH
1.8
—
—
V
Input Low Voltage Level
VIL
—
—
0.8
V
Input Leakage Current
ILK
—
0.01
1
µA
VCE = VDD
Input Source Selection (SEL)
Input High Voltage Level
VIH
1.8
—
—
V
Input Low Voltage Level
VIL
—
—
0.8
V
Input Leakage Current
ILK
—
0.01
1
µA
VSEL = VDD
Thermistor Bias
Thermistor Current
Source
ITHERM
47
50
53
µA
2 k< RTHERM < 50 k
Thermistor Comparator
Upper Trip Threshold
VT1
1.20
1.24
1.26
V
VT1 Low-to-High
Upper Trip Point
Hysteresis
VT1HYS
—
-40
—
mV
Lower Trip Threshold
VT2
0.23
0.25
0.27
V
VT2 High-to-Low
Lower Trip Point
Hysteresis
VT2HYS
—
40
—
mV
Thermal Shutdown
Die Temperature
TSD
—
150
—
C
Die Temperature
Hysteresis
TSDHYS
—
10
—
C
DC CHARACTERISTICS (CONTINUED)
Electrical Specifications: Unless otherwise indicated, all limits apply for VIN = VREG + 0.3V to 6V, TA = -40°C to +85°C.
Typical values are at +25°C, VIN = [VREG (typical) + 1.0V]
Parameters
Sym
Min
Typ
Max
Units
Conditions
Note
1:
The value is ensured by design and not production tested.
2:
The maximum available charge current is also limited by the value set at PROG1 input.

<!-- Page 8 -->

MCP73871
DS20002090F-page 8
 2008-2022 Microchip Technology Inc. and its subsidiaries
AC CHARACTERISTICS
Electrical Specifications: Unless otherwise indicated, all limits apply for VIN = 4.6V to 6V.
Typical values are at +25°C, VDD = [VREG (typical) + 1.0V]
Parameters
Sym
Min
Typ
Max
Units
Conditions
UVLO Start Delay
tSTART
—
—
5
ms
VDD Low-to-High
Current Regulation
Transition Time Out of Precondition
tDELAY
—
—
10
ms
VBAT < VPTH to VBAT > VPTH
Current Rise Time Out of Precondition
tRISE
—
—
10
ms
IOUT Rising to 90% of IREG
Precondition Comparator Filter Time
tPRECON
0.4
1.3
3.2
ms
Average VBAT Rise/Fall
Termination Comparator Filter Time
tTERM
0.4
1.3
3.2
ms
Average IOUT Falling
Charge Comparator Filter Time
tCHARGE
0.4
1.3
3.2
ms
Average VBAT Falling
Thermistor Comparator Filter Time
tTHERM
0.4
1.3
3.2
ms
Average THERM Rise/Fall
Elapsed Timer
Elapsed Timer Period
tELAPSED
—
0
—
Hours
3.6
4.0
4.4
Hours
5.4
6.0
6.6
Hours
7.2
8.0
8.8
Hours
Status Indicators
Status Output Turn-off
tOFF
—
—
500
µs
ISINK = 1 mA to 0 mA
Status Output Turn-on
tON
—
—
500
µs
ISINK = 0 mA to 1 mA
Note
1:
Internal safety timer is tested based on internal oscillator frequency measurement.
TEMPERATURE SPECIFICATIONS
Electrical Specifications: Unless otherwise indicated, all limits apply for VIN = 4.6V to 6V.
Typical values are at +25°C, VDD = [VREG (typical) + 1.0V]
Parameters
Sym
Min
Typ
Max
Units
Conditions
Temperature Ranges
Specified Temperature Range
TA
-40
—
+85
°C
Operating Temperature Range
TJ
-40
—
+125
°C
Storage Temperature Range
TA
-65
—
+150
°C
Thermal Package Resistances
Thermal Resistance, 20LD-QFN, 4x4
JA
—
50
—
°C/W
4-Layer JC51-7 Standard Board,
Natural Convection
JC
—
8
—
—

<!-- Page 9 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 9
MCP73871
2.0
TYPICAL PERFORMANCE CURVES
Note: Unless otherwise indicated, VIN = [VREG(typical) + 1V], IOUT = 10 mA and TA = +25°C, Constant Voltage mode.
FIGURE 2-1:
Battery Regulation Voltage
(VBAT) vs. Supply Voltage (VDD).
FIGURE 2-2:
Battery Regulation Voltage
(VBAT) vs. Ambient Temperature (TA).
FIGURE 2-3:
Charge Current (IOUT) vs.
Programming Resistor (RPROG).
FIGURE 2-4:
Charge Current (IOUT) vs.
Battery Regulation Voltage (VBAT).
FIGURE 2-5:
Output Leakage Current
(IDISCHARGE) vs. Ambient Temperature (TA).
FIGURE 2-6:
Output Leakage Current
(IDISCHARGE) vs. Battery Regulation Voltage
(VBAT).
Note:
The graphs and tables provided following this note are a statistical summary based on a limited number of
samples and are provided for informational purposes only. The performance characteristics listed herein
are not tested or guaranteed. In some graphs or tables, the data presented may be outside the specified
operating range (e.g., outside specified power supply range) and therefore outside the warranted range.
4.176
4.184
4.192
4.200
4.208
4.216
4.224
4.232
4.240
4.6
4.9
5.1
5.4
5.6
5.9
Supply Voltage (V)
Battery Regulation Voltage (V)
Temperature = +25°C
IOUT= 100 mA
IOUT= 500 mA
IOUT= 900 mA
IOUT= 10 mA
4.190
4.198
4.206
4.214
4.222
4.230
4.238
-45
-30
-15
0
15
30
45
60
75
90
Ambient Temperature (°C)
Battery Regulation Voltage (V)
IOUT = 10 mA
IOUT = 100 mA
IOUT = 500 mA
IOUT = 1000 mA
0
100
200
300
400
500
600
700
800
900
1000
1 2 3 4 5 6 7 8 9 1011121314151617181920
RPROG (kΩ)
IREG (mA)
VDD= 5.2V
Temperature = +25°C
4.100
4.120
4.140
4.160
4.180
4.200
4.220
4.240
4.260
4.280
4.300
0
100
200
300
400
500
600
700
800
900
1000
Charge Current (mA)
Battery Regulation Voltage
(V)
Temperature = +25°C
VDD = 5.2V
10.0
15.0
20.0
25.0
30.0
35.0
40.0
-45
-30
-15
0
15
30
45
60
75
90
Temperature (°C)
Battery Discharge Current
(µA)
VBAT = 4.2V
VDD= Floating
0.0
5.0
10.0
15.0
20.0
25.0
30.0
35.0
3.0
3.2
3.4
3.6
3.8
4.0
4.2
Battery Voltage (V)
Battery Discharge Current
(µA)
VDD= VBAT
Temperature = +25°C

<!-- Page 10 -->

MCP73871
DS20002090F-page 10
 2008-2022 Microchip Technology Inc. and its subsidiaries
Note: Unless otherwise indicated, VIN = [VREG(typical) + 1V], IOUT = 10 mA and TA = +25°C, Constant Voltage mode.
FIGURE 2-7:
Output Leakage Current
(IDISCHARGE) vs. Battery Voltage (VBAT).
FIGURE 2-8:
Charge Current (IOUT) vs.
Supply Voltage (VDD).
FIGURE 2-9:
Charge Current (IOUT) vs.
Supply Voltage (VDD).
FIGURE 2-10:
Charge Current (IOUT) vs.
Supply Voltage (VDD).
FIGURE 2-11:
Charge Current (IOUT) vs.
Ambient Temperature (TA).
FIGURE 2-12:
Charge Current (IOUT) vs.
Ambient Temperature (TA).
0.0
5.0
10.0
15.0
20.0
25.0
30.0
35.0
3.0
3.2
3.4
3.6
3.8
4.0
4.2
Battery Voltage (V)
Battery Discharge Current
(µA)
VDD= Floating
Temperature = +25°C
800
830
860
890
920
950
980
1010
1040
1070
1100
1130
1160
1190
4.5
4.8
5.0
5.3
5.5
5.8
6.0
Supply Voltage (V)
IREG (mA)
RPROG = 1 kΩ
Temperature = +25°C
450
460
470
480
490
500
510
520
530
540
550
4.5
4.8
5.0
5.3
5.5
5.8
6.0
Supply Voltage (V)
IREG (mA)
RPROG = 2 kΩ
Temperature = +25°C
90
92
94
96
98
100
102
104
106
108
110
4.5
4.8
5.0
5.3
5.5
5.8
6.0
Supply Voltage (V)
IREG (mA)
RPROG = 10 kΩ
Temperature = +25°C
700
740
780
820
860
900
940
980
1020
1060
1100
-45
-30
-15
0
15
30
45
60
75
90
Ambient Temperature (°C)
Charge Current (mA)
RPROG = 1 kΩ
VDD = 5.2V
90
92
94
96
98
100
102
104
106
108
110
-45
-30
-15
0
15
30
45
60
75
90
Ambient Temperature (°C)
Charge Current (mA)
RPROG = 10 kΩ
VDD = 5.2V

<!-- Page 11 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 11
MCP73871
Note: Unless otherwise indicated, VIN = [VREG(typical) + 1V], IOUT = 10 mA and TA = +25°C, Constant Voltage mode.
FIGURE 2-13:
Charge Current (IOUT) vs.
Ambient Temperature (TA).
FIGURE 2-14:
Charge Current (IOUT) vs.
Junction Temperature (TJ).
FIGURE 2-15:
Charge Current (IOUT) vs.
Junction Temperature (TJ).
FIGURE 2-16:
Charge Current (IOUT) vs.
Junction Temperature (TJ).
FIGURE 2-17:
Thermistor Current (ITHERM)
vs. Supply Voltage (VDD).
FIGURE 2-18:
Thermistor Current (ITHERM)
vs. Ambient Temperature (TA).
41
43
45
47
49
51
53
55
-45
-30
-15
0
15
30
45
60
75
90
Ambient Temperature (°C)
Charge Current (mA)
RPROG = 20 kΩ
VDD = 5.2V
0
200
400
600
800
1000
1200
25
50
75
100
125
150
Charge Current (mA)
Ambient Temperature (°C)
VDD = 5.2V
RPROG = 1 kȍ
0
100
200
300
400
500
600
25
50
75
100
125
150
Charge Current (mA)
Ambient Temperature (°C)
VDD = 5.2V
RPROG = 2 kȍ
0
20
40
60
80
100
120
25
50
75
100
125
150
Charge Current (mA)
Ambient Temperature (°C)
VDD = 5.2V
RPROG = 10 kȍ
47.0
47.5
48.0
48.5
49.0
49.5
50.0
50.5
51.0
51.5
52.0
4.6
4.8
5.0
5.2
5.4
5.6
5.8
6.0
Supply Voltage (V)
Thermistor Current (µA)
Temperature = +25°C
47.0
47.5
48.0
48.5
49.0
49.5
50.0
50.5
51.0
51.5
52.0
-45
-30
-15
0
15
30
45
60
75
90
Ambient Temperature (°C)
Thermistor Current (µA)
VDD = 5.2V

<!-- Page 12 -->

MCP73871
DS20002090F-page 12
 2008-2022 Microchip Technology Inc. and its subsidiaries
Note: Unless otherwise indicated, VIN = [VREG(typical) + 1V], IOUT = 10 mA and TA = +25°C, Constant Voltage mode.
FIGURE 2-19:
Power Supply Ripple
Rejection (PSRR).

FIGURE 2-20:
 Line Transient Response.
IOUT = 100 mA.

FIGURE 2-21:
 Line Transient Response.
IOUT = 500 mA.

FIGURE 2-22:
Load Transient Response.
IOUT = 100 mA.

FIGURE 2-23:
Load Transient Response.
IOUT = 500 mA.
FIGURE 2-24:
Undervoltage Lockout.
-60
-50
-40
-30
-20
-10
0
0.01
0.1
1
10
100
1000
Frequency (kHz)
PSRR (dB)
IOUT = 10 mA
4.5
5
5.5
6
6.5
7
7.5
8
8.5
9
-0.0008 -0.0006 -0.0004 -0.0002
0
0.0002
Time (s)
Output Voltage (V)
-0.7
-0.5
-0.3
-0.1
0.1
0.3
Output Current (A)
IOUT = 100 mA
4
4.5
5
5.5
6
6.5
7
7.5
8
8.5
9
-0.0008 -0.0006 -0.0004 -0.0002
0
0.0002
Time (s)
Output Voltage (V)
0
0.1
0.2
0.3
0.4
0.5
0.6
0.7
Output Current (A)
IOUT = 500 mA
-0.2
0
0.2
0.4
0.6
0.8
1
1.2
1.4
1.6
1.8
-0.001
0
0.001
0.002
0.003
0.004
Time (s)
Output Current (A)
-0.5
-0.4
-0.3
-0.2
-0.1
0
0.1
0.2
Output Ripple (V)
IOUT = 100 mA
-0.2
0
0.2
0.4
0.6
0.8
1
1.2
1.4
1.6
1.8
0.00075
0.00115
0.00155
0.00195
0.00235
0.00275
Time (s)
Output Current (A)
-0.5
-0.4
-0.3
-0.2
-0.1
0
0.1
0.2
Output Ripple (V)
IOUT = 500 mA
Input Voltage (V)
UVLO (V)
Time (ms)

<!-- Page 13 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 13
MCP73871
Note: Unless otherwise indicated, VIN = [VREG(typical) + 1V], IOUT = 10 mA and TA = +25°C, Constant Voltage mode.
FIGURE 2-25:
Start-Up Delay.
FIGURE 2-26:
Start Charge Cycle
(130 mAh Li-Ion Battery).
FIGURE 2-27:
Complete Charge Cycle
(130 mAh Li-Ion Battery).
FIGURE 2-28:
Complete Charge Cycle
(1000 mAh Li-Ion Battery).

FIGURE 2-29:
Typical Charge Profile in
Preconditioning (1000 mAh Battery).
Input Voltage (V)
Startup Voltage (V)
Time (ms)
0
0.5
1
1.5
2
2.5
3
3.5
4
4.5
0
0.1
0.2
0.3
0.4
0.5
Time (Minutes)
Charge Voltage (V)
0
0.1
0.2
0.3
0.4
0.5
Charge Current (A)
MCP73871
VDD = 5.2V
SEL = Low
PROG2 = Low
0
0.5
1
1.5
2
2.5
3
3.5
4
4.5
0
7
14
21
28
35
42
49
56
63
Time (Minutes)
Charge Voltage (V)
0
0.1
0.2
0.3
0.4
0.5
Charge Current (A)
MCP73871
VDD = 5.2V
SEL = Low
PROG2 = Low
0
0.5
1
1.5
2
2.5
3
3.5
4
4.5
0
10
20
30
40
50
60
70
80
Time (Minute)
Charge Voltage (V)
0
0.2
0.4
0.6
0.8
1
1.2
1.4
1.6
1.8
2
Charge Current (A)
MCP73871
VDD = 5.2V
RPROG1 = 1 kΩ
RPROG3 = 25 kΩ
0
0.5
1
1.5
2
2.5
3
3.5
4
4.5
0
0.2
0.4
0.6
0.8
1
Time (Minute)
Charge Voltage (V)
0
0.2
0.4
0.6
0.8
1
1.2
1.4
1.6
1.8
2
Charge Current (A)
Preconditioning
Preconditioning Threshold Voltage
Fast Charge (Constant Current)
MCP73871
VDD = 5.2V
RPROG1 = 1 kΩ
RPROG3 = 25 kΩ

<!-- Page 14 -->

MCP73871
DS20002090F-page 14
 2008-2022 Microchip Technology Inc. and its subsidiaries
3.0
PIN DESCRIPTION
The descriptions of the pins are listed in Table 3-1.
3.1
Power Supply Input (IN - also
referred to as VIN)
A
supply
voltage
of
VREG + 0.3V
to
6V
is
recommended. Bypass to VSS with a minimum of
4.7 µF.
3.2
System Output Terminal (OUT -
also referred to as VOUT)
The MCP73871 device powers the system via output
terminals while independently charging the battery.
This feature reduces the charge and discharge cycles
on the battery, allowing proper charge termination and
the system to run with an absent or defective battery
pack. It also gives the system priority on input power,
allowing the system to power-up with deeply depleted
battery packs. Bypass to VSS with a minimum of 4.7 µF
is recommended.
3.3
Voltage Proportional Charge
Control (VPCC)
If the voltage on the IN pin drops to a preset value
determined by the threshold established at the VPCC
input due to a limited amount of input current or input
source impedance, the battery charging current is
reduced. If possible, further demand from the system is
supported by the battery. To enable this feature, simply
supply 1.23V or greater to the VPCC pin. This feature
can be disabled by connecting the VPCC pin to IN.
For example, a system is designed with a 5.5V rated
DC power supply with ±0.5V tolerance. The worst
condition of 5V is selected, which is used to calculate
the VPCC supply voltage with divider.
TABLE 3-1:
PIN FUNCTION TABLE
Pin
Number
Symbol
I/O
Function
1, 20
OUT
O
System Output Terminal
2
VPCC
I
Voltage proportional charge control
3
SEL
I
Input type selection (low for USB port, high for AC-DC adapter)
4
PROG2
I
USB port input current limit selection when SEL = Low
(Low = 100 mA, High = 500 mA)
5
THERM
I/O
Thermistor monitoring input and bias current
6
PG
O
Power Good Status Output (Open-Drain)
7
STAT2
O
Charge Status Output 2 (Open-Drain)
8
STAT1/LBO
O
Charge Status Output 1 (Open-Drain). Low battery output indicator when
VBAT > VIN
9
TE
I
Timer Enable; Enables Safety Timer when active-low
10, 11, EP
VSS
—
Battery Management 0V Reference. EP (Exposed Thermal Pad).
There is an internal electrical connection between the exposed thermal pad and
VSS. The EP must be connected to the same potential as the VSS pin on the
Printed Circuit Board (PCB)
12
PROG3
I/O
Termination set point for both AC-DC adapter and USB port
13
PROG1
I/O
Fast charge current regulation setting with SEL = high. Preconditioning set point
for both USB port and AC-DC adapter
14, 15
VBAT
I/O
Battery Positive Input and Output connection
16
VBAT_SENSE
I/O
Battery Voltage Sense
17
CE
I
Device Charge Enable; Enabled when CE = high
18, 19
IN
I
Power Supply Input
Legend:
I = Input, O = Output, I/O = Input/Output
Note:
To ensure proper operation, the input pins must not allow floating and should always tie to either high or low.

<!-- Page 15 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 15
MCP73871
The voltage divider equation is shown below:
EQUATION 3-1:
The calculated R1 equals 337.2 kwhen 110 k is
selected for R2. The 330 k resistor is selected for R1
to build the voltage divider for VPCC.
FIGURE 3-1:
Voltage Divider Example.
3.4
Input Source Type Selection (SEL)
The input source type selection (SEL) pin is used to
select the input power source for the input current limit
control feature. With the SEL input high, the
MCP73871 device is capable of providing 1.65 (typical)
total amperes to be shared by the system load and Li-
Ion battery charging. The MCP73871 device limits the
input current up to 1.8A. When SEL active-low, the
input source is designed to provide system power and
Li-Ion battery charging from a USB Port input while
adhering to the current limits governed by the USB
specification.
3.5
Battery Management 0V Reference
(VSS)
Connect to the negative terminal of the battery, system
load and input supply.
3.6
Battery Charge Control Output
(VBAT)
Connect to positive terminal of the Li-Ion/Li-Polymer
battery. Bypass to VSS with a minimum of 4.7 µF to
ensure loop stability when the battery is disconnected.
3.7
Battery Voltage Sense
(VBAT_SENSE)
Connect to the positive terminal of the battery. A
precision internal voltage sense regulates the final
voltage on this pin to VREG.
3.8
Charge Current Regulation Set
(PROG1)
The maximum constant charge current is set by placing
a resistor from PROG1 to VSS. PROG1 sets the
maximum constant charge current for both the AC-DC
adapter and USB port. However, the actual charge
current is based on the input source type and the
system load requirement.
3.9
USB-Port Current Regulation Set
(PROG2)
The MCP73871 device USB-Port current regulation set
input (PROG2) is a digital input selection. A logic Low
selects a one unit load input current from the USB port
(100 mA) while a logic high selects a five unit load input
current from the USB port (500 mA).
3.10
Charge Status Output 1 (STAT1)
STAT1 is an open-drain logic output for connection to
an LED for charge status indication. Alternatively, a
pull-up resistor can be applied for interfacing to a host
microcontroller. Refer to Table 5-1 for a summary of the
status output during a charge cycle.
3.11
Charge Status Output 2 (STAT2)
STAT2 is an open-drain logic output for connection to
an LED for charge status indication. Alternatively, a pull
up resistor can be applied for interfacing to a host
microcontroller. Refer to Table 5-1 for a summary of the
status output during a charge cycle.
3.12
Power Good (PG)
The power good (PG) is an open-drain logic output for
input power supply indication. The PG output is low
whenever the input to the MCP73871 device is above
the UVLO threshold and greater than the battery
voltage. The PG output may be used with an LED or as
an interface to a host microcontroller to signal when an
input power source is supplying power to the system
and the battery. Refer to Table 5-1 for a summary of the
status output during a charge cycle.
VVPCC
R2
R1
R2
+
------------------




VIN
1.23V
=

=
1.23V
110k
110k
R1
+
-----------------------------




5V

=
R1
337.2k
=
330 k
110 k
VIN
VPCC

<!-- Page 16 -->

MCP73871
DS20002090F-page 16
 2008-2022 Microchip Technology Inc. and its subsidiaries
3.13
Low Battery Output (LBO)
STAT1 also serves as low battery output (LBO) if the
selected MCP73871 is equipped with this feature. It
provides an indication to the system or end user when
the Li-Ion battery voltage level is low. The LBO feature
is enabled when the system is running from the Li-Ion
battery. The LBO output may be used with an LED or
as an interface to a host microcontroller to signal when
the system is operating from the battery and the battery
is running low on charge. Refer to Table 5-1 for a
summary of the status output during a charge cycle.
3.14
Timer Enable (TE)
The timer enable (TE) feature is used to enable or
disable the internal timer. A low signal enables and a
high signal disables the internal timer on this pin. The
TE input can be used to disable the timer when the sys-
tem load is substantially limiting the available supply
current to charge the battery. The TE input is
compatible with 1.8V logic. The TE signal asserted low
will stop the timer but not Reset it. The timer can be
reset by cycling the CE pin. The second character of
the operational output options code indicates the Timer
interval: A = disable, B = 4 hours, C = 6 hours and D =
8 hours.
3.15
Battery Temperature Monitor
(THERM)
The MCP73871 device continuously monitors battery
temperature during a charge cycle by measuring the
voltage between the THERM and VSS pins. An internal
50 µA current source provides the bias for most
common 10 k Negative Temperature Coefficient
(NTC) thermistors. The MCP73871 device compares
the voltage at the THERM pin to factory set thresholds
of 1.24V and 0.25V, typically. Once a voltage outside
the thresholds is detected during a charge cycle, the
MCP73871 device immediately suspends the charge
cycle. The charge cycle resumes when the voltage at
the THERM pin returns to the normal range. The
charge temperature window can be set by placing fixed
value resistors in series-parallel with a thermistor.
Refer to Section 6.0 “Applications” for calculations
of resistance values.
3.16
Charge Enable (CE)
With the CE input Low, the Li-Ion battery charger
feature of the MCP73871 is disabled. The charger
feature is enabled when CE is active-high. Allowing the
CE pin to float during the charge cycle may cause
system instability. The CE input is compatible with 1.8V
logic. Refer to Section 6.0 “Applications” for various
applications in designing with CE features.
3.17
Exposed Thermal Pad (EP)
An internal electrical connection exists between the
Exposed Thermal Pad (EP) and the VSS pin. They must
be connected to the same potential on the Printed
Circuit Board (PCB).
Note:
The built-in safety timer is available for the
following options: 4 HR, 6 HR and 8 HR.

<!-- Page 17 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 17
MCP73871
4.0
DEVICE OVERVIEW
The MCP73871 device is a simple but fully integrated
linear charge management controller with system load
sharing feature. Figure 4-1 depicts the operational flow
algorithm.
FIGURE 4-1:
MCP73871 Device Flow Chart.
SHUTDOWN MODE *
 VDD < VUVLO
 VDD < VBAT
STAT1 = Hi-Z
STAT2 = Hi-Z
PG = Hi-Z
PRECONDITIONING  MODE
Charge Current = IPREG
STAT1 = LOW
STAT2 = Hi-Z
PG = LOW
Timer Reset
CONSTANT VOLTAGE MODE
Charge Voltage = VREG
STAT1 = LOW
PG = LOW
VBAT > VPTH
CHARGE COMPLETE MODE
No Charge Current
STAT1 = Hi-Z
STAT2 = LOW
PG = LOW
Timer Reset
IBAT < ITERM
Timer Expired
VBAT < VPTH
STANDBY MODE *
VBAT > (VREG + 100 mV)
CE = LOW
STAT1 = Hi-Z
STAT2 = Hi-Z
PG = LOW
* Continuously Monitored
TEMPERATURE FAULT
No Charge Current
STAT1 = LOW
STAT2 = LOW
PG = LOW
Timer Suspended
TIMER FAULT
No Charge Current
STAT1 = LOW
STAT2 = LOW
PG = LOW
Timer Expired
LBO *
VIN < VBAT
STAT1 = LOW
STAT2 = Hi-Z
PG = Hi-Z
VBAT > VPTH
STAT2 = Hi-Z
Timer Reset
FAST CHARGE MODE
Charge Current = IREG
STAT1 = LOW
STAT2 = Hi-Z
PG = LOW
Timer Enabled

<!-- Page 18 -->

MCP73871
DS20002090F-page 18
 2008-2022 Microchip Technology Inc. and its subsidiaries
Table 4-1 shows the chip behavior based upon the operating conditions.
TABLE 4-1:
CHIP BEHAVIOR REFERENCE TABLE
4.1
UnderVoltage Lockout (UVLO)
An internal undervoltage lockout (UVLO) circuit
monitors the input voltage and keeps the charger in
shutdown mode until the input supply rises above the
UVLO threshold.
In the event a battery is present when the input power
is applied, the input supply must rise approximately
100 mV above the battery voltage before the
MCP73871 device becomes operational.
The UVLO circuit places the device in Shutdown mode
if the input supply falls to within approximately 100 mV
of the battery voltage.
The UVLO circuit is always active. At any time the input
supply is below the UVLO threshold or falls within
approximately 100 mV of the voltage at the VBAT pin,
the MCP73871 device is placed in Shutdown mode.
During any UVLO condition, the battery reverse
discharge current is less than 2 µA.
4.2
System Load Sharing
The system load sharing feature gives the system
output pin (OUT) priority, allowing the system to power-
up with deeply depleted battery packs.
With the SEL input active-low, the MCP73871 device is
designed to provide system power and Li-Ion battery
charging from a USB input while adhering to the current
limits governed by the USB specification.
With the SEL input active-high, the MCP73871 device
limits the total supply current to 1.8A (system power
and charge current combined).
FIGURE 4-2:
System Load Sharing
Diagram.
VIN ? VBAT
VIN > 2V
VIN > UVLO
CE
VBAT ? VOUT
State
Bias + VREF
Thermal
Block
Synchronous
Diode
System Power FET
(Figure 4-2)
Charge
1
VBAT > VIN
0
0
0
—
Shutdown
OFF
OFF
2
1
Battery
powered
system
ON
3
VIN > VBAT
0
0
X
—
Shutdown
OFF
4
VIN > VBAT
1
0
0
—
Shutdown
ON
OFF
OFF
5
1
Battery
powered
system
ON
6
1
0
VBAT < VOUT
Standby
ON
OFF
ON
OFF
7
VBAT > VOUT
IN + BAT
powered
system
ON
8
1
VBAT < VOUT
IN powered,
Charge
possible
OFF
ON/OFF
9
VBAT > VOUT
IN + BAT
powered
system
ON
OFF
0.2
Ideal
Diode,
Synchronous
Switch
Direction
Control
0.2
Current
Limit
Direction
Control
Charge
FET
System
Power
FET
VBAT
IN
OUT
Charge
Control

<!-- Page 19 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 19
MCP73871
4.3
Charge Qualification
For a charge cycle to begin, all UVLO conditions must
be met and a battery or output load must be present.
A charge current programming resistor must be
connected from PROG1 to VSS when SEL = high.
When SEL = low, PROG2 needs to be tied high or low
for proper operation.
4.4
Preconditioning
If the voltage at the VBAT pin is less than the
preconditioning threshold, the MCP73871 device
enters a preconditioning mode. The preconditioning
threshold is factory set. Refer to Section 1.0
“Electrical
Characteristics”
for
preconditioning
threshold options.
In this mode, the MCP73871 device supplies 10% of
the fast charge current (established with the value of
the resistor connected to the PROG1 pin) to the
battery.
When the voltage at the VBAT pin rises above the
preconditioning threshold, the MCP73871 device
enters the Constant Current (fast charge) mode.
4.5
Constant Current Mode – Fast
Charge
During the Constant Current mode, the programmed
charge current is supplied to the battery or load. The
charge current is established using a single resistor
from PROG1 to VSS. The program resistor and the
charge current are calculated using the following
equation:
EQUATION 4-1:
Constant Current mode is maintained until the voltage
at the VBAT pin reaches the regulation voltage, VREG.
When Constant Current mode is invoked, the internal
timer is reset.
4.5.1
TIMER EXPIRED DURING
CONSTANT CURRENT - FAST
CHARGE MODE
If the internal timer expires before the recharge voltage
threshold is reached, a timer fault is indicated and the
charge cycle terminates. The MCP73871 device
remains in this condition until the battery is removed. If
the battery is removed, the MCP73871 device enters
the Standby mode where it remains until a battery is
reinserted.
4.6
Constant Voltage Mode
When the voltage at the VBAT pin reaches the
regulation voltage, VREG, constant voltage regulation
begins. The regulation voltage is factory set to 4.10V
or 4.20V with a tolerance of ±0.5%.
4.7
Charge Termination
The Constant Voltage mode charge cycle terminates
either when the average charge current diminishes
below a threshold established by the value of the
resistor connected from PROG3 to VSS or when the
internal charge timer expires. When the charge cycle
terminates due to a fully charged battery, the charge
current is latched off and the MCP73871 device enters
the Charge Complete mode. A 1 ms filter time on the
termination comparator ensures that transient load
conditions do not result in premature charge cycle
termination. The timer period is factory set and can be
disabled.
Refer
to
Section 1.0
“Electrical
Characteristics” for timer period options.
The program resistor and the charge current are
calculated using the following equation:
EQUATION 4-2:
The recommended PROG3 resistor values are
between 5 k and 100 k.
4.8
Automatic Recharge
The MCP73871 device continuously monitors the
voltage at the VBAT pin in the Charge Complete mode.
If the voltage drops below the recharge threshold,
another charge cycle begins and current is supplied
again to the battery or load. The recharge threshold is
factory
set.
Refer
to
Section 1.0
“Electrical
Characteristics” for recharge threshold options.
IREG
1000V
RPROG1
-------------------
=
Where:
RPROG
=
kilo-ohms (k
IREG
=
milliampere (mA)
Note:
Charge
termination
and
automatic
recharge
features
avoid
constantly
charging Li-Ion batteries, resulting in
prolonged battery life while maintaining
full cell capacity.
ITERMINATION
1000V
RPROG3
-------------------
=
Where:
RPROG
=
kilo-ohms (k
IREG
=
milliampere (mA)

<!-- Page 20 -->

MCP73871
DS20002090F-page 20
 2008-2022 Microchip Technology Inc. and its subsidiaries
4.9
Thermal Regulation
The MCP73871 device limits the charge current based
on the die temperature. The thermal regulation
optimizes the charge cycle time while maintaining
device reliability. Figure 4-3 depicts the thermal
regulation for the MCP73871 device. Refer to
Section 1.0 “Electrical Characteristics” for thermal
package resistances and Section 6.1.1.2 “Thermal
Considerations” for calculating power dissipation.
.
FIGURE 4-3:
Thermal Regulation.
4.10
Thermal Shutdown
The MCP73871 device suspends charge if the die
temperature exceeds 150°C. Charging resumes when
the die temperature has cooled by approximately 10°C.
The thermal shutdown is a secondary safety feature in
the event that there is a failure within the thermal
regulation circuitry.
4.11
Temperature Qualification
The MCP73871 device continuously monitors battery
temperature during a charge cycle by measuring the
voltage between the THERM and VSS pins. An internal
50 µA current source provides the bias for most
common 10 k NTC thermistors. The MCP73871
device compares the voltage at the THERM pin to
factory set thresholds of 1.24V and 0.25V, typically.
Once a voltage outside the thresholds is detected
during a charge cycle, the MCP73871 device
immediately
suspends
the
charge
cycle.
The
MCP73871 device suspends charging by turning off
the charge pass transistor and holding the timer value.
The charge cycle resumes when the voltage at the
THERM pin returns to the normal range.
4.12
Voltage Proportional Charge
Control (VPCC)
If the voltage on the IN pin drops to a preset value
determined by the threshold established at the VPCC
input due to a limited amount of input current or input
source impedance, the battery charging current is
reduced. The VPCC control tries to reach a steady
state condition where the system load has priority and
the battery is charged with the remaining current.
Therefore, if the system demands more current than
the input can provide, the ideal diode becomes
forward-biased and the battery may supplement the
input current to the system load.
The VPCC sustains the system load as its highest
priority. It does this by reducing the noncritical charge
current while maintaining the maximum power output of
the adapter. Further demand from the system is
supported by the battery, if possible.
The VPCC feature functions identically for USB port or
AC-DC adapter inputs. This feature can be disabled by
connecting the VPCC to IN pin.
4.13
Input Current Limit Control (ICLC)
If the input current threshold is reached, then the
battery charging current is reduced. The ICLC tries to
reach a steady state condition where the system load
has priority and the battery is charged with the
remaining current. No active control limits the current
to the system. Therefore, if the system demands more
current than the input can provide or the ICLC is
reached, the ideal diode becomes forward biased and
the battery may supplement the input current to the
system load.
The ICLC sustains the system load as its highest
priority. This is done by reducing the non-critical charge
current while adhering to the current limits governed by
the USB specification or the maximum AC-DC adapter
current supported. Further demand from the system is
supported by the battery, if possible.
FIGURE 4-4:
Input Current Limit Control -
USB Port.













&KDUJH&XUUHQWP$
-XQFWLRQ7HPSHUDWXUH&
9'' 9
5352* Nȍ
-200
-100
0
100
200
300
400
500
600
700
0
100
200
300
400
500
600
700
Load Current (mA)
Current (mA)
Input Current
Battery Current
Load Current
Ideal
Diode

<!-- Page 21 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 21
MCP73871
5.0
DETAILED DESCRIPTION
5.1
Analog Circuitry
5.1.1
LOAD SHARING AND LI-ION
BATTERY MANAGEMENT INPUT
SUPPLY (VIN)
The VIN input is the input supply to the MCP73871
device. The MCP73871 device can be supplied by
either AC Adapter (VAC) or USB Port (VUSB) with SEL
pin. The MCP73871 device automatically powers the
system with the Li-Ion battery when the VIN input is not
present.
5.1.2
FAST CHARGE CURRENT
REGULATION SET (PROG1)
For the MCP73871 device, the charge current
regulation can be scaled by placing a programming
resistor (RPROG1) from the PROG1 pin to VSS. The
program resistor and the charge current are calculated
using the following equation:
EQUATION 5-1:
The fast charge current is set for maximum charge
current from AC-DC adapter and USB port. The
preconditioning current is 10% (0.1C) of the fast charge
current.
5.1.3
BATTERY CHARGE CONTROL
OUTPUT (VBAT)
The battery charge control output is the drain terminal
of an internal P-channel MOSFET. The MCP73871
device
provides
constant
current
and
voltage
regulation to the battery pack by controlling this
MOSFET in the linear region. The battery charge
control output should be connected to the positive
terminal of the battery pack.
5.1.4
TEMPERATURE QUALIFICATION
(THERM)
The MCP73871 device continuously monitors battery
temperature during a charge cycle by measuring the
voltage between the THERM and VSS pins. An internal
50 µA current source provides the bias for most
common
10 k
NTC
or
Positive Temperature
Coefficient (PTC) thermistors.The current source is
controlled,
avoiding
measurement
sensitivity
to
fluctuations in the supply voltage (VDD). The
MCP73871 device compares the voltage at the
THERM pin to factory set thresholds of 1.24V and
0.25V, typically. Once a voltage outside the thresholds
is detected during a charge cycle, the MCP73871
device immediately suspends the charge cycle.
The MCP73871 device suspends the charge by turning
off the pass transistor and holding the timer value. The
charge cycle resumes when the voltage at the THERM
pin returns to the normal range.
If temperature monitoring is not required, place a
standard 10 k resistor from THERM to VSS.
5.2
Digital Circuitry
5.2.1
STATUS INDICATORS AND POWER
GOOD (PG)
The charge status outputs have two different states:
Low-Impedance (L) and High-Impedance (High-Z).
The charge status outputs can be used to illuminate
LEDs. Optionally, the charge status outputs can be
used as an interface to a host microcontroller. Table 5-
1 summarizes the state of the status outputs during a
charge cycle.
TABLE 5-1:
STATUS OUTPUTS
IREG
1000V
RPROG1
-------------------
=
Where:
RPROG
=
kilo-ohms (k
IREG
=
milliampere (mA)
CHARGE CYCLE STATE
STAT1
STAT2
PG
Shutdown (VDD = VBAT)
High-Z
High-Z
High-Z
Shutdown (VDD = IN)
High-Z
High-Z
L
Shutdown (CE = L)
High-Z
High-Z
L
Preconditioning
L
High-Z
L
Constant Current
L
High-Z
L
Constant Voltage
L
High-Z
L
Charge Complete - Standby
High-Z
L
L
Temperature Fault
L
L
L
Timer Fault
L
L
L
Low Battery Output
L
High-Z
High-Z
No Battery Present
High-Z
High-Z
L
No Input Power Present
High-Z
High-Z
High-Z

<!-- Page 22 -->

MCP73871
DS20002090F-page 22
 2008-2022 Microchip Technology Inc. and its subsidiaries
5.2.2
AC-DC ADAPTER AND USB PORT
POWER SOURCE REGULATION
SELECT (SEL)
With the SEL input low, the MCP73871 device is
designed to provide system power and Li-Ion battery
charging from a USB input while adhering to the current
limits governed by the USB specification. The host
microcontroller has the option to select either
a 100 mA (L) or a 500 mA (H) current limit based on
the PROG2 input. With the SEL input high, the
MCP73871 device limits the input current to 1.8A. The
programmed charge current is established using a
single resistor from PROG1 to VSS when driving SEL
high.
5.2.3
USB PORT CURRENT
REGULATION SELECT (PROG2)
Driving the PROG2 input to a logic low selects the low
USB port source current setting (maximum 100 mA).
Driving the PROG2 input to a logic high selects the high
USB port source current setting (maximum 500 mA).
5.2.4
POWER GOOD (PG)
The power good (PG) option is a pseudo open-drain
output. The PG output can sink current, but not source
current. The PG output must not be pulled up higher
than VIN because there is a diode path back to VIN. The
PG output is low whenever the input to the MCP73871
device is above the UVLO threshold and greater than
the battery voltage. The PG output can be used as an
indication to the system that an input source other than
the battery is supplying power.
5.2.5
TIMER ENABLE (TE) OPTION
The timer enable (TE) input option is used to enable or
disable the internal timer. A low signal on this pin
enables the internal timer and a high signal disables
the internal timer. The TE input can be used to disable
the timer when the charger is supplying current to
charge the battery and power the system load. The TE
input is compatible with 1.8V logic.

<!-- Page 23 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 23
MCP73871
6.0
APPLICATIONS
The MCP73871 device is designed to operate in
conjunction
with
a
host
microcontroller
or
in
stand-alone applications. The MCP73871 device
provides the preferred charge algorithm for Lithium-Ion
and Lithium-Polymer cells. The algorithm uses
Constant Current mode followed by Constant Voltage
mode. Figure 6-1 depicts a typical stand-alone
MCP73871 application circuit, while Figure 6-2 and
Figure 6-3 depict the accompanying charge profile.
FIGURE 6-1:
MCP73871 Typical Stand-Alone Application Circuit with VPCC.

FIGURE 6-2:
Typical Charge Profile
(1000 mAh Battery).

FIGURE 6-3:
Typical Charge Profile in
Preconditioning (1000 mAh Battery).
STAT1
LBO
IN
OUT
PG
VBAT
Single-Cell
Li-Ion Battery
7
1, 20
8
18, 19
10 µF
10, 11, EP
5V AC-DC Adapter
or
USB Port
STAT2
THERM
VSS
PROG1
PROG3 12
13 RPROG1
6
5
14, 15, 16
470
470
470
2
4.7 µF
System
Load
SEL
TE
PROG2
Hi
Low
Hi
Low
Hi
Low
3
4
9
RPROG3
VPCC
NTC
10 k
Hi
Low
17 CE
4.7 µF
330 k
110 k
MCP73871 Device Typical Application
SMAJ5.0A/AC
0
0.5
1
1.5
2
2.5
3
3.5
4
4.5
0
10
20
30
40
50
60
70
80
Time (Minute)
Charge Voltage (V)
0
0.2
0.4
0.6
0.8
1
1.2
1.4
1.6
1.8
2
Charge Current (A)
MCP73871
VDD = 5.2V
RPROG1 = 1 kΩ
RPROG3 = 25 kΩ
0
0.5
1
1.5
2
2.5
3
3.5
4
4.5
0
0.2
0.4
0.6
0.8
1
Time (Minute)
Charge Voltage (V)
0
0.2
0.4
0.6
0.8
1
1.2
1.4
1.6
1.8
2
Charge Current (A)
Preconditioning
Preconditioning Threshold Voltage
Fast Charge (Constant Current)
MCP73871
VDD = 5.2V
RPROG1 = 1 kΩ
RPROG3 = 25 kΩ

<!-- Page 24 -->

MCP73871
DS20002090F-page 24
 2008-2022 Microchip Technology Inc. and its subsidiaries
6.1
Application Circuit Design
Due to the low efficiency of linear charging, the most
important factors are thermal design and cost, which
are a direct function of the input voltage, output current
and thermal impedance between the battery charger
and the ambient cooling air. The worst-case situation is
when
the
device
has
transitioned
from
the
Preconditioning mode to the Constant Current mode. In
this situation, the battery charger has to dissipate the
maximum power. A trade-off must be made between
the charge current, cost and thermal requirements of
the charger.
6.1.1
COMPONENT SELECTION
Selection of the external components in Figure 6-1 is
crucial to the integrity and reliability of the charging
system. The following discussion is intended as a guide
for the component selection process.
6.1.1.1
Charge Current
The preferred fast charge current for Lithium-Ion cells
should always follow references and guidances from
battery manufacturers. For example, a 1000 mAh
battery pack has a preferred fast charge current of
0.7C. Charging at 700 mA provides the shortest charge
cycle times without degradation to the battery pack
performance or life.
6.1.1.2
Thermal Considerations
The worst-case power dissipation in the battery
charger occurs when the input voltage is at the
maximum and the device has transitioned from the
Preconditioning mode to the Constant Current mode. In
this case, the power dissipation is:
EQUATION 6-1:
For example, if VREG = 4.2V and VPTH/VREG = 69%,
power dissipation with a 5V, ±10% input voltage source
and 500 mA, ±10% fast charge current is:
EXAMPLE 6-1:
This power dissipation with the battery charger in the
QFN-20 package causes thermal regulation to enter as
depicted. Alternatively, the 4 mm x 4 mm DFN package
could be utilized to reduce heat by adding vias on the
exposed pad.
6.1.1.3
External Capacitors
The MCP73871 device is stable with or without a
battery load. To maintain good AC stability in the
Constant Voltage mode, a minimum capacitance of
4.7 µF is recommended to bypass the VBAT pin to VSS.
This capacitance provides compensation when there is
no battery load. In addition, the battery and
interconnections appear inductive at high frequencies.
These elements are in the control feedback loop during
Constant Voltage mode. Therefore, the bypass
capacitance may be necessary to compensate for the
inductive nature of the battery pack.
Virtually any good quality output filter capacitor can be
used, regardless of the capacitor’s minimum Effective
Series Resistance (ESR) value. The actual value of the
capacitor (and its associated ESR) depends on the
output load current. A 4.7 µF ceramic, tantalum or
aluminum electrolytic capacitor at the output is usually
sufficient to ensure stability for charge currents up to
1000 mA.
6.1.1.4
Reverse-Blocking Protection
The MCP73871 device provides protection from a
faulted or shorted input. Without the protection, a
faulted or shorted input would discharge the battery
pack through the body diode of the internal pass
transistor.
6.1.1.5
Temperature Monitoring
The charge temperature window can be set by placing
fixed value resistors in series-parallel with a thermistor.
The resistance values of RT1 and RT2 can be calculated
with the following equations to set the temperature
window of interest.
For NTC thermistors:
EQUATION 6-2:
PowerDissipation
VDDMAX
VPTHMIN
–


IREGMAX

=
Where:
VDDMAX
=
the maximum input voltage
IREGMAX
=
the maximum fast charge current
VPTHMIN
=
the minimum transition threshold
voltage
PowerDissipation
5.5V
2.89V
–


550mA

1.44W
=
=
24k
RT1
RT2
RCOLD

RT2
R
+
COLD
---------------------------------
+
=
5k
RT1
RT2
RHOT

RT2
R
+
HOT
-----------------------------
+
=
Where:
RT1
=
the fixed series resistance
RT2
=
the fixed parallel resistance
RCOLD
=
the thermistor resistance at the
lower temperature of interest
RHOT
=
the thermistor resistance at the
upper temperature of interest

<!-- Page 25 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 25
MCP73871
For example, by utilizing a 10 k at 25°C NTC
thermistor with a sensitivity index, , of 3892, the
charge temperature range can be set to 0-50°C by
placing a 1.54 k resistor in series (RT1), and a
69.8 k resistor in parallel (RT2) with the thermistor.
6.1.1.6
Charge Status Interface
A status output provides information on the state of
charge. The output can be used to illuminate external
LEDs or interface to a host microcontroller. Refer to
Table 5-1 for a summary of the state of the status
output during a charge cycle.
6.1.1.7
System Load Current
The preferred discharge current for Lithium-Ion cells
should always follow references and guidance from
battery manufacturers. The recommended system
load should be the lesser of 1.0 amperes or the
maximum discharge rate of the selected Lithium-Ion
cell. This limits the safety concerns of power
dissipation
and
exceeding
the
manufacturer’s
maximum discharge rate of the cell.
The ideal diode between VBAT and OUT is designed to
drive a maximum current up to 2A. The built-in thermal
shutdown protection may turn the MCP73871 device
off with high current.
6.1.1.8
Input Overvoltage Protection (IOVP)
The input overvoltage protection must be used when
the input power source is hot-pluggable. This includes
USB cables and wall-type power supplies. The cabling
of these supplies acts as an inductor. When the
supplies are connected/disconnected from the system,
large voltage transients are created and this may
damage the system circuitry. These transients should
be snubbed out. A unidirectional or bidirectional
transzorb connected from the V+ input supply connec-
tor to the 0V ground reference will snub the transients.
An example can be seen in Figure 6-1.
6.2
PCB Layout Issues
For optimum voltage regulation, it is recommended to
place the battery pack closest to the device’s VBAT and
VSS pins to minimize voltage drops along the high
current-carrying PCB traces.
If the PCB layout is used as a heat sink, adding many
vias in the heat sink pad can help conduct more heat to
the PCB backplane, thus reducing the maximum
junction temperature.

<!-- Page 26 -->

MCP73871
DS20002090F-page 26
 2008-2022 Microchip Technology Inc. and its subsidiaries
7.0
PACKAGING INFORMATION
7.1
Package Marking Information
20-Lead QFN (4 x 4 x 0.9 mm)
Example
Legend:
XX...X
Customer-specific information
Y
Year code (last digit of calendar year)
YY
Year code (last 2 digits of calendar year)
WW
Week code (week of January 1 is week ‘01’)
NN
Alphanumeric traceability code
Pb-free JEDEC designator for Matte Tin (Sn)
*
This package is Pb-free. The Pb-free JEDEC designator (
)
can be found on the outer packaging for this package.
3
e
3
e
Note:
In the event the full Microchip part number cannot be marked on one line, it will
be carried over to the next line, thus limiting the number of available
characters for customer-specific information.
73871
1AA
I/ML
203256
3
e

<!-- Page 27 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 27
MCP73871
B
A
0.15 C
0.15 C
0.10
C A B
0.05
C
(DATUM B)
(DATUM A)
C
SEATING
PLANE
NOTE 1
N
2X
TOP VIEW
SIDE VIEW
BOTTOM VIEW
NOTE 1
1
2
N
0.10
C A B
0.10
C A B
0.10 C
0.08 C
Microchip Technology Drawing  C04-126-ML Rev D Sheet 1 of 2
D
E
A
(A3)
20X b
e
2X
D2
E2
K
L
20X
A1
For the most current package drawings, please see the Microchip Packaging Specification located at
http://www.microchip.com/packaging
Note:
20-Lead Plastic Quad Flat, No Lead Package (ML) - 4x4 mm Body [QFN]
Also called VQFN
1
2

<!-- Page 28 -->

MCP73871
DS20002090F-page 28
 2008-2022 Microchip Technology Inc. and its subsidiaries

Microchip Technology Drawing  C04-126-ML Rev D Sheet 2 of 2
Number of Terminals
Overall Height
Terminal Width
Overall Width
Terminal Length
Exposed Pad Width
Terminal Thickness
Pitch
Standoff
Units
Dimension Limits
A1
A
b
E2
A3
e
L
E
N
0.50 BSC
0.20 REF
2.60
0.30
0.18
0.80
0.00
0.25
0.40
2.70
0.90
0.02
4.00 BSC
MILLIMETERS
MIN
NOM
20
2.80
0.50
0.30
1.00
0.05
MAX
K
-
0.20
-
REF: Reference Dimension, usually without tolerance, for information purposes only.
BSC: Basic Dimension. Theoretically exact value shown without tolerances.
1.
2.
3.
Notes:
Pin 1 visual index feature may vary, but must be located within the hatched area.
Package is saw singulated
Dimensioning and tolerancing per ASME Y14.5M
Terminal-to-Exposed-Pad
20-Lead Plastic Quad Flat, No Lead Package (ML) - 4x4 mm Body [QFN]
For the most current package drawings, please see the Microchip Packaging Specification located at
http://www.microchip.com/packaging
Note:
Also called VQFN
Overall Length
Exposed Pad Length
D
D2
2.60
4.00 BSC
2.70
2.80

<!-- Page 29 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 29
MCP73871
RECOMMENDED LAND PATTERN
Dimension Limits
Units
C2
Optional Center Pad Width
Contact Pad Spacing
Optional Center Pad Length
Contact Pitch
Y2
X2
2.80
2.80
MILLIMETERS
0.50 BSC
MIN
E
MAX
4.00
Contact Pad Length (X20)
Contact Pad Width (X20)
Y1
X1
0.80
0.30
Microchip Technology Drawing C04-2126-ML Rev D
NOM
20-Lead Plastic Quad Flat, No Lead Package (ML) - 4x4 mm Body [QFN]
SILK SCREEN
1
2
20
C1
C2
E
X1
Y1
G1
Y2
X2
C1
Contact Pad Spacing
4.00
Contact Pad to Center Pad (X16)
G1
0.20
Thermal Via Diameter
V
Thermal Via Pitch
EV
0.30
1.00
ØV
EV
EV
BSC: Basic Dimension. Theoretically exact value shown without tolerances.
Notes:
Dimensioning and tolerancing per ASME Y14.5M
For best soldering results, thermal vias, if used, should be filled or tented to avoid solder loss during
reflow process
1.
2.
For the most current package drawings, please see the Microchip Packaging Specification located at
http://www.microchip.com/packaging
Note:
Also called VQFN

<!-- Page 30 -->

MCP73871
DS20002090F-page 30
 2008-2022 Microchip Technology Inc. and its subsidiaries
NOTES:

<!-- Page 31 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 31
MCP73871
APPENDIX A:
REVISION HISTORY
Revision F (February 2022)
• Updated Table 4-1 to improve clarity (“IOUT”
replaced with “System Power FET”).
• Updated document layout.
• Updated Section 7.0 “Packaging Information”
drawings and information.
• Updated Product Identification System.
Revision E (April 2019)
• Updated DC CHARACTERISTICS table.
• Updated Figure 2-14, Figure 2-15, Figure 2-16,
and Figure 4-3.
• Updated Section 3.14 “Timer Enable (TE)”.
• Updated Section 6.1.1.2 “Thermal
Considerations” and Equation 6-2.
Revision D (February 2018)
• Corrected Figure 2-26.
• Added Figure 2-27.
• Updated Figure 6-1.
• Added Section 6.1.1.8 “Input Overvoltage
Protection (IOVP)”.
• Minor typographical edits.
Revision C (September 2013)
• Updated Functional Block Diagram.
• Added Table 4-1 in Section 4.0 “Device
Overview”.
• Updated Section 7.0 “Packaging Information”.
• Minor grammatical and editorial corrections.
Revision B (May 2009)
• Updated the QFN-20 package drawing.
• Updated Equation 4-1.
• Updated Section 4.7 “Charge Termination” and
Equation 4-2.
• Updated Equation 5-1.
Revision A (July 2008)
• Original Release of this Document.

<!-- Page 32 -->

MCP73871
DS20002090F-page 32
 2008-2022 Microchip Technology Inc. and its subsidiaries
NOTES:

<!-- Page 33 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 33
MCP73871
PRODUCT IDENTIFICATION SYSTEM
To order or obtain information, e.g., on pricing or delivery, refer to the factory or the listed sales office.
Device:
MCP73871:
USB/AC Battery Charger with PPM
Tape and Reel
Option:
(Blank)
T
= Standard packaging (tube or tray)
= Tape and Reel(1)
Output Options * *
* Refer to table below for different operational
options.
** Consult Factory for Alternative Device Options.
Temperature:
I
= -40C to +85C
Package Type:
ML
= Plastic Quad Flat No Lead (QFN),
4x4x0.9 mm Body, 20-lead
PART NO.
-XXX
Output
Device
Options*
X
Temp.
/XX
Package
Examples: **
a) MCP73871-1AAI/ML:
Tube,
4.10V PPM Battery Charger,
20-LD QFN package
b) MCP73871T-1CAI/ML:
Tape and Reel,
4.10V PPM Battery Charger,
-40C to +85C,
20-LD QFN package
c) MCP73871-2AAI/ML:
Tube,
4.20V PPM Battery Charger,
-40°C to +85°C,
20-LD QFN package
d) MCP73871T-2CCI/ML:
Tape and Reel,
4.20V PPM Battery Charger,
-40°C to +85°C,
20-LD QFN package
e) MCP73871-3CAI/ML:
Tube,
4.35V PPM Battery Charger,
-40°C to +85°C,
20-LD QFN package
f) MCP73871T-4CCI/ML:
Tape and Reel,
4.40V PPM Battery Charger,
-40°C to +85°C,
20-LD QFN package
** Consult Factory for Alternative Device Options
[T](1)
Tape and Reel
Note 1:
Tape and Reel identifier only appears in the
catalog part number description. This identifier is
used for ordering purposes and is not printed on
the device package. Check with your Microchip
Sales Office for package availability with the
Tape and Reel option.
* Operational Output Options
Output
Options
VREG
Safety Timer
Duration (Hours)
LBO Voltage
Threshold (V)
1AA
4.10V
Disabled
Disabled
1CA
4.10V
6
Disabled
1CC
4.10V
6
3.1
2AA
4.20V
Disabled
Disabled
2CA
4.20V
6
Disabled
2CC
4.20V
6
3.1
3CA
4.35V
6
Disabled
3CC
4.35V
6
3.1
4CA
4.40V
6
Disabled
4CC
4.40V
6
3.1
** Consult Factory for Alternative Device Options.

<!-- Page 34 -->

MCP73871
DS20002090F-page 34
 2008-2022 Microchip Technology Inc. and its subsidiaries
NOTES:

<!-- Page 35 -->

 2008-2022 Microchip Technology Inc. and its subsidiaries
DS20002090F-page 35
This publication and the information herein may be used only
with Microchip products, including to design, test, and integrate
Microchip products with your application. Use of this informa-
tion in any other manner violates these terms. Information
regarding device applications is provided only for your conve-
nience and may be superseded by updates. It is your responsi-
bility to ensure that your application meets with your
specifications. Contact your local Microchip sales office for
additional support or, obtain additional support at https://
www.microchip.com/en-us/support/design-help/client-support-
services.
THIS INFORMATION IS PROVIDED BY MICROCHIP "AS IS".
MICROCHIP MAKES NO REPRESENTATIONS OR WAR-
RANTIES OF ANY KIND WHETHER EXPRESS OR IMPLIED,
WRITTEN OR ORAL, STATUTORY OR OTHERWISE,
RELATED TO THE INFORMATION INCLUDING BUT NOT
LIMITED TO ANY IMPLIED WARRANTIES OF NON-
INFRINGEMENT, MERCHANTABILITY, AND FITNESS FOR A
PARTICULAR PURPOSE, OR WARRANTIES RELATED TO
ITS CONDITION, QUALITY, OR PERFORMANCE.
IN NO EVENT WILL MICROCHIP BE LIABLE FOR ANY INDI-
RECT, SPECIAL, PUNITIVE, INCIDENTAL, OR CONSE-
QUENTIAL LOSS, DAMAGE, COST, OR EXPENSE OF ANY
KIND WHATSOEVER RELATED TO THE INFORMATION OR
ITS USE, HOWEVER CAUSED, EVEN IF MICROCHIP HAS
BEEN ADVISED OF THE POSSIBILITY OR THE DAMAGES
ARE
FORESEEABLE.
TO
THE
FULLEST
EXTENT
ALLOWED BY LAW, MICROCHIP'S TOTAL LIABILITY ON
ALL CLAIMS IN ANY WAY RELATED TO THE INFORMATION
OR ITS USE WILL NOT EXCEED THE AMOUNT OF FEES, IF
ANY, THAT YOU HAVE PAID DIRECTLY TO MICROCHIP
FOR THE INFORMATION.
Use of Microchip devices in life support and/or safety applica-
tions is entirely at the buyer's risk, and the buyer agrees to
defend, indemnify and hold harmless Microchip from any and
all damages, claims, suits, or expenses resulting from such
use. No licenses are conveyed, implicitly or otherwise, under
any Microchip intellectual property rights unless otherwise
stated.
Trademarks
The Microchip name and logo, the Microchip logo, Adaptec,
AnyRate, AVR, AVR logo, AVR Freaks, BesTime, BitCloud,
CryptoMemory, CryptoRF, dsPIC, flexPWR, HELDO, IGLOO,
JukeBlox, KeeLoq, Kleer, LANCheck, LinkMD, maXStylus,
maXTouch, MediaLB, megaAVR, Microsemi, Microsemi logo,
MOST, MOST logo, MPLAB, OptoLyzer, PIC, picoPower,
PICSTART, PIC32 logo, PolarFire, Prochip Designer, QTouch,
SAM-BA, SenGenuity, SpyNIC, SST, SST Logo, SuperFlash,
Symmetricom, SyncServer, Tachyon, TimeSource, tinyAVR, UNI/O,
Vectron, and XMEGA are registered trademarks of Microchip
Technology Incorporated in the U.S.A. and other countries.
AgileSwitch, APT, ClockWorks, The Embedded Control Solutions
Company, EtherSynch, Flashtec, Hyper Speed Control, HyperLight
Load, IntelliMOS, Libero, motorBench, mTouch, Powermite 3,
Precision Edge, ProASIC, ProASIC Plus, ProASIC Plus logo, Quiet-
Wire, SmartFusion, SyncWorld, Temux, TimeCesium, TimeHub,
TimePictra, TimeProvider, TrueTime, WinPath, and ZL are
registered trademarks of Microchip Technology Incorporated in the
U.S.A.
Adjacent Key Suppression, AKS, Analog-for-the-Digital Age, Any
Capacitor, AnyIn, AnyOut, Augmented Switching, BlueSky,
BodyCom, CodeGuard, CryptoAuthentication, CryptoAutomotive,
CryptoCompanion, CryptoController, dsPICDEM, dsPICDEM.net,
Dynamic Average Matching, DAM, ECAN, Espresso T1S,
EtherGREEN, GridTime, IdealBridge, In-Circuit Serial
Programming, ICSP, INICnet, Intelligent Paralleling, Inter-Chip
Connectivity, JitterBlocker, Knob-on-Display, maxCrypto, maxView,
memBrain, Mindi, MiWi, MPASM, MPF, MPLAB Certified logo,
MPLIB, MPLINK, MultiTRAK, NetDetach, NVM Express, NVMe,
Omniscient Code Generation, PICDEM, PICDEM.net, PICkit,
PICtail, PowerSmart, PureSilicon, QMatrix, REAL ICE, Ripple
Blocker, RTAX, RTG4, SAM-ICE, Serial Quad I/O, simpleMAP,
SimpliPHY, SmartBuffer, SmartHLS, SMART-I.S., storClad, SQI,
SuperSwitcher, SuperSwitcher II, Switchtec, SynchroPHY, Total
Endurance, TSHARC, USBCheck, VariSense, VectorBlox, VeriPHY,
ViewSpan, WiperLock, XpressConnect, and ZENA are trademarks
of Microchip Technology Incorporated in the U.S.A. and other
countries.
SQTP is a service mark of Microchip Technology Incorporated in
the U.S.A.
The Adaptec logo, Frequency on Demand, Silicon Storage
Technology, Symmcom, and Trusted Time are registered
trademarks of Microchip Technology Inc. in other countries.
GestIC is a registered trademark of Microchip Technology Germany
II GmbH & Co. KG, a subsidiary of Microchip Technology Inc., in
other countries.
All other trademarks mentioned herein are property of their
respective companies.
© 2008-2022, Microchip Technology Incorporated and its subsidiar-
ies.
All Rights Reserved.
ISBN: 978-1-5224-9870-4
Note the following details of the code protection feature on Microchip products:
•
Microchip products meet the specifications contained in their particular Microchip Data Sheet.
•
Microchip believes that its family of products is secure when used in the intended manner, within operating specifications, and
under normal conditions.
•
Microchip values and aggressively protects its intellectual property rights. Attempts to breach the code protection features of
Microchip product is strictly prohibited and may violate the Digital Millennium Copyright Act.
•
Neither Microchip nor any other semiconductor manufacturer can guarantee the security of its code. Code protection does not
mean that we are guaranteeing the product is “unbreakable”. Code protection is constantly evolving. Microchip is committed to
continuously improving the code protection features of our products.
For information regarding Microchip’s Quality Management Systems,
please visit www.microchip.com/quality.

<!-- Page 36 -->

DS20002090F-page 36
 2008-2022 Microchip Technology Inc. and its subsidiaries
AMERICAS
Corporate Office
2355 West Chandler Blvd.
Chandler, AZ 85224-6199
Tel: 480-792-7200
Fax: 480-792-7277
Technical Support:
http://www.microchip.com/
support
Web Address:
www.microchip.com
Atlanta
Duluth, GA
Tel: 678-957-9614
Fax: 678-957-1455
Austin, TX
Tel: 512-257-3370
Boston
Westborough, MA
Tel: 774-760-0087
Fax: 774-760-0088
Chicago
Itasca, IL
Tel: 630-285-0071
Fax: 630-285-0075
Dallas
Addison, TX
Tel: 972-818-7423
Fax: 972-818-2924
Detroit
Novi, MI
Tel: 248-848-4000
Houston, TX
Tel: 281-894-5983
Indianapolis
Noblesville, IN
Tel: 317-773-8323
Fax: 317-773-5453
Tel: 317-536-2380
Los Angeles
Mission Viejo, CA
Tel: 949-462-9523
Fax: 949-462-9608
Tel: 951-273-7800
Raleigh, NC
Tel: 919-844-7510
New York, NY
Tel: 631-435-6000
San Jose, CA
Tel: 408-735-9110
Tel: 408-436-4270
Canada - Toronto
Tel: 905-695-1980
Fax: 905-695-2078
ASIA/PACIFIC
Australia - Sydney
Tel: 61-2-9868-6733
China - Beijing
Tel: 86-10-8569-7000
China - Chengdu
Tel: 86-28-8665-5511
China - Chongqing
Tel: 86-23-8980-9588
China - Dongguan
Tel: 86-769-8702-9880
China - Guangzhou
Tel: 86-20-8755-8029
China - Hangzhou
Tel: 86-571-8792-8115
China - Hong Kong SAR
Tel: 852-2943-5100
China - Nanjing
Tel: 86-25-8473-2460
China - Qingdao
Tel: 86-532-8502-7355
China - Shanghai
Tel: 86-21-3326-8000
China - Shenyang
Tel: 86-24-2334-2829
China - Shenzhen
Tel: 86-755-8864-2200
China - Suzhou
Tel: 86-186-6233-1526
China - Wuhan
Tel: 86-27-5980-5300
China - Xian
Tel: 86-29-8833-7252
China - Xiamen
Tel: 86-592-2388138
China - Zhuhai
Tel: 86-756-3210040
ASIA/PACIFIC
India - Bangalore
Tel: 91-80-3090-4444
India - New Delhi
Tel: 91-11-4160-8631
India - Pune
Tel: 91-20-4121-0141
Japan - Osaka
Tel: 81-6-6152-7160
Japan - Tokyo
Tel: 81-3-6880- 3770
Korea - Daegu
Tel: 82-53-744-4301
Korea - Seoul
Tel: 82-2-554-7200
Malaysia - Kuala Lumpur
Tel: 60-3-7651-7906
Malaysia - Penang
Tel: 60-4-227-8870
Philippines - Manila
Tel: 63-2-634-9065
Singapore
Tel: 65-6334-8870
Taiwan - Hsin Chu
Tel: 886-3-577-8366
Taiwan - Kaohsiung
Tel: 886-7-213-7830
Taiwan - Taipei
Tel: 886-2-2508-8600
Thailand - Bangkok
Tel: 66-2-694-1351
Vietnam - Ho Chi Minh
Tel: 84-28-5448-2100
EUROPE
Austria - Wels
Tel: 43-7242-2244-39
Fax: 43-7242-2244-393
Denmark - Copenhagen
Tel: 45-4485-5910
Fax: 45-4485-2829
Finland - Espoo
Tel: 358-9-4520-820
France - Paris
Tel: 33-1-69-53-63-20
Fax: 33-1-69-30-90-79
Germany - Garching
Tel: 49-8931-9700
Germany - Haan
Tel: 49-2129-3766400
Germany - Heilbronn
Tel: 49-7131-72400
Germany - Karlsruhe
Tel: 49-721-625370
Germany - Munich
Tel: 49-89-627-144-0
Fax: 49-89-627-144-44
Germany - Rosenheim
Tel: 49-8031-354-560
Israel - Ra’anana
Tel: 972-9-744-7705
Italy - Milan
Tel: 39-0331-742611
Fax: 39-0331-466781
Italy - Padova
Tel: 39-049-7625286
Netherlands - Drunen
Tel: 31-416-690399
Fax: 31-416-690340
Norway - Trondheim
Tel: 47-7288-4388
Poland - Warsaw
Tel: 48-22-3325737
Romania - Bucharest
Tel: 40-21-407-87-50
Spain - Madrid
Tel: 34-91-708-08-90
Fax: 34-91-708-08-91
Sweden - Gothenberg
Tel: 46-31-704-60-40
Sweden - Stockholm
Tel: 46-8-5090-4654
UK - Wokingham
Tel: 44-118-921-5800
Fax: 44-118-921-5820
Worldwide Sales and Service


---

# 2. MAX17048/MAX17049 — Fuel Gauge

> **Role:** Battery gauge — MAX17048G+T10  
> **Covers:** `C2682616` (Gauge)

<!-- Page 1 -->

19-6171; Rev 7; 11/16
General Description
The MAX17048/MAX17049 ICs are tiny, micropower cur-
rent fuel gauges for lithium-ion (Li+) batteries in handheld
and portable equipment. The MAX17048 operates with
a single lithium cell and the MAX17049 with two lithium
cells in series.
The ICs use the sophisticated Li+ battery-modeling algo-
rithm ModelGauge™ to track the battery relative state-of-
charge (SOC) continuously over widely varying charge
and discharge conditions. The ModelGauge algorithm
eliminates current-sense resistor and battery-learn cycles
required in traditional fuel gauges. Temperature compen-
sation is implemented using the system microcontroller.
The ICs automatically detect when the battery enters a
low-current state and enters low-power 3µA hibernate
mode, while still providing accurate fuel gauging. The
ICs automatically exit hibernate mode when the system
returns to active state.
On battery insertion, the ICs debounce initial voltage
measurements to improve the initial SOC estimate,
thus allowing them to be located on system side. SOC,
voltage, and rate information is accessed using the I2C
interface. The ICs are available in a tiny 0.9mm x 1.7mm,
8-bump wafer-level package (WLP), or a 2mm x 2mm,
8-pin TDFN package.
Applications
●
●
Smartphones, Tablets
●
●
Smartwatches, Wearables
●
●
Bluetooth Headsets
●
●
Health and Fitness Monitors
●
●
Digital Still, Video, and Action Cameras
●
●
Medical Devices
●
●
Handheld Computers and Terminals
●
●
Wireless Speakers
●
●
Home and Building Automation, Sensors
Features and Benefits
●
●
MAX17048: 1 Cell, MAX17049: 2 Cells
●
●
Precision ±7.5mV/Cell Voltage Measurement
●
●
ModelGauge Algorithm
•	 Provides Accurate State-of-Charge
•	 Compensates for Temperature/Load Variation
•	 Does Not Accumulate Errors, Unlike Coulomb
Counters
•	 Eliminates Learning
•	 Eliminates Current-Sense Resistor
●
●
Ultra-Low Quiescent Current
•	 3μA Hibernate, 23μA Active
•	 Fuel Gauges in Hibernate Mode
•	 Automatically Enters and Exits Hibernate Mode
●
●
Reports Charge and Discharge Rate
●
●
Battery-Insertion Debounce
•	 Best of 16 Samples to Estimate Initial SOC
●
●
Programmable Reset for Battery Swap
•	 2.28V to 3.48V Range
●
●
Configurable Alert Indicator
•	 Low SOC
•	 1% Change in SOC
•	 Battery Undervoltage/Overvoltage
•	 VRESET Alert
●
●
I2C Interface
●
●
8-Bit OTP ID Register (Contact Factory)
ModelGauge is a trademark of Maxim Integrated Products, Inc.
Ordering Information appears at end of data sheet.
ONLY ONE
EXTERNAL
COMPONENT
VDD
ALRT
SDA
SCL
CELL
QSTRT
CTG
GND
SYSTEM
µP
MAX17048
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
Simple Fuel-Gauge Circuit Diagram
EVALUATION KIT AVAILABLE

<!-- Page 2 -->

CELL to GND.........................................................-0.3V to +12V
All Other Pins to GND..............................................-0.3V to +6V
Continuous Sink Current, SDA, ALRT................................20mA
Operating Temperature Range........................... -40°C to +85°C
Storage Temperature Range............................. -55°C to +125°C
Lead Temperature (TDFN only) (soldering, 10s) ............+300°C
Soldering Temperature (reflow).......................................+260°C
(VDD = 2.5V to 4.5V, TA= -20°C to +70°C, unless otherwise noted. Typical values are at TA = +25°C.) (Note 1)
PARAMETER
SYMBOL
CONDITIONS
MIN
TYP
MAX
UNITS
Supply Voltage
VDD
(Note 2)
2.5
4.5
V
Fuel-Gauge SOC Reset
(VRESET Register)
VRST
Configuration range, in 40mV steps
2.28
3.48
V
Trimmed at 3V
2.85
3.0
3.15
V
Data I/O Pins
SCL, SDA,
ALRT
(Note 2)
-0.3
+5.5
V
Supply Current
IDD0
Sleep mode, TA ≤ +50°C
0.5
2
µA
Hibernate mode, reset comparator
disabled (VRESET.Dis = 1)
3
5
Hibernate mode, reset comparator
enabled (VRESET.Dis = 0)
4
IDD1
Active mode
23
40
Time Base Accuracy
tERR
Active, hibernate modes (Note 3)
-3.5
±1
+3.5
%
ADC Sample Period
Active mode
250
ms
Hibernate mode
45
s
Voltage Error
VERR
VCELL = 3.6V, TA = +25°C (Note 4)
-7.5
+7.5
mV/cell
-20
+20
Voltage-Measurement Resolution
1.25
mV/cell
Voltage-Measurement Range
MAX17048: VDD pin
2.5
5
V
MAX17049: CELL pin
5
10
SDA, SCL, QSTRT Input
Logic-High
VIH
1.4
V
SDA, SCL, QSTRT Input
Logic-Low
VIL

0.5
V
SDA, ALRT Output
Logic-Low
VOL
IOL = 4mA
0.4
V
SDA, SCL Bus
Low-Detection Current
IPD
VSDA = VSCL = 0.4V (Note 5)
0.2
0.4
µA
Bus Low-Detection Timeout
tSLEEP
(Note 6)
1.75
2.5
s
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  2
Absolute Maximum Ratings
Stresses beyond those listed under “Absolute Maximum Ratings” may cause permanent damage to the device. These are stress ratings only, and functional operation of the device at these
or any other conditions beyond those indicated in the operational sections of the specifications is not implied. Exposure to absolute maximum rating conditions for extended periods may affect
device reliability.
Electrical Characteristics

<!-- Page 3 -->

(2.5V < VDD < 4.5V, TA = -20°C to +70°C, unless otherwise noted.) (Note 1)
Note 1:	 Specifications are 100% tested at TA = +25°C. Limits over the operating range are guaranteed by design and
characterization.
Note 2:	 All voltages are referenced to GND.
Note 3:	 Test is performed on unmounted/unsoldered parts.
Note 4:	 The voltage is trimmed and verified with 16x averaging.
Note 5:	 This current is always present.
Note 6:	 The IC enters shutdown mode after SCL < VIL and SDA < VIL for longer than 2.5s.
Note 7:	 Timing must be fast enough to prevent the IC from entering sleep mode due to bus low for period > tSLEEP.
Note 8:	 fSCL must meet the minimum clock low time plus the rise/fall times.
Note 9:	 The maximum tHD:DAT has to be met only if the device does not stretch the low period (tLOW) of the SCL signal.
Note 10:	This device internally provides a hold time of at least 100ns for the SDA signal (referred to the VIH,MIN of the SCL signal) to
bridge the undefined region of the falling edge of SCL.
Note 11:	Filters on SDA and SCL suppress noise spikes at the input buffers and delay the sampling instance.
Note 12:	CB is total capacitance of one bus line in pF.
PARAMETER
SYMBOL
CONDITIONS
MIN
TYP
MAX
UNITS
SCL Clock Frequency
fSCL
(Note 7)
0
400
kHz
Bus Free Time Between a
STOP and START Condition
tBUF
1.3
µs
START Condition (Repeated)
Hold Time
tHD:STA
(Note 8)
0.6
µs
Low Period of SCL Clock
tLOW
1.3
µs
High Period of SCL Clock
tHIGH
0.6
µs
Setup Time for a Repeated
START Condition
tSU:STA
0.6
µs
Data Hold Time
tHD:DAT
(Notes 9, 10)
0
0.9
µs
Data Setup Time
tSU:DAT
(Note 9)
100
ns
Rise Time of Both SDA and
SCL Signals
tR
20 + 0.1CB
300
ns
Fall Time of Both SDA and SCL
Signals
tF
20 + 0.1CB
300
ns
Setup Time for STOP Condition
tSU:STO
0.6
µs
Spike Pulse Widths Suppressed
by Input Filter
tSP
(Note 11)
0
50
ns
Capacitive Load for Each Bus
Line
CB
(Note 12)
400
pF
SCL, SDA Input Capacitance
CB,IN
60
pF
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  3
Electrical Characteristics (I2C INTERFACE)

<!-- Page 4 -->

(TA = +25°C, battery is Sanyo UF504553F, unless otherwise noted.)
Figure 1. I2C Bus Timing Diagram
CRATE ACCURACY
MAX17048 toc04
CRATE (%/Hr)
-0.75
-0.50
-0.25
0
0.25
0.50
0.75
1.00
-1.00
TIME (Hr)
6
4
2
0
-2
-4
8
MAX17048 CRATE
MEASURED CRATE
ENTER HIBERNATE MODE
AUTOMATICALLY
MAX17048 toc05
TIME (min)
CURRENT (I_BATT mA, I_DD uA)
VBATT (V)
15
10
5
0
3.70
100
200
300
400
500
600
-100
0
20
VBATT
IBATT
IDD1
IDD0
3.75
3.80
3.85
3.90
3.95
4.00
3.65
QUIESCENT CURRENT vs. SUPPLY
VOLTAGE (HIBERNATE MODE)
MAX17048 toc01
VCELL (V)
QUIESCENT CURRENT (µA)
4.0
3.5
3.0
0
2.5
4.5
TA = +70°C
1
2
3
4
5
TA = -20°C
TA = +25°C
5
10
15
20
25
30
35
40
QUIESCENT CURRENT vs. SUPPLY
VOLTAGE (ACTIVE MODE)
MAX17048 toc02
VCELL (V)
QUIESCENT CURRENT (µA)
4.0
3.5
3.0
0
2.5
4.5
TA = +70°C
TA = -20°C
TA = +25°C
VOLTAGE ADC ERROR vs. TEMPERATURE
MAX17048 toc03
TEMPERATURE (°C)
VOLTAGE ADC ERROR (mV/CELL)
55
40
-5
10
25
-15
-10
-5
0
5
10
15
20
-20
-20
70
VCELL = 3.6V
VCELL = 2.5V
VCELL = 4.5V
SDA
SCL
tF
tLOW
tHD:STA
tHD:DAT
tSU:STA
tSU:STO
tSU:DAT
tHD:STA
tSP
tR
tBUF
tR
tF
S
Sr
P
S
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  4
Typical Operating Characteristics

<!-- Page 5 -->

(TA = +25°C, battery is Sanyo UF504553F, unless otherwise noted.)
EXIT HIBERNATE MODE
AUTOMATICALLY
MAX17048 toc06
TIME (min)
CURRENT (I_BATT mA, I_DD uA)
VBATT (V)
8
2
4
6
0
3.70
100
200
300
400
500
600
-100
0
10
VBATT
IBATT
IDD1
IDD0
3.75
3.80
3.85
3.90
3.95
4.00
3.65
SOC ACCURACY TA = 20°C, HIBERNATE MODE
MAX17048 toc07
TIME (Hr)
SOC (%)
ERROR (%)
8
6
4
REFERENCE SOC
MODELGAUGE
ERROR
2
25
50
75
100
0
-5
0
5
10
-10
-4
-2
0
10
ZIGZAG PATTERN SOC ACCURACY (1/3)
MAX17048 toc08
SOC (%)
ERROR (%)
REFERENCE SOC
MODELGAUGE
ERROR
25
50
75
100
0
-5
0
5
10
-10
TIME (Hr)
80
60
40
20
0
100
ZIGZAG PATTERN SOC ACCURACY (2/3)
MAX17048 toc09
TIME (Hr)
SOC (%)
ERROR (%)
8
6
4
REFERENCE SOC
MODELGAUGE
ERROR
2
25
50
75
100
0
-5
0
5
10
-10
0
10
ZIGZAG PATTERN SOC ACCURACY (3/3)
MAX17048 toc10
TIME (Hr)
SOC (%)
ERROR (%)
103
101
99
REFERENCE SOC
MODELGAUGE
ERROR
97
25
50
75
100
0
-5
0
5
10
-10
95
105
MAX17048 toc11
0A
0V
0V
0V
4ms/div
DEBOUNCE
COMPLETED
DEBOUNCE
BEGINS
VCELL
OCV
BATTERY-INSERTION DEBOUNCE/
OCV ACQUISITION
Maxim Integrated  │  5
www.maximintegrated.com
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
Typical Operating Characteristics (continued)

<!-- Page 6 -->

PIN/BUMP
NAME
FUNCTION
TDFN
WLP
1
A1
CTG
Connect to Ground
2
A2
CELL
Connect to the Positive Battery Terminal.
MAX17048: Not internally connected.
MAX17049: Voltage sense input.
3
A3
VDD
Power-Supply Input. Bypass with 0.1µF to GND.
MAX17048: Voltage sense input. Connect to positive battery terminal.
MAX17049: Connect to regulated power-supply voltage.
4
A4
GND
Ground. Connect to negative battery terminal.
5
B4
ALRT
Open-Drain, Active-Low Alert Output. Optionally connect to interrupt input of the system
microcontroller.
6
B3
QSTRT
Quick-Start Input. Allows reset of the device through hardware. Connect to GND if not used.
7
B2
SCL
I2C Clock Input. SCL has an internal pulldown (IPD) for sensing disconnection.
8
B1
SDA
Open-Drain I2C Data Input/Output. SDA has an internal pulldown (IPD) for sensing
disconnection.
—
—
EP
Exposed Pad (TDFN Only). Connect to GND.
1
+
3
4
8
6
5
SDA
QSTRT
ALRT
MAX17048
MAX17049
2
7
SCL
CTG
VDD
GND
CELL
TDFN
TOP VIEW
(PAD SIDE DOWN)
A1
A2
A3
A4
B1
B2
B3
B4
+
TOP VIEW
(BUMP SIDE DOWN)
MAX17048
MAX17049
WLP
CTG
CELL
VDD
GND
SDA
SCL
QSTRT
ALRT
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  6
Pin/Bump Descriptions
Pin/Bump Configurations

<!-- Page 7 -->

Detailed Description
ModelGauge Theory of Operation
The MAX17048/MAX17049 ICs simulate the internal,
nonlinear dynamics of a Li+ battery to determine its SOC.
The sophisticated battery model considers impedance
and the slow rate of chemical reactions in the battery
(Figure 2).
ModelGauge performs best with a custom model, obtained
by characterizing the battery at multiple discharge cur-
rents and temperatures to precisely model it. At power-on
reset (POR), the ICs have a preloaded ROM model that
performs well for some batteries. Contact Maxim if you
need a custom model.
Fuel-Gauge Performance
In coulomb counter-based fuel gauges, SOC drifts
because offset error in the current-sense ADC measure-
ment accumulates over time. Instantaneous error can be
very small, but never precisely zero. Error accumulates
over time in such systems (typically 0.5%–2% per day)
and requires periodic corrections. Some algorithms cor-
rect drift using occasional events, and until such an event
occurs the algorithm’s error is boundless:
•	 Reaching predefined SOC levels near full or empty
•	 Measuring the relaxed battery voltage after a long
period of inactivity
•	 Completing a full charge/discharge cycle
ModelGauge requires no correction events because it
uses only voltage, which is stable over time. As TOCs 8,
9, and 10 show, ModelGauge remains accurate despite
the absence of any of the above events; it neither drifts
nor accumulates error over time.
To correctly measure performance of a fuel gauge as
experienced by end-users, exercise the battery dynami-
cally. Accuracy cannot be fully determined from only
simple cycles.
Battery Voltage and State-Of-Charge
Open-circuit voltage (OCV) of a Li+ battery uniquely
determines its SOC; one SOC can have only one value of
OCV. In contrast, a given VCELL can occur at many differ-
ent values of OCV because VCELL is a function of time,
OCV, load, temperature, age, and impedance, etc.; one
value of OCV can have many values of VCELL. Therefore,
one SOC can have many values of VCELL, so VCELL can-
not uniquely determine SOC.
Figure 3 shows that VCELL = 3.81V occurs at 2%, 50%,
and 72% SOC.
Even the use of sophisticated tables to consider both
voltage and load results in significant error due to the
load transients typically experienced in a system. During
charging or discharging, and for approximately 30min
after, VCELL and OCV differ substantially, and VCELL has
been affected by the preceding hours of battery activity.
ModelGauge uses voltage comprehensively.
Figure 2. Block Diagram
Figure 3. Instantaneous Voltage Does Not Translate Directly to
SOC
STATE
MACHINE
(SOC, RATE)
2-WIRE
INTERFACE
IC
GROUND
TIME BASE
(32kHz)
ADC (VCELL)
VOLTAGE
REFERENCE
BIAS
GND
CELL
VDD
SCL
SDA
ALRT
QSTRT
CTG
MAX17048
MAX17049
TIME (HOURS)
SOC
VCELL
100%
80%
60%
40%
20%
0%
0
1
2
3
4
5
6
7
8
3.4V
3.6V
3.8V
4.0V
4.2V
3.2V
3.81V = 2%
VCELL
SOC
3.81V = 72%
3.81V = 50%
3.81V
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  7

<!-- Page 8 -->

Temperature Compensation
For best performance, the host microcontroller must mea-
sure battery temperature periodically, and compensate
the RCOMP ModelGauge parameter accordingly, at least
once per minute. Each custom model defines constants
RCOMP0 (default is 0x97), TempCoUp (default is -0.5),
and TempCoDown (default is -5.0). To calculate the new
value of CONFIG.RCOMP:
// T is battery temperature (degrees Celsius)
if (T > 20) {
RCOMP = RCOMP0 + (T - 20) x TempCoUp;
}
else {
RCOMP = RCOMP0 + (T - 20) x TempCoDown;
}
Impact of Empty-Voltage Selection
Most applications have a minimum operating voltage
below which the system immediately powers off (empty
voltage). When characterizing the battery to create a cus-
tom model, choose empty voltage carefully. As shown in
Figure 4, capacity unavailable to the system increases at
an accelerating rate as empty voltage increases.
To ensure a controlled shutdown, consider including
operating margin into the fuel gauge based on some low
threshold of SOC, for example shutting down at 3% or
5%. This utilizes the battery more effectively than adding
error margin to empty voltage.
Battery Insertion
When the battery is first inserted into the system, the
fuel-gauge IC has no previous knowledge about the bat-
tery’s SOC. Assuming that the battery is relaxed, the IC
translates its first VCELL measurement into the best initial
estimate of SOC. Initial error caused by the battery not
being in a relaxed state diminishes over time, regardless
of loading following this initial conversion. While SOC esti-
mated by a coulomb counter diverges, ModelGauge SOC
converges, correcting error automatically as illustrated in
Figure 5; initial error has no long-lasting impact.
Battery Insertion Debounce
Any time the IC powers on or resets (see the VRESET/
ID Register (0x18) section), it estimates that OCV is the
maximum of 16 VCELL samples (1ms each, full 12-bit
resolution). OCV is ready 17ms after battery insertion,
and SOC is ready 175ms after that.
Figure 4. Increasing Empty Voltage Reduces Battery Capacity
Figure 5. ModelGauge Heals Error Automatically
CAPACITY LOST (%)
60
50
40
30
20
10
0
TARGET EMPTY VOLTAGE (V)
3.0
3.1
3.2
3.3
3.4
3.5
C/3 LOAD
C/10 LOAD
LONGER BATTERY RELAXATION
IMPROVES INITIAL ACCURACY
RELAXATION TIME BEFORE INSERTION (MINUTES)
INITIAL VOLTAGE ERROR (mV)
SOC ERROR (%)
0
-10
-20
0
-5
-10
0.1
1
10
100
1000
SOC ERROR
VOLTAGE ERROR
MODELGAUGE HEALS ERROR
AUTOMATICALLY OVER TIME
TIME AFTER INSERTION (MINUTES)
SOC (%)
0
-5
-10
30
45
15
0
0
20
40
60
80
RELAXED SOC
REFERENCE SOC
RELAXED ERROR
UNRELAXED ERROR
UNRELAXED SOC
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  8

<!-- Page 9 -->

Battery Swap Detection
If VCELL falls below VRST, the IC quick-starts when
VCELL returns above VRST. This handles battery swap;
the SOC of the previous battery does not affect that of the
new one. See the Quick-Start and VRESET/ID Register
(0x18) sections.
Quick-Start
If the IC generates an erroneous initial SOC, the battery
insertion and system powerup voltage waveforms must
be examined to determine if a quick-start is necessary,
as well as the best time to execute the command. The IC
samples the maximum VCELL during the first 17ms. See
the Battery Insertion Debounce section. Unless VCELL is
fully relaxed, even the best sampled voltage can appear
greater or less than OCV. Therefore, quick-start must be
used cautiously.
Most systems should not use quick-start because the
ICs handle most startup problems transparently, such as
intermittent battery-terminal connection during insertion. If
battery voltage stabilizes faster than 17ms, as illustrated
in Figure 6, then do not use quick-start.
The quick-start command restarts fuel-gauge calcula-
tions in the same manner as initial power-up of the IC. If
the system power-up sequence is so noisy that the initial
estimate of SOC has unacceptable error, the system
microcontroller might be able to reduce the error by using
quick-start. A quick-start is initiated by a rising edge on
the QSTRT pin, or by writing 1 to the quick-start bit in the
MODE register.
Power-On Reset (POR)
POR includes a quick-start, so only use it when the bat-
tery is fully relaxed. See the Quick-Start section. This
command restores all registers to their default values.
After this command, reload the custom model. See the
CMD Register (0xFE) section.
Hibernate Mode
The ICs have a low-power hibernate mode that can accu-
rately fuel gauge the battery when the charge/discharge
rate is low. By default, the device automatically enters
and exits the hibernate mode according to the charge/
discharge rate, which minimizes quiescent current (below
5µA) without compromising fuel-gauge accuracy. The ICs
can be forced into hibernate or active modes. Force the
IC into hibernate mode to reduce power consumption in
applications with less than C/4-rate maximum loading.
For applications with higher loading, Maxim recommends
the default configuration of automatic control of hibernate
mode.
In hibernate mode, the device reduces its ADC conver-
sion period and SOC update to once per 45s. See the
HIBRT Register (0x0A) section for details on how the IC
automatically enters and exits hibernate mode.
Figure 6. Insertion Waveform Not Requiring Quick-Start
Command
Figure 7. Insertion Waveform Requiring Quick-Start Command
STEADY SYSTEM
LOAD BEGINS
VCELL HAS
FULLY RELAXED
TIME
VCELL
INITIAL SAMPLE
DEBOUNCE WINDOW
TIME
VCELL
INITIAL SAMPLE
DEBOUNCE WINDOW
QUICK-START DURING
THIS TIME SPAN
STEADY
SYSTEM
LOAD BEGINS
BEST TIME TO
QUICK-START
VCELL HAS
FULLY RELAXED
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  9

<!-- Page 10 -->

Alert Interrupt
The ICs can interrupt a system microcontroller with
five configurable alerts (see Table 1). All alerts can be
disabled or enabled with software. When the interrupt
occurs, the system microcontroller can determine the
cause from the STATUS register.
When an alert is triggered, the IC drives the ALRT
pin logic-low and sets CONFIG.ALRT = 1. The ALRT
pin remains logic-low until the system software writes
CONFIG.ALRT = 0 to clear the alert. The alert function
is enabled by default, so any alert can occur immediately
upon power-up. Entering sleep mode clears no alerts.
Sleep Mode
In sleep mode, the IC halts all operations, reducing cur-
rent consumption to below 1µA. After exiting sleep mode,
the IC continues normal operation. In sleep mode, the
IC does not detect self-discharge. If the battery changes
state while the IC sleeps, the IC cannot detect it, causing
SOC error. Wake up the IC before charging or discharg-
ing. To enter sleep mode, write MODE.EnSleep = 1 and
either:
•	 Hold SDA and SCL logic-low for a period for tSLEEP.
A rising edge on SDA or SCL wakes up the IC.
•	 Write CONFIG.SLEEP = 1. To wake up the IC, write
CONFIG.SLEEP = 0. Other communication does not
wake up the IC. POR does wake up the IC.
Applications which can tolerate 4µA should use hibernate
rather than sleep mode.
Register Summary
All registers must be written and read as 16-bit words;
8-bit writes cause no effect. Any bits marked X (don’t
care) or read only must be written with the rest of the
register, but the value written is ignored by the IC. The
values read from don’t care bits are undefined. Calculate
the register’s value by multiplying the 16-bit word by the
register’s LSb value, as shown in Table 2.
VCELL Register (0x02)
The MAX17048 measures VCELL between the VDD and
GND pins. The MAX17049 measures VCELL between the
CELL and GND pins. VCELL is the average of four ADC
conversions. The value updates every 250ms in active
mode and every 45s in hibernate mode.
SOC Register (0x04)
The ICs calculate SOC using the ModelGauge algorithm.
This register automatically adapts to variation in battery
size since ModelGauge naturally recognizes relative SOC.
The upper byte least-significant bit has units of 1%. The
lower byte provides additional resolution.
The first update is available approximately 1s after POR
of the IC. Subsequent updates occur at variable intervals
depending on application conditions.
Table 1. Alert Interrupt Summary
Table 2. Register Summary
ALERT FUNCTION
WHERE CONFIGURED
INDICATOR BIT
Low SOC
CONFIG.ATHD
STATUS.HD
SOC 1% change
CONFIG.ALSC
STATUS.SC
Reset
VRESET, STATUS.RI
STATUS.VR
Overvoltage
VALRT.MAX
STATUS.VH
Undervoltage
VALRT.MIN
STATUS.VL
ADDRESS
REGISTER
NAME
16-BIT LSb
DESCRIPTION
READ/WRITE
DEFAULT
0x02
VCELL
78.125µV/cell
ADC measurement of VCELL.
R
—
0x04
SOC
1%/256
Battery state of charge.
R
—
0x06
MODE
—
Initiates quick-start, reports hibernate mode,
and enables sleep mode.
W
0x0000
0x08
VERSION
—
IC production version.
R
0x001_
0x0A
HIBRT
—
Controls thresholds for entering and exiting
hibernate mode.
R/W
0x8030
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  10

<!-- Page 11 -->

MODE Register (0x06)
The MODE register allows the system processor to send
special commands to the IC (see Figure 8).
•	 Quick-Start generates a first estimate of OCV and
SOC based on the immediate cell voltage. Use with
caution; see the Quick-Start section.
•	 EnSleep enables sleep mode. See the Sleep Mode
section.
•	 HibStat indicates when the IC is in hibernate mode
(read only).
VERSION Register (0x08)
The value of this read-only register indicates the produc-
tion version of the IC.
Table 2. Register Summary (continued)
Figure 8. MODE Register Format
ADDRESS
REGISTER
NAME
16-BIT LSb
DESCRIPTION
READ/WRITE
DEFAULT
0x0C
CONFIG
—
Compensation to optimize performance, sleep
mode, alert indicators, and configuration.
R/W
0x971C
0x14
VALRT
—
Configures the VCELL range outside of which
alerts are generated.
R/W
0x00FF
0x16
CRATE
0.208%/hr
Approximate charge or discharge rate of the
battery.
R
—
0x18
VRESET/ID
—
Configures VCELL threshold below which
the IC resets itself, ID is a one-time factory-
programmable identifier.
R/W
0x96__
0x1A
STATUS
—
Indicates overvoltage, undervoltage, SOC
change, SOC low, and reset alerts.
R/W
0x01__
0x40 to 0x7F
TABLE
—
Configures battery parameters.
W
—
0xFE
CMD
—
Sends POR command.
R/W
0xFFFF
MSB—ADDRESS 0x06
LSB—ADDRESS 0x07
X
Quick-
Start
EnSleep
HibStat
X
X
X
X
X
X
X
X
X
X
X
X
MSb
LSb
MSb
LSb
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  11

<!-- Page 12 -->

HIBRT Register (0x0A)
To disable hibernate mode, set HIBRT = 0x0000. To
always use hibernate mode, set HIBRT = 0xFFFF (see
Figure 9).
•	 ActThr (active threshold): If at any ADC sample |OCV-
CELL| is greater than ActThr, the IC exits hibernate
mode. 1 LSb = 1.25mV.
•	 HibThr (hibernate threshold). If the absolute value of
CRATE is less than HibThr for longer than 6min, the IC
enters hibernate mode. 1 LSb = 0.208%/hr.
CONFIG Register (0x0C)
•	 RCOMP is an 8-bit value that can be adjusted to opti-
mize IC performance for different lithium chemistries
or different operating temperatures. Contact Maxim
for instructions for optimization. The POR value of
RCOMP is 0x97.
•	 SLEEP forces the IC in or out of sleep mode if Mode.
EnSleep is set. Writing 1 forces the IC to enter sleep
mode, and 0 forces the IC to exit. The POR value of
SLEEP is 0.
•	 ALSC (SOC change alert) enables alerting when
SOC changes by at least 1%. Each alert remains until
STATUS.SC is cleared, after which the alert automati-
cally clears until SOC again changes by 1%. Do not
use this alert to accumulate changes in SOC.
•	 ALRT (alert status bit) is set by the IC when an alert
occurs. When this bit is set, the ALRT pin asserts
low. Clear this bit to service and deassert the ALRT
pin. The power-up default value for ALRT is 0. The
STATUS register specifies why the ALRT pin was
asserted.
•	 ATHD (empty alert threshold) sets the SOC threshold,
where an interrupt is generated on the ALRT pin and
can be programmed from 1% up to 32%. The value is
(32 - ATHD)% (e.g., 00000b → 32%, 00001b → 31%,
00010b → 30%, 11111b → 1%). The POR value of
ATHD is 0x1C, or 4%. The alert only occurs on a falling
edge past this threshold.
Figure 9. HIBRT Register Format
Figure 10. CONFIG Register Format
MSB (HibThr)—ADDRESS 0x0A
LSB (ActThr)—ADDRESS 0x0B
27
26
25
24
23
22
21
20
27
26
25
24
23
22
21
20
MSb
LSb
MSb
LSb
HibThr 20 UNIT: 0.208%/hr
ActThr 20 UNIT: 1.25mV
MSB (RCOMP)—ADDRESS 0x0C
LSB—ADDRESS 0x0D
RCOMP
7
RCOMP
6
RCOMP
5
RCOMP
4
RCOMP
3
RCOMP
2
RCOMP
1
RCOMP
0
SLEEP ALSC ALRT ATHD
4
ATHD
3
ATHD
2
ATHD
1
ATHD
0
MSb
LSb
MSb
LSb
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  12

<!-- Page 13 -->

VALRT Register (0x14)
This register is divided into two thresholds: Voltage alert
maximum (VALRT.MAX) and minimum (VALRT. MIN).
Both registers have 1 LSb = 20mV. The IC alerts while
VCELL > VALRT.MAX or VCELL < VALRT.MIN (see
Figure 11).
CRATE Register (0x16)
The IC calculates an approximate value for the average
SOC rate of change. 1 LSb = 0.208% per hour (not for
conversion to ampere).
VRESET/ID Register (0x18)
See Figure 12.
•	 ID is an 8-bit read-only value that is one-time program-
mable at the factory, which can be used as an identifier
to distinguish multiple cell types in production. Writes
to these bits are ignored.
•	 VRESET[7:1] adjusts a fast analog comparator and a
slower digital ADC threshold to detect battery removal
and reinsertion. For captive batteries, set to 2.5V. For
removable batteries, set to at least 300mV below the
application’s empty voltage, according to the desired
reset threshold for your application. If the comparator
is enabled, the IC resets 1ms after VCELL rises above
the threshold. Otherwise, the IC resets 250ms after the
VCELL register rises above the threshold.
•	 Dis. Set Dis = 1 to disable the analog comparator in
hibernate mode to save approximately 0.5µA.
Figure 11. VALRT Register Format
Figure 12. VRESET/ID Register Format
MSB (VALRT.MIN)—ADDRESS 0x14
LSB (VALRT.MAX)—ADDRESS 0x15
MIN7 MIN6 MIN5 MIN4 MIN3 MIN2 MIN1 MIN0
MAX7 MAX6 MAX5 MAX4 MAX3 MAX2 MAX1 MAX0
MSb
LSb
MSb
LSb
UNIT: 20mV
MSB (VRESET)—ADDRESS 0x18
LSB (ID)—ADDRESS 0x19
27
26
25
24
23
22
21
Dis
ID6
ID5
ID4
ID3
ID2
ID1
ID0
ID
MSb
LSb
MSb
LSb
VRESET 20 UNITS: 40mV
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  13

<!-- Page 14 -->

STATUS Register (0x1A)
An alert can indicate many different conditions. The
STATUS register identifies which alert condition was met.
Clear the corresponding bit after servicing the alert (see
Figure 13).
Reset Indicator:
•	 RI (reset indicator) is set when the device powers up.
Any time this bit is set, the IC is not configured, so the
model should be loaded and the bit should be cleared.
Alert Descriptors:
These bits are set only when they cause an alert (e.g., if
CONFIG.ALSC = 0, then SC is never set).
•	 VH (voltage high) is set when VCELL has been above
ALRT.VALRTMAX.
•	 VL (voltage low) is set when VCELL has been below
ALRT.VALRTMIN.
•	 VR (voltage reset) is set after the device has been
reset if EnVr is set.
•	 HD (SOC low) is set when SOC crosses the value in
CONFIG.ATHD.
•	 SC (1% SOC change) is set when SOC changes by at
least 1% if CONFIG.ALSC is set.
Enable or Disable VRESET Alert:
•	 EnVr (enable voltage reset alert) when set to 1 asserts
the ALRT pin when a voltage-reset event occurs under
the conditions described by the VRESET/ ID register.
TABLE Registers (0x40 to 0x7F)
Contact Maxim for details on how to configure these
registers. The default value is appropriate for some Li+
batteries.
To unlock the TABLE registers, write 0x57 to address
0x3F, and 0x4A to address 0x3E. While TABLE is
unlocked, no ModelGauge registers are updated, so
relock as soon as possible by writing 0x00 to address
0x3F, and 0x00 to address 0x3E.
CMD Register (0xFE)
Writing a value of 0x5400 to this register causes
the device to completely reset as if power had been
removed (see the Power-On Reset (POR) section). The
reset occurs when the last bit has been clocked in. The
IC does not respond with an I2C ACK after this com-
mand sequence.
Application Examples
The ICs have a variety of configurations, depending on
the application. Table 3 shows the most common system
configurations and the proper pin connections for each.
In all cases, the system must provide pullup circuits for
ALRT (if used), SDA, and SDL.
Figure 14 shows an example application for a 1S cell
pack. In this example, the ALRT pin is connected to the
microcontroller’s interrupt input to allow the MAX17048 to
signal when the battery is low. The QSTRT pin is unused
in this application and is connected to GND.
Figure 15 shows a MAX17049 example application using
a 2S cell pack. The MAX17049 is mounted on the system
side and powered from a 3.3V supply generated by the
system. The CELL pin is still connected directly to PACK+.
Figure 13. STATUS Register Format
MSB—ADDRESS 0x1A
LSB—ADDRESS 0x1B
X
EnVR
SC
HD
VR
VL
VH
RI
X
X
X
X
X
X
X
X
MSb
LSb
MSb
LSb
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  14

<!-- Page 15 -->

Figure 14. MAX17048 Application Circuit (1S Cell Pack)
Figure 15. MAX17049 Application Circuit (2S Cell Pack)
Table 3. Possible Application Configurations
SYSTEM CONFIGURATION
IC
VDD
ALRT
QSTRT
1S pack-side location
MAX17048
Power directly from battery
Leave unconnected
Connect to GND
1S host-side location
MAX17048
Power directly from battery
Leave unconnected
Connect to GND
1S host-side location,
low-cell interrupt
MAX17048
Power directly from battery
Connect to system
interrupt
Connect to GND
1S host-side location,
hardware quick-start
MAX17048
Power directly from battery
Leave unconnected
Connect to rising-edge
reset signal
2S pack-side location
MAX17049
Power from +2.5V to +4.5V
LDO in pack
Leave unconnected
Connect to GND
2S host-side location
MAX17049
Power from +2.5V to +4.5V
LDO or PMIC
Leave unconnected
Connect to GND
2S host-side location,
low-cell interrupt
MAX17049
Power from +2.5V to +4.5V
LDO or PMIC
Connect to system
interrupt
Connect to GND
2S host-side location,
hardware quick-start
MAX17049
Power from +2.5V to +4.5V
LDO or PMIC
Leave unconnected
Connect to rising-edge
reset signal
VDD
ALRT
SDA
SCL
CELL
QSTRT
CTG
GND
INTERRUPT
SDA
SCL
SYSTEM µP
I2C MASTER
MAX17048
BATTERY PACK
PROTECTION
0.1µF
VDD
ALRT
SDA
SCL
CELL
QSTRT
CTG
GND
INTERRUPT
SDA
SCL
SYSTEM µP
I2C MASTER
MAX17049
BATTERY PACK
PROTECTION
0.1µF
SYSTEM
2.5V TO 4.5V OUTPUT
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  15

<!-- Page 16 -->

I2C Bus System
The I2C bus system supports operation as a slave-only
device in a single or multislave, and single or multimaster
system. Slave devices can share the bus by uniquely set-
ting the 7-bit slave address. The I2C interface consists of
a serial-data line (SDA) and serial-clock line (SCL). SDA
and SCL provide bidirectional communication between
the IC’s slave device and a master device at speeds up to
400kHz. The IC’s SDA pin operates bidirectionally; that is,
when the IC receives data, SDA operates as an input, and
when the IC returns data, SDA operates as an open-drain
output, with the host system providing a resistive pullup.
The IC always operates as a slave device, receiving and
transmitting data under the control of a master device.
The master initiates all transactions on the bus and gener-
ates the SCL signal, as well as the START and STOP bits,
which begin and end each transaction.
Bit Transfer
One data bit is transferred during each SCL clock cycle,
with the cycle defined by SCL transitioning low-to-high
and then high-to-low. The SDA logic level must remain
stable during the high period of the SCL clock pulse.
Any change in SDA when SCL is high is interpreted as a
START or STOP control signal.
Bus Idle
The bus is defined to be idle, or not busy, when no master
device has control. Both SDA and SCL remain high when
the bus is idle. The STOP condition is the proper method
to return the bus to the idle state.
START and STOP Conditions
The master initiates transactions with a START condition
(S) by forcing a high-to-low transition on SDA while SCL
is high. The master terminates a transaction with a STOP
condition (P), a low-to-high transition on SDA while SCL
is high. A Repeated START condition (Sr) can be used in
place of a STOP then START sequence to terminate one
transaction and begin another without returning the bus to
the idle state. In multimaster systems, a Repeated START
allows the master to retain control of the bus. The START
and STOP conditions are the only bus activities in which
the SDA transitions when SCL is high.
Acknowledge Bits
Each byte of a data transfer is acknowledged with an
acknowledge bit (A) or a no-acknowledge bit (N). Both
the master and the MAX17048 slave generate acknowl-
edge bits. To generate an acknowledge, the receiving
device must pull SDA low before the rising edge of the
acknowledge-related clock pulse (ninth pulse) and keep it
low until SCL returns low. To generate a no- acknowledge
(also called NAK), the receiver releases SDA before the
rising edge of the acknowledge-related clock pulse and
leaves SDA high until SCL returns low. Monitoring the
acknowledge bits allows for detection of unsuccessful
data transfers. An unsuccessful data transfer can occur
if a receiving device is busy or if a system fault has
occurred. In the event of an unsuccessful data transfer,
the bus master should reattempt communication.
Data Order
A byte of data consists of 8 bits ordered most significant
bit (MSb) first. The least significant bit (LSb) of each
byte is followed by the acknowledge bit. The IC registers
composed of multibyte values are ordered MSB first.
The MSB of multibyte registers is stored on even data-
memory addresses.
Slave Address
A bus master initiates communication with a slave device
by issuing a START condition followed by a slave address
(SAddr) and the read/write (R/W) bit. When the bus is
idle, the ICs continuously monitor for a START condition
followed by its slave address. When the ICs receive a
slave address that matches the value in the slave address
register, they respond with an acknowledge bit during the
clock period following the R/W bit. The 7-bit slave address
is fixed to 0x6C (write)/0x6D (read):
Read/Write Bit
The R/W bit following the slave address determines the
data direction of subsequent bytes in the transfer. R/W =
0 selects a write transaction with the following bytes being
written by the master to the slave. R/W = 1 selects a read
transaction with the following bytes being read from the
slave by the master (Table 4).
0110110
MAX17048 /MAX17049
SLAVE ADDRESS
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  16

<!-- Page 17 -->

Bus Timing
The ICs are compatible with any bus timing up to 400kHz.
No special configuration is required to operate at any
speed.
I2C Command Protocols
The command protocols involve several transaction
formats. The simplest format consists of the master
writing the START bit, slave address, R/W bit, and then
monitoring the acknowledge bit for presence of the ICs.
More complex formats, such as the Write Data and Read
Data, read data and execute device-specific operations.
All bytes in each command format require the slave or
host to return an acknowledge bit before continuing with
the next byte. Table 4 shows the key that applies to the
transaction formats.
Basic Transaction Formats
A write transaction transfers 2 or more data bytes to the
ICs. The data transfer begins at the memory address
supplied in the MAddr byte. Control of the SDA signal is
retained by the master throughout the transaction, except
for the acknowledge cycles:
A read transaction transfers 2 or more bytes from the
ICs. Read transactions are composed of two parts, a
write portion followed by a read portion, and are therefore
inherently longer than a write transaction. The write por-
tion communicates the starting point for the read opera-
tion. The read portion follows immediately, beginning with
a Repeated START, slave address with R/W set to a 1.
Control of SDA is assumed by the ICs, beginning with the
slave address acknowledge cycle. Control of the SDA
signal is retained by the ICs throughout the transaction,
except for the acknowledge cycles. The master indicates
the end of a read transaction by responding to the last
byte it requires with a no acknowledge. This signals the
ICs that control of SDA is to remain with the master fol-
lowing the acknowledge clock.
Write: S. SAddr W. A. MAddr. A. Data0. A. Data1. A. P
Read: S. SAddr W. A. MAddr. A. Sr. SAddr R. A. Data0. A. Data1. N. P
Write Portion
Read Portion
Write Data Protocol
The write data protocol is used to write to register to the
ICs starting at memory address MAddr. Data0 represents
the data written to MAddr, Data1 represents the data
written to MAddr + 1, and DataN represents the last data
byte, written to MAddr + N. The master indicates the end
of a write transaction by sending a STOP or Repeated
START after receiving the last acknowledge bit:
S. SAddr W. A. MAddr. A. Data0. A. Data1. A... DataN. A. P
The MSb of the data to be stored at address MAddr can
be written immediately after the MAddr byte is acknowl-
edged. Because the address is automatically incremented
after the LSb of each byte is received by the ICs, the MSb
of the data at address MAddr + 1 can be written imme-
diately after the acknowledgment of the data at address
MAddr. If the bus master continues an autoincremented
write transaction beyond address 4Fh, the ICs ignore
the data. A valid write must include both register bytes.
Data is also ignored on writes to read-only addresses.
Incomplete bytes and bytes that are not acknowledged by
the ICs are not written to memory.
Table 4. I2C Protocol Key
KEY
DESCRIPTION
KEY
DESCRIPTION
S
START bit
Sr
Repeated START
SAddr
Slave address (7 bit)
W
R/W bit = 0
MAddr
Memory address byte
P
STOP bit
Data
Data byte written by master
Data
Data byte returned by slave
A
Acknowledge bit—master
A
Acknowledge bit—slave
N
No acknowledge—master
N
No acknowledge bit—slave
R
R/W bit = 1
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  17

<!-- Page 18 -->

Read Data Protocol
The read data protocol is used to read to register from the
ICs starting at the memory address specified by MAddr.
Both register bytes must be read in the same transaction
for the register data to be valid. Data0 represents the data
byte in memory location MAddr, Data1 represents the
data from MAddr + 1, and DataN represents the last byte
read by the master:
S. SAddr W. A. MAddr. A. Sr. SAddr R. A.
Data0. A. Data1. A... DataN. N. P
Data is returned beginning with the MSb of the data in
MAddr. Because the address is automatically incremented
after the LSb of each byte is returned, the MSb of the data
at address MAddr + 1 is available to the host immediately
after the acknowledgment of the data at address MAddr.
If the bus master continues to read beyond address FFh,
the ICs output data values of FFh. Addresses labeled
Reserved in the memory map return undefined data. The
bus master terminates the read transaction at any byte
boundary by issuing a no acknowledge followed by a
STOP or Repeated START.
+Denotes a lead(Pb)-free/RoHS-compliant package.
*EP = Exposed pad.
T = Tape and reel.
PACKAGE TYPE
PACKAGE CODE
OUTLINE NO.
LAND PATTERN NO.
8 WLP
W80B1+1
21-0555
Refer to
Application Note 1891
8 TDFN-EP
T822+3
21-0168
90-0065
PART
TEMP RANGE
PIN-PACKAGE
DESCRIPTION
MAX17048G+
-40°C to +85°C
8 TDFN-EP*
1-Cell ModelGauge IC
MAX17048G+T10
-40°C to +85°C
8 TDFN-EP*
1-Cell ModelGauge IC
MAX17048X+
-40°C to +85°C
8 WLP
1-Cell ModelGauge IC
MAX17048X+T10
-40°C to +85°C
8 WLP
1-Cell ModelGauge IC
MAX17049G+
-40°C to +85°C
8 TDFN-EP*
2-Cell ModelGauge IC
MAX17049G+T10
-40°C to +85°C
8 TDFN-EP*
2-Cell ModelGauge IC
MAX17049X+
-40°C to +85°C
8 WLP
2-Cell ModelGauge IC
MAX17049X+T10
-40°C to +85°C
8 WLP
2-Cell ModelGauge IC
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
www.maximintegrated.com
Maxim Integrated  │  18
Package Information
For the latest package outline information and land patterns (footprints), go to www.maximintegrated.com/packages. Note that a “+”,
“#”, or “-” in the package code indicates RoHS status only. Package drawings may show a different suffix character, but the drawing
pertains to the package regardless of RoHS status.
Ordering Information

<!-- Page 19 -->

REVISION
NUMBER
REVISION
DATE
DESCRIPTION
PAGES
CHANGED
0
2/12
Initial release
—
1
4/12
Corrected byte-order errors
10, 11, 13
2
8/12
Updated soldering temperature in Absolute Maximum Ratings; corrected Hibernate
register names that were switched
2, 12, 14
3
10/12
Corrected VDD pin names in Absolute Maximum Ratings and Electrical
Characteristics
2, 3
4
8/13
Corrected version number
10
5
10/13
Corrected conditions for Supply Current in Electrical Charateristics
2
6
10/14
Updated VRESET recommendation from 40mV–80mV below 300mW empty voltage
and corrected VR bit of Status register
13, 14
7
11/16
Updated front page title, description, applications, and features
1
Maxim Integrated cannot assume responsibility for use of any circuitry other than circuitry entirely embodied in a Maxim Integrated product. No circuit patent licenses
are implied. Maxim Integrated reserves the right to change the circuitry and specifications without notice at any time. The parametric values (min and max limits)
shown in the Electrical Characteristics table are guaranteed. Other parametric values quoted in this data sheet are provided for guidance.
Maxim Integrated and the Maxim Integrated logo are trademarks of Maxim Integrated Products, Inc.
©  2016 Maxim Integrated Products, Inc.  │  19
MAX17048/MAX17049
3μA 1-Cell/2-Cell Fuel Gauge with ModelGauge
Revision History
For pricing, delivery, and ordering information, please contact Maxim Direct at 1-888-629-4642, or visit Maxim Integrated’s website at www.maximintegrated.com.


---

# 3. AP2112 — 600mA CMOS LDO Regulator

> **Role:** Regulator — AP2112K-3.3  
> **Covers:** `C51118` (Regulator: 3.3V)

<!-- Page 1 -->

AP2112
Document number: DS39724  Rev. 2 - 2
1 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112
600mA CMOS LDO REGULATOR WITH ENABLE

Description
The AP2112 is CMOS process low dropout linear regulator with
enable function, the regulator delivers a guaranteed 600mA (min.)
continuous load current.

The AP2112 is available with a fixed output voltage of 1.2V, 1.8V,
2.5V, 2.6V, or 3.3V. The LDO has an output accuracy of ±1.5% and a
very fast loop response providing excellent performance for dealing
with line and load transients. The AP2112 includes an auto discharge
function which connects the output to ground via 60 of resistance
when the device is disabled.

The regulator features low power consumption, and provides SOT25,
SOT89-5, and SO-8 packages. Previously SOT-23-5, SOT-89-5 and
SOIC-8 packages were respectively identified as SOT23-5, SOT89-5
and SO-8 but have been renamed to match the latest Diodes
Incorporated‘s nomenclature.

Features

Output Voltage Accuracy: ±1.5%

Output Current: 600mA (Min.)

Foldback Short Current Protection: 50mA

Enable Function to Turn ON/OFF VOUT

Low Dropout Voltage (3.3V): 250mV (Typ.) @IOUT = 600mA

Excellent Load Regulation: 0.2%/A (Typ.)

Excellent Line Regulation: 0.02%/V (Typ.)

Low Quiescent Current: 55µA (Typ.)

Low Standby Current: 0.01µA (Typ.)

Low Output Noise: 50µVRMS

PSRR: 100Hz -65dB, 1kHz -65dB

OTSD Protection

Stable with 1.0µF Flexible Cap: Ceramic, Tantalum and
Aluminum Electrolytic

Operation Temperature Range: -40°C to +85°C

ESD: MM 400V, HBM 4000V

Totally Lead-Free & Fully RoHS Compliant (Notes 1 & 2)

Halogen and Antimony Free. “Green” Device (Note 3)

Applications

Laptop Computer

LCD Monitor

Portable DVD

Pin Assignments

(Top View)                                      (Top View)

1
2
3
4
5
VOUT
NC
EN
GND
VIN
1
2
3
4
8
7
6
5
VOUT
NC
VIN
GND
GND
EN
NC
NC

                         SOT25                                              SO-8

(Top View)                                       (Top View)

1
2
3
4
5
VOUT
VIN
NC
GND
EN

1
2
3
4
5
VOUT
VIN
NC
GND
EN

   (R5 Package)                                  (R5A Package)
SOT89-5 (Option 1)

(Top View)                                      (Top View)

1
2
3
4
5
VOUT
VIN
NC
GND
EN

1
2
3
4
5
VOUT
VIN
EN
GND
NC

   (R5 Package)                                  (R5A Package)
SOT89-5 (Option 2)

Notes:
1. No purposely added lead. Fully EU Directive 2002/95/EC (RoHS) & 2011/65/EU (RoHS 2) compliant.

2. See http://www.diodes.com/quality/lead_free.html for more information about Diodes Incorporated‘s definitions of Halogen- and Antimony-free, "Green"

    and Lead-free.

3. Halogen- and Antimony-free "Green‖ products are defined as those which contain <900ppm bromine, <900ppm chlorine (<1500ppm total Br + Cl) and

    <1000ppm antimony compounds.

<!-- Page 2 -->

AP2112
Document number: DS39724  Rev. 2 - 2
2 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Typical Applications Circuit (Note 4)

AP2112
GND
VIN
CIN
VOUT
COUT
OFF
VEN
VIN
VOUT
1mF
1.2V/1.8V/
2.5V/2.6V/
3.3V
1mF
ON

Note 4:      It is recommended to use X7R or X5R dielectric capacitor if 1.0µF ceramic capacitor is selected as input/output capacitors.

Pin Descriptions

Pin Number
Pin Name
Function
SOT25
SOT89-5
SO-8
1
4
8
VIN
Input Voltage
2
2
6, 7
GND
GND
3
3 (R5)
5
EN
Chip Enable, H – normal work, L – shutdown output
1 (R5A)
—
1 (R5)
2, 3, 4
NC
No Connection
3 (R5A)
5
5
1
VOUT
Output Voltage

Functional Block Diagram

Shutdown Logic
Thermal
Shutdown
Foldback
Current Limit
VREF
GND
EN
VOUT
VIN
3M
4(4){8}[1]
2(2){6,7}[2]
3(1){5}[3]
5(5){1}[5]
A (B){C}[D]
A: SOT89-5 (R5)
B: SOT89-5 (R5A)
C: SO-8
D: SOT25

<!-- Page 3 -->

AP2112
Document number: DS39724  Rev. 2 - 2
3 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Absolute Maximum Ratings (Note 5)

Symbol
Parameter
Rating
Unit
VCC
Power Supply Voltage
6.5
V
TJ
Operating Junction Temperature Range
+150
°C
TSTG
Storage Temperature Range
-65 to +150
°C
TLEAD
Lead Temperature (Soldering, 10 Seconds)
+260
°C
θJA
Thermal Resistance (Junction to Ambient)(No Heatsink)
SOT25
184
°C/W
SO-8
114
SOT89-5
120
—
ESD (Machine Model)
400
V
—
ESD (Human Body Model)
4000
V

Note 5:    Stresses greater than those listed under ―Absolute Maximum Ratings‖ may cause permanent damage to the device. These are stress ratings only, and
functional operation of the device at these or any other conditions beyond those indicated under ―Recommended Operating Conditions‖ is not implied.
Exposure to ―Absolute Maximum Ratings‖ for extended periods may affect device reliability.

Recommended Operating Conditions

Symbol
Parameter
Min
Max
Unit
VIN
Supply Voltage
2.5
6.0
V
TA
Ambient Operation Temperature Range
-40
+85
°C

<!-- Page 4 -->

AP2112
Document number: DS39724  Rev. 2 - 2
4 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Electrical Characteristics
AP2112-1.2 Electrical Characteristics (@VIN = 2.5V, CIN = 1.0µF (Ceramic), COUT = 1.0µF (Ceramic), Typical TA = +25°C,
unless otherwise specified (Note 6))

Symbol
Parameter
Conditions
Min
Typ
Max
Unit
VOUT
Output Voltage
VIN = 2.5V, 1mA ≤ IOUT ≤ 30mA
VOUT
*98.5%
1.2
VOUT
*101.5%
V
IOUT(MAX)
Maximum Output Current
VIN = 2.5V, VOUT = 1.182V to 1.218V
600
—
—
mA
(∆VOUT/VOUT)/∆IOUT
Load Regulation
VIN = 2.5V, 1mA ≤ IOUT ≤ 600mA
-1
0.2
1
%/A
(∆VOUT/VOUT)/∆VIN
Line Regulation
2.5V ≤ VIN  ≤ 6V, IOUT = 30mA
-0.1
0.02
0.1
%/V
VDROP
Dropout Voltage
IOUT = 10mA
—
1000
1300
mV
IOUT = 300mA
—
1000
1300
IOUT = 600mA
—
1000
1300
IQ
Quiescent Current
VIN = 2.5V, IOUT = 0mA
—
55
80
µA
ISTD
Standby Current
VIN = 2.5V, VEN in OFF mode
—
0.01
1.0
µA
PSRR
Power Supply Rejection Ratio
Ripple 0.5Vp-p
VIN = 2.5V,
IOUT = 100mA
f = 100Hz
—
65
—
dB
f = 1kHz
—
65
—
(∆VOUT/VOUT)/∆T
Output Voltage Temperature
Coefficient
IOUT = 30mA
TA = -40°C to +85°C
—
±100
—
ppm/°C
ISHORT
Short Current Limit
VOUT = 0V
—
50
—
mA
VNOISE
RMS Output Noise
No Load, 10Hz ≤ f ≤ 100kHz
—
50
—
µVRMS
VIH
VEN High Voltage
Enable logic high, regulator on
1.5
—
6.0
V
VIL
VEN Low Voltage
Enable logic low, regulator off
0
—
0.4
tS
Start-up Time
No Load
—
20
—
µs
RPD
EN Pull Down Resistor
—
—
3.0
—
MΩ
RDCHG
VOUT Discharge Resistor
Set EN pin at Low
—
60
—
Ω
TOTSD
Thermal Shutdown Temperature
—
—
+160
—
°C
THYOTSD
Thermal Shutdown Hysteresis
—
—
+25
—
θJC
Thermal Resistance
(Junction to Case)
SOT25
—
96
—
°C/W
SO-8
—
75
—
SOT89-5
—
47
—
Note 6:        Production testing at TA = +25°C. Over temperature specifications guaranteed by design only.

<!-- Page 5 -->

AP2112
Document number: DS39724  Rev. 2 - 2
5 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Electrical Characteristics (Cont.)
AP2112-1.8 Electrical Characteristics (@VIN = 2.8V, CIN = 1.0µF (Ceramic), COUT = 1.0µF (Ceramic), Typical TA = +25°C,
unless otherwise specified (Note 6))

Symbol
Parameter
Conditions
Min
Typ
Max
Unit
VOUT
Output Voltage
VIN = 2.8V, 1mA ≤ IOUT ≤ 30mA
VOUT
*98.5%
1.8
VOUT
*101.5%
V
IOUT(MAX)
Maximum Output Current
VIN = 2.8V, VOUT = 1.773V to 1.827V
600
—
—
mA
(∆VOUT/VOUT)/∆IOUT
Load Regulation
VOUT = 1.8V, VIN = VOUT+1V,
1mA ≤ IOUT ≤ 600mA
-1
0.2
1
%/A
(∆VOUT/VOUT)/∆VIN
Line Regulation
2.8V ≤ VIN ≤ 6V, IOUT = 30mA
-0.1
0.02
0.1
%/V
VDROP
Dropout Voltage
IOUT = 10mA
—
500
700
mV
IOUT = 300mA
—
500
700
IOUT = 600mA
—
500
700
IQ
Quiescent Current
VIN = 2.8V, IOUT = 0mA
—
55
80
µA
ISTD
Standby Current
VIN = 2.8V, VEN in OFF mode
—
0.01
1.0
µA
PSRR
Power Supply Rejection Ratio
Ripple 0.5Vp-p
VIN = 2.8V,
IOUT = 100mA
f = 100Hz
—
65
—
dB
f = 1kHz
—
65
—
(∆VOUT/VOUT)/∆T
Output Voltage Temperature
Coefficient
IOUT = 30mA
TA = -40°C to +85°C
—
±100
—
ppm/°C
ISHORT
Short Current Limit
VOUT = 0V
—
50
—
mA
VNOISE
RMS Output Noise
No Load, 10Hz ≤ f ≤ 100kHz
—
50
—
µVRMS
VIH
VEN High Voltage
Enable logic high, regulator on
1.5
—
6.0
V
VIL
VEN Low Voltage
Enable logic low, regulator off
0
—
0.4
tS
Start-up Time
No Load
—
20
—
µs
RPD
EN Pull Down Resistor
—
—
3.0
—
MΩ
RDCHG
VOUT Discharge Resistor
Set EN pin at Low
—
60
—
Ω
TOTSD
Thermal Shutdown Temperature
—
—
+160
—
°C
THYOTSD
Thermal Shutdown Hysteresis
—
—
+25
—
θJC
Thermal Resistance
(Junction to Case)
SOT25
—
96
—
°C/W
SO-8
—
75
—
SOT89-5
—
47
—
Note 6:        Production testing at TA = +25°C. Over temperature specifications guaranteed by design only.

<!-- Page 6 -->

AP2112
Document number: DS39724  Rev. 2 - 2
6 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Electrical Characteristics (Cont.)
AP2112-2.5 Electrical Characteristics (@VIN = 3.5V, CIN = 1.0µF (Ceramic), COUT = 1.0µF (Ceramic), Typical TA = +25°C,
unless otherwise specified (Note 6))

Symbol
Parameter
Conditions
Min
Typ
Max
Unit
VOUT
Output Voltage
VIN  = 3.5V, 1mA ≤ IOUT ≤ 30mA
VOUT
*98.5%
2.5
VOUT
*101.5%
V
IOUT(MAX)
Maximum Output Current
VIN = 3.5V,
VOUT = 2.463V to 2.537V
600
—
—
mA
(∆VOUT/VOUT)/∆IOUT
Load Regulation
VOUT = 2.5V, VIN = VOUT+1V,
1mA ≤ IOUT ≤ 600mA
-1
0.2
1
%/A
(∆VOUT/VOUT)/∆VIN
Line Regulation
3.5V ≤ VIN ≤ 6V, IOUT = 30mA
-0.1
0.02
0.1
%/V
VDROP
Dropout Voltage
IOUT  = 10mA
—
5
8
mV
IOUT = 300mA
—
125
200
IOUT = 600mA
—
250
400
IQ
Quiescent Current
VIN = 3.5V, IOUT = 0mA
—
55
80
µA
ISTD
Standby Current
VIN = 3.5V, VEN in OFF mode
—
0.01
1.0
µA
PSRR
Power Supply Rejection Ratio
Ripple 0.5Vp-p
VIN = 3.5V,
IOUT = 100mA
f = 100Hz
—
65
—
dB
f = 1KHz
—
65
—
(∆VOUT/VOUT)/∆T
Output Voltage Temperature
Coefficient
IOUT = 30mA
TA = -40°C to +85°C
—
±100
—
ppm/°C
ISHORT
Short Current Limit
VOUT = 0V
—
50
—
mA
VNOISE
RMS Output Noise
No Load, 10Hz ≤ f ≤ 100kHz
—
50
—
µVRMS
VIH
VEN High Voltage
Enable logic high, regulator on
1.5
—
6.0
V
VIL
VEN Low Voltage
Enable logic low, regulator off
0
—
0.4
tS
Start-up Time
No Load
—
20
—
µs
RPD
EN Pull Down Resistor
—
—
3.0
—
MΩ
RDCHG
VOUT Discharge Resistor
Set EN pin at Low
—
60
—
Ω
TOTSD
Thermal Shutdown Temperature
—
—
+160
—
°C
THYOTSD
Thermal Shutdown Hysteresis
—
—
+25
—
θJC
Thermal Resistance
(Junction to Case)
SOT25
—
96
—
°C/W
SO-8
—
75
—
SOT89-5
—
47
—
Note 6:       Production testing at TA = +25°C. Over temperature specifications guaranteed by design only.

<!-- Page 7 -->

AP2112
Document number: DS39724  Rev. 2 - 2
7 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Electrical Characteristics (Cont.)
AP2112-2.6 Electrical Characteristics (@VIN = 3.6V, CIN = 1.0µF (Ceramic), COUT = 1.0µF (Ceramic), Typical TA = +25°C,
unless otherwise specified (Note 6))

Symbol
Parameter
Conditions
Min
Typ
Max
Unit
VOUT
Output Voltage
VIN = 3.6V, 1mA ≤ IOUT ≤ 30mA
VOUT
*98.5%
2.6
VOUT
*101.5%
V
IOUT(MAX)
Maximum Output Current
VIN = 3.6V,
VOUT = 2.561V to 2.639V
600
—
—
mA
(∆VOUT/VOUT)/∆IOUT
Load Regulation
VOUT = 2.6V, VIN = VOUT+1V,
1mA ≤ IOUT ≤ 600mA
-1
0.2
1
%/A
(∆VOUT/VOUT)/∆VIN
Line Regulation
3.6V ≤ VIN ≤ 6V, IOUT = 30mA
-0.1
0.02
0.1
%/V
VDROP
Dropout Voltage
IOUT = 10mA
—
5
8
mV
IOUT = 300mA
—
125
200
IOUT = 600mA
—
250
400
IQ
Quiescent Current
VIN = 3.6V, IOUT = 0mA
—
55
80
µA
ISTD
Standby Current
VIN = 3.6V, VEN in OFF mode
—
0.01
1.0
µA
PSRR
Power Supply Rejection Ratio
Ripple 0.5Vp-p
VIN = 3.6V,
IOUT = 100mA
f = 100Hz
—
65
—
dB
f = 1kHz
—
65
—
(∆VOUT/VOUT)/∆T
Output Voltage
Temperature Coefficient
IOUT = 30mA
TA = -40°C to +85°C
—
±100
—
ppm/°C
ISHORT
Short Current Limit
VOUT = 0V
—
50
—
mA
VNOISE
RMS Output Noise
No Load, 10Hz ≤ f ≤ 100kHz
—
50
—
µVRMS
VIH
VEN High Voltage
Enable logic high, regulator on
1.5
—
6.0
V
VIL
VEN Low Voltage
Enable logic low, regulator off
0
—
0.4
tS
Start-up Time
No Load
—
20
—
µs
RPD
EN Pull Down Resistor
—
—
3.0
—
MΩ
RDCHG
VOUT Discharge Resistor
Set EN pin at Low
—
60
—
Ω
TOTSD
Thermal Shutdown Temperature
—
—
+160
—
°C
THYOTSD
Thermal Shutdown Hysteresis
—
—
+25
—
θJC
Thermal Resistance
(Junction to Case)
SOT25
—
96
—
°C/W
SO-8
—
75
—
SOT89-5
—
47
—
Note 6:       Production testing at TA = +25°C. Over temperature specifications guaranteed by design only.

<!-- Page 8 -->

AP2112
Document number: DS39724  Rev. 2 - 2
8 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Electrical Characteristics (Cont.)
AP2112-3.3 Electrical Characteristics (@VIN = 4.3V, CIN = 1.0µF (Ceramic), COUT = 1.0µF (Ceramic), Typical TA = +25°C,
unless otherwise specified (Note 6))

Symbol
Parameter
Conditions
Min
Typ
Max
Unit
VOUT
Output Voltage
VIN = 4.3V, 1mA ≤ IOUT ≤ 30mA
VOUT
*98.5%
3.3
VOUT
*101.5%
V
IOUT(MAX)
Maximum Output Current
VIN = 4.3V, VOUT = 3.251V to 3.350V
600
—
—
mA
(∆VOUT/VOUT)/∆IOUT
Load Regulation
VIN = 4.3V, 1mA ≤ IOUT ≤ 600mA
-1
0.2
1
%/A
(∆VOUT/VOUT)/∆VIN
Line Regulation
4.3V≤ VIN  ≤ 6V, IOUT = 30mA
-0.1
0.02
0.1
%/V
VDROP
Dropout Voltage
IOUT = 10mA
—
5
8
mV
IOUT = 300mA
—
125
200
IOUT = 600mA
—
250
400
IQ
Quiescent Current
VIN = 4.3V, IOUT = 0mA
—
55
80
µA
ISTD
Standby Current
VIN = 4.3V, VEN in OFF mode
—
0.01
1.0
µA
PSRR
Power Supply Rejection Ratio
Ripple 0.5Vp-p
VIN = 4.3V,
IOUT = 100mA
f = 100Hz
—
65
—
dB
f = 1kHz
—
65
—
(∆VOUT/VOUT)/∆T
Output Voltage Temperature
Coefficient
IOUT = 30mA
TA = -40°C to +85°C
—
±100
—
ppm/°C
ISHORT
Short Current Limit
VOUT = 0V
—
50
—
mA
VNOISE
RMS Output Noise
No Load, 10Hz ≤ f ≤ 100kHz
—
50
—
µVRMS
VIH
VEN High Voltage
Enable logic high, regulator on
1.5
—
6.0
V
VIL
VEN Low Voltage
Enable logic low, regulator off
0
—
0.4
tS
Start-up Time
No Load
—
20
—
µs
RPD
EN Pull Down Resistor
—
—
3.0
—
MΩ
RDCHG
VOUT Discharge Resistor
Set EN pin at Low
—
60
—
Ω
TOTSD
Thermal Shutdown Temperature
—
—
+160
—
°C
THYOTSD
Thermal Shutdown Hysteresis
—
—
+25
—
θJC
Thermal Resistance
(Junction to Case)
SOT25
—
96
—
°C/W
SO-8
—
75
—
SOT89-5
—
47
—
Note 6:       Production testing at TA = +25°C. Over temperature specifications guaranteed by design only.

<!-- Page 9 -->

AP2112
Document number: DS39724  Rev. 2 - 2
9 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Performance Characteristics

Output Voltage vs. Input Voltage                                              Output Voltage vs. Input Voltage

Quiescent Current vs. Temperature                                         Quiescent Current vs. Input Voltage

Output Voltage vs. Temperature                                               Output Voltage vs. Temperature

0.0
0.5
1.0
1.5
2.0
2.5
3.0
3.5
4.0
4.5
5.0
5.5
6.0
0.0
0.2
0.4
0.6
0.8
1.0
1.2
1.4
1.6
NO Load
 TA=-40
oC
 TA=25
oC
  TA=85
oC
VOUT=1.2V

Output Voltage (V)
Input Voltage (V)
0.0
0.5
1.0
1.5
2.0
2.5
3.0
3.5
4.0
4.5
5.0
5.5
6.0
0.0
0.5
1.0
1.5
2.0
2.5
3.0
3.5
4.0
Output Voltage (V)
Input Voltage (V)
 TA=-40
oC
 TA=25
oC
 TA=85
oC
VOUT=3.3V
No Load
-40.0
-20.0
0.0
20.0
40.0
60.0
80.0
46
48
50
52
54
56
58
60
62
64
66
68
70
VIN=2.5V
No Load
Quiescent Current (mA)
Temperature (
oC)
1.0
1.5
2.0
2.5
3.0
3.5
4.0
4.5
5.0
5.5
6.0
0
10
20
30
40
50
60
70
Quiescent Current (mA)
 TA=-40
OC
 TA=25
OC
 TA=85
OC
No Load
Input Voltage (V)
-40
-20
0
20
40
60
80
3.25
3.26
3.27
3.28
3.29
3.30
3.31
3.32
3.33
3.34
3.35
Output Voltage (V)
Temperature(
oC)
 IOUT=10mA
 IOUT=100mA
 IOUT=300mA
 IOUT=600mA
VIN=4.3V
CIN=1mF
COUT=1mF
-40.0
-20.0
0.0
20.0
40.0
60.0
80.0
1.200
1.202
1.204
1.206
1.208
1.210
 IOUT=300mA
 IOUT=600mA
 IOUT=10mA
 IOUT=100mA
VIN=2.5V
CIN=1mF
COUT=1mF
Output Voltage (V)
Temperature (
oC)

<!-- Page 10 -->

AP2112
Document number: DS39724  Rev. 2 - 2
10 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Performance Characteristics (Cont.)

Output Voltage vs. Output Current                                          Output Voltage vs. Output Current

Output Voltage vs. Output Current                                           Output Voltage vs. Output Current

Dropout Voltage vs. Output Current                                          Ground Current vs. Output Current

0.0
0.1
0.2
0.3
0.4
0.5
0.6
0.7
0.8
0.9
1.0
-0.1
0.0
0.1
0.2
0.3
0.4
0.5
0.6
0.7
0.8
0.9
1.0
1.1
1.2
1.3
VIN=2.5V
Output Voltage (V)
Output Current (A)
 TA= -40
oC
 TA=25
oC
 TA=85
oC
0.0
0.1
0.2
0.3
0.4
0.5
0.6
0.7
0.8
0.9
1.0
-0.5
0.0
0.5
1.0
1.5
2.0
2.5
3.0
3.5
4.0
Output Voltage (V)
Output Current (A)
 TA=-40
oC
 TA= 25
oC
 TA= 85
oC
VIN=4.3V
0.0
0.1
0.2
0.3
0.4
0.5
0.6
0.7
0.8
0.9
1.0
0.0
0.2
0.4
0.6
0.8
1.0
1.2
T
A=25
oC
CIN=1mF
COUT=1mF
 VIN=5V
 VIN=2V
 VIN=5.5V
 VIN=6V
 VIN=2.5V
Output Voltage (V)
Output Current (A)
0.0
0.1
0.2
0.3
0.4
0.5
0.6
0.7
0.8
0.9
1.0
0.0
0.5
1.0
1.5
2.0
2.5
3.0
3.5
4.0
Output Voltage (V)
Output Current (A)
 VIN=4.0V
 VIN=4.3V
 VIN=5.0V
 VIN=5.5V
 VIN=6.0V
TA=25
oC
CIN=1mF
COUT=1mF
0.0
0.1
0.2
0.3
0.4
0.5
0.6
40
60
80
100
120
140
160
180
200
220
240
260
Ground Current (mA)
Output Current (A)
 TA=-40
oC
 TA= 25
oC
 TA= 85
oC
VIN=4.3V
0.0
0.1
0.2
0.3
0.4
0.5
0.6
0
50
100
150
200
250
300
350
Dropout Voltage (mV)
Output Current (A)
 TA=-40
oC
 TA= 25
oC
 TA= 85
oC
VOUT=3.3V

<!-- Page 11 -->

AP2112
Document number: DS39724  Rev. 2 - 2
11 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Performance Characteristics (Cont.)

PSRR vs. Frequency                                                                  Load Transient

Enable On                                                                                Enable Off

Application Note
In some unusual applications where a current load could be present at the output before the part is enabled the fold back current limiting may
prevent the part from starting. Applications with multiple supplies or negative supplies need to be evaluated for this possibility. Product testing
where a current source is applied before the part is enabled could be another area of concern.  With a normal load as shown below there is no
interference of the fold back current limiting circuit.

100
1k
10k
100k
30
35
40
45
50
55
60
65
70
 IOUT=10mA
IOUT=100mA
 IOUT=300mA
VOUT=1.2V
PSRR (dB)
Frequency (Hz)
20
VIN=2.5V
Ripple=0.5V
0mA
VIN=2.5V, CIN=1mF, COUT=1mF
CH1: VOUT
10mV/div
CH2: IOUT
200mA/div
600mA
VIN
(2V/div)
VIN
(2V/div)
VEN
(2V/div)
VEN
(2V/div)
VOUT
(2V/div)
VOUT
(2V/div)
20ms/div
VIN
(2V/div)
VIN
(2V/div)
VEN
(2V/div)
VEN
(2V/div)
VOUT
(2V/div)
VOUT
(2V/div)
200ms/div
0.0
0.1
0.2
0.3
0.4
0.5
0.6
0.7
0.8
0.9
1.0
0.0
0.5
1.0
1.5
2.0
2.5
3.0
3.5
4.0
Output Voltage (V)
Output Current (A)
 VIN=4.0V
 VIN=4.3V
 VIN=5.0V
 VIN=5.5V
 VIN=6.0V
TA=25
oC
CIN=1mF
COUT=1mF
Load Line

<!-- Page 12 -->

AP2112
Document number: DS39724  Rev. 2 - 2
12 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Ordering Information

AP2112 X - X X X
Packing
Package
K : SOT25
M : SO-8
Product Name
Output Voltage
1.8 : 1.8V
2.5 : 2.5V
2.6 : 2.6V
1.2 : 1.2V
RoHS/Green
R5/R5A : SOT89-5
TR : Tape & Reel
G1 : Green
3.3 : 3.3V

Package
Temperature
Range
Condition
Part Number
Marking ID
Packing
SOT25
-40 to +85°C
1.2V
AP2112K-1.2TRG1
G3L
3000/7‖/Tape & Reel
1.8V
AP2112K-1.8TRG1
G3M
3000/7‖/Tape & Reel
2.5V
AP2112K-2.5TRG1
G3N
3000/7‖/Tape & Reel
2.6V
AP2112K-2.6TRG1
G5N
3000/7‖/Tape & Reel
3.3V
AP2112K-3.3TRG1
G3P
3000/7‖/Tape & Reel
SO-8
-40 to +85°C
1.2V
AP2112M-1.2TRG1
2112M-1.2G1
4000/13‖/Tape & Reel
1.8V
AP2112M-1.8TRG1
2112M-1.8G1
4000/13‖/Tape & Reel
2.5V
AP2112M-2.5TRG1
2112M-2.5G1
4000/13‖/Tape & Reel
2.6V
AP2112M-2.6TRG1
2112M-2.6G1
4000/13‖/Tape & Reel
3.3V
AP2112M-3.3TRG1
2112M-3.3G1
4000/13‖/Tape & Reel
SOT89-5
-40 to +85°C
1.2V(R5)
AP2112R5-1.2TRG1
G37D
1000/7‖/Tape & Reel
1.8V(R5)
AP2112R5-1.8TRG1
G37E
1000/7‖/Tape & Reel
2.5V(R5)
AP2112R5-2.5TRG1
G37F
1000/7‖/Tape & Reel
2.6V(R5)
AP2112R5-2.6TRG1
G13F
1000/7‖/Tape & Reel
3.3V(R5)
AP2112R5-3.3TRG1
G37G
1000/7‖/Tape & Reel
SOT89-5
-40 to +85°C
1.2V(R5A)
AP2112R5A-1.2TRG1
G33C
1000/7‖/Tape & Reel
1.8V(R5A)
AP2112R5A-1.8TRG1
G33E
1000/7‖/Tape & Reel
2.5V(R5A)
AP2112R5A-2.5TRG1
G28G
1000/7‖/Tape & Reel
2.6V(R5A)
AP2112R5A-2.6TRG1
G13E
1000/7‖/Tape & Reel
3.3V(R5A)
AP2112R5A-3.3TRG1
G28H
1000/7‖/Tape & Reel

<!-- Page 13 -->

AP2112
Document number: DS39724  Rev. 2 - 2
13 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Marking Information

(1) SOT25

XXX

(2) SO-8

(3) SOT89-5

: Logo
XXX : Marking ID (See Ordering Information)
XXXX
YWWAXX
First Line: Logo and Marking ID
Second line: Date Code
Y: Year
WW: Work Week of Molding
A: Assembly House Code
XX: 7th and 8th Digits of Batch Number
2112M-X.XG1
YWWAXX
First line: Logo and Marking ID
Second line: Date Code
Y: Year
WW: Work Week of Molding
A: Assembly House Code
XX: 7th and 8th Digits of Batch Number

<!-- Page 14 -->

AP2112
Document number: DS39724  Rev. 2 - 2
14 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Package Outline Dimensions (Previously identified as SOT-23-5 for this product)
Please see http://www.diodes.com/package-outlines.html for the latest version.

SOT25

Suggested Pad Layout
Please see http://www.diodes.com/package-outlines.html for the latest version.

SOT25

Note:
The suggested land pattern dimensions have been provided for reference only, as actual pad layouts may vary depending on application. These
dimensions may be modified based on user equipment capability or fabrication criteria. A more robust pattern may be desired for wave soldering
and is calculated by adding 0.2 mm to the ‗Z‘ dimension. For further information, please reference document IPC-7351A, Naming Convention for
Standard SMT Land Patterns, and for International grid details, please see document IEC, Publication 97.

Note:
For high voltage applications, the appropriate industry sector guidelines should be considered with regards to creepage and clearance distances
between device Terminals and PCB tracking.

SOT25
Dim
Min
Max Typ
A
0.35
0.50 0.38
B
1.50
1.70 1.60
C
2.70
3.00 2.80
D
-
-
0.95
H
2.90
3.10 3.00
J
0.013 0.10 0.05
K
1.00
1.30 1.10
L
0.35
0.55 0.40
M
0.10
0.20 0.15
N
0.70
0.80 0.75

0°
8°
-
All Dimensions in mm
Dimensions
Value
Z
3.20
G
1.60
X
0.55
Y
0.80
C1
2.40
C2
0.95
A
M
J
L
D
B C
H
K
N
X
Z
Y
C1
C2
C2
G

<!-- Page 15 -->

AP2112
Document number: DS39724  Rev. 2 - 2
15 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Package Outline Dimensions (All dimensions in mm.) (Previously identified as SOT-89-5 for this product)

SOT89-5

45
1.030(0.041)REF
1.550(0.061)REF
4.400(0.173)
4.600(0.181)
0.900(0.035)
1.100(0.043)
3.950(0.156)
4.250(0.167)
3.000(0.118)
TYP
0.480(0.019)
2.300(0.091)
2.600(0.102)
0.320(0.013)
3
10
2.060(0.081)REF
0.350(0.014)
0.450(0.018)
R0.150(0.006)
3
10
1.500(0.059)
0.320(0.013)REF
1.620(0.064)REF
2.210(0.087)REF
0.320(0.013)
1.800(0.071)
Option 1
1.100(0.043)
0.900(0.035)
TYP
0.540(0.021)
0.540(0.021)
Option 2
1.620(0.064)
1.830(0.072)
R 0.200(0.008)
2.630(0.104)
2.930(0.115)
0.950(0.037)
0.650(0.026)
0.650(0.026)
0.950(0.037)
0.500(0.020)
0.620(0.024)
1.400(0.055)
1.600(0.063)
Option 1

<!-- Page 16 -->

AP2112
Document number: DS39724  Rev. 2 - 2
16 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Suggested Pad Layout (Previously identified as SOT-89-5 for this product)

SOT89-5

X1
X2
Y1
E
Z
Y
X

Dimensions
Z
(mm)/(inch)
X
(mm)/(inch)
X1
(mm)/(inch)
X2
(mm)/(inch)
Y
(mm)/(inch)
Y1
(mm)/(inch)
E
(mm)/(inch)
Value
4.600/0.181
0.550/0.022
1.850/0.073
0.800/0.031
1.300/0.051
1.475/0.058
1.500/0.059

<!-- Page 17 -->

AP2112
Document number: DS39724  Rev. 2 - 2
17 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

Package Outline Dimensions (Previously identified as SOIC-8 for this product)
Please see http://www.diodes.com/package-outlines.html for the latest version.

SO-8

SO-8
Dim
Min
Max
Typ
A
1.40
1.50
1.45
A1
0.10
0.20
0.15
b
0.30
0.50
0.40
c
0.15
0.25
0.20
D
4.85
4.95
4.90
E
5.90
6.10
6.00
E1
3.80
3.90
3.85
E0
3.85
3.95
3.90
e
--
--
1.27
h
-
--
0.35
L
0.62
0.82
0.72
Q
0.60
0.70
0.65
All Dimensions in mm

Suggested Pad Layout
Please see http://www.diodes.com/package-outlines.html for the latest version.

SO-8

Note:
The suggested land pattern dimensions have been provided for reference only, as actual pad layouts may vary depending on application. These
dimensions may be modified based on user equipment capability or fabrication criteria. A more robust pattern may be desired for wave soldering
and is calculated by adding 0.2 mm to the ‗Z‘ dimension. For further information, please reference document IPC-7351A, Naming Convention for
Standard SMT Land Patterns, and for International grid details, please see document IEC, Publication 97.

Note:
For high voltage applications, the appropriate industry sector guidelines should be considered with regards to creepage and clearance distances
between device Terminals and PCB tracking.

1
b
e
E
A
A1
9° (All sides)
4°± 3°
c
Q
h
45°
R 0.1
7°
D
E0
E1
L
Seating Plane
Gauge Plane
Dimensions Value (in mm)
C
1.27
X
0.802
X1
4.612
Y
1.505
Y1
6.50
C
X
Y
Y1
X1

<!-- Page 18 -->

AP2112
Document number: DS39724  Rev. 2 - 2
18 of 18
www.diodes.com
June 2017
© Diodes Incorporated

AP2112

IMPORTANT NOTICE

DIODES INCORPORATED MAKES NO WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, WITH REGARDS TO THIS DOCUMENT,
INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
(AND THEIR EQUIVALENTS UNDER THE LAWS OF ANY JURISDICTION).

Diodes Incorporated and its subsidiaries reserve the right to make modifications, enhancements, improvements, corrections or other changes
without further notice to this document and any product described herein. Diodes Incorporated does not assume any liability arising out of the
application or use of this document or any product described herein; neither does Diodes Incorporated convey any license under its patent or
trademark rights, nor the rights of others.  Any Customer or user of this document or products described herein in such applications shall assume
all risks of such use and will agree to hold Diodes Incorporated and all the companies whose products are represented on Diodes Incorporated
website, harmless against all damages.

Diodes Incorporated does not warrant or accept any liability whatsoever in respect of any products purchased through unauthorized sales channel.
Should Customers purchase or use Diodes Incorporated products for any unintended or unauthorized application, Customers shall indemnify and
hold Diodes Incorporated and its representatives harmless against all claims, damages, expenses, and attorney fees arising out of, directly or
indirectly, any claim of personal injury or death associated with such unintended or unauthorized application.

Products described herein may be covered by one or more United States, international or foreign patents pending.  Product names and markings
noted herein may also be covered by one or more United States, international or foreign trademarks.

This document is written in English but may be translated into multiple languages for reference.  Only the English version of this document is the
final and determinative format released by Diodes Incorporated.

LIFE SUPPORT

Diodes Incorporated products are specifically not authorized for use as critical components in life support devices or systems without the express
written approval of the Chief Executive Officer of Diodes Incorporated. As used herein:

A.   Life support devices or systems are devices or systems which:

1. are intended to implant into the body, or

2. support or sustain life and whose failure to perform when properly used in accordance with instructions for use provided in the

     labeling can be reasonably expected to result in significant injury to the user.

B.   A critical component is any component in a life support device or system whose failure to perform can be reasonably expected to cause the
      failure of the life support device or to affect its safety or effectiveness.

Customers represent that they have all necessary expertise in the safety and regulatory ramifications of their life support devices or systems, and
acknowledge and agree that they are solely responsible for all legal, regulatory and safety-related requirements concerning their products and any
use of Diodes Incorporated products in such safety-critical, life support devices or systems, notwithstanding any devices- or systems-related
information or support that may be provided by Diodes Incorporated.  Further, Customers must fully indemnify Diodes Incorporated and its
representatives against any damages arising out of the use of Diodes Incorporated products in such safety-critical, life support devices or systems.

Copyright © 2017, Diodes Incorporated

www.diodes.com


---

# 4. NT3H2111/2211 — NTAG I2C plus (NFC)

> **Role:** NFC chip — NT3H2111W0FHKH  
> **Covers:** `C710403` (NFC)

<!-- Page 1 -->

NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and
energy harvesting
Rev. 3.6 — 21 July 2023
Product data sheet
1   General description
Designed to be the perfect enabler for NFC in home-automation and consumer applications, this feature-
packed, second-generation connected NFC tag is the fastest, least expensive way to add tap-and-go
connectivity to just about any electronic device.
NXPNTAG I2C plus is a family of connected NFC tags that combine a passive NFC interface with a contact I2C
interface. As the second generation of NXP’s industry leading connected-tag technology, these devices maintain
full backward compatibility with first-generation NTAG I2C products, while adding new, advanced features for
password protection, full memory-access configuration from both interfaces, and an originality signature for
protection against cloning.
The second-generation technology provides four times higher pass-through performance, along with energy
harvesting capabilities, yet NTAG I2C plus devices are optimized for use in entry-level NFC applications and
offer the lowest BoM of any NFC solution.
I2C and NFC communications are based on simple, standard command sets, and are augmented by the
demo board OM5569/NT322E, which includes online reference source code. All that is required is a simple
antenna design, with no or only limited extra components, and there are plenty of reference designs online for
inspiration. NTAG I2C plus development board is certified as NFC Forum Type 2 Tag (Certification ID: 58514).
aaa-030257
SRAM
I2C
0
1
1
0
1
0
EEPROM
Energy harvesting
Event detection
Data
ISO/IEC 14443
Energy
Data
Energy
MCU
Figure 1. Contactless and contact system

<!-- Page 2 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
2   Features and benefits
2.1  Key features
• Interoperability
– ISO/IEC 14443 Part 2 and 3 compliant
– NTAG I2C plus development board is certified as NFC Forum Type 2 Tag (Certification ID: 58514)
– Unique 7 byte UID
– GET_VERSION command for easy identification of chip type and supported features
– Input capacitance of 50 pF
• Host interface
– I2C slave
– Configurable field detection pin based on open-drain implementation to signal NFC events or synchronize
pass-through data transfer
• Memory
– 2k bytes EEPROM
– 64 bytes SRAM buffer for transfer of data between NFC and I2C interfaces with memory mirror or pass-
through mode
– Clear arbitration between NFC and I2C memory access
• Data transfer
– Pass-through mode with 64 byte SRAM buffer
– FAST_WRITE and FAST_READ NFC commands for higher data throughput
• Security and memory-access management
– Full, read-only, or no memory access from NFC interface, based on 32-bit password
– Full, read-only, or no memory access from I2C interface
– NFC silence feature to disable the NFC interface
– Originality signature based on Elliptic Curve Cryptography (ECC) for simple, genuine authentication
• Power Management
– Configurable field-detection output signal for data-transfer synchronization and device wake-up
– Energy harvesting from NFC field, so as to power external devices (e.g. connected microcontroller)
• Industrial requirements
– Temperature range from -40 °C up to 105 °C
2.2  NFC interface
• NFC Forum Type 2 Tag compliant
• Contactless transmission of data at 106 kbit/s
• NTAG I2C plus development board is certified as NFC Forum Type 2 Tag (Certification ID: 58514)
• ISO/IEC 14443A compliant
• Data transfer of 106 kbit/s
• 4 bytes (one page) written including all overhead in 4.8 ms via EEPROM or 0.8 ms via SRAM
• 64 bytes (whole SRAM) written including all overhead in 6.1 ms using FAST_WRITE command
• Data integrity of 16-bit CRC, parity, bit coding, bit counting
• Operating distance of up to 100 mm (depending on various parameters, such as field strength and antenna
geometry)
• True anticollision
• Unique 7 byte serial number (UID) according to ISO/IEC 14443-3
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
2 / 84

<!-- Page 3 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
2.3  Memory
• 2k bytes EEPROM
• 64 bytes SRAM volatile memory without write endurance limitation
• Data retention time of minimum 20 years
• EEPROM write endurance minimum 500.000 cycles
2.4  I2C interface
• I2C slave interface supports frequencies up to 400 kHz
• Fail-safe I2C operation
• I2C slave supports 7-bit slave address.
• As the least significant R/W bit is used to indicate data transfer direction, default slave address 55h
recalculates to an I2C write address AAh and an I2C read address ABh respectively.
• 16 bytes (one block) written in 4 ms (EEPROM) or 0.4 ms (SRAM)
• NTAG I2C plus can be used as standard I2C EEPROM and I2C SRAM
2.5  Security
• Manufacturer-programmed 7-byte UID for each device
• Capability container with one time programmable bits
• Field programmable read-only locking function per page for first 12 pages and per 16 (1k version) or 32 (2k
version) pages for the extended memory section
• ECC-based originality signature
• 32-bit password protection to prevent unauthorized memory operations from NFC perspective may be
enabled for parts of, or complete memory
• Access to password protected data area may be restricted from I2C perspective
• Pass-through and mirror mode operation may be password protected
• Protected data can be safeguarded against limited number of negative password authentication attempts
2.6  Key benefits
• Full interoperability with every NFC-enabled device
• Smooth end-user experience with super-fast data exchange (up to 40 kbit/s) via NFC and I2C interface
• Zero-power operation with non-volatile data storage
• Energy harvesting feature delivers up to 15 mW out of NFC field to power (parts of) host system
• Data protection to prevent unauthorized data manipulation
• Multi-application support, enabled by memory size and segmentation options
• Lowest bill of materials and smallest footprint for NFC wireless charging solution in embedded electronics
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
3 / 84

<!-- Page 4 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
3   Applications
NXP NTAG I2C plus is a family of connected NFC tags that combine a passive NFC interface with a contact
I2C interface. As the second generation of NXP’s industry-leading connected-tag technology, these devices
maintain full backward compatibility with first-generation NTAG I2C products, while adding new, advanced
features for password protection, full memory-access configuration from both interfaces, and an originality
signature for protection against cloning.
The second-generation technology provides four times higher pass-through performance, along with energy
harvesting capabilities, yet NTAG I2C plus devices are optimized for use in NFC applications like:
• IoT nodes (home automation, smart home, etc.)
• Pairing and configuration of consumer applications
• NFC accessories (headsets, speakers, etc.)
• Wearable infotainment
• Fitness equipment
• Consumer electronics
• Healthcare
• Smart printers
• Meters
• Electronic shelf labels
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
4 / 84

<!-- Page 5 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
4   Ordering information
Package
Orderable part
number
Name
Description
Version
NT3H2111W0
FHKH
XQFN8
Plastic, extremely thin quad flat package; no leads; 8 terminals; body 1.6 x
1.6 x 0.5 mm; 1k bytes memory, 50 pF input capacitance; 4000 pcs. on 7''
reel
SOT902-3
NT3H2211W0
FHKH
XQFN8
Plastic, extremely thin quad flat package; no leads; 8 terminals; body 1.6 x
1.6 x 0.5 mm; 2k bytes memory, 50 pF input capacitance; 4000 pcs. on 7''
reel
SOT902-3
NT3H2111W0FTTJ
TSSOP8
Plastic thin shrink small outline package; 8 leads; body width 3 mm; 1k
bytes memory; 50 pF input capacitance; 2500 pcs. on 13'' reel
SOT505-1
NT3H2211W0FTTJ
TSSOP8
Plastic thin shrink small outline package; 8 leads; body width 3 mm; 2k
bytes memory; 50 pF input capacitance; 2500 pcs. on 13'' reel
SOT505-1
NT3H2111W0FT1X
SO8
Plastic small outline package; 8 leads; body width 3.9 mm, 1k bytes
memory; 50 pF input capacitance; 1000 pcs. on 7'' reel
SOT96-1
NT3H2211W0FT1X SO8
Plastic small outline package; 8 leads; body width 3.9 mm, 2k bytes
memory; 50 pF input capacitance; 1000 pcs. on 7'' reel
SOT96-1
Table 1. Ordering information
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
5 / 84

<!-- Page 6 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
5   Marking
Marking code
Orderable part number
Line 1
Line 2
Line 3
NT3H2111W0FHKH
211
-
-
NT3H2211W0FHKH
221
-
-
NT3H2111W0FTTJ
32111
DBSN ASID
YWW
NT3H2211W0FTTJ
32211
DBSN ASID
YWW
NT3H2111W0FT1X
NT32111
DBSN ASID
nDYWW
NT3H2211W0FT1X
NT32211
DBSN ASID
nDYWW
Table 2. Marking codes
Used abbreviations:
DBSN: Diffusion Batch Sequence Number
ASID: Assembly Sequence ID
n: Assembly Centre Code
D: RHF-2006 indicator
Y: year
WW: week
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
6 / 84

<!-- Page 7 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
6   Block diagram
aaa-010358
I2C
SLAVE
I2C
CONTROL
RF
INTERFACE
LA
LB
POWER MANAGEMENT/
ENERGY HARVESTING
DIGITAL CONTROL UNIT
MEMORY
EEPROM
SRAM
ARBITER/STATUS
REGISTERS
ANTICOLLISION
COMMAND
INTERPRETER
MEMORY
INTERFACE
SDA
SCL
GND
FD
Vout
VCC
Figure 2. Block diagram
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
7 / 84

<!-- Page 8 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
7   Pinning information
7.1  Pinning
7.1.1  XQFN8
aaa-021647
FD
Transparent top view
4
8
6
5
7
3
1
2
VSS
LA
SCL
LB
VCC
SDA
VOUT
Figure 3. Pin configuration for XQFN8
Center pad - metal area - not for soldering.
Detailed package and soldering information may be found here.
7.1.2  TSSOP8
aaa-021648
SDA
VCC
VOUT
LB
FD
SCL
VSS
LA
1
2
3
4
6
5
8
7
Figure 4. Pin configuration for TSSOP8
Detailed package and soldering information may be found here.
7.1.3  SO8
LA
LB
VSS
VOUT
SCL
VCC
FD
SDA
aaa-021649
1
2
3
4
6
5
8
7
Figure 5. Pin configuration for SO8
Detailed package and soldering information may be found here.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
8 / 84

<!-- Page 9 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
7.2  Pin description
Pin
Symbol
Description
1
LA
Antenna connection LA
2
VSS
GND
3
SCL
Serial clock I2C
4
FD
Field detection
5
SDA
Serial data I2C
6
VCC
VCC in connection (external power supply)
7
VOUT
Voltage out (energy harvesting)
8
LB
Antenna connection LB
Table 3. Pin description for XQFN8, TSSOP8 and SO8
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
9 / 84

<!-- Page 10 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
8   Functional description
8.1  Block description
The NTAG I2C plus IC consist of EEPROM, SRAM, NFC interface, Digital Control Unit (Command interpreter,
Anticollision, Arbiter/Status registers, I2C control and Memory Interface), Power Management and Energy
Harvesting Unit and an I2C slave interface. Energy and data are transferred via an antenna consisting of a coil
with a few turns, which is directly connected to NTAG I2C plus IC.
8.2  NFC interface
The passive NFC-interface is based on the ISO/IEC 14443-3 Type A standard.
It requires to be supplied by an NFC field (e.g. NFC enabled device) always to be able to receive appropriate
commands and send the related responses.
As defined in ISO/IEC 14443-3 Type A for both directions of data communication, there is one start bit (start of
communication) at the beginning of each frame. Each byte is transmitted with an odd parity bit at the end. The
least significant bit of the byte 0 of the selected block is transmitted first.
For a multi-byte parameter, the least significant byte is always transmitted first. For example, when reading from
the memory using the READ command, byte 0 from the addressed block is transmitted first, followed by bytes 1
to byte 3 out of this block. The same sequence continues for the next block and all subsequent blocks.
8.2.1  Data integrity
The following mechanisms are implemented in the contactless communication link between the NFC device and
the NTAG I2C plus IC to ensure very reliable data transmission:
• 16 bits CRC per block
• Parity bits for each byte
• Bit count checking
• Bit coding to distinguish between "1", "0" and "no information"
• Channel monitoring (protocol sequence and bit stream analysis)
The commands are initiated by the NFC device and controlled by the Digital Control Unit of the NTAG I2C plus
IC. The command response depends on the state of the IC, and for memory operations, the access conditions
valid for the corresponding page.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
10 / 84

<!-- Page 11 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
8.2.2  NFC state machine
PWD_AUTH
SELECT
cascade level 2
SELECT
cascade level 1
WUPA
REQA
WUPA
READY 1
READY 2
ACTIVE
AUTHENTICATED
IDLE
HALT
POR
ANTICOLLISION
HLTA
HLTA
memory
operations
identification
and
selection
procedure
aaa-021650
READ
FAST_READ
WRITE
FAST_WRITE
GET_VERSION
READ_SIG
ANTICOLLISION
READ
FAST_READ
WRITE
PWD_AUTH
GET_VERSION
READ_SIG
Figure 6. NFC state machine of NTAG I2C plus
The overall NFC state machine is summarized in Figure 6. When an error is detected or an unexpected
command is received, in each state the tag returns to IDLE or HALT state as defined in ISO/IEC 14443-3 Type
A.
8.2.2.1  IDLE state
After a Power-On Reset (POR), the NTAG I2C plus switches to the default waiting state, namely the IDLE state.
It exits IDLE towards READY 1 state when a REQA or a WUPA command is received from the NFC device. Any
other data received while in IDLE state is interpreted as an error, and the NTAG I2C plus remains in the IDLE
state.
8.2.2.2  READY 1 state
In the READY 1 state, the NFC device resolves the first part of the UID (3 bytes) using the ANTICOLLISION or
SELECT commands for cascade level 1. READY 1 state is correctly exited after.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
11 / 84

<!-- Page 12 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
• receiving SELECT command from cascade level 1 with the matching of complete first part of the UID. In this
case, the NFC device switches the NTAG I2C plus into READY 2 state where the second part of the UID gets
resolved.
Remark: The response of the NTAG I2C plus to the SELECT command is the Select AcKnowledge (SAK) byte
with cascade bit set to 1b indicating that UID is not complete.
8.2.2.3  READY 2 state
In the READY 2 state, the NFC device resolves the second part of the UID (4 bytes) using the ANTICOLLISION
or SELECT command for cascade level 2. READY2 state is correctly exited after.
• receiving SELECT command from cascade level 2 with the matching of complete second part of the UID.
In this case, the NFC device switches the NTAG I2C plus into ACTIVE state where all application-related
commands can be executed.
Remark: The response of the NTAG I2C plus to the SELECT command in READY 2 state is the Select
AcKnowledge (SAK) byte with cascade bit cleared to indicate, that NTAG I2C plus is now uniquely selected and
only this device will communicate with the NFC device even when other contactless devices are present in the
NFC device field.
8.2.2.4  ACTIVE state
All unprotected memory operations are operated in the ACTIVE and AUTHENTICATED states.
The ACTIVE state is exited with the PWD_AUTH command or with the HLTA command.
Upon reception of a correct password within PWD_AUTH command, the NTAG I2C plus transits to
AUTHENTICATED state after responding with PACK.
With the HLTA command, the NTAG I2C plus transits to the HALT state.
Any other invalid command in ACTIVE state is interpreted as an error. Depending on its previous state, the
NTAG I2C plus returns to either to the IDLE or HALT state.
8.2.2.5  AUTHENTICATED state
Protected memory operations are only operated in the AUTHENTICATED state, however access to the
unprotected memory is possible, too.
The AUTHENTICATED state is exited with the HLTA command and upon reception, the NTAG I2C plus transits
to the HALT state.
Any other invalid command in AUTHENTICATED state is interpreted as an error. Depending on its previous
state, the NTAG I2C plus returns to either to the IDLE or HALT state.
8.2.2.6  HALT state
HALT and IDLE states constitute the two waiting states implemented in the NTAG I2C plus. An already
processed NTAG I2C plus in ACTIVE or AUTHENTICATED state can be set into the HALT state using the HLTA
command. In the anticollision phase, this state helps the NFC device distinguish between processed tags and
tags yet to be selected. The NTAG I2C plus can only exit HALT state upon execution of the WUPA command.
Any other data received when the device is in this state is interpreted as an error, and NTAG I2C plus state
remains unchanged.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
12 / 84

<!-- Page 13 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
8.3  Memory organization
The memory map is detailed in Table 4 (1k memory) and Table 5 (2k memory) from the NFC interface and in
Table 6 (1k memory) and Table 7 (2k memory) from the I2C interface. The SRAM memory is only available and
accessible when powered via VCC. Please refer to Section 11 for examples of memory map from the NFC
interface with SRAM mapping.
The structure of manufacturing data, static and dynamic lock bytes, capability container and user memory
pages are compatible with other NTAG products.
Any memory access which starts at a valid address and extends into an invalid access region will return 00h
value for the invalid region.
Bits and bytes marked as reserved for future use (RFU) SHALL NOT be changed, as it may lead to unintended
tag behavior.
8.3.1  Memory map from NFC perspective
Memory access from the NFC perspective is organized in pages of 4 bytes each. If password protection is not
used, complete user memory is unprotected.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
13 / 84

<!-- Page 14 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
0
0
00h
Serial number (UID)
READ
1
01h
Serial number (UID)
Internal
READ
2
02h
Internal
Static lock bytes
READ/R&W
3
03h
Capability Container (CC)
READ&WRITE
4
04h
...
...
Unprotected user memory
READ&WRITE
AUTH0
AUTH0
...
...
225
E1h
Protected user memory
READ1
READ&WRITE
226
E2h
Dynamic lock bytes
00h
R&W/READ
227
E3h
RFU
RFU
RFU
AUTH0
READ1
READ&WRITE
228
E4h
ACCESS
RFU
RFU
RFU
READ1
READ&WRITE
229
E5h
PWD2
READ1
READ&WRITE
230
E6h
PACK2
RFU
RFU
READ1
READ&WRITE
231
E7h
PT_I2C
RFU
RFU
RFU
READ1
READ&WRITE
232
E8h
233
E9h
Configuration registers
see Table 11
234
EAh
235
EBh
Invalid access - returns NAK
n.a.
236
ECh
237
EDh
Session registers
see Table 12
238
EEh
239
EFh
Invalid access - returns NAK
n.a.
240
F0h
...
...
255
FFh
Invalid access - returns NAK
n.a.
1
...
...
Invalid access - returns NAK
n.a.
2
...
...
Invalid access - returns NAK
n.a.
0
00h
...
...
Invalid access - returns NAK
n.a.
248
F8h
249
F9h
Mirrored session registers
see Table 12
...
...
3
255
FFh
Invalid access - returns NAK
n.a.
1 If NFC_PROT bit is set to 1b, NTAG I2C plus returns NAK, and Password authentication will not be effective.
Table 4. NTAG I2C plus 1k memory organization from the NFC perspective
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
14 / 84

<!-- Page 15 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
2 On reading PWD or PACK, NTAG I2C plus always returns 00h for all bytes
Table 4. NTAG I2C plus 1k memory organization from the NFC perspective...continued
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
15 / 84

<!-- Page 16 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
0
00h
Serial number (UID)
READ
1
01h
Serial number (UID)
Internal
READ
2
02h
Internal
Static lock bytes
READ/R&W
3
03h
Capability Container (CC)
READ&WRITE
4
04h
...
...
Unprotected user memory
READ&WRITE
AUTH0
AUTH0
...
...
225
E1h
Protected user memory
READ1
READ&WRITE
226
E2h
Dynamic lock bytes
00h
R&W/READ
227
E3h
RFU
RFU
RFU
AUTH0
READ1
READ&WRITE
228
E4h
ACCESS
RFU
RFU
RFU
READ1
READ&WRITE
229
E5h
PWD2
READ1
READ&WRITE
230
E6h
PACK2
RFU
RFU
READ1
READ&WRITE
231
E7h
PT_I2C
RFU
RFU
RFU
READ1
READ&WRITE
232
E8h
233
E9h
Configuration registers
see Table 11
234
EAh
235
EBh
Invalid access - returns NAK
n.a.
236
ECh
237
EDh
Session registers
see Table 12
238
EEh
...
...
0
255
FFh
Invalid access - returns NAK
n.a.
0
00h
...
...
1
255
FFh
(Un-)protected user memory3,4
see protected user
memory in Sector 0
2
...
...
Invalid access - returns NAK
n.a.
0
00h
...
...
Invalid access - returns NAK
n.a.
248
F8h
249
F9h
Mirrored session registers
see Table 12
...
...
3
255
FFh
Invalid access - returns NAK
n.a.
1 If NFC_PROT bit is set to 1b, NTAG I2C plus returns NAK, and Password authentication will not be effective.
Table 5. NTAG I2C plus 2k memory organization from the NFC perspective
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
16 / 84

<!-- Page 17 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
2 On reading PWD or PACK, NTAG I2C plus always returns 00h for all bytes
3 If 2K_PROT bit is set to 1b, complete Sector 1 of NTAG I2C plus is password protected
4 If NFC_DIS_SEC1 bit is set to 1b, complete Sector 1 of NTAG I2C plus is not accessible from NFC perspective
Remark: Although NTAG I2C plus is fully compliant to the standard, some outdated mobiles might not parse it well.
Table 5. NTAG I2C plus 2k memory organization from the NFC perspective...continued
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
17 / 84

<!-- Page 18 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
8.3.2  Memory map from I2C interface
The memory access of NTAG I2C plus from the I2C interface is organized in blocks of 16 bytes each.
I2C slave address is stored in most significant 7 bits of byte 0 in block 0. However, when reading block 0, NTAG
I2C plus always returns 04h for byte 0.
WARNING: When configuring Static lock bytes and Capability container, Address byte gets updated, too.
Address byte consists of slave address (coded in most significant 7 bits) and least significant bit set to 0b.
REMARK: For convenience reasons it is recommended to configure Address byte (block 0, byte 0) to 04h.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
18 / 84

<!-- Page 19 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Byte number within a block
Access conditions
0
1
2
3
4
5
6
7
I2C_PROT
I2C block
address
8
9
10
11
Dec.
Hex.
12
13
14
15
00b
01b
1xb
Addr.1
Serial number (UID)
Serial number (UID)
Internal
Internal
Static lock bytes
0
00h
Capability Container (CC)
READ&WRITE
1
01h
...
...
Unprotected user memory
READ&WRITE
AUTH0
AUTH0
...
...
55
37h
Protected user memory
READ&WRITE
READ
NAK
Protected user memory
READ&WRITE
READ
NAK
Dynamic lock bytes
00h
56
38h
RFU
RFU
RFU
AUTH0
ACCESS
RFU
RFU
RFU
PWD2
PACK2
RFU
RFU
57
39h
PT_I2C
RFU
RFU
RFU
READ&WRITE
Configuration
registers
see Table 11
00h
00h
00h
00h
58
3Ah
00h
00h
00h
00h
READ
59
3Bh
...
...
247
F7h
Invalid access - returns NAK
n.a.
248
F8h
...
...
251
FBh
SRAM memory (64 bytes)
READ&WRITE
...
...
Invalid access - returns NAK
n.a.
Session
registers
see Table 12
00h
00h
00h
00h
254
FEh
00h
00h
00h
00h
READ
255
FFh
Invalid access - returns NAK
n.a.
1 The byte 0 of block 0 is always read as 04h (UID0). Writing to block 0 updates the I2C address.
Table 6. NTAG I2C plus 1k memory organization from the I2C perspective
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
19 / 84

<!-- Page 20 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Byte number within a block
Access conditions
0
1
2
3
4
5
6
7
I2C_PROT
I2C block
address
8
9
10
11
Dec.
Hex.
12
13
14
15
00b
01b
1xb
2 On reading PWD and PACK, NTAG I2C plus always returns 00h for all bytes
Table 6. NTAG I2C plus 1k memory organization from the I2C perspective...continued
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
20 / 84

<!-- Page 21 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Byte number within a block
Access conditions
0
1
2
3
4
5
6
7
I2C_PROT
I2C block
address
8
9
10
11
Dec.
Hex.
12
13
14
15
00b
01b
1xb
Addr.1
Serial number (UID)
Serial number (UID)
Internal
Internal
Static lock bytes
0
00h
Capability Container (CC)
READ&WRITE
1
01h
...
...
Unprotected user memory
READ&WRITE
AUTH0
AUTH0
...
...
Protected user memory
READ&WRITE
READ
NAK
Protected user memory
READ&WRITE
READ
NAK
Protected user memory
Dynamic lock bytes
00h
56
38h
RFU
RFU
RFU
AUTH0
ACCESS
RFU
RFU
RFU
PWD2
PACK2
RFU
RFU
57
39h
PT_I2C
RFU
RFU
RFU
READ&WRITE
Configuration
registers
see Table 11
00h
00h
00h
00h
58
3Ah
00h
00h
00h
00h
READ
...
...
Invalid access - returns NAK
n.a.
64
40h
...
...
127
7Fh
(Un-)protected user memory
READ&WRITE
READ
NAK
...
...
Invalid access - returns NAK
n.a.
248
F8h
...
...
251
FBh
SRAM memory (64 bytes)
READ&WRITE
...
...
Invalid access - returns NAK
n.a.
Session
registers
see Table 12
00h
00h
00h
00h
254
FEh
00h
00h
00h
00h
READ
Table 7. NTAG I2C plus 2k memory organization from the I2C perspective
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
21 / 84

<!-- Page 22 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Byte number within a block
Access conditions
0
1
2
3
4
5
6
7
I2C_PROT
I2C block
address
8
9
10
11
Dec.
Hex.
12
13
14
15
00b
01b
1xb
255
FFh
Invalid access - returns NAK
n.a.
1 The byte 0 of block 0 is always read as 04h (UID0). Writing to block 0 updates the I2C address.
2 On reading PWD and PACK, NTAG I2C plus always returns 00h for all bytes
Table 7. NTAG I2C plus 2k memory organization from the I2C perspective...continued
8.3.3  EEPROM
The EEPROM is a non-volatile memory that stores the 7 byte UID, the memory lock conditions, IC configuration
information and the user memory.
Sector 0 memory map looks totally the same for NTAG I2C plus 1k and 2k version, the only difference is the
dynamic lock bit granularity.
NXP introduced with NTAG I2C plus the possibility to split the memory in an open and a password protected
area see Section 8.3.11.
8.3.4  SRAM
For frequently changing data, a volatile memory of 64 bytes with unlimited endurance is built in. The 64 bytes
are mapped in a similar way as done in the EEPROM, i.e., 64 bytes are seen as 16 pages of 4 bytes from NFC
perspective.
The SRAM is only available when the tag is powered via the VCC pin.
The SRAM is located at the end of the memory space and it is always directly accessible by the I2C host
(addresses F8h to FBh). An NFC device cannot access the SRAM memory in normal mode (i.e., outside
the pass-through mode). The SRAM is only accessible by the NFC device if the SRAM is mirrored onto the
EEPROM memory space.
With SRAM mirror enabled (SRAM_MIRROR_ON_OFF = 1b - see Section 11.2), the SRAM can be mirrored in
the User Memory from start page 01h to 74h for access from the NFC side.
The Memory mirror must be enabled once both interfaces are ON as this feature is disabled after each POR.
The register SRAM_MIRROR_BLOCK (see Table 11) indicates the address of the first page of the SRAM buffer.
In the case where the SRAM mirror is enabled and the READ command is addressing blocks where the SRAM
mirror is located, the SRAM byte values will be returned instead of the EEPROM byte values. Similarly, if the tag
is not VCC powered, the SRAM mirror is disabled and reading out the bytes related to the SRAM mirror position
would return the values from the EEPROM.
In the pass-through mode (PTHRU_ON_OFF = 1b - see Table 11), the SRAM is mirrored to the fixed address
F0h - FFh for NFC access (see Section 11) in the first memory sector (Sector 0) of NTAG I2C plus.
8.3.5  Serial number (UID)
The unique 7 byte serial number (UID) is programmed into the first 7 bytes of memory covering page addresses
00h and 01h - see Figure 7. These bytes are programmed and write protected during production.
UID0 is fixed to the value 04h - the manufacturer ID for NXP Semiconductors in accordance with ISO/
IEC 7816-6.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
22 / 84

<!-- Page 23 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
aaa-012802
MSB
LSB
page 0
byte
manufacturer ID for NXP Semiconductors (04h)
0
0
0
0
0
1
0
0
UID0 UID1 UID2 UID3
UID4 UID5 UID6 SAK
page 1
page 2
0
1
2
3
ATQA1
ATQA0
7 bytes UID
lock bytes
Figure 7. Serial number (UID)
8.3.6  Static Lock Bytes
According to NFC Forum Type 2 Tag specification, the bits of byte 2 and byte 3 of page 02h (via NFC) or byte
10 and 11 address 00h (via I2C) represent the field programmable, read-only locking mechanism (see Figure 8).
Each page from 03h (CC) to 0Fh can be individually locked by setting the corresponding locking bit to logic 1b
to prevent further write access. After locking, the corresponding page becomes read-only memory.
This read only locking is address-based. This means, when SRAM is mirrored to these blocks, also SRAM
blocks are read only from NFC perspective.
In addition, NTAG I2C plus uses the three least significant bits of lock byte 0 as the block-locking bits. Bit 2
controls pages 0Ah to 0Fh (via NFC), bit 1 controls pages 04h to 09h (via NFC) and bit 0 controls page 03h
(CC). Once the block-locking bits are set, the locking configuration for the corresponding memory area is frozen,
e.g. cannot be changed to read-only anymore.
L
7
L
6
L
5
L
4
L
CC
BL
15-10
BL
9-4
BL
CC
MSB
0
page 2
Lx locks page x to read-only
BLx blocks further locking for the memory area x
lock byte 0
lock byte 1
1
2
3
LSB
L
15
L
14
L
13
L
12
L
11
L
10
L
9
L
8
MSB
LSB
aaa-006983
Figure 8. Static lock bytes 0 and 1
For example, if BL15-10 is set to logic 1b, then bits L15 to L10 (lock byte 1, bit[7:2]) can no longer be changed.
The static locking and block-locking bits are set by the bytes 2 and 3 of the WRITE command to page 02h. The
contents of the lock bytes are bit-wise OR’ed and the result then becomes the new content of the lock bytes.
This process is irreversible from NFC perspective. If a bit is set to logic 1b, it cannot be changed back to logic
0b. From I2C perspective, the bits can be reset to 0b by writing bytes 10 and 11 of block 00h. As I2C address is
coded in byte 0 of block 0, it may be changed unintentionally.
The contents of bytes 0 and 1 of page 02h (via NFC) are unaffected by the corresponding data bytes of the
WRITE command.
The default value of the static lock bytes is 0000h.
8.3.7  Dynamic Lock Bytes
To lock the pages of NTAG I2C plus starting at page address 16 and onwards, the dynamic lock bytes are used.
The dynamic lock bytes are located in Sector 0 at page E2h. The three lock bytes cover the memory area of
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
23 / 84

<!-- Page 24 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
840 data bytes (NTAG I2C plus 1k) or 1864 data bytes (NTAG I2C plus 2k). The granularity is 16 pages for
NTAG I2C plus 1k (see Figure 9) and 32 pages for NTAG I2C plus 2k (see Figure 10) compared to a single page
for the first 48 bytes.
NTAG I2C plus needs a Lock Control TLV as specified in NFC Forum Type 2 Tag specification to ensure NFC
Forum Type 2 Tag compliancy.
When NFC Forum Type 2 Tag transition to READ ONLY state is intended, all bits marked as RFUI and dynamic
lock bits related to the protected area shall be set to 0b when writing to the dynamic lock bytes.
The default value of the dynamic lock bytes is 000000h. The value of Byte 3 is always 00h.
Like for the static lock bytes, this process of modifying the dynamic lock bits is irreversible from NFC
perspective and applies also for potentially mirrored SRAM. If a bit is set to logic 1b, it cannot be changed back
to logic 0b. From I2C interface, these bits can be set to 0b again.
aaa-008092
0
1
2
3
page 226 (E2h)
LOCK PAGE
128-143
MSB
LSB
bit 7
6
LOCK PAGE
112-127
LOCK PAGE
96-111
LOCK PAGE
80-95
LOCK PAGE
64-79
LOCK PAGE
48-63
LOCK PAGE
32-47
LOCK PAGE
16-31
LOCK PAGE
224-225
5
4
3
2
1
0
RFUI
MSB
LSB
bit 7
6
RFUI
LOCK PAGE
208-223
LOCK PAGE
192-207
LOCK PAGE
176-191
LOCK PAGE
160-175
LOCK PAGE
144-159
5
4
3
2
1
0
RFUI
MSB
LSB
bit 7
6
BL 208-225
BL 176-207
BL 144-175
BL 112-143
BL 80-111
BL 48-79
BL 16-47
5
4
3
2
1
0
Figure 9.  NTAG I2C plus1k  Dynamic lock bytes 0, 1 and 2
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
24 / 84

<!-- Page 25 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
0
1
2
3
page 226 (E2h)
Sector 0
Block Locking (BL) bits
LOCK PAGE
256-271
MSB
LSB
bit 7
6
5
4
3
2
1
0
MSB
LSB
bit 7
6
5
4
3
2
1
0
MSB
LSB
bit 7
6
5
4
3
2
1
0
aaa-021651
LOCK PAGE
208-225
LOCK PAGE
176-207
LOCK PAGE
144-175
LOCK PAGE
112-143
LOCK PAGE
80-111
LOCK PAGE
48-79
LOCK PAGE
16-47
BL 464-511
LOCK PAGE
464-495
LOCK PAGE
496-511
LOCK PAGE
432-463
LOCK PAGE
400-431
LOCK PAGE
368-399
LOCK PAGE
336-367
LOCK PAGE
304-335
LOCK PAGE
272-303
BL 400-463
BL 336-399
BL 272-335
BL 208-271
BL 144-207
BL 80-143
BL 16-79
Figure 10. NTAG I2C plus 2k Dynamic lock bytes 0, 1 and 2
8.3.8  Capability Container (CC)
According to NFC Forum Type 2 Tag specification the CC is located on page 03h. To keep full flexibility to split
the memory into an open and protected area, the default value of the CC is initialized with 00000000h during
the IC production.
NDEF messages can only be written with NFC Forum devices, after setting these CC bytes according to
application-specific needs and NFC Forum specification by a WRITE command from the I2C or NFC interface.
According to NFC Forum specification, a bit once set to 1b, an NFC Forum Device cannot set bits of the CC
back to 0b. However, similar to the lock bits, setting these bits back to 0b is again possible from I2C perspective.
WARNING: As I2C address (byte 0) and static lock bytes (byte 10 and byte 11) are coded in block 00h from I2C
side, the I2C address may be changed or the tag may be locked unintentionally, when changing CC.
REMARK: When reading out byte 0, NTAG I2C plus always returns 04h (UID0). Therefore, for convenience
reasons it is recommended to configure I2C address byte to 04h.
NXP recommends setting the size parameter of the CC only to values that the T2T_Area ends at lock bit
granularity boundaries when using only part of the memory for storing NDEF messages. Consequently
T2T_Area size should be 112 + 64*N or 888 bytes with N less or equal to 13 for the 1k version, or 176 + 128*N
or 2032 bytes with N less or equal to 14 for the 2k version.
In Figure 11 it is shown how the CC is changed when going from READ/WRITE to READ ONLY state according
to NFC Forum.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
25 / 84

<!-- Page 26 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
aaa-021725
byte E1h 10h 6Dh 00h
Example
CC bytes
CC bytes
byte
0
1
2
3
page 3
possible content after initialization
11100001
00010000
01101101
00000000
write command to page 3 over RF
00000000
00000000
00000000
00001111
result in page 3 (read-only state over RF)
11100001
00010000
01101101
00001111
Figure 11. Possible configuration of CC bytes of NTAG I2C plus 1k version
8.3.9  User Memory pages
Pages 04h to E1h of Sector 0 via the NFC interface - Block 01h to 37h, plus the first 8 bytes of block 38h via the
I2C interface is the user memory area for NTAG I2C plus  1k and 2k version.
In addition, complete Sector 1 (page 00h to FFh) via the NFC interface - block 40h to 7Fh via the I2C interface is
used as user memory area for NTAG I2C plus 2k version.
8.3.10  Memory content at delivery
As described above the CC in page 03h is set to all 00h to keep the full flexibility. To allow NFC Forum NDEF
message reading and writing page 03h (CC) and the following data page (NDEF TLV) of NTAG I2C plus need
to be initialized by the user according to the NFC Forum Type 2 Tag specification. Table 8 shows an example of
NFC Forum-compliant content using the whole memory of sector 0 for NDEF messages.
Remark: The default content of the data pages from page 04h onwards is not defined at delivery.
Page Address
Byte number within page
0
1
2
3
03h
E1h
10h
6Dh
00h
04h
03h
00h
FEh
00h
Table 8. Minimum memory content to be in initialized state for NTAG I2C plus
8.3.11  Password and Access Configuration
NTAG I2C plus can be configured to have password protected memory areas.
If this feature is used, NXP recommends changing and diversify the PWD and PACK for every single chip.
The password and access configuration area of pages E3h to E7h (Sector 0 - see Table 9) via the NFC
interface or blocks 38h and 39h via the I2C interface are used to configure the password and access conditions
of the NTAG I2C plus. Those bit values are stored in the EEPROM. Their values can be read and written by both
interfaces when applicable and when not locked by the register lock bits (see REG_LOCK in Table 11).
AUTH0 defines the starting page address of the protected area in Sector 0. NXP recommends setting AUTH0 in
a way always respecting the lock bit granularity. Setting AUTH0 greater EBh, disables password protection.
The NFC_PROT bit is used to either only require a PWD_AUTH for writing data to the protected area or even
protect reading data from the protected area.
If password authentication is used, even the SRAM access can be protected by setting SRAM_PROT bit to 1b.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
26 / 84

<!-- Page 27 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
I2C_PROT enables the possibility to limit access to the protected area from I2C perspective to read only or no
access at all.
AUTLIM value can be used to limit negative PWD_AUTH attempts.
For the 2k version of NTAG I2C plus NFC_DIS_SEC1 bit can be used to disable the access to Sector 1 from
NFC perspective with the 2K_PROT bit password protection for Sector 1 can be enabled.
Once password protection is enabled, writing to Password and Access Configuration bytes is only possible after
a successful password authentication. On reading the PWD or PACK, from NFC or I2C perspective, NTAG I2C
plus always returns all 00h bytes.
A detailed description of the mechanism and how to program all the parameters is given in Section 8.7.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
27 / 84

<!-- Page 28 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
NFC page address
(Sector 0)
I2C block address
Byte number from NFC perspective
Dec
Hex
Dec
Hex
0
1
2
3
224
E0h
225
E1h
User Memory
226
E2h
Dynamic lock bytes
00h
227
E3h
56
38h
RFU
RFU
RFU
AUTH0
228
E4h
ACCESS
RFU
RFU
RFU
229
E5h
PWD
230
E6h
PACK
RFU
RFU
231
E7h
57
39h
PT_I2C
RFU
RFU
RFU
Table 9. Password and Access Configuration Register
Bit
Field
Access
via NFC
Access
via I2C
Default
values
Description
Authentication Pointer (AUTH0)
7-0
AUTH0
R&W
R&W
FFh
Page address of Sector 0 from which onwards the password
authentication is required to access the user memory from NFC
perspective, dependent on NFC_PROT bit.
If AUTH0 is set to a page address greater than EBh, the
password protection is effectively disabled. Password protected
area starts from page AUTH0 and ends at page EBh.
Password protection is excluded for Dynamic Lock Bits, session
registers and mirrored SRAM pages.
REMARK: From I2C interface, you have access to all
configuration pages until REG_LOCK_I2C bit is set to 1b.
Access Conditions (ACCESS)
7
NFC_PROT
R&W
R&W
0b
Memory protection bit:
0b: write access to protected area is protected by the password
1b: read and write access to protected area is protected by the
password
6
RFU
R&W
R&W
0b
RFU - SHALL be 0b
5
NFC_DIS_SEC1
R&W
R&W
0b
NFC access protection to Sector 1
0b: Sector 1 is accessible in 2k version
1b: Sector 1 in inaccessible and returns NAK0
4-3
RFU
R&W
R&W
00b
RFU - SHALL be 00b
2-0
AUTHLIM
R&W
R&W
000b
Limitation of negative password authentication attempts. After
reaching the limit, protected area is not accessible any longer.
000b: limiting of negative password authentication attempts
disabled.
001b-111b: maximum number of negative password
authentication attempts is 2AUTHLIM
Password (PWD)
31-0 PWD
R&W
R&W
FFFFFFFFh 32-bit password used for memory access protection.
Table 10.  Password and Access Configuration bytes
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
28 / 84

<!-- Page 29 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Bit
Field
Access
via NFC
Access
via I2C
Default
values
Description
Reading PWD always returns 00000000h
Password Acknowledge (PACK)
15-0 PACK
R&W
R&W
0000h
16-bit password acknowledge used during the password
authentication process.
Reading PACK always returns 0000h
Protection bits (PT_I2C)
7-4
RFU
R&W
R&W
0000b
RFU - SHALL be 0000b
3
2K_PROT
R&W
R&W
0b
Password protection for Sector 1 for 2k version
0b: password authentication for Sector 1 disabled
1b: password authentication needed to access Sector 1
2
SRAM_PROT
R&W
R&W
0b
Password protection for pass-through and mirror mode
0b: password authentication for pass-through mode disabled
1b: password authentication needed to access SRAM in pass-
through mode
1-0
I2C_PROT
R&W
R&W
00b
Access to protected area from I2C perspective
00b: Entire user memory accessible from I2C
01b: read and write access to unprotected user area, read only
access to protected area
1Xb: read and write access to unprotected area, no access to
protected area.
REMARK: Independent from these bits I2C always has R&W
access to:
• Session registers
• SRAM
• Configuration pages including PWD Configuration area, but
dependent on REG_LOCK_I2C bit
Table 10.  Password and Access Configuration bytes...continued
8.3.12  NTAG I2C plus configuration and session registers
NTAG I2C plus behavior can be configured and read in two separate locations depending if the configurations
shall be effective within the communication session (use session registers) or by default after Power-On Reset
(POR) (use configuration registers).
The configuration registers of pages E8h to E9h (Sector 0 - see Table 11) via the NFC interface or block 3Ah via
the I2C interface are used to configure the default behavior of the NTAG I2C plus. Those bit values are stored in
the EEPROM and represent the default settings to be effective after POR. Their values can be read and written
by both interfaces when applicable and when not locked by the register lock bits (see REG_LOCK in Table 13).
NFC address
(Sector 0)
I2C Address
Byte number from NFC perspective
Dec
Hex
Dec
Hex
0
1
2
3
232
E8h
NC_REG
LAST_NDEF_BLOCK
SRAM_MIRROR_BLOCK
WDT_LS
233
E9h
58
3Ah
WDT_MS
I2C_CLOCK_STR
REG_LOCK
RFU
Table 11. Configuration bytes NTAG I2C plus
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
29 / 84

<!-- Page 30 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
The session register on pages ECh to EDh (Sector 0) via the NFC interface or block FEh via I2C, see Table 12,
are used to configure or monitor the values of the current communication session. Those bits are read only via
the NFC interface but may be read and written via the I2C interface.
For backward compatibility reasons, the session registers are mirrored to Sector 3 (page F8h and F9h via the
NFC interface).
NFC
address
(Sector 0)
I2C Address
Byte number
Dec
Hex
Dec
Hex
0
1
2
3
236
ECh
NC_REG
LAST_NDEF_BLOCK
SRAM_MIRROR _BLOCK
WDT_LS
237
EDh
254
FEh
WDT_MS
I2C_CLOCK_STR
NS_REG
RFU
Table 12. Session bytes NTAG I2C plus
Both, the session and the configuration registers have the same configuration options and parameters except
the REG_LOCK bits, which are only available in the configuration register and the NS_REG bits which are only
available in the session register. After POR, the content of the configuration register is loaded into the session
register.
The values of both registers can be changed during a communication session. If the desired effect should be
visible immediately, but only for the current communication session, the session registers must be used. After
POR, the session registers values will again contain the configuration register values as before.
To change the default behavior, changes to the configuration register are needed, but the related effect will only
be visible after the next POR.
To make the effect immediately and after next POR visible, changes to configuration and session registers are
needed.
All registers and configuration default values, access conditions and descriptions are defined in Table 13 and
Table 14.
Reading and writing the session registers via I2C can only be done via the READ and WRITE registers
operation - see Section 9.8.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
30 / 84

<!-- Page 31 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Bit
Field
Access
via NFC
Access
via I2C
Default
values
Description
Configuration register: NC_REG
7
NFCS_I2C_RST_ON_OFF
R&W
R&W
0b
Enables the NFC disable feature and enables soft
reset through I2C repeated start - see Section 9.3
6
PTHRU_ON_OFF
R&W
R&W
0b
1b: pass-through mode using SRAM enabled and
SRAM mapped to end of Sector 0.
0b: pass-through mode disabled
5-4
FD_OFF
R&W
R&W
00b
defines the event upon which the signal output on the
FD pin is released
00b: if the field is switched off
01b: if the field is switched off or the tag is set to the
HALT state
10b: if the field is switched off or the last page of the
NDEF message has been read (defined in LAST_
NDEF_BLOCK)
11b: (if FD_ON = 11b) if the field is switched off or if
last data is read by I2C (in pass-through mode NFC
---> I2C) or last data is written by I2C (in pass-through
mode I2C---> NFC)
11b: (if FD_ON = 00b or 01b or 10b) if the field is
switched off
See Section 8.4 for more details
3-2
FD_ON
R&W
R&W
00b
defines the event upon which the signal output on the
FD pin is pulled low
00b: if the field is switched on
01b: by first valid start of communication (SoC)
10b: by selection of the tag
11b: (in pass-through mode NFC-->I2C) if the data is
ready to be read from the I2C interface
11b: (in pass-through mode I2C--> NFC) if the data is
read by the NFC interface
See Section 8.4 for more details
1
SRAM_MIRROR_ON_OFF
R&W
R&W
0b
1b: SRAM mirror enabled and mirrored SRAM starts at
page SRAM_MIRROR_BLOCK
0b: SRAM mirror disabled
0
TRANSFER_DIR
R&W
R&W
1b
defines the data flow direction when pass-through
mode is enabled
0b: from I2C to NFC interface
1b: from NFC to I2C interface
In case the pass-through mode is NOT enabled, this
bit should be set to 1b, otherwise there is no WRITE
access from the NFC perspective
Configuration register: LAST_NDEF_BLOCK
7-0
LAST_NDEF_BLOCK
R&W
R&W
00h
I2C block address of I2C block, which contains last
byte(s) of stored NDEF message. An NFC read of the
last page of this I2C block sets the register NDEF_
DATA_READ to 1b and triggers field detection pin if
FD_OFF is set to 10b.
Valid range starts
Table 13.  Configuration bytes
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
31 / 84

<!-- Page 32 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Bit
Field
Access
via NFC
Access
via I2C
Default
values
Description
from 01h (NFC page 04h)
up to 37h (NFC page DCh) NTAG I2C plus 1k
or up to 7Fh (NFC page FCh on Sector 1) forNTAG
I2C plus 2k.
Configuration register: SRAM_MIRROR_BLOCK
7-0
SRAM_MIRROR_BLOCK
R&W
R&W
F8h
I2C block address of SRAM when mirrored into the
User memory.
Valid range starts
from 01h (NFC page 04h)
up to 34h (NFC page D0h) NTAG I2C plus 1k
or up to 7Ch (NFC page F0h on memory Sector 1) for
NTAG I2C plus 2k
Configuration register: WDT_LS
7-0
WDT_LS
R&W
R&W
48h
Least Significant byte of watchdog time control register
Configuration register: WDT_MS
7-0
WDT_MS
R&W
R&W
08h
Most Significant byte of watchdog time control register.
When writing WDT_MS byte, the content of WDT_MS
and WDT_LS gets active for the watchdog timer.
Configuration register: I2C_CLOCK_STR
7-1
RFU
R&W
R&W
0000000b RFU - all 7 bits SHALL be 0b
0
I2C_CLOCK_STR
R&W
R&W
1b
Enables (1b) or disable (0b) the I2C clock stretching
Configuration register: REG_LOCK
7-2
RFU
R&W
R&W
000000b
RFU - all 6 bits SHALL be 0b
1
REG_LOCK_I2C1
R&W
R&W
0b
I2C Configuration Lock Bit
0b: Configuration bytes may be changed via I2C
1b: Configuration bytes cannot be changed via I2C
Once set to 1b, cannot be reset to 0b anymore.
0
REG_LOCK_NFC1
R&W
R&W
0b
NFC Configuration Lock Bit
0b: Configuration bytes may be changed via NFC
1b… Configuration bytes cannot be changed via NFC
Once set to 1b, cannot be reset to 0b anymore.
1 Setting both bits REG_LOCK_I2C and REG_LOCK_NFC to 1b, permanently locks write access to register default values
(as no write is allowed anymore). As long as one bit is still 0b, the corresponding interface can still access and change the
register lock bytes.
Table 13.  Configuration bytes...continued
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
32 / 84

<!-- Page 33 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Bit
Field
Access
via NFC
Access
via I2C
Default
values
Description
Session register: NC_REG
7
NFCS_I2C_RST_ON_OFF
READ
R&W
-
see configuration bytes description
6
PTHRU_ON_OFF
READ
R&W
-
see configuration bytes description, the bit is
cleared automatically, when one of the interfaces
is OFF
5-4
FD_OFF
READ
R&W
-
see configuration bytes description
3-2
FD_ON
READ
R&W
1
SRAM_MIRROR_ON_
OFF
READ
R&W
-
see configuration bytes description, the bit is
cleared automatically, when there is no Vcc power.
0
TRANSFER_DIR
READ
R&W
see configuration bytes description
Session register: LAST_NDEF_BLOCK
7-0
LAST_NDEF_BLOCK
READ
R&W
-
see configuration bytes description
Session register: SRAM_MIRROR_BLOCK
7-0
SRAM_MIRROR_BLOCK
READ
R&W
-
see configuration bytes description
Session register: WDT_LS
7-0
WDT_LS
READ
R&W
-
see configuration bytes description
Session register: WDT_MS
7-0
WDT_MS
READ
R&W
-
see configuration bytes description
Session register: I2C_CLOCK_STR
7-2
RFU
READ
READ
-
RFU, all 6 bits locked to 0b
1
NEG_AUTH_REACHED
READ
READ
0b
Status bit to show the number of negative PWD_
AUTH attempts reached
0b: PWD_AUTH still possible
1b: PWD_AUTH locked
0
I2C_CLOCK_STR
READ
READ
-
See configuration bytes description
Session register: NS_REG
7
NDEF_DATA_READ
READ
READ
0b
1b: all data bytes read from the address specified
in LAST_NDEF_BLOCK. Bit is reset to 0b when
read
6
I2C_LOCKED
READ
R&W
0b
1b: Memory access is locked to the I2C interface
5
RF_LOCKED
READ
READ
0b
1b: Memory access is locked to the NFC interface
4
SRAM_I2C_READY
READ
READ
0b
1b: data is ready in SRAM buffer to be read by I2C
3
SRAM_RF_READY
READ
READ
0b
1b: data is ready in SRAM buffer to be read by
NFC
2
EEPROM_WR_ERR
READ
R&W
0b
1b: HV voltage error during EEPROM write or
erase cycle
Needs to be written back via I2C to 0b to be
cleared
1
EEPROM_WR_BUSY
READ
READ
0b
1b: EEPROM write cycle in progress - access to
EEPROM disabled
Table 14.  Session register bytes
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
33 / 84

<!-- Page 34 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Bit
Field
Access
via NFC
Access
via I2C
Default
values
Description
0b: EEPROM access possible
0
RF_FIELD_PRESENT
READ
READ
0b
1b: NFC field is detected
Table 14.  Session register bytes...continued
8.4  Configurable Field Detection Pin
The field detection pin based on open-drain implementation provides the capability to trigger an external device
(e.g. μController) or switch on the connected circuitry by an external power management unit depending on
activities on the NFC interface.
As the field detection pin functionality is operated via NFC field power, VCC supply for the tag itself is not
required.
NOTE: In some cases VOUT pin might be used as field detection trigger.
The conditions for pulling the field detection signal to low, FD_ON can be:
• The presence of the NFC field
• The detection of a valid command (Start of Communication)
• The selection of the IC
Remark: When FD_ON is configured to trigger on NFC field presence (00b), FD will be pulled low again, when
host is reading the NDEF_DATA_READ bit of NS_REG session register from I2C perspective.
The conditions for releasing the field detection signal defined with FD_OFF can be:
• The absence of the NFC field
• The detection of the HALT state
• The NFC interface has read the last part of the NDEF message defined with LAST_NDEF_BLOCK
All the various combinations of configurations are described in Table 13 and illustrated in the Figures below for
all various combinations of the field detection signal configuration. The timing diagrams are not in scale and all
given timing values are typical values.
The field detection pin can be used also as a handshake mechanism in the pass-through mode to signal to the
external μController if
• New data is written to SRAM on the NFC interface
• Data written to SRAM from the μController is read via the NFC interface.
See Section 11 for more information on this handshake mechanism.
In Figure 12 an example how to connect the FD pin is given. All given values are typical values and may vary
from application to application.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
34 / 84

<!-- Page 35 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
LA
LB
VSS
VOUT
SCL
GND
VCC
FD
event detect signal
APPLICATION
SDA
aaa-021652
1
2
3
4
6
5
8
7
Rpu
>2 kΩ
supply
(1.2 V ~ 3.6 V)
Figure 12. FD pin example circuit
aaa-021653
RF field
switches ON
First valid start of
communication
Tag selected
Tag set to HALT
RF field
switches OFF
ON
OFF
HIGH
LOW
RF field
FD pin
Event
0
01h
t
0
FD_ON = 00b
FD_OFF = 00b
NC_REG
RF_FIELD_PRESENT
NS_REG
1
Figure 13. Illustration of the field detection feature when configured for simple field detection
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
35 / 84

<!-- Page 36 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
aaa-021654
RF field
switches ON
First valid start of
communication
Tag selected
RF field
switches OFF
ON
OFF
HIGH
LOW
RF field
FD pin
Event
0
15h
t
0
FD_ON = 01b
FD_OFF = 01b
NC_REG
RF_FIELD_PRESENT
NS_REG
Start of HALT
command
1
Figure 14. Illustration of the field detection feature when configured for first valid start of communication
detection
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
36 / 84

<!-- Page 37 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
aaa-021655
RF field
switches ON
First valid start of
communication
RF field
switches OFF
ON
OFF
HIGH
LOW
RF field
FD pin
Event
0
29h
t
0
FD_ON = 10b
FD_OFF = 10b
NC_REG
RF_FIELD_PRESENT
NS_REG
Start of SEL CL2
command
Start of READ of last
page of NDEF msg.
1
Figure 15. Illustration of the field detection feature when configured for selection of the tag detection
8.5  Watchdog timer
In order to allow the I2C interface to perform all necessary commands (READ, WRITE, ..), the memory access
remains locked to the I2C interface until the register I2C_LOCKED is cleared by the host - see Table 13.
However, to avoid that the memory stays 'locked' to the I2C for a long period of time, it is possible to program
a watchdog timer to unlock the I2C host from the tag, so that the NFC device can access the tag after a period
of time of inactivity. The host itself will not be notified of this event directly, but the NS_REG register is updated
accordingly (the register bit I2C_LOCKED will be cleared - see Table 13).
The default value is set to 20 ms (848h), but the watchdog timer can be freely set from 0001h (9.43 μs) up to
FFFFh (617.995 ms). The timer starts ticking when the communication between the NTAG I2C plus and the I2C
interface starts. In case the communication with the I2C is still going on after the watchdog timer expires, the
communication will continue until the communication has completed. Then the status register I2C_LOCKED will
be immediately cleared.
In the case where the communication with the I2C interface has completed before the end of the timer and the
status register I2C_LOCKED was not cleared by the host, it will be cleared at the end of the watchdog timer.
The watchdog timer is only effective if the VCC pin is powered and will be reset and stopped if the NTAG I2C
plus is not VCC powered or if the register status I2C_LOCKED is set to 0 and RF_LOCKED is set to 1b.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
37 / 84

<!-- Page 38 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
8.6  Energy harvesting
The NTAG I2C plus provides the capability to supply external low-power devices with energy harvested from the
NFC field of an NFC device as illustrated in Figure 16. All given values are typical values. For more details, refer
to the energy harvesting application note.
The voltage and current from the energy harvesting depend on various parameters, such as the strength of the
NFC field, the tag antenna size, or the distance from the NFC device. NTAG I2C plus provides typically 5 mA at
2 V on the VOUT pin with an NFC Phone.
Operating NTAG I2C plus in energy harvesting mode requires a number of precautions:
• A complete total connected capacitor in the range of typically 150 nF up to 220 nF maximum shall be
connected between VOUT and GND close to the terminals to ensure that the voltage does not drop below
VCC min during modulation or during any application operation.
• Start up load current on VOUT should be limited until sufficient voltage is built on VOUT.
• If NTAG I2C plus also powers the I2C bus, then VCC must be connected to VOUT, and pull-up resistors on
the SCL and SDA pins must be sized to control SCL and SDA sink current when those lines are pulled low by
NTAG I2C plus or the I2C host
• If NTAG I2C plus also powers the Field Detect bus, then the pull-up resistor on the Field Detect line must be
sized to control the sink current into the Field Detect pin when NTAG I2C plus pulls it low
• The NFC reader device communicating with NTAG I2C plus shall apply polling cycles including an NFC Field
Off condition of at least 5.1 ms as defined in NFC Forum Activity specification.
REMARK: increasing the output current on Vout decreases the NFC communication range.
LA
LB
VSS
VOUT
SCL
VCC
FD
event detect signal
SDA
SCL
GND
SDA
aaa-021656
1
4
3
2
8
5
6
7
Rpu
>5 kΩ
Rpu
>5 kΩ
Rpu
>5 kΩ
supply
(2.2 V ~ 3 V)
Cload
150 nF ~ 220 nF
APPLICATION
Figure 16. Energy harvesting example circuit
8.7  Password authentication
The memory write or read/write access to a configurable part of the memory can be constrained to a positive
password authentication. The 32-bit secret password (PWD) and the 16-bit password acknowledge (PACK)
response shall be typically programmed into the configuration pages at the tag personalization stage.
The AUTHLIM parameter specified in Table 10 can be used to limit the negative authentication attempts.
In the initial state of NTAG I2C plus, password protection is disabled by an AUTH0 value of FFh. PWD and
PACK are freely writable in this state. Access to the configuration pages and any part of the user memory can
be restricted by setting AUTH0 to a page address within the available memory space. This page address is the
first one protected.
For a comprehensive description of all protection mechanism, refer to the application note.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
38 / 84

<!-- Page 39 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Remark: The password protection method provided in NTAG I2C plus has to be intended as an easy
and convenient way to prevent unauthorized memory accesses. If a higher level of protection is required,
cryptographic methods can be implemented at application layer to increase overall system security.
8.7.1  Programming of PWD and PACK
The 32-bit PWD and the 16-bit PACK need to be programmed into the configuration pages, see Table 9. The
password as well as the password acknowledge are written LSByte first. This byte order is the same as the byte
order used during the PWD_AUTH command and its response.
The PWD and PACK bytes can never be read out of the memory. Instead of transmitting the real value on any
valid read command from both - NFC and I2C - interface, only 00h bytes are replied.
If the password authentication is disabled, PWD and PACK can be written at any time.
If the password authentication is enabled, PWD and PACK can be written after a successful PWD_AUTH
command only.
Remark: To improve the overall system security, it is advisable to diversify the password and the password
acknowledge using a die individual parameter of the IC, which can be the 7 byte UID available on NTAG I2C
plus.
8.7.2  Limiting negative verification attempts
To prevent brute-force attacks on the password, the maximum allowed number of negative password
authentication attempts can be set using AUTHLIM. This mechanism is disabled by setting AUTHLIM to a value
of 000b, which is also the initial state of NTAG I2C plus.
If AUTHLIM is not equal to 000b, each negative authentication verification is internally counted. As soon as
this internal counter reaches the number 2AUTHLIM, any further negative password authentication leads to a
permanent locking of the protected part of the memory for the specified access modes. Independently, whether
the provided password is correct or not, each subsequent PWD_AUTH fails.
Any successful password verification, before reaching the limit of negative password verification attempts,
resets the internal counter to zero.
8.7.3  Protection of configuration segments
The configuration pages can be protected by the password authentication as well. The protection level is
defined with the NFC_PROT bit.
The protection is enabled by setting the AUTH0 byte (see Table 9) to a value that is within the addressable
memory space.
8.8  Originality signature
NTAG I2C plus features a cryptographically supported originality check. With this feature, it is possible to
verify that the tag is using an IC manufactured by NXP Semiconductors. This check can be performed on
personalized tags as well.
NTAG I2C plus digital signature is based on standard Elliptic Curve Cryptography (ECC), according to the
ECDSA algorithm. The use of a standard algorithm and curve ensures easy software integration of the
originality check procedure in an application running on an NFC device without specific hardware requirements.
Each NTAG I2C plus UID is signed with an NXP private key and the resulting 32-byte signature is stored in a
hidden part of the NTAG I2C plus memory during IC production.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
39 / 84

<!-- Page 40 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
This signature can be retrieved using the READ_SIG command and can be verified in the NFC device by using
the corresponding ECC public key provided by NXP. In case the NXP public key is stored in the NFC device, the
complete signature verification procedure can be performed offline.
To verify the signature (for example with the use of the public domain crypto library OpenSSL) the tool domain
parameters shall be set to secp128r1, defined within the standards for elliptic curve cryptography SEC.
Details on how to check the signature value are provided in corresponding application note. It is foreseen to
offer not only offline, as well as online way to verify originality of NTAG I2C plus.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
40 / 84

<!-- Page 41 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
9   I2C commands
For details about I2C interface, refer to the NXP user manual.
SCL
SDA
SCL
1
2
3
7
8
9
1
2
3
7
8
9
ACK
MSB
ACK
MSB
Start
Condition
SDA
Input
SDA
Change
Stop
Condition
Stop
Condition
Start
Condition
SDA
SCL
SDA
001aao231
Figure 17. I2C bus protocol
The NTAG I2C plus supports the I2C protocol. This protocol is summarized in Figure 17. Any device that sends
data onto the bus is defined as a transmitter, and any device that reads the data from the bus is defined as a
receiver. The device that controls the data transfer is known as the "bus master", and the other as the "slave"
device. A data transfer can only be initiated by the bus master, which will also provide the serial clock for
synchronization. The NTAG I2C plus is always a slave in all communications.
9.1  Start condition
Start is identified by a falling edge of Serial Data (SDA), while Serial Clock (SCL) is stable in the high state.
A Start condition must precede any data transfer command. The NTAG I2C plus continuously monitors SDA
(except during a Write cycle) and SCL for a Start condition, and will not respond unless one is given.
9.2  Stop condition
Stop is identified by a rising edge of SDA while SCL is stable and driven high. A Stop condition terminates
communication between the NTAG I2C plus and the bus master. A Stop condition at the end of a Write
command triggers the internal Write cycle.
WARNING: Host shall respect EEPROM programming time (~4 ms) after this Stop condition in any case. If
host sends next command too early, the memory may be corrupted as ongoing EEPROM write cycle might get
terminated.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
41 / 84

<!-- Page 42 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
9.3  I2C soft reset and NFC disable feature
With the bit NFCS_I2C_RST_ON_OFF (see Table 13) NTAG I2C plus enables two features: a soft reset of the
I2C subsystem, and NFC disable, in which the NFC demodulator is disabled.
The I2C soft reset feature interprets an I2C repeated start (no I2C stop in between) as a command to execute a
soft reset of the I2C subsystem. This is useful when heavy bus interference can cause the I2C interface to get
stuck. A drawback of this feature is that every start symbol then has to be terminated with a Stop, slowing down
communication. If a Stop is forgotten, the I2C interface is cleared and previous communication, if any, is lost.
Consequently when this feature is used, stop conditions after MEMA for READ/WRITE (see Figure 18) and after
REGA for READ/WRITE registers (see Figure 19) shall be send.
The NFC disable feature disables the demodulator. When feature is set, no NFC commands are received, and
no replies are issued to commands that were not fully received when NFC disable was set. This feature allows
the tag to "disappear" even if it still is in the reader field. NTAG I2C plus will remain in the ISO state it was in
when NFC disable was enabled, until NFC disable is cleared.
The combination of these two features in a single bit means that I2C soft reset is only active during NFC disable.
9.4  Acknowledge bit (ACK)
The acknowledge bit is used to indicate a successful byte transfer. The bus transmitter, whether it is the bus
master or slave device, releases Serial Data (SDA) after sending 8 bits of data. During the ninth clock pulse
period, the receiver pulls Serial Data (SDA) low to acknowledge the receipt of the 9th data bits.
9.5  Data input
During data input, the NTAG I2C plus samples SDA on the rising edge of SCL. For correct device operation,
SDA must be stable during the rising edge of SCL, and the SDA signal must change only when SCL is driven
low.
9.6  Addressing
To start communication between a bus master and the NTAG I2C plus slave device, the bus master must initiate
a Start condition (see Section 9.1). Following this initiation, the bus master sends the 7-bit device address,
called Slave Address (SA) in following figures.
The 8th bit is the Read/Write bit (R/W). This bit is set to 1b for Read and 0b for Write operations.
Default device address of 55h results in AAh default I2C write address and ABh default I2C read address.
As from I2C perspective I2C address can be configured via byte 0 of block 0. Reading this block gives 04h, as it
is returning UID0 (see Section 8.3.2). Therefore it is recommended to us 04h as I2C write address (02h device
address).
NOTE: Byte 0 of block 0 is used to configure the device address. The 7-bit device address needs to be
programmed in the 7 most significant bits of this byte. Least significant bit needs to be set to 0b when
programming the device address. E.g. to keep default device address of 55h, byte 0 of block 0 needs to be set
to AAh.
If a match occurs on the device address, the NTAG I2C plus gives an acknowledgment on SDA during the 9th
bit time. If the NTAG I2C plus address does not match, it deselects itself from the bus and clears the register
I2C_LOCKED (see Table 14).
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
42 / 84

<!-- Page 43 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Device / Slave Address (SA)
R/W
b7
b6
b5
b4
b3
b2
b1
b0
Value [1]
1
0
1
0
1
0
1
1/0
Table 15. Default NTAG I2C plus address from I2C
[1]
Initial values can be changed from I2C perspective
The I2C address of the NTAG I2C plus (byte 0 - block 0h) can only be modified by the I2C interface. Both
interfaces cannot read the device address and a READ command from the NFC or I2C interface to this byte will
return 04h (UID 0 - manufacturer ID for NXP Semiconductors - see Figure 7).
9.7  READ and WRITE Operation
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
43 / 84

<!-- Page 44 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
aaa-012811
7 bits SA and `0'
Host
Tag
Tag
Start
Stop
Stop
D0
D1
D0
D1
D15
D15
MEMA
A
A
A
A
A
A
A
A
A
7 bits SA and `0'
Host
Start
Write:
Read:
7 bits SA and `1'
Start
Stop
MEMA
A
A
Figure 18. I2C READ and WRITE operation
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
44 / 84

<!-- Page 45 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
The READ and WRITE operation always handle 16 bytes to be read or written (one block - see Table 6)
For the READ operation (see Figure 18), following a Start condition, the bus master/host sends the NTAG I2C
plus slave address code (SA - 7 bits) with the Read/Write bit (R/W) set to 0b. The NTAG I2C plus acknowledges
this (A), and waits for one address byte (MEMA), which should correspond to the address of the block of
memory (SRAM or EEPROM) that is intended to be read. The NTAG I2C plus responds to a valid address byte
with an acknowledge (A). A Stop condition can be then issued. Then the host again issues a start condition
followed by the NTAG I2C plus slave address with the Read/Write bit set to 1b. When I2C_CLOCK_STR is set
to 0b, a pause of at least 50 μs shall be kept before this start condition. The NTAG I2C plus acknowledges this
(A) and sends the first byte of data read (D0).The bus master/host acknowledges it (A) and the NTAG I2C plus
will subsequently transmit the following 15 bytes of memory read with an acknowledge from the host after every
byte. After the last byte of memory data has been transmitted by the NTAG I2C plus, the bus master/host will
acknowledge it and issue a Stop condition.
WARNING: READ sequence shall be atomic. Complete sequence of above figure needs to be executed,
otherwise that tag may go to undefined state and stretches the clock infinitely.
For the WRITE operation (see Figure 18), following a Start condition, the bus master/host sends the NTAG I2C
plus slave address code (SA - 7 bits) with the Read/Write bit (R/W) set to 0b. The NTAG I2C plus acknowledges
this (A), and waits for one address byte (MEMA), which should correspond to the address of the block of
memory (SRAM or EEPROM) that is intended to be written. The NTAG I2C plus responds to a valid address
byte with an acknowledge (A) and, in the case of a WRITE operation, the bus master/host starts transmitting
every 16 bytes (D0...D15) that shall be written at the specified address with an acknowledge of the NTAG I2C
plus after each byte (A). After the last byte acknowledge from the NTAG I2C plus, the bus master/host issues a
Stop condition.
WARNING: Host shall respect EEPROM programming time (~4 ms) after this Stop condition in any case. If
host sends next command too early, the memory may be corrupted as ongoing EEPROM write cycle will get
terminated.
The memory address accessible via the READ and WRITE operations can only correspond to the EEPROM or
SRAM (respectively 00h to 3Ah or F8h to FBh for NTAG I2C plus 1k and 00h to 7Ah or F8h to FBh for NTAG I2C
plus 2k).
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
45 / 84

<!-- Page 46 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
9.8   WRITE and READ register operation
In order to modify or read the session register bytes (see Table 12), NTAG I2C plus requires the WRITE and
READ register operation (see Figure 19).
aaa-012812
7 bits SA and `0'
Host
Tag
Tag
Start
Stop
MEMA
REGA
A
A
A
A
7 bits SA and `0'
Host
Start
Write:
Read:
7 bits SA and `1'
Start
Stop
Stop
MEMA
MASK
REGDAT
REGDAT
A
REGA
A
A
A
A
A
Figure 19. WRITE and READ register operation
For the READ register operation, following a Start condition the bus master/host sends the NTAG I2C plus slave
address code (SA - 7 bits) with the Read/Write bit (R/W) set to 0b. The NTAG I2C plus acknowledges this (A),
and waits for one address byte (MEMA) which corresponds to the address of the block of memory with the
session register bytes (FEh). The NTAG I2C plus responds to the address byte with an acknowledge (A). Then
the bus master/host issues a register address (REGA), which corresponds to the address of the targeted byte
inside the block FEh (00h, 01h...to 07h) and then waits for the Stop condition.
Then the bus master/host again issues a start condition followed by the NTAG I2C plus slave address with the
Read/Write bit set to 1b. The NTAG I2C plus acknowledges this (A), and sends the selected byte of session
register data (REGDAT) within the block FEh. The bus master/host will acknowledge it and issue a Stop
condition.
WARNING: READ sequence shall be atomic. Complete sequence of above figure needs to be executed,
otherwise that tag may go to undefined state and stretches the clock infinitely.
For the WRITE register operation, following a Start condition, the bus master/host sends the NTAG I2C plus
slave address code (SA - 7 bits) with the Read/Write bit (R/W) set to 0b. The NTAG I2C plus acknowledges
this (A), and waits for one address byte (MEMA), which corresponds to the address of the block of memory
within the session register bytes (FEh). After the NTAG I2C plus acknowledge (A), the bus master/host issues
a register address (REGA), which corresponds to the address of the targeted byte inside the block FEh (00h,
01h...to 07h). After acknowledgment (A) by NTAG I2C plus, the bus master/host issues a MASK byte that
defines exactly which bits shall be modified by a 1b bit value at the corresponding bit position. Following the
NTAG I2C plus acknowledge (A), the new register data (one byte - REGDAT) to be written is transmitted by the
bus master/host. The NTAG I2C plus acknowledges it (A), and the bus master/host issues a stop condition.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
46 / 84

<!-- Page 47 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
10   NFC Command
NTAG I2C plus activation follows the ISO/IEC 14443-3 Type ANFC Forum Activity specification. After NTAG
I2C plus has been selected, it can either be deactivated using the ISO/IEC 14443 HALT command, or NTAG
commands (e.g. READ_SIG, PWD_AUTH, SECTOR_SELECT, READ or WRITE) can be performed. For more
details about the card activation, refer to ISO/IEC 14443-3 or NFC Forum Activity specification.
10.1  NTAG I2C plus command overview
All available commands for NTAG I2C plus are shown in Table 16.
Command [1]
ISO/IEC 14443
NFC Forum
Command code
(hexadecimal)
Request
REQA
SENS_REQ
26h (7 bit)
Wake-up
WUPA
ALL_REQ
52h (7 bit)
Anticollision CL1
Anticollision CL1
SDD_REQ CL1
93h 20h
Select CL1
Select CL1
SEL_REQ CL1
93h 70h
Anticollision CL2
Anticollision CL2
SDD_REQ CL2
95h 20h
Select CL2
Select CL2
SEL_REQ CL2
95h 70h
Halt
HLTA
SLP_REQ
50h 00h
GET_VERSION
-
-
60h
READ
-
READ
30h
FAST_READ
-
-
3Ah
WRITE
-
WRITE
A2h
FAST_WRITE
-
-
A6h
SECTOR_SELECT
-
SECTOR_SELECT
C2h
PWD_AUTH
-
-
1Bh
READ_SIG
-
-
3Ch
Table 16. Command overview
[1]
Unless otherwise specified, all commands use the coding and framing as described in ISO/IEC 14443 or NFC Forum Digital specification.
10.2  Timing
The command and response timing shown in this document are not to scale and values are rounded to 1 μs.
All given command and response times refer to the data frames, including start of communication and end
of communication. They do not include the encoding (like the Miller pulses). An NFC device data frame
contains the start of communication (1 "start bit") and the end of communication (one logic 0 + 1-bit length of
unmodulated carrier). An NFC tag data frame contains the start of communication (1 "start bit") and the end of
communication (1-bit length of no subcarrier).
The minimum and maximum command response time is specified according to the standard. The minimum
frame delay time from NFC tag to NFC device is 86.43 μs. The maximum command response time is specified
as a timeout value. Depending on the command, the TACK value specified for command responses defines the
NFC device to NFC tag frame delay time. It does it for either the 4-bit ACK value specified or for a data frame.
All timing can be measured according to the ISO/IEC 14443-3 frame specification as shown for the Frame
Delay Time in Figure 20. For more details, refer to ISO/IEC 14443 or NFC Forum specification.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
47 / 84

<!-- Page 48 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
last data bit transmitted by the NFC device
FDT = (n* 128 + 84)/fc
first modulation of the NFC TAG
FDT = (n* 128 + 20)/fc
aaa-006986
128/fc
logic „1“
128/fc
logic „0“
256/fc
end of communication (E)
256/fc
end of communication (E)
128/fc
start of
communication (S)
communication (S)
128/fc
start of
Figure 20. Frame Delay Time (from NFC device to NFC tag), TACK and TNAK
Remark: Due to the coding of commands, the measured timings usually exclude (a part of) the end of
communication. Consider this factor when comparing the specified with the measured times.
10.3  NTAG ACK and NAK
NTAG I2C plus uses a 4-bit ACK / NAK as shown in Table 17.
Code (4 bit)
ACK/NAK
Ah
Acknowledge (ACK)
0h
NAK for invalid argument (i.e. invalid page address or wrong password)
1h
NAK for parity or CRC error
3h
NAK for Arbiter locked to I2C
4h
Number of negative PWD_AUTH commands limit reached
7h
NAK for EEPROM write error
Table 17. ACK and NAK values
10.4  ATQA and SAK responses
NTAG I2C plus replies to a REQA or WUPA command with the ATQA value shown below. It replies to a Select
CL2 command with the SAK value shown below. The 2 byte ATQA value is transmitted with the least significant
byte first (44h).
Bit number
Sales type
Hex value
15
14
13
12
11
10
9
8
7
6
5
4
3
2
1
0
NTAG I2C plus
00 44h
0
0
0
0
0
0
0
0
0
1
0
0
0
1
0
0
Table 18. ATQA response of the NTAG I2C plus
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
48 / 84

<!-- Page 49 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Bit number
Sales type
Hex value
7
6
5
4
3
2
1
0
NTAG I2C plus
00h
0
0
0
0
0
0
0
0
Table 19. SAK response of the NTAG I2C plus
Remark: The ATQA coding in bits 7 and 6 indicates the UID size according to ISO/IEC 14443.
Remark: The bit numbering in ISO/IEC 14443 specification starts with bit 1 as least significant bit.
10.5  GET_VERSION
The GET_VERSION command is used to retrieve information about the NTAG family, the product version,
storage size and other product data required to identify the specific NTAG I2C plus.
This command is also available on other NTAG products to have a common way of identifying products across
platforms and evolution steps.
The GET_VERSION command has no arguments and returns the version information for the specific NTAG I2C
plus type. The command structure is shown in Figure 21 and Table 20.
Table 21 shows the required timing.
CRC
CRC
NFC device
Cmd
Data
NTAG ,,ACK''
283 µs
868 µs
NTAG ,,NAK''
NAK
Time out
TTimeOut
TNAK
TACK
57 µs
aaa-006987
Figure 21. GET_VERSION command
Name
Code
Description
Length
Cmd
60h
Get product version
1 byte
CRC
-
CRC according to ISO/IEC 14443
2 bytes
Data
-
Product version information
8 bytes
NAK
see Table 17
see Section 10.3
4 bit
Table 20. GET_VERSION command
These times exclude the end of communication of the NFC device.
TACK/NAK min
TACK/NAK max
TTimeOut
GET_VERSION
n=9 [1]
TTimeOut
5 ms
Table 21. GET_VERSION timing
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
49 / 84

<!-- Page 50 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
[1]
Refer to Section 10.2.
Byte no.
Description
NTAG I2C plus 512
NTAG I2C plus 1k
NTAG I2C plus 2k
Interpretation
0
fixed Header
00h
00h
00h
1
vendor ID
04h
04h
04h
NXP
Semiconductors
2
product type
04h
04h
04h
NTAG
3
product subtype
05h
05h
05h
50 pF I2C, Event
detection
4
major product
version
02h
02h
02h
5
minor product
version
02h
02h
02h
6
storage size
12h
13h
15h
see following
information
7
protocol type
03h
03h
03h
ISO/IEC 14443-3
compliant
Table 22. GET_VERSION response
The most significant 7 bits of the storage size byte are interpreted as an unsigned integer value n. As a result,
it codes the total available user memory size as 2n. If the least significant bit is 0b, the user memory size is
exactly 2n. If the least significant bit is 1b, the user memory size is between 2n and 2n+1.
10.6  READ_SIG
The READ_SIG command returns an IC specific, 32-byte ECC signature, to verify NXP Semiconductors as
the silicon vendor. The signature is programmed at chip production and cannot be changed afterwards. The
command structure is shown in Figure 24 and Table 27.
Table 28 shows the required timing.
CRC
CRC
Addr
NFC device
Cmd
Data
NTAG ,,ACK''
368 µs
2907 µs
NTAG ,,NAK''
NAK
Time out
TTimeOut
TNAK
TACK
57 µs
aaa-021657
Figure 22. READ_SIG command
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
50 / 84

<!-- Page 51 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Name
Code
Description
Length
Cmd
3Ch
read ECC signature
1 byte
Addr
00h
RFU, is set to 00h
1 byte
CRC
-
CRC according to ISO/IEC 14443
2 bytes
Signature
-
ECC Signature
32 bytes
NAK
see Table 17
see Section 10.3
4 bit
Table 23. READ_SIG command
These times exclude the end of communication of the NFC device.
TACK/NAK min
TACK/NAK max
TTimeOut
READ_SIG
n=9 [1]
TTimeOut
5 ms
Table 24. READ_SIG timing
[1]
Refer to Section 10.2 "Timing".
Details on how to check the signature value are provided in the corresponding application note. It is foreseen to
offer an online and offline way to verify originality of NTAG I2C plus.
10.7  PWD_AUTH
A protected memory area can be accessed only after a successful password verification using the PWD_AUTH
command. The AUTH0 configuration byte defines the start of the protected area. It specifies the first page that
the password mechanism protects. The level of protection can be configured using the NFC_PROT bit either
for write protection or read/write protection. The PWD_AUTH command takes the password as parameter and,
if successful, returns the password authentication acknowledge, PACK. By setting the AUTHLIM configuration
bits to a value larger than 000b, the number of unsuccessful password verifications can be limited. Each
unsuccessful authentication is then counted. After reaching the limit (2AUTHLIM) of unsuccessful attempts, the
memory write access or the memory access at all (specified in NFC_PROT) to the protected area, is no longer
possible. The PWD_AUTH command is shown in Figure 23 and Table 25.
Table 26 shows the required timing.
CRC
CRC
NFC device
Cmd
NTAG ,,ACK''
623 µs
NTAG ,,NAK''
NAK
Time out
TTimeOut
TNAK
TACK
57 µs
PACK
368 µs
Pwd
aaa-021658
Figure 23. PWD_AUTH command
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
51 / 84

<!-- Page 52 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Name
Code
Description
Length
Cmd
1Bh
password authentication
1 byte
Pwd
-
password
4 bytes
CRC
-
CRC according to ISO/IEC 14443
2 bytes
PACK
-
password authentication acknowledge
2 bytes
NAK
see Table 17
see Section 10.3
4-bit
Table 25. PWD_AUTH command
These times exclude the end of communication of the NFC device.
TACK/NAK min
TACK/NAK max
TTimeOut
PWD_AUTH
n=9 [1]
TTimeOut
5 ms
Table 26. PWD_AUTH timing
[1]
Refer to Section 10.2.
Remark: It is strongly recommended to change - and diversify for each tag - the password and PACK from its
delivery state at tag issuing.
10.8  READ
The READ command requires a start page address, and returns the 16 bytes of four NTAG I2C plus pages. For
example, if address (Addr) is 03h then pages 03h, 04h, 05h, 06h are returned. Special conditions apply if the
READ command address is near the end of the accessible memory area. For details on those cases and the
command structure, refer to Figure 24 and Table 27.
Table 28 shows the required timing.
CRC
CRC
Addr
NFC device
Cmd
Data
NTAG ,,ACK''
368 µs
1548 µs
NTAG ,,NAK''
NAK
Time out
TTimeOut
TNAK
TACK
57 µs
aaa-006988
Figure 24. READ command
Name
Code
Description
Length
Cmd
30h
read four pages
1 byte
Addr
-
start page address
1 byte
CRC
-
CRC according to ISO/IEC 14443
2 bytes
Table 27. READ command
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
52 / 84

<!-- Page 53 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Name
Code
Description
Length
Data
-
Data content of the addressed pages
16 bytes
NAK
see Table 17
see Section 10.3
4 bit
Table 27. READ command...continued
These times exclude the end of communication of the NFC device.
TACK/NAK min
TACK/NAK max
TTimeOut
READ
n=9 [1]
TTimeOut
5 ms
Table 28. READ timing
[1]
Refer to Section 10.2.
In the initial state of NTAG I2C plus, all memory pages are allowed as Addr parameter to the READ command:
• Page address from 00h to E9h and pages ECh and EDh for NTAG I2C plus 1k and 2k
• Page address from 00h to FFh (Sector 1) for NTAG I2C plus 2k only
• SRAM buffer address when pass-through mode is enabled
Addressing a start memory page beyond the limits above results in a NAK response from NTAG I2C plus.
In case a READ command addressing start with a valid memory area but extends over an invalid memory area,
the content of the invalid memory area will be reported as 00h.
10.9  FAST_READ
The FAST_READ command requires a start page address and an end page address and returns all n*4 bytes
of the addressed pages. For example, if the start address is 03h and the end address is 07h, then pages 03h,
04h, 05h, 06h and 07h are returned.
For details on those cases and the command structure, refer to Figure 25 and Table 29.
Table 30 shows the required timing.
CRC
CRC
StartAddr
NFC device
Cmd
Data
NTAG ,,ACK''
453 µs
depending on nr of read pages
NTAG  ,,NAK''
NAK
Time out
TTimeOut
TNAK
TACK
57 µs
EndAddr
aaa-006989
Figure 25. FAST_READ command
Name
Code
Description
Length
Cmd
3Ah
read multiple pages
1 byte
Table 29. FAST_READ command
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
53 / 84

<!-- Page 54 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Name
Code
Description
Length
StartAddr
-
start page address
1 byte
EndAddr
-
end page address
1 byte
CRC
-
CRC according to ISO/IEC 14443
2 bytes
Data
-
data content of the addressed pages
n*4 bytes
NAK
see Table 17
see Section 10.3
4 bit
Table 29. FAST_READ command...continued
These times exclude the end of communication of the NFC device.
TACK/NAK min
TACK/NAK max
TTimeOut
FAST_READ
n=9 [1]
TTimeOut
5 ms
Table 30. FAST_READ timing
[1]
Refer to Section 10.2.
In the initial state of NTAG I2C plus, all memory pages are allowed as StartAddr parameter to the FAST_READ
command:
• Page address from 00h to E9h and pages ECh and EDh for NTAG I2C plus 1k and 2k
• Page address from 00h to FFh (Sector 1) for NTAG I2C plus 2k only
• SRAM buffer address when pass-through mode is enabled
If the start addressed memory page (StartAddr) is outside of accessible area, NTAG I2C plus replies a NAK.
In case the FAST_READ command starts with a valid memory area but extends over an invalid memory area,
the content of the invalid memory area will be reported as 00h.
The EndAddr parameter must be equal to or higher than the StartAddr.
Remark: The FAST_READ command is able to read out the entire memory of one sector with one command.
Nevertheless, the receive buffer of the NFC device must be able to handle the requested amount of data as no
chaining is possible.
10.10  WRITE
The WRITE command requires a page address, and writes 4 bytes of data into the addressed NTAG I2C plus
page. The WRITE command is shown in Figure 26 and Table 31.
Table 32 shows the required timing.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
54 / 84

<!-- Page 55 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
CRC
Addr
NFC device
Cmd
NTAG ,,ACK''
708 µs
NTAG ,,NAK''
NAK
Time out
TTimeOut
TNAK
TACK
57 µs
ACK
57 µs
Data
aaa-006990
Figure 26. WRITE command
Name
Code
Description
Length
Cmd
A2h
write one page
1 byte
Addr
-
page address
1 byte
Data
-
data
4 bytes
CRC
-
CRC according to ISO/IEC 14443
2 bytes
NAK
see Table 17
see Section 10.3
4 bit
Table 31. WRITE command
These times exclude the end of communication of the NFC device.
TACK/NAK min
TACK/NAK max
TTimeOut
WRITE
n=9 [1]
TTimeOut
5 ms
Table 32. WRITE timing
[1]
Refer to Section 10.2.
In the initial state of NTAG I2C plus, the following memory pages are valid Addr parameters to the WRITE
command:
• Page address from 02h to E9h (Sector 0) for NTAG I2C plus 1k and 2k
• Page address from 00h to FFh (Sector 1) for NTAG I2C plus 2k
• SRAM buffer addresses when pass-through mode is enabled
Addressing a memory page beyond the limits above results in a NAK response from NTAG I2C plus.
Pages that are locked against writing cannot be reprogrammed using any write command. The locking
mechanisms include static and dynamic lock bits, as well as the locking of the configuration pages.
10.11  FAST_WRITE
The FAST_WRITE allows writing data in ACTIVE state to the complete SRAM (64 bytes) in pass-through mode.
It requires the start block address (F0h), end address (FFh) and writes 64 bytes of data into the NTAG I2C plus
SRAM. The FAST_WRITE command is shown in Figure 27 and Table 33.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
55 / 84

<!-- Page 56 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
WARNING: Data is written directly to SRAM. If received CRC at the end of transmission is wrong and response
was a NAK, received (corrupted) data is still in SRAM. Hence it is recommended to implement a protocol on top
to ensure data integrity (e.g. include own CRC at the end of the payload) when using SRAM.
Table 34 shows the required timing.
CRC
Start
End
NFC device
Cmd
NTAG ,,ACK''
5881 µs
NTAG ,,NAK''
NAK
Time out
TTimeOut
TNAK
TACK
57 µs
ACK
57 µs
Data
aaa-021659
Figure 27. FAST_WRITE command
Name
Code
Description
Length
Cmd
A6h
write complete SRAM
1 byte
START_ADDR
F0h
start SRAM in pass-through mode
1 byte
END_ADDR
FFh
end SRAM in pass-through mode
1 byte
Data
-
data
64 bytes
-
CRC
CRC according to ISO/IEC 14443
2 bytes
ACK
see Table 17
see Section 10.3
4 bit
NAK
see Table 17
see Section 10.3
4 bit
Table 33. FAST_WRITE command
These times exclude the end of communication of the NFC device.
TACK/NAK min
TACK/NAK max
TTimeOut
FAST_WRITE
n=9 [1]
TTimeOut
5 ms
Table 34. FAST_WRITE timing
[1]
Refer to Section 10.2.
10.12  SECTOR SELECT
The SECTOR SELECT command consists of two commands packet: the first one is the SECTOR SELECT
command (C2h), FFh and CRC. Upon an ACK answer from the Tag, the second command packet needs to be
issued with the related sector address to be accessed and 3 bytes RFU.
To successfully access to the requested memory sector, the tag shall issue a passive ACK, which is sending NO
REPLY for more than 1 ms after the CRC of the second command set.
The SECTOR SELECT command is shown in Figure 28 and Table 35.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
56 / 84

<!-- Page 57 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Table 36 shows the required timing.
aaa-014051
CRC
FFh
NFC device
Cmd
SecNo
00h
00h
00h
CRC
368 µs
NTAG I2C ,,NAK''
NTAG I2C ,,ACK''
NTAG I2C ,,NAK''
NTAG I2C ,,ACK''
NAK
Time out
NFC device
TTimeOut
TNAK
TACK
57 µs
ACK
57 µs
NAK
<1ms
>1ms
537 µs
57 µs
Passive ACK
SECTOR SELECT packet 2
SECTOR SELECT packet 1
(any reply)
(no reply)
Figure 28. SECTOR_SELECT command
Name
Code
Description
Length
Cmd
C2h
sector select
1 byte
FFh
-
1 byte
CRC
-
CRC according to ISO/IEC 14443
2 bytes
SecNo
-
Memory sector to be selected
(00h - FEh)
1 byte
NAK
see Table 17
see Section 10.3
4 bit
Table 35. SECTOR_SELECT command
These times exclude the end of communication of the NFC device.
TACK/NAK min
TACK/NAK max
TTimeOut
SECTOR_SELECT
n=9 [1]
TTimeOut
5 ms
Table 36. SECTOR_SELECT timing
[1]
Refer to Section 10.2 "Timing".
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
57 / 84

<!-- Page 58 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
11   Communication and arbitration between NFC and I2C interface
If both interfaces are powered by their corresponding source, only one interface shall have access to the
memory according to the "first-come, first-serve" principle.
In NS_REG, the two status bits I2C_LOCKED and RF_LOCKED reflect the status of the NTAG I2C plus
memory access and indicate which interface is locking the memory access. At power-on, both bits are 0b,
setting the arbitration in idle mode.
In the case arbiter locks to the I2C interface, an NFC device can still read the session registers. If the NFC state
machine is in ACTIVE state, only the SECTOR SELECT command is allowed. But any other command requiring
EEPROM access like READ or WRITE is handled as an illegal command and replied to with a NAK value.
In the case where the memory access is locked to the NFC interface, the I2C host can still access the session
register, by issuing a 'Register READ/WRITE' command. All other read or write commands will be replied to with
a NACK to the I2C host.
11.1  Pass-through mode not activated
PTHRU_ON_OFF = 0b (see Table 13) indicates non-pass-through mode.
11.1.1  I2C interface access
If the tag is in the IDLE or HALT state (NFC state after POR or HALT-command) and the correct I2C slave
address of NTAG I2C plus is received following the START condition, the bit I2C_LOCKED will be automatically
set to 1b. If I2C_LOCKED = 1b, the I2C interface has access to the tag memory and the tag will respond with
a NACK to any memory READ/WRITE command on the NFC interface other than reading the session register
bytes during this time.
I2C_LOCKED must be either reset to 0b at the end of the I2C sequence or will be cleared automatically after the
end of the watchdog timer.
11.1.2  NFC interface access
The arbitration allows the NFC interface read and write accesses to EEPROM only when I2C_LOCKED is set to
0b.
RF_LOCKED is automatically set to 1b if the tag receives a valid command (EEPROM access commands)
on the NFC interface. If RF_LOCKED = 1b, the tag is locked to the NFC interface and will not respond to any
command from the I2C interface other than READ register command (see Table 13).
RF_LOCKED is automatically set to 0b in one of the following conditions:
• At POR or if the NFC field is switched off
• If the tag is set to the HALT state with a HALT command on the NFC interface
• If the memory access command is finished on the NFC interface
When the NFC interface has read the last page of the NDEF message specified in LAST_NDEF_BLOCK (see
Table 11 and Table 12) the bit NDEF_DATA_READ - in the register NS_REG see Table 13 - is set to 1b and
indicates to the I2C interface that, for example, new NDEF data can be written.
11.2  SRAM buffer mapping with Memory Mirror enabled
With SRAM_MIRROR_ON_OFF= 1b, the SRAM buffer mirroring is enabled. This mode cannot be combined
with the pass-through mode (see Section 11.3).
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
58 / 84

<!-- Page 59 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
With the memory mirror enabled, the SRAM is now mapped into the user memory from the NFC interface
perspective using the SRAM mirror lower page address specified in SRAM_MIRROR_BLOCK byte (Table 11
and Table 12). See Table 37 (NTAG I2C plus 1k) and Table 38 (NTAG I2C plus 2k) for an illustration of this
SRAM memory mapping when SRAM_MIRROR_BLOCK is set to 01h.
Password protection to this mapped SRAM may be enabled by enabling password authentication and setting
SRAM_PROT bit to 1b.
In contrary to password protection, for read only locking there are no special lock bits for the SRAM. Whenever
user EEPROM blocks are locked to read-only with static and/or dynamic lock bits, potential mirrored SRAM
blocks are read-only, too.
The tag must be VCC powered to make this mode work, because without VCC, the SRAM will not be accessible
via NFC powered only.
When mapping the SRAM buffer to the user memory, the user shall be aware that all data written into the SRAM
will be lost once the NTAG I2C plus is no longer powered from the I2C side (as SRAM is a volatile memory).
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
0
0
00h
Serial number (UID)
READ
1
01h
Serial number (UID)
Internal
READ
2
02h
Internal
Static lock bytes
READ/R&W
3
03h
Capability Container (CC)
READ&WRITE
4
04h
...
...
19
13h
SRAM
READ&WRITE
...
...
Unprotected user memory
READ&WRITE
AUTH0
AUTH0
...
...
225
E1h
Protected user memory
READ
READ&WRITE
226
E2h
Dynamic lock bytes
00h
R&W/READ
227
E3h
RFU
RFU
RFU
AUTH0
READ
READ&WRITE
228
E4h
ACCESS
RFU
RFU
RFU
READ
READ&WRITE
229
E5h
PWD
READ
READ&WRITE
230
E6h
PACK
RFU
RFU
READ
READ&WRITE
231
E7h
PT_I2C
RFU
RFU
RFU
READ
READ&WRITE
232
E8h
233
E9h
Configuration registers
see Table 11
234
EAh
235
EBh
Invalid access - returns NAK
n.a.
236
ECh
237
EDh
Session registers
see Table 12
Table 37. Illustration of the SRAM memory addressing via the NFC interface (with SRAM_MIRROR_ON_OFF set to
1b and SRAM_MIRROR_BLOCK set to 01h) for the NTAG I2C plus 1k
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
59 / 84

<!-- Page 60 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
238
EEh
239
EFh
Invalid access - returns NAK
n.a.
240
F0h
...
...
255
FFh
Invalid access - returns NAK
n.a.
1
...
...
Invalid access - returns NAK
n.a.
2
...
...
Invalid access - returns NAK
n.a.
0
00h
...
...
Invalid access - returns NAK
n.a.
248
F8h
249
F9h
Session registers
see Table 12
...
...
3
255
FFh
Invalid access - returns NAK
n.a.
Table 37. Illustration of the SRAM memory addressing via the NFC interface (with SRAM_MIRROR_ON_OFF set to
1b and SRAM_MIRROR_BLOCK set to 01h) for the NTAG I2C plus 1k...continued
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
0
00h
Serial number (UID)
READ
1
01h
Serial number (UID)
Internal
READ
2
02h
Internal
Static lock bytes
READ/R&W
3
03h
Capability Container (CC)
READ&WRITE
4
04h
...
...
19
13h
SRAM
READ&WRITE
...
...
Unprotected user memory
READ&WRITE
AUTH0
AUTH0
...
...
225
E1h
Protected user memory
READ
READ&WRITE
226
E2h
Dynamic lock bytes
00h
R&W/READ
227
E3h
RFU
RFU
RFU
AUTH0
READ
READ&WRITE
228
E4h
ACCESS
RFU
RFU
RFU
READ
READ&WRITE
229
E5h
PWD
READ
READ&WRITE
0
230
E6h
PACK
RFU
RFU
READ
READ&WRITE
Table 38. Illustration of the SRAM memory addressing via the NFC interface (with SRAM_MIRROR_ON_OFF set to
1b and SRAM_MIRROR_BLOCK set to 01h) for the NTAG I2C plus 2k
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
60 / 84

<!-- Page 61 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
231
E7h
PT_I2C
RFU
RFU
RFU
READ
READ&WRITE
232
E8h
233
E9h
Configuration registers
see Table 11
234
EAh
235
EBh
Invalid access - returns NAK
n.a.
236
ECh
237
EDh
Session registers
see Table 12
238
EEh
239
EFh
Invalid access - returns NAK
n.a.
240
F0h
...
...
255
FFh
Invalid access - returns NAK
n.a.
0
00h
...
...
1
255
FFh
(Un-)protected user memory
READ&WRITE
2
...
...
Invalid access - returns NAK
n.a.
0
00h
...
...
Invalid access - returns NAK
n.a.
248
F8h
249
F9h
Session registers
see Table 12
...
...
3
255
FFh
Invalid access - returns NAK
n.a.
Table 38. Illustration of the SRAM memory addressing via the NFC interface (with SRAM_MIRROR_ON_OFF set to
1b and SRAM_MIRROR_BLOCK set to 01h) for the NTAG I2C plus 2k...continued
11.3  Pass-through mode
PTHRU_ON_OFF = 1b (see Table 13) enables and indicates pass-through mode.
Password protection for pass-through mode may be enabled by enabling password authentication and setting
SRAM_PROT bit to 1b.
To handle large amount of data transfer from one interface to the other, NTAG I2C plus offers the pass-through
mode where data is transferred via a 64 byte SRAM. This buffer offers fast write access and unlimited write
endurance as well as an easy handshake mechanism between the two interfaces.
This buffer is mapped directly at the end of the Sector 0 of NTAG I2C plus.
In both directions, the principle of access to the SRAM buffer via the NFC and I2C interface is exactly the same
(see Section 11.3.2 and Section 11.3.3).
The data flow direction must be set with the TRANSFER_DIR bit (see Table 14) within the current
communication session using the session registers (it can only be set via the I2C interfaces) or for the
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
61 / 84

<!-- Page 62 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
configuration bits after POR (in this case both NFC and I2C interface can set it). This pass-through direction
setting avoids locking the memory access during the data transfer from one interface to the SRAM buffer.
The pass-through mode can only be enabled via I2C interface when both interfaces are powered. The
PTHRU_ON_OFF bit, located in the session registers NC_REG (see Table 14), needs to be set to 1b. In case
one interface powers off, the pass-through mode is disabled automatically.
NTAG I2C plus introduces in addition to the FAST_READ command a FAST_WRITE command. With this
new command in ACTIVE state whole SRAM can be written at once, which improves the total pass-through
performance significantly.
For more information read related application note.
11.3.1  SRAM buffer mapping
In pass-through mode, the SRAM of NTAG I2C plus is mirrored to pages F0h to FFh of Sector 0.
The last page/block of the SRAM (page FFh) is used as the terminator page. Once the terminator page/block
in the respective interfaces is read/written, the control would be transferred to other interface (NFC/I2C) - see
Section 11.3.2 and Section 11.3.3 for more details.
Accordingly, the application can align on the reader and host side to transfer 16/32/48/64 bytes of data in one
pass-through step by only using the last blocks/page of the SRAM buffer.
For best performance in addition to the FAST_READ, the FAST_WRITE command should be used.
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
0
0
00h
Serial number (UID)
READ
1
01h
Serial number (UID)
Internal
READ
2
02h
Internal
Static lock bytes
READ/R&W
3
03h
Capability Container (CC)
READ&WRITE
4
04h
...
...
Unprotected user memory
READ&WRITE
AUTH0
AUTH0
...
...
225
E1h
Protected user memory
READ
READ&WRITE
226
E2h
Dynamic lock bytes
00h
R&W/READ
227
E3h
RFU
RFU
RFU
AUTH0
READ
READ&WRITE
228
E4h
ACCESS
RFU
RFU
RFU
READ
READ&WRITE
229
E5h
PWD
READ
READ&WRITE
230
E6h
PACK
RFU
RFU
READ
READ&WRITE
231
E7h
PT_I2C
RFU
RFU
RFU
READ
READ&WRITE
232
E8h
233
E9h
Configuration registers
see Table 11
234
EAh
Invalid access - returns NAK
n.a.
Table 39. Illustration of the SRAM memory addressing via the NFC interface in pass-through mode
(PTHRU_ON_OFF set to 1b) for the NTAG I2C plus 1k
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
62 / 84

<!-- Page 63 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
235
EBh
236
ECh
237
EDh
Session registers
see Table 12
238
EEh
239
EFh
Invalid access - returns NAK
n.a.
240
F0h
...
...
255
FFh
SRAM
READ&WRITE
1
...
...
Invalid access - returns NAK
n.a.
2
...
...
Invalid access - returns NAK
n.a.
0
00h
...
...
Invalid access - returns NAK
n.a.
248
F8h
249
F9h
Session registers
see Table 12
...
...
3
255
FFh
Invalid access - returns NAK
n.a.
Table 39. Illustration of the SRAM memory addressing via the NFC interface in pass-through mode
(PTHRU_ON_OFF set to 1b) for the NTAG I2C plus 1k...continued
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
0
00h
Serial number (UID)
READ
1
01h
Serial number (UID)
Internal
READ
2
02h
Internal
Static lock bytes
READ/R&W
3
03h
Capability Container (CC)
READ&WRITE
4
04h
...
...
Unprotected user memory
READ&WRITE
AUTH0
AUTH0
...
...
225
E1h
Protected user memory
READ
READ&WRITE
226
E2h
Dynamic lock bytes
00h
R&W/READ
227
E3h
RFU
RFU
RFU
AUTH0
READ
READ&WRITE
228
E4h
ACCESS
RFU
RFU
RFU
READ
READ&WRITE
0
229
E5h
PWD
READ
READ&WRITE
Table 40. Illustration of the SRAM memory addressing via the NFC interface in pass-through mode
(PTHRU_ON_OFF set to 1b) for the NTAG I2C plus 2k
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
63 / 84

<!-- Page 64 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Page address
Byte number within a page
Sector
address
Dec.
Hex.
0
1
2
3
Access cond.
ACTIVE state
Access cond.
AUTH. state
230
E6h
PACK
RFU
RFU
READ
READ&WRITE
231
E7h
PT_I2C
RFU
RFU
RFU
READ
READ&WRITE
232
E8h
233
E9h
Configuration registers
see Table 11
234
EAh
235
EBh
Invalid access - returns NAK
n.a.
236
ECh
237
EDh
Session registers
see Table 12
238
EEh
239
EFh
Invalid access - returns NAK
n.a.
240
F0h
...
...
255
FFh
SRAM
READ&WRITE
0
00h
...
...
1
255
FFh
(Un-)protected user memory
READ&WRITE
2
...
...
Invalid access - returns NAK
n.a.
0
00h
...
...
Invalid access - returns NAK
n.a.
248
F8h
249
F9h
Session registers
see Table 12
...
...
3
255
FFh
Invalid access - returns NAK
n.a.
Table 40. Illustration of the SRAM memory addressing via the NFC interface in pass-through mode
(PTHRU_ON_OFF set to 1b) for the NTAG I2C plus 2k...continued
11.3.2  NFC to I2C data transfer
If the NFC interface is enabled (RF_LOCKED = 1b) and data is written to the terminator page FFh of the
SRAM via the NFC interface, at the end of the WRITE command, bit SRAM_I2C_READY is set to 1b and bit
RF_LOCKED is set to 0b automatically, and the NTAG I2C plus is locked to the I2C interface.
To signal the host that data is ready to be read following mechanisms are in place:
• The host polls/reads bit SRAM_I2C_READY from NS_REG (see Table 14) to know if data is ready in SRAM
• A trigger on the FD pin indicates to the host that data is ready to be read from SRAM. This feature can be
enabled by programming bits 5:2 (FD_OFF, FD_ON) of the NC_REG appropriately (see Table 13)
This is illustrated in the Figure 29.
If the tag is addressed with the correct I2C slave address, the I2C_LOCKED bit is automatically set
to 1b (according to the interface arbitration). After a READ from the terminator page of the SRAM, bit
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
64 / 84

<!-- Page 65 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
SRAM_I2C_READY and bit I2C_LOCKED are automatically reset to 0b. The tag returns to the arbitration idle
mode where, for example, further data from the NFC interface can be transferred.
aaa-021660
Enable pass through
PTHRU_ON_OFF = 1b
RF starts writing data
to SRAM buffer
Last 4 bytes of
SRAM written by RF
Start reading
SRAM by I2C
Last 16 bytes
SRAM by I2C
ON
OFF
HIGH
LOW
RF field
FD pin
Event
I2C_LOCKED
RF_LOCKED
SRAM_I2C_READY
RF_FIELD_PRESENT
0
3Dh
7Dh
more data available?
3Dh
t
0
NS_REG
PTHRU_ON_OFF = 0b,
FD_ON = 11b, FD_OFF = 11b
SRAM_MIRROR_ON_OFF = 0b
TRANSFER_DIR = 1b
NC_REG
RF OFF
1
0
0
1
0
0
1
0
0
1
1
Figure 29. Illustration of the Field detection feature in combination with the pass-through mode for data transfer
from NFC to I2C
11.3.3  I2C to NFC data transfer
If the I2C interface is enabled (I2C_LOCKED is 1b) and data is written to the terminator block FBh of the
SRAM via the I2C interface, at the end of the WRITE command, bit SRAM_RF_READY is set to 1b and bit
I2C_LOCKED is automatically reset to 0b to set the tag in the arbitration idle state.
The RF_LOCKED bit is then automatically set to 1b (according to the interface arbitration). After a READ
or FAST_READ command involving the terminator page of the SRAM, bit SRAM_RF_READY and bit
RF_LOCKED are automatically reset to 0b allowing the I2C interface to further write data into the SRAM buffer.
To signal to the host that further data is ready to be written, the following mechanisms are in place:
• The NFC interface polls/reads the bit SRAM_RF_READY from NS_REG (see Table 14) to know if new data
has been written by the I2C interface in the SRAM
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
65 / 84

<!-- Page 66 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
• A trigger on the FD pin indicates to the host that data has been read from SRAM by the NFC interface. This
feature can be enabled by programming bits 5:2 (FD_OFF, FD_ON) of the NC_REG appropriately (see
Table 13)
The above mechanism is illustrated in the Figure 30.
1
aaa-021661
Enable pass through
PTHRU_ON_OFF = 1b
I2C starts writing
data to SRAM buffer
Last 4 bytes written
to SRAM  by I2C
Start reading
SRAM by RF
Last 4 bytes
read by RF
ON
OFF
HIGH
LOW
RF field
FD pin
Event
I2C_LOCKED
RF_LOCKED
SRAM_RF_READY
RF_FIELD_PRESENT
0
3Ch
7Ch
more data available?
3Ch
t
0
0
NS_REG
PTHRU_ON_OFF = 0b,
FD_ON = 11b, FD_OFF = 11b
SRAM_MIRROR_ON_OFF = 0b
TRANSFER_DIR = 0b
NC_REG
RF OFF
1
0
0
1
0
1
0
0
1
Figure 30. Illustration of the Field detection signal feature in combination with pass-through mode for data
transfer from I2C to NFC
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
66 / 84

<!-- Page 67 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
12   Limiting values
Exceeding the limits of one or more values in reference may cause permanent damage to the device. Exposure
to limiting values for extended periods may affect device reliability.
In accordance with the Absolute Maximum Rating System (IEC 60134). [1] [2]
Symbol
Parameter
Conditions
Min
Max
Unit
Tstg
storage temperature
-55
+125
°C
Tj(max)
maximum junction temperature
-
+105
°C
human body model (HBM)[3]
-
2
kV
VESD
electrostatic discharge voltage
charge device model (CDM)[4]
-
1
kV
VDD
supply voltage
on pin VCC
-0.5
4.6
V
Vi
input voltage
on pin FD, SDA, SCL
-0.5
4.6
V
Ii
input current
on pin LA, LB
-
40
mA
Vi(RF)
RF input voltage
on pin LA, LB
-
4.6
Vpeak
Table 41. Limiting values
[1]
Stresses above one or more of the limiting values may cause permanent damage to the device.
[2]
Exposure to limiting values for extended periods may affect device reliability.
[3]
According to ANSI/ESDA/JEDEC JS-001.
[4]
According to ANSI/ESDA/JEDEC JS-002.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
67 / 84

<!-- Page 68 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
13   Characteristics
13.1  Electrical characteristics
Symbol
Parameter
Conditions
Min
Typ
Max
Unit
Ci
input capacitance
LA - LB, on-chip - CIC, f=13.56
MHz,
VLA-LB=2.4 VRMS
44
50
56
pF
fi
input frequency
-
13.56
-
MHz
Tamb
operating ambient
temperature
-40
25
+105 [1]
°C
RTH_JA
thermal resistance
JEDEC 2s2p board and XQFN8
package
-
150
-
K/W
RTH_JA
thermal resistance
JEDEC 2s2p board and TSSOP8
package
-
211
-
K/W
RTH_JA
thermal resistance
JEDEC 2s2p board and SO8
package
-
115
-
K/W
Energy harvesting characteristics
Vout,max
output voltage
generated at the Vout pin, Class 5
antenna, 14 A/m, load current 1 mA
[2]
-
3.3
V
I2C interface characteristics
VCC
supply voltage
supplied via VCC only
1.67
-
3.6
V
VCC=1.8 V I2C; idle bus
-
160
-
μA
IDD
supply current
VCC=3.3 V I2C; idle bus
-
195
-
μA
VCC=1.8 V I2C@400KHz
-
-
185
μA
VCC=2.5 V I2C@400KHz
-
-
210
μA
IDD
supply current
VCC=3.3 V I2C@400KHz
-
-
240
μA
I2C pin characteristics
IOL= 3 mA; VCC > 2 V
-
-
0.4
V
VOL
LOW-level output voltage
IOL= 2 mA; VCC < 2 V
-
-
0.2*VCC
V
VIH
HIGH-level input voltage
0.7*VCC
-
-
V
VIL
LOW-level input voltage
-
-
0.3*VCC
V
Ci
input capacitance
SCL and SDA pin
-
2.4
-
pF
IL
leakage current
0 V and VCC,max
-
-
10
μA
thigh
SCL high time
fast mode 400 kHz
950
-
-
ns
FD pin characteristics
IOL= 4 mA; VCC > 2 V
-
-
0.4
V
VOL
LOW-level output voltage
IOL= 3 mA; VCC < 2 V
-
-
0.2*VCC
V
IL
leakage current
-
1.5
10
μA
EEPROM characteristics
Table 42. Characteristics
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
68 / 84

<!-- Page 69 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Symbol
Parameter
Conditions
Min
Typ
Max
Unit
tret
retention time
Tamb
20
50
-
year
Nendu(W)
write endurance
Tamb
200000
-
-
cycle
Nendu(W)
write endurance
-40 °C to 95 °C
500000
1000000 -
cycle
Table 42. Characteristics...continued
[1]
Dependent on PCB design and operating conditions
[2]
Minimum value depends on available field strength and load current conditions. For details refer to energy harvesting application note
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
69 / 84

<!-- Page 70 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
14   Package outline
References
Outline
version
European
projection
Issue date
IEC
JEDEC
JEITA
SOT902-3
- - -
MO-255
- - -
sot902-3_po
11-08-16
20-10-09
Unit
mm
max
nom
min
0.5
0.05
0.00
1.65
1.60
1.55
1.65
1.60
1.55
0.6
0.5
0.1
0.05
A
Dimensions
Note
1. Plastic or metal protrusions of 0.075 mm maximum per side are not included.
XQFN8: plastic, extremely thin quad flat package; no leads;
8 terminals; body 1.6 x 1.6 x 0.5 mm
SOT902-3
A1
b
0.25
0.20
0.15
D
E
e
e1
L
0.45
0.40
0.35
v
w
0.05
y
y1
0.05
0
1
2 mm
scale
terminal 1
index area
B
A
D
E
X
C
y
C
y1
terminal 1
index area
3
L
e1
e
A
C
B
v
C
w
2
1
5
6
7
metal area
not for soldering
8
4
e1
e
b
A1
A
detail X
A
C
B
v
C
w
b1
L1
L2
L1
b1
0.35
0.30
0.25
L1
0.35
0.30
0.25
L2
0.35
0.30
0.25
Figure 31. Package outline SOT902-3 (XQFN8)
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
70 / 84

<!-- Page 71 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
SOT902-3
DIMENSIONS in mm
Footprint information for reflow soldering of XQFN8 package
Ay
D
SLx
SLy
1.2
0.4
C
0.22
0.5
0.5
Hx
Hy
1.9
1.9
occupied area
solder land plus solder paste
solder land
solder paste deposit
sot902-3_fr
Issue date
12-12-19
13-01-02
D
(8×)
0.025
0.025
C (7×)
Hy
Hx
0.110
SLy
1.000
Ay
0.320
SLx
1.200
Figure 32. Footprint information for reflow soldering of XQFN8 package - SOT902-3
Find here detailed package and soldering information.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
71 / 84

<!-- Page 72 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
UNIT
A1
A
max.
A2
A3
bp
L
HE
Lp
w
y
v
c
e
D(1)
E(2)
Z(1)
θ
 REFERENCES
OUTLINE
VERSION
EUROPEAN
PROJECTION
ISSUE DATE
 IEC
 JEDEC
 JEITA
mm
0.15
0.05
0.95
0.80
0.45
0.25
0.28
0.15
3.1
2.9
3.1
2.9
0.65
5.1
4.7
0.70
0.35
6°
0°
0.1
0.1
0.1
0.94
DIMENSIONS (mm are the original dimensions)
Notes
1. Plastic or metal protrusions of 0.15 mm maximum per side are not included.
2. Plastic or metal protrusions of 0.25 mm maximum per side are not included.
0.7
0.4
 SOT505-1

99-04-09
03-02-18
w M
bp
D
Z
e
0.25
1
4
8
5
θ
A
A2 A1
Lp
(A3)
detail X
L
HE
E
c
v M A
X
A
y
2.5
5 mm
0
scale
TSSOP8: plastic thin shrink small outline package; 8 leads; body width 3 mm
SOT505-1
1.1
pin 1 index
Figure 33. Package outline SOT505-1 (TSSOP8)
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
72 / 84

<!-- Page 73 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
sot505-1_fr
occupied area
solder lands
Dimensions in mm
3.200
3.600
5.750
0.725
0.650
0.125
0.450
0.600
3.600
2.950
0.125
1.150
5.500
Figure 34.  Footprint information for reflow soldering of TSSOP8 package - SOT505-1
Find here detailed package and soldering information.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
73 / 84

<!-- Page 74 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
UNIT
A
max.
A 1
A 2
A 3
b p
c
D (1)
E (2)
(1)
e
H E
L
L p
Q
Z
y
w
v
θ
 REFERENCES
OUTLINE
VERSION
EUROPEAN
PROJECTION
ISSUE DATE
 IEC
 JEDEC
 JEITA
mm
inches
1.75
0.25
0.10
1.45
1.25
0.25
0.49
0.36
0.25
0.19
5.0
4.8
4.0
3.8
1.27
6.2
5.8
1.05
0.7
0.6
0.7
0.3
8
0
o
o
0.25
0.1
0.25
DIMENSIONS (inch dimensions are derived from the original mm dimensions)
Notes
1. Plastic or metal protrusions of 0.15 mm (0.006 inch) maximum per side are not included.
2. Plastic or metal protrusions of 0.25 mm (0.01 inch) maximum per side are not included.
1.0
0.4
 SOT96-1
X
w M
θ
A
A 1
A 2
b p
D
H E
L p
Q
detail X
E
Z
e
c
L
v M A
(A  )
3
A
4
5
pin 1 index
1
8
y
076E03
 MS-012
0.069 0.010
0.004
0.057
0.049
0.01
0.019
0.014
0.0100
0.0075
0.20
0.19
0.16
0.15
0.05
0.244
0.228
0.028
0.024
0.028
0.012
0.01
0.01
0.041
0.004
0.039
0.016
0
2.5
5 mm
scale
SO8: plastic small outline package; 8 leads; body width 3.9 mm
SOT96-1
99-12-27
03-02-18
Figure 35. Package outline SOT96-1 (SO8)
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
74 / 84

<!-- Page 75 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
sot505-1_fr
occupied area
solder lands
Dimensions in mm
3.200
3.600
5.750
0.725
0.650
0.125
0.450
0.600
3.600
2.950
0.125
1.150
5.500
Figure 36.  Footprint information for reflow soldering of SO8 package - SOT96-1
sot096-1_fw
solder resist
occupied area
solder lands
Dimensions in mm
board direction
placement accurracy ± 0.25
4.00
5.50
1.30
0.3 (2×)
0.60 (6×)
1.20 (2×)
1.27 (6×)
7.00
6.60
enlarged solder land
Figure 37.  Footprint information for wave soldering of SO8 package - SOT96-1
Find here detailed package and soldering information.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
75 / 84

<!-- Page 76 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
15   Handling information
CAUTION
This device is sensitive to ElectroStatic Discharge (ESD). Observe precautions for handling
electrostatic sensitive devices.
Such precautions are described in the ANSI/ESD S20.20, IEC/ST 61340-5, JESD625-A or equivalent
standards.
For assembly guidelines refer to AN1902.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
76 / 84

<!-- Page 77 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
16   Abbreviations
Acronym
Description
ACK
ACKnowledge
ASID
Assembly Sequence ID
CC
Capability Container
CRC
Cyclic Redundancy Check
DBSN
Diffusion Batch Sequence number
EEPROM
Electrically Erasable Programmable Read-Only Memory
fc
carrier frequency
GND
GrouND
IC
Integrated Circuit
I2C
Inter-Integrated Circuit
LSB
Least Significant Bit
MCU
Micro-Controller Unit
MSB
Most Significant Bit
NAK
Not-AcKnowledge
NDEF
NFC Data Exchange Format
NFC
Near Field Communication
POR
Power-On Reset
RF
Radio Frequency
RFU
Reserved for Future Use
SRAM
Static Random-Access Memory
TLV
Tag - Length - Value
UID
Unique IDentifier
Table 43. Abbreviations
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
77 / 84

<!-- Page 78 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
17   References
[1]
NFC Forum - Digital Protocol Technical Specification
https://nfc-forum.org/product-category/specification/
[2]
NFC Forum - Activity Technical Specification
https://nfc-forum.org/product-category/specification/
[3]
NFC Forum - Type 2 Tag Technical Specification
https://nfc-forum.org/product-category/specification/
[4]
Explorer Kit Development NFC Forum Certificate
https://nfc-forum.org/wp-content/uploads/2017/08/NXP_NTAG_I%C2%B2C-_CertID_58514.pdf
[5]
ISO/IEC 14443 - Identification cards - Contactless integrated circuit cards - Proximity cards
https://www.iso.org/ics/35.240.15/x/
[6]
ISO/IEC 7816-6 - Identification cards - Integrated circuit cards - Interindustry data elements for interchange
https://www.iso.org/ics/35.240.15/x/
[7]
UM10204 I2C-bus specification and user manual
https://www.nxp.com/docs/en/user-guide/UM10204.pdf
[8]
AN11276 NTAG Antenna Design Guide
https://www.nxp.com/docs/en/application-note/AN11276.zip
[9]
AN11350 NTAG21x Originality Signature Validation
https://www.nxp.com/confidential/AN11350
[10]
AN11578 NTAG I2C energy harvesting
http://www.nxp.com/documents/application_note/AN11578.pdf
[11]
AN11579 How to use the NTAG I2C (plus) for bidirectional communication
http://www.nxp.com/documents/application_note/AN11579.pdf
[12]
AN11786 Memory Configuration Options
http://www.nxp.com/documents/application_note/AN11786.pdf
[13]
XQFN8 - SOT902-3 package and soldering information
https://www.nxp.com/docs/en/package-information/SOT902-3.pdf
[14]
TSSOP8 - SOT505-1 package and soldering information
https://www.nxp.com/docs/en/package-information/SOT505-1.pdf
[15]
SO8 - SOT96-1 package and soldering information
https://www.nxp.com/docs/en/package-information/SOT96-1.pdf
[16]
AN1902 Assembly guidelines for QFN and SON packages
https://www.nxp.com/docs/en/application-note/AN1902.pdf
[17]
Certicom Research SEC 2: Recommended Elliptic Curve Domain Parameters V2.0
https://www.secg.org/sec2-v2.pdf
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
78 / 84

<!-- Page 79 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
18   Revision history
Document ID
Release date
Data sheet status
Change notice
Supersedes
NT3H2111_2211 v. 3.6
20230721
Product data sheet
-
NT3H2111_2211 v. 3.5
Modifications:
• Remove the wafer deliver form
• Clarifying the condition NFC_PORT bit
• Add the compatibility related information with a mobile
• Editorial updates
NT3H2111_2211 v. 3.5
20190507
Product data sheet
-
NT3H2111_2211 v. 3.4
NT3H2111_2211 v. 3.4
20190108
Product data sheet
-
NT3H2111_2211 v. 3.3
NT3H2111_2211 v. 3.3
20180808
Product data sheet
-
NT3H2111_2211 v. 3.2
NT3H2111_2211 v. 3.2
20171130
Product data sheet
-
NT3H2111_2211 v. 3.1
NT3H2111_2211 v. 3.1
20171009
Product data sheet
-
v. 3.0
NT3H2111_2211 v. 3.0
20160203
Product data sheet
-
-
Table 44. Revision history
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
79 / 84

<!-- Page 80 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
19   Legal information
19.1  Data sheet status
Document status[1][2]
Product status[3]
Definition
Objective [short] data sheet
Development
This document contains data from the objective specification for product
development.
Preliminary [short] data sheet
Qualification
This document contains data from the preliminary specification.
Product [short] data sheet
Production
This document contains the product specification.
[1]
Please consult the most recently issued document before initiating or completing a design.
[2]
The term 'short data sheet' is explained in section "Definitions".
[3]
The product status of device(s) described in this document may have changed since this document was published and may differ in case of multiple
devices. The latest product status information is available on the Internet at URL http://www.nxp.com.
19.2  Definitions
Draft — A draft status on a document indicates that the content is still
under internal review and subject to formal approval, which may result
in modifications or additions. NXP Semiconductors does not give any
representations or warranties as to the accuracy or completeness of
information included in a draft version of a document and shall have no
liability for the consequences of use of such information.
Short data sheet — A short data sheet is an extract from a full data sheet
with the same product type number(s) and title. A short data sheet is
intended for quick reference only and should not be relied upon to contain
detailed and full information. For detailed and full information see the
relevant full data sheet, which is available on request via the local NXP
Semiconductors sales office. In case of any inconsistency or conflict with the
short data sheet, the full data sheet shall prevail.
Product specification — The information and data provided in a Product
data sheet shall define the specification of the product as agreed between
NXP Semiconductors and its customer, unless NXP Semiconductors and
customer have explicitly agreed otherwise in writing. In no event however,
shall an agreement be valid in which the NXP Semiconductors product
is deemed to offer functions and qualities beyond those described in the
Product data sheet.
19.3  Disclaimers
Limited warranty and liability — Information in this document is believed
to be accurate and reliable. However, NXP Semiconductors does not give
any representations or warranties, expressed or implied, as to the accuracy
or completeness of such information and shall have no liability for the
consequences of use of such information. NXP Semiconductors takes no
responsibility for the content in this document if provided by an information
source outside of NXP Semiconductors.
In no event shall NXP Semiconductors be liable for any indirect, incidental,
punitive, special or consequential damages (including - without limitation -
lost profits, lost savings, business interruption, costs related to the removal
or replacement of any products or rework charges) whether or not such
damages are based on tort (including negligence), warranty, breach of
contract or any other legal theory.
Notwithstanding any damages that customer might incur for any reason
whatsoever, NXP Semiconductors’ aggregate and cumulative liability
towards customer for the products described herein shall be limited in
accordance with the Terms and conditions of commercial sale of NXP
Semiconductors.
Right to make changes — NXP Semiconductors reserves the right to
make changes to information published in this document, including without
limitation specifications and product descriptions, at any time and without
notice. This document supersedes and replaces all information supplied prior
to the publication hereof.
Suitability for use — NXP Semiconductors products are not designed,
authorized or warranted to be suitable for use in life support, life-critical or
safety-critical systems or equipment, nor in applications where failure or
malfunction of an NXP Semiconductors product can reasonably be expected
to result in personal injury, death or severe property or environmental
damage. NXP Semiconductors and its suppliers accept no liability for
inclusion and/or use of NXP Semiconductors products in such equipment or
applications and therefore such inclusion and/or use is at the customer’s own
risk.
Applications — Applications that are described herein for any of these
products are for illustrative purposes only. NXP Semiconductors makes no
representation or warranty that such applications will be suitable for the
specified use without further testing or modification.
Customers are responsible for the design and operation of their
applications and products using NXP Semiconductors products, and NXP
Semiconductors accepts no liability for any assistance with applications or
customer product design. It is customer’s sole responsibility to determine
whether the NXP Semiconductors product is suitable and fit for the
customer’s applications and products planned, as well as for the planned
application and use of customer’s third party customer(s). Customers should
provide appropriate design and operating safeguards to minimize the risks
associated with their applications and products.
NXP Semiconductors does not accept any liability related to any default,
damage, costs or problem which is based on any weakness or default
in the customer’s applications or products, or the application or use by
customer’s third party customer(s). Customer is responsible for doing all
necessary testing for the customer’s applications and products using NXP
Semiconductors products in order to avoid a default of the applications
and the products or of the application or use by customer’s third party
customer(s). NXP does not accept any liability in this respect.
Limiting values — Stress above one or more limiting values (as defined in
the Absolute Maximum Ratings System of IEC 60134) will cause permanent
damage to the device. Limiting values are stress ratings only and (proper)
operation of the device at these or any other conditions above those
given in the Recommended operating conditions section (if present) or the
Characteristics sections of this document is not warranted. Constant or
repeated exposure to limiting values will permanently and irreversibly affect
the quality and reliability of the device.
Terms and conditions of commercial sale — NXP Semiconductors
products are sold subject to the general terms and conditions of commercial
sale, as published at http://www.nxp.com/profile/terms, unless otherwise
agreed in a valid written individual agreement. In case an individual
agreement is concluded only the terms and conditions of the respective
agreement shall apply. NXP Semiconductors hereby expressly objects to
applying the customer’s general terms and conditions with regard to the
purchase of NXP Semiconductors products by customer.
No offer to sell or license — Nothing in this document may be interpreted
or construed as an offer to sell products that is open for acceptance or
the grant, conveyance or implication of any license under any copyrights,
patents or other industrial or intellectual property rights.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
80 / 84

<!-- Page 81 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Quick reference data — The Quick reference data is an extract of the
product data given in the Limiting values and Characteristics sections of this
document, and as such is not complete, exhaustive or legally binding.
Export control — This document as well as the item(s) described herein
may be subject to export control regulations. Export might require a prior
authorization from competent authorities.
Suitability for use in non-automotive qualified products — Unless
this document expressly states that this specific NXP Semiconductors
product is automotive qualified, the product is not suitable for automotive
use. It is neither qualified nor tested in accordance with automotive testing
or application requirements. NXP Semiconductors accepts no liability for
inclusion and/or use of non-automotive qualified products in automotive
equipment or applications.
In the event that customer uses the product for design-in and use in
automotive applications to automotive specifications and standards,
customer (a) shall use the product without NXP Semiconductors’ warranty
of the product for such automotive applications, use and specifications, and
(b) whenever customer uses the product for automotive applications beyond
NXP Semiconductors’ specifications such use shall be solely at customer’s
own risk, and (c) customer fully indemnifies NXP Semiconductors for any
liability, damages or failed product claims resulting from customer design and
use of the product for automotive applications beyond NXP Semiconductors’
standard warranty and NXP Semiconductors’ product specifications.
Translations — A non-English (translated) version of a document, including
the legal information in that document, is for reference only. The English
version shall prevail in case of any discrepancy between the translated and
English versions.
NXP B.V. - NXP B.V. is not an operating company and it does not distribute
or sell products.
19.4  Licenses
Purchase of NXP ICs with NFC technology — Purchase of an NXP
Semiconductors IC that complies with one of the Near Field Communication
(NFC) standards ISO/IEC 18092 and ISO/IEC 21481 does not convey an
implied license under any patent right infringed by implementation of any of
those standards. Purchase of NXP Semiconductors IC does not include a
license to any NXP patent (or other IP right) covering combinations of those
products with other products, whether hardware or software.
19.5  Trademarks
Notice: All referenced brands, product names, service names, and
trademarks are the property of their respective owners.
NXP — wordmark and logo are trademarks of NXP B.V.
I2C-bus — logo is a trademark of NXP B.V.
NTAG — is a trademark of NXP B.V.
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
81 / 84

<!-- Page 82 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Tables
Tab. 1.
Ordering information ..........................................5
Tab. 2.
Marking codes ...................................................6
Tab. 3.
Pin description for XQFN8, TSSOP8 and
SO8 ................................................................... 9
Tab. 4.
NTAG I2C plus 1k memory organization
from the NFC perspective ............................... 14
Tab. 5.
NTAG I2C plus 2k memory organization
from the NFC perspective ............................... 16
Tab. 6.
NTAG I2C plus 1k memory organization
from the I2C perspective .................................19
Tab. 7.
NTAG I2C plus 2k memory organization
from the I2C perspective .................................21
Tab. 8.
Minimum memory content to be in
initialized state for NTAG I2C plus .................. 26
Tab. 9.
Password and Access Configuration
Register ........................................................... 28
Tab. 10.
Password and Access Configuration bytes ..... 28
Tab. 11.
Configuration bytes NTAG I2C plus ................ 29
Tab. 12.
Session bytes NTAG I2C plus .........................30
Tab. 13.
Configuration bytes ......................................... 31
Tab. 14.
Session register bytes .....................................33
Tab. 15.
Default NTAG I2C plus address from I2C ........43
Tab. 16.
Command overview .........................................47
Tab. 17.
ACK and NAK values ......................................48
Tab. 18.
ATQA response of the NTAG I2C plus ............ 48
Tab. 19.
SAK response of the NTAG I2C plus .............. 49
Tab. 20.
GET_VERSION command .............................. 49
Tab. 21.
GET_VERSION timing .................................... 49
Tab. 22.
GET_VERSION response ............................... 50
Tab. 23.
READ_SIG command ..................................... 51
Tab. 24.
READ_SIG timing ............................................51
Tab. 25.
PWD_AUTH command ................................... 52
Tab. 26.
PWD_AUTH timing ..........................................52
Tab. 27.
READ command ............................................. 52
Tab. 28.
READ timing ....................................................53
Tab. 29.
FAST_READ command ...................................53
Tab. 30.
FAST_READ timing .........................................54
Tab. 31.
WRITE command ............................................55
Tab. 32.
WRITE timing ..................................................55
Tab. 33.
FAST_WRITE command ................................. 56
Tab. 34.
FAST_WRITE timing ....................................... 56
Tab. 35.
SECTOR_SELECT command .........................57
Tab. 36.
SECTOR_SELECT timing ...............................57
Tab. 37.
Illustration of the SRAM memory
addressing via the NFC interface (with
SRAM_MIRROR_ON_OFF set to 1b and
SRAM_MIRROR_BLOCK set to 01h) for
the NTAG I2C plus 1k .....................................59
Tab. 38.
Illustration of the SRAM memory
addressing via the NFC interface (with
SRAM_MIRROR_ON_OFF set to 1b and
SRAM_MIRROR_BLOCK set to 01h) for
the NTAG I2C plus 2k .....................................60
Tab. 39.
Illustration of the SRAM memory
addressing via the NFC interface in pass-
through mode (PTHRU_ON_OFF set to 1b)
for the NTAG I2C plus 1k ................................62
Tab. 40.
Illustration of the SRAM memory
addressing via the NFC interface in pass-
through mode (PTHRU_ON_OFF set to 1b)
for the NTAG I2C plus 2k ................................63
Tab. 41.
Limiting values ................................................ 67
Tab. 42.
Characteristics .................................................68
Tab. 43.
Abbreviations ...................................................77
Tab. 44.
Revision history ...............................................79
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
82 / 84

<!-- Page 83 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Figures
Fig. 1.
Contactless and contact system ....................... 1
Fig. 2.
Block diagram ................................................... 7
Fig. 3.
Pin configuration for XQFN8 ............................. 8
Fig. 4.
Pin configuration for TSSOP8 ...........................8
Fig. 5.
Pin configuration for SO8 ..................................8
Fig. 6.
NFC state machine of NTAG I2C plus .............11
Fig. 7.
Serial number (UID) ........................................ 23
Fig. 8.
Static lock bytes 0 and 1 .................................23
Fig. 9.
NTAG I2C plus1k Dynamic lock bytes 0, 1
and 2 ............................................................... 24
Fig. 10.
NTAG I2C plus 2k Dynamic lock bytes 0, 1
and 2 ............................................................... 25
Fig. 11.
Possible configuration of CC bytes of
NTAG I2C plus 1k version ...............................26
Fig. 12.
FD pin example circuit .................................... 35
Fig. 13.
Illustration of the field detection feature
when configured for simple field detection ...... 35
Fig. 14.
Illustration of the field detection feature
when configured for first valid start of
communication detection .................................36
Fig. 15.
Illustration of the field detection feature
when configured for selection of the tag
detection ..........................................................37
Fig. 16.
Energy harvesting example circuit .................. 38
Fig. 17.
I2C bus protocol ..............................................41
Fig. 18.
I2C READ and WRITE operation .................... 44
Fig. 19.
WRITE and READ register operation ..............46
Fig. 20.
Frame Delay Time (from NFC device to
NFC tag), TACK and TNAK ............................ 48
Fig. 21.
GET_VERSION command .............................. 49
Fig. 22.
READ_SIG command ..................................... 50
Fig. 23.
PWD_AUTH command ................................... 51
Fig. 24.
READ command ............................................. 52
Fig. 25.
FAST_READ command ...................................53
Fig. 26.
WRITE command ............................................55
Fig. 27.
FAST_WRITE command ................................. 56
Fig. 28.
SECTOR_SELECT command .........................57
Fig. 29.
Illustration of the Field detection feature in
combination with the pass-through mode
for data transfer from NFC to I2C ................... 65
Fig. 30.
Illustration of the Field detection signal
feature in combination with pass-through
mode for data transfer from I2C to NFC ..........66
Fig. 31.
Package outline SOT902-3 (XQFN8) ..............70
Fig. 32.
Footprint information for reflow soldering of
XQFN8 package - SOT902-3 ..........................71
Fig. 33.
Package outline SOT505-1 (TSSOP8) ............72
Fig. 34.
Footprint information for reflow soldering of
TSSOP8 package - SOT505-1 ........................73
Fig. 35.
Package outline SOT96-1 (SO8) .....................74
Fig. 36.
Footprint information for reflow soldering of
SO8 package - SOT96-1 ................................ 75
Fig. 37.
Footprint information for wave soldering of
SO8 package - SOT96-1 ................................ 75
NT3H2111/NT3H2211
All information provided in this document is subject to legal disclaimers.
© 2023 NXP B.V. All rights reserved.
Product data sheet
Rev. 3.6 — 21 July 2023
83 / 84

<!-- Page 84 -->

NXP Semiconductors
NT3H2111_2211
NTAG I2C plus: NFC Forum T2T with I2C interface, password protection and energy harvesting
Contents
1
General description ............................................ 1
2
Features and benefits .........................................2
2.1
Key features ...................................................... 2
2.2
NFC interface .................................................... 2
2.3
Memory ..............................................................3
2.4
I2C interface ...................................................... 3
2.5
Security ..............................................................3
2.6
Key benefits .......................................................3
3
Applications .........................................................4
4
Ordering information .......................................... 5
5
Marking .................................................................6
6
Block diagram ..................................................... 7
7
Pinning information ............................................ 8
7.1
Pinning ...............................................................8
7.1.1
XQFN8 ...............................................................8
7.1.2
TSSOP8 .............................................................8
7.1.3
SO8 ....................................................................8
7.2
Pin description ...................................................9
8
Functional description ......................................10
8.1
Block description ............................................. 10
8.2
NFC interface .................................................. 10
8.2.1
Data integrity ................................................... 10
8.2.2
NFC state machine ..........................................11
8.2.2.1
IDLE state ........................................................11
8.2.2.2
READY 1 state ................................................ 11
8.2.2.3
READY 2 state ................................................ 12
8.2.2.4
ACTIVE state ...................................................12
8.2.2.5
AUTHENTICATED state .................................. 12
8.2.2.6
HALT state .......................................................12
8.3
Memory organization ....................................... 13
8.3.1
Memory map from NFC perspective ................13
8.3.2
Memory map from I2C interface ......................18
8.3.3
EEPROM ......................................................... 22
8.3.4
SRAM ...............................................................22
8.3.5
Serial number (UID) ........................................ 22
8.3.6
Static Lock Bytes .............................................23
8.3.7
Dynamic Lock Bytes ........................................23
8.3.8
Capability Container (CC) ................................25
8.3.9
User Memory pages ........................................ 26
8.3.10
Memory content at delivery ............................. 26
8.3.11
Password and Access Configuration ............... 26
8.3.12
NTAG I2C plus configuration and session
registers ........................................................... 29
8.4
Configurable Field Detection Pin ..................... 34
8.5
Watchdog timer ................................................37
8.6
Energy harvesting ............................................38
8.7
Password authentication ..................................38
8.7.1
Programming of PWD and PACK .................... 39
8.7.2
Limiting negative verification attempts .............39
8.7.3
Protection of configuration segments ...............39
8.8
Originality signature .........................................39
9
I2C commands .................................................. 41
9.1
Start condition ..................................................41
9.2
Stop condition ..................................................41
9.3
I2C soft reset and NFC disable feature ........... 42
9.4
Acknowledge bit (ACK) ....................................42
9.5
Data input ........................................................ 42
9.6
Addressing .......................................................42
9.7
READ and WRITE Operation .......................... 43
9.8
WRITE and READ register operation .............. 46
10
NFC Command .................................................. 47
10.1
NTAG I2C plus command overview .................47
10.2
Timing .............................................................. 47
10.3
NTAG ACK and NAK .......................................48
10.4
ATQA and SAK responses .............................. 48
10.5
GET_VERSION ............................................... 49
10.6
READ_SIG .......................................................50
10.7
PWD_AUTH .....................................................51
10.8
READ ...............................................................52
10.9
FAST_READ ....................................................53
10.10
WRITE ............................................................. 54
10.11
FAST_WRITE .................................................. 55
10.12
SECTOR SELECT ...........................................56
11
Communication and arbitration between
NFC and I2C interface ...................................... 58
11.1
Pass-through mode not activated ....................58
11.1.1
I2C interface access ........................................58
11.1.2
NFC interface access ...................................... 58
11.2
SRAM buffer mapping with Memory Mirror
enabled ............................................................ 58
11.3
Pass-through mode ......................................... 61
11.3.1
SRAM buffer mapping ..................................... 62
11.3.2
NFC to I2C data transfer .................................64
11.3.3
I2C to NFC data transfer .................................65
12
Limiting values ..................................................67
13
Characteristics .................................................. 68
13.1
Electrical characteristics .................................. 68
14
Package outline .................................................70
15
Handling information ........................................76
16
Abbreviations .................................................... 77
17
References .........................................................78
18
Revision history ................................................ 79
19
Legal information ..............................................80
Please be aware that important notices concerning this document and the product(s)
described herein, have been included in section 'Legal information'.
© 2023 NXP B.V.
All rights reserved.
For more information, please visit: http://www.nxp.com
Date of release: 21 July 2023
Document identifier: NT3H2111/NT3H2211


---

# 5. AFC07-S24ECA-00 — 24-pin FPC Connector

> **Role:** FPC connector — AFC07-S24ECA-00  
> **Covers:** `C262643` (FPC connector)

<!-- Page 1 -->

深圳市钜硕电子有限公司
承 认 书
 SPECIFICATIONS FOR APPROVAL
客    户:
CUSTOMER:
品       名:
DESCRIPTION:
料   号:
PART NO:
核 准
APPROVAL
吴 佩 隽
贺 文 超
王 成 铎
◎联 系 人:
CONTACT PERSON
◎公 司 电 话：0755-27220896
COMPANY TELEGRAMS
◎公 司 地 址：广东省深圳市松岗镇下山门钜硕工业园
COMPANY ADDRESS
◎公 司 官 网：http://www.jushuo.net.cn
COMPANY WEBSITE
 客 户 确 认
CUSTOMER APPROVAL
工 程
PROJECT
品 保
Q A
工 程
 PROJECT
品 保
Q A
承   认  印
ACKNOWLEDGMENT SEAL
核 准
APPROVAL
本 司 确 认
TRX  APPROVAL
FPC连接器 0.5mm间距抽拉卧式上接H2.0
◎手 机:
MOBILE PHONE
◎邮 箱：jushuo518@163.com
E-MAIL
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
AFC07-S**ECC-00(小批可用管装）
AFC07-S**ECA-00(批货推荐卷装）

<!-- Page 2 -->

1.0
0.5Pitch H=2.0 FPC ZIF R/A Upper Type3 SMT CONN
深圳市钜硕电子有限公司
AFC07-S**ECA-00
E  C
1 1
MM
A4
10F1
程玉红
张德成
幸坤新
2024/05/18
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
产品实拍图：

<!-- Page 3 -->

AFC07-S**ECA-00
深圳市钜硕电子有限公司
程玉红
张德成
幸坤新
2024/05/18
2024/05/18
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
包装实拍图：

<!-- Page 4 -->

深圳市钜硕电子有限公司
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
第 1 页 共 4 页
产  品  规  格  书
本规格书适用于：0.5mm间距柔性扁平电缆连接器（有锁式）
产品名称 Product Name
产品型号Part Number
FFC/FPC 扁平电缆连接器
【3】定格 RATINGS
项目  Item
规
格
Requirement
最大容许电压
Rated Voltage(MAX)
50V
最大容许电流
Rated Current(MAX)
0.5A
[AC/DC(有效值
Virtual value)50Hz]
使用温度范围
Ambient temperature Range
-45℃ ～ +85℃
AFC07-S**ECA-00
This specification covers the 0.5mm Pitch FPC/FFC Connectors（series
Locking）
【2】产品名称及型号 PRODUCT NAME AND PART NUMBER
PRODUCT SPECIFICATION
【1】适用范围 SCOPE

<!-- Page 5 -->

深圳市钜硕电子有限公司
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
第 2 页 共 4 页
4.1 电气性能 Electrical Performance
项目 Item
条  件
  Test Condition
规格 Requirement
4.1.1
接触电阻
Contact
Resistance
适合FPC/FFC 嵌合；开放电压20mV 以下；短
路电流10mA 的状态下测定。
Mate applicable FPC/FFC and measure by dry
circuit，20mV MAX，10mA.
≤20 mΩMAX
4.1.2
绝缘电阻
Insulation
Resistance
适合FPC/FFC 嵌合；相邻端子间或端子与地面
间加DC 500V 下测定。
Mate applicable FPC/FFC and apply 500V DC
between adjacent terminal or ground.
500MΩMIN
4.1.3
耐电压
Dielectric
适合FPC/FFC 嵌合；相邻端子间或端子与地面
间加AC 200V（有效值）历时1 分钟下测定。
Mate applicable FPC/FFC and apply 200V AC
（virtual value）for 1minute between adjacent
terminal or ground.
无击穿现象
No Breakdown
4.2 机械性能 Mechanical Performance
项目 Item
条  件
  Test Condition
规格 Requirement
4.2.1
锁紧力及拔出力
Locking
and
Withdrawal Force
适合0.3mm 厚的FFC；用每分钟25±3mm
的速度；平行地插入、锁紧、拔出。
Insert and extract applicable FFC at the speed
rate of 25±3mm/minute.
锁紧力 Locking
1.96*n  (N)  MAX
拔出力 Withdrawal
0.49*n  (N)  MIN
4.2.2
端子保持力
Terminal
/Housing
Retention Force
以用每分钟25±3mm 的速度平行向外拉
Pull the terminal at the speed rate of 25±
3mm per minute
3.92N  MIN
4.3 环境和其他性能 Environmental Performance and Others
项目 Item
条  件
  Test Condition
规格 Requirement
4.3.1
重复插拔
Repeated
Insertion and
Withdrawal
无通电状态；以10 次/分钟的速度插拔
20 次
Insertion and withdrawal actuator up to
20 cycles at the speed rate of less than 10
cycles/minute
接触抵抗
Contact
Resistance
60 mΩ
MAX
4.3.2
温度上升
Temperature
Rise
适合FPC/FFC 嵌合；最大容许电流通
电，温度测定。（UL 498）
Carrying rated current load.（UL 498）
温度上升
Temperature
Rise
30 ℃MAX
【4】性能 PERFORMANCE

<!-- Page 6 -->

深圳市钜硕电子有限公司
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
第 3 页 共 4 页
项目 Item
条  件
  Test Condition
规格 Requirement
外观
Appearance
无损坏
No Damage
接触抵抗
Contact
Resistance
60 mΩ
MAX
4.3.3
耐振动性
Vibration
DC 1mA 通电状态下；嵌合轴沿XYZ
三个方向振动；振幅1.5mm；频率
10-55-10Hz/分；历时2 小时
Amplitude：1.5mm P-P
Sweep time：10-55-10Hz in 1 minute
Duration：2 hours in each X.Y.Z. axes
瞬断
Discontinuity
1 ms MAX.
外观
Appearance
无损坏
No Damage
4.3.4
耐冲击性
Shock
DC 1mA 通电状态下；嵌合轴沿相互垂
直的6 个方向；以490m/s2{50G}冲击；
各3 次
490m/s2{50G}，3 strokes in each X.Y.Z.
axes.
瞬断
Discontinuity
1 ms MAX.
外观
Appearance
无损坏
No Damage
4.3.5
耐热性
Heat
Resistance
适合FPC/FFC 嵌合；85±2℃的空气中；
放置96 小时；再回到室温中放置1-2
小时
85±2℃，96 hour
接触抵抗
Contact
Resistance
60 mΩ
MAX
外观
Appearance
无损坏
No Damage
4.3.6
耐寒性
Cold
Resistance
适合FPC/FFC 嵌合；-40±2℃的空气中；
放置96 小时；再回到室温中放置1-2
小时
-40±2℃，96 hour
接触抵抗
Contact
Resistance
60 mΩ
MAX
外观
Appearance
无损坏
No Damage
接触抵抗
Contact
Resistance
60 mΩ
MAX
耐电压
Dielectric
Strength
必须满足
4.1.3
Must meet
4.1.3
4.3.7
耐湿性
Humidity
适合FPC/FFC 嵌合；40±2℃、相对湿
度90-95%的空气中；放置96 小时；再
回到室温中0.5 小时内测定
Temperature：40±2℃
Relative Humidity：90-95%
Duration：96 Hours
绝缘抵抗
Insulation
Resistance
20 MΩ
MIN
外观
Appearance
无损坏
No Damage
4.3.8
温度循环
Temperature
Cycling
适合 FPC/FFC 嵌合；-45±2℃ 30 分
钟；常温常湿 10-15 分钟；85±2℃ 30
分钟；常温常湿 10-15 分钟，循环 5
次。 5 cycles of：
 30 minutes
a ) -45±2℃
b ) 85±2℃
 30 minutes
接触抵抗
Contact
Resistance
60 mΩ
MAX

<!-- Page 7 -->

深圳市钜硕电子有限公司
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
第 4 页 共 4 页
项目 Item
条  件
  Test Condition
规格 Requirement
外观
Appearance
无损坏、腐蚀
No Damage
4.3.9
耐盐雾性
Salt Spray
适合FPC/FFC 嵌合；35±2℃、5±1%
的盐水喷雾48 小时；试验后常温水
洗；再室温干燥。
48±4 hours exposure to a salt spray
from the 5±1% solution at 35±2℃.
接触抵抗
Contact
Resistance
60 mΩ
MAX
4.3.10
耐亚硫酸
SO2 Gas
适合FPC/FFC 嵌合；40±2℃、50±
5ppm 的亚硫酸中放置24 小时
24 hours exposure to 50±5ppm. SO2
gas at 40±2℃.
接触抵抗
Contact
Resistance
60 mΩ
MAX
外观
Appearance
无损坏
No Damage
4.3.11
耐氨性
NH3 Gas
适合FPC/FFC 嵌合；浓度为28%的氨
水容器中；放置40 分钟。
40 minutes exposure to NH3 gas
evaporating
from
28%
Ammonia
solution
接触抵抗
Contact
Resistance
60 mΩ
MAX
4.3.12
可焊性
Solder ability
端子前端基准面0.2mm 处浸入235±
5℃的锡槽中；历时2±0.5 sec。
Soldering Time：2±0.5 sec.
Soldering Temperature：235±5℃
0.2 mm from terminal tip
沾敷性
Solder
Wetting
沾敷面积
95%以上
4.3.13
耐焊接热
Resistance to
Soldering heat
端子前端基准面0.2mm 处浸入260±
5℃的锡槽中；历时5±0.5 sec。
Soldering Time：5±0.5 sec.
Soldering Temperature：260±5℃
0.2 mm from terminal tip
外观
Appearance
无损坏、变形
No Damage
(     ) ：参考规格 Reference Standard
{     } ：参考单位 Reference Unit
【5】外观形状、寸法及材质PRODUCT SHAPE,DIMENSIONS AND MATERIALS
图面参照 Refer to the drawing.
名 称  NAME
材 质
MATERIALS
主体 Main body
LCP(本色)   UL 94V-0
锁扣 Housing  Lock
LCP(黑色)   UL 94V-0
端子 Sit uip
磷青铜  Phosphor Bronze
焊片 Contact
磷青铜  Phosphor Bronze
备注 Remark
金属表面镀金/镀锡 Metal Gold Plated/Tinning

<!-- Page 8 -->

地点：深圳市宝安区松岗街道广深路480号
制程界限名称：System Default for Reflow
 温度设置 (摄氏度)
温区
1
2
3
4
5
6
上温区
180
190
200
230
250
265
下温区
180
190
200
230
250
265
传送带速度 (英寸/分):    40.0
 温度曲线是由 KIC 科技所得
 KIC
 San Diego, CA USA
 电话:  +1-858-673-6050
 传真:  +1-858-673-0085
 www.kicthermal.com
 tech@kicmail.com
 描述:
 制程界限:
 锡膏:
 System Default for Reflow
 统计数名称
 最低界限
 最高界限
 单位
 最高温度上升斜率 (目标=1.5)
 0
 3
 度/秒
 (计算斜率的时间距离= 30 秒)
 恒温时间140-170摄氏度
 50
 90
 秒
 回流以上时间 - 183摄氏度
 30
 90
 秒
 最高温度
 205
 225
 度 摄氏度
PWI= 458%
     <TC2>
     <TC3>
     <TC4>
 温差
最高上升斜率
        恒温时间140至170C                     回流时间/183C
最高温度
1.85
23%
69.43
-3%
190.00
433%
260.78
458%
1.66
11%
65.91
-20%
177.80
393%
259.31
443%
2.02
34%
73.66
18%
183.16
411%
260.34
453%
0.36
7.75
12.20
1.47
 秒
 0
 100
 200
 300
 400
摄氏度
0
50
100
150
200
250
300
Z1
Z2
Z3
Z4
Z5
Z6
深圳市钜硕电子有限公司
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
 公司名称：深圳市钜硕电子有限公司
炉子名称：066
6635

<!-- Page 9 -->

产品料号：适用于所有
FPC&WAFER连接器系列
版本：A
作业流程
作业过程描述
控制要点/参数/条件
检验频率
作业者/
检验者
管制界限值
检测方法
判
定
级
别
处理方式
开　始
进料检验
原材料、零部件料号、规格
MIL-STD-
105E
IQC
依工程图
/SOP/SIP
目视/送实验
室检测
2&3
允收/退货/挑选/
特采
投入物料
原材料、零部件料号、规格
每批物料
线长/IPQC
生产任务单/BOM
目视/送实验
室检测
1
退货
冲压/成型生产
尺寸/外观/功能/装配等
抽检/自检
2模/1H
作业员
/IPQC
依工程图
/SOP/SIP
目视/测试/测
量/装配
1
标示隔离/重工/报
废
外观
外观/尺寸/功能
全检
两模/1H
作业员
/IPQC
依工程图
/SOP/SIP
目视/测量
1
标示隔离/重工
包装入库
标示日期/班次/小心运输
袋 /每批
作业员
/IPQC
入库单
目视
1
调整
投入物料
零部件料号/规格
每批物料
线长/IPQC
生产任务单/BOM
目视/送实验
室检测
1
退货/挑选/特采
裁切端子
端子无变形/氧化等
自检
作业员
作业指导书
目视
0
调整
自动机插端/手工插端
端子无变形/铆合尺寸/折料带端
子无变形
2模/1H
作业员
/IPQC
依工程图
/SOP/SIP
目视/测量
1
调机
装配塑胶
装配到位/无缺料/毛边/堵孔/断
裂/混料/错位/保持力
2模/1H
作业员
/IPQC
依工程图
/SOP/SIP
目视/送实验
室检测
1
标示隔离/重工/报
废
装配焊片
装配到位/毛边/堵孔/断裂/混料
/脱落
2模/1H
作业员
/IPQC
依工程图
/SOP/SIP
目视/送实验
室检测
1
标示隔离/重工/报
废
核准：幸坤新
审核：刘朋飞
制订：陈艳
QC工程图
深圳市钜硕电子有限公司
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
产品描述：FPC&WAFER连接器系列
编号及版本:JS-SIP-0075-01
制定日期:2024/05/18

<!-- Page 10 -->

产品料号：适用于所有
FPC&WAFER连接器系列
版本：A
作业流程
作业过程描述
控制要点/参数/条件
检验频率
作业者/检
验者
管制界限值
检测方法
判定
级别
处理方式
初检
无缺料/毛边/堵孔/色差/高低针
/混料/斜针/缺针/电镀不良等
全检
FQC
作业指导书
目视/测量
0
标示隔离/重工
入管
无混料/少数/多装等
自检
作业员
作业指导书
目视
0
重工
总检
无缺料/毛边/堵孔/色差/高低针
/混料/斜针/缺针/电镀不良等
全检
FQC
作业指导书
目视/测量
0
标示隔离/重工
OQC抽检
无缺料/毛边/堵孔/色差/高低针
/混料/斜针/缺针/电镀不良等
抽检
OQC
SIP/SOP/MIL-
STD-105E II
目视/测量
0
标示隔离/重工
包装入库
分清每批日期/搬运/轻放
每批
作业员
入库单
目视
0
调整
出货检验
合格标签内容/出货内容
每批
OQC
作业指导书
目视
1
标示隔离/重工
完　成
备注:
判定级别:
作业流程符号:
0.作业员自检
开始/终止
物料投入
1.线长/IPQC/IPQC线长
作业
存储
2.工程师/课长/经理
检验/测试
3.副总/总经理
核准：
审核：刘朋飞
制订：陈艳
QC工程图
产品描述：FPC&WAFER连接器系列
编号及版本:JS-SIP-0075-02
制定日期:2024/05/18
1.每次开始生产调机及换料后必须进行首件检验,数量为两模。工程图面标示“▼”的尺寸全量测；耐温测试、焊锡性测试、功能测试等。
2.插入力、拔出力及保持力请参见工程图及规格书
深圳市钜硕电子有限公司
SHENZHEN JUSHUO ELECTRONICS CO.,LTD
幸坤新


---

# 6. TYPE-C-31-M-12 — USB-C Receptacle (OCR)

> **Role:** USB-C connector — Hroparts TYPE-C-31-M-12  
> **Covers:** `C165948` (USB-C)

<!-- Page 1 -->

ROHS a

8-03
16-0.20+0.05 a

  

 

NOTE
A o| 1.MATERIAL SPECIFICATION
1,HOUSING: HIGH TEMPERATURE RESISTANT PLASTIC,UL94 V—
2.CONTAC

   

 

AMIB12 A4/B9 BB AS B7 AGA7B6 AB BS B4IAQ

A B12 Aq BOBS AS B7 AB A7 BB A8 BS B4 AD B1A12 N

   

 

 
  

 

 

 

 

 

 

     

      
   
   
 

 

L\ Lyf
SON ap mone oe
5 : ae Os 2.PLATING SPECIFICATION
zim fP g phe! 4 2-1.CONTAC
ooo q S Es Ni 50u” MIN. UNDER PLATED OVER ALL
|g + Au PLATED ON THE FUNCTIONAL AREA Of \cowTAcT
ga q (GOLD PLATING THICKNESS FOLLOW p
‘ i 7 |} SEs 9 GOLD FLASH PLATING ON SOL ,
A Cy 2-2.FRONT SHELL

Ni 30u” MIN. UI
Yo S.MECHANICAL fy

   

 

 

 

 

 

 

 

RECOMMEND P.C.B LAYOUT(CO
TOLERANCE FOR PCB LAY.

 

> 100V FOR 1 MINUTE

 

 

 

ON THE BOARD SHALL

WW Y)

r Ss - OR 10 SECONDS AT 260°C.
Ae ° oe

B12

 

 

 

 

 

 

  

 

 

GND B12 GND

VBUS Bg

CCl B8

DPI B7

DN1 B6

SBU1 B5
AQ VBUS B4 VBUS
A12 GND Bi GND

 

 

 

PIN | SIGNAL NAME | PIN] SIGNAL NAME

 

 

 

 

 

        

 

 
  

 

 

 

 

 

 

 

 

 

   
 

APPROVALS DATE Lj VL DEES .
DRAWN uucan |2020.12.08) ELECTRONICS CO.,LTD
CHECKED TITLE DETECTOR SWITCHS
APPROVALS PART NO TYPE-—C-—31-—M-12
A | —— NEW — _ | — | — hrrcrances ar ANGLE] UNIT; mm | SCALE: 1:1
ECN NO. |REV.| DATE. DESCRIPTION. CHANGE.| CHECK. | APPRO. S018) £2 [DRAWING NO

£0.10


---

# 7. SI1304BDL — N-Channel MOSFET (OCR)

> **Role:** NMOS — SI1304BDL  
> **Covers:** `C7419947` (NMOS)

<!-- Page 1 -->

7

TECH PUBLIC $I1304BDL

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

—ahbs—
N-Channel Enhancement Mode MOSFET
www.sot23.com.tw
$11304BDL-T1-GE3 pin to pin fully compatible
Features Application
¢ Load/Power Switching
BVpss 30V * Interfacing Switching
e Battery Management for Ultra Small Portable
Rpscon) 450mQ Electronics
e Logic Level Shift
Package and Pin Configuration Circuit diagram
D
°
D s
ff +
G
SOT323
Oo
s
Marking:KFT
Absolute Maximum Ratings (Ta=25°C unless otherwise noted
Parameter Symbol Max. Unit
Drain-Source Voltage Vos 30 V
Gate-Source Voltage Ves +12 V
Drain Current-Continuous(T~=25°C) 800 mA
|
Drain Current-Pulsed' lom 2100 mA
Power Dissipation(Tc=25°C) 360 mW
Pp
Power Dissipation-Derate Above 25°C 1.25 mvVv/°C
Storage Temperature Range Tste -55 To +150 °C

 

Operating Junction Temperature Range Ty -55 To +150 °C

<!-- Page 2 -->

7

TECH PUBLIC SI1304BDL
a — N-Channel Enhancement Mode MOSFET

www.sot23.com.tw

 

Electrical Characteristics (T, = 25°C unless otherwise noted )

 

Parameter Symbol Conditions Min. Typ. Max. Unit

 

Off Characteristics

 

 

 

 

 

Drain-Source Breakdown Voltage BVpss Ves=0V, Ip=250uA 30 - - V
, Reference fo 25°C,
BVpss Temperature Coefficient | ABVpss/AT, Ip=1mA - -0.03 - virC
Vps=30V , Vcs=OV,
Drain-Source Leakage Current | TiF25°C ! WA
9 Dss Vos=24V , Vas=0V, 40 A
T)=125°C - - H
Gate-Source Leakage Current less Ves=t12V, Vps=0V - - +20 UA

 

On Characteristics

 

 

 

 

 

 

Static Drain-Source On- R Ves=4.5V, Ip=0.5A - 350 450 0
Resist DS(ON) m
esistance Ves=2.5V, Ip=0.5A - 450 650
Gate Threshold Voltage Vesith) 0.5 0.8 1.2 V
Vos=Ves; Ip=250yuA
Vesithy) Temperature Coefficient AVesith) - -1.74 - mV/°C
Forward Transconductance Ors Vps=4V, |p=0.3A - 1 - S

 

Dynamic and Switching Characteristics

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

Total Gate Charge? Q, - 2.6 5.2
Vps=15V, Ip=0.3A,
Gate-Source Charge? Qgs Ves=4.5V - 0.9 1.8 nC
Gate-Drain Charge? Qga : 0.6 1.2
Turn-On Delay Time?* tayon) - 5.5 11
Rise Time23 t, Vop=15V, Re=100 - 4 8 S
- = n
Turn-Off Delay Time?3 taott ~~ FO - 14.5 29
Fall Time? t; - 6.5 13
Input Capacitance Ciss - 72.9 146
Vps=15V, Ves=0V,
Output Capacitance Coss F=1MHz - 18.3 36.6 PF
Reverse Transfer Capacitance Crss - 7.4 14.8

 

Drain-Source Diode Characteristics and Maximum Ratings

 

 

 

 

 

 

 

Continuous Source Current Is Vo=Vp=O0V, - - 400 A
m
Pulsed Source Current Ism Force Current - - 800
: Vos=0V, 1s=0.2A,
Diode Forward Voltage Vsp T)=25°C - - 1 V
Reverse Recovery Time ain sat00AIue, - 13 - ns
Reverse Recovery Charge Qre Ty=25°C - 6 - nc

<!-- Page 3 -->

T

TECH PUBLIC SI1304BDL
oS — N-Channel Enhancement Mode MOSFET

 

.sot23.
Typical Electrical and Thermal Characteristic Curves www.sot23.com.tw

0.4 2

< = NN

ec

oO 03 s Oo

5 id 8 45 a
”

= ®

© \ ~

a N\ c

8 oO
S \ o 1 es
£ a ra

= 0.1

 

 

 

 

 

 

 

 

 

 

 

re Zz
0 0.5
25 50 75 4100 125 150 -50 0 50 400 150
Tc , Case Temperature (°C) T, , Junction Temperature (°C)
Figure 1. Continuous Drain Current vs. Tc Figure 2. Normalized Rpson vs. Ty
13 45
_ ID=0.3A JL
© > VDS=15V
5)
8 © 36 LZ

 

 

$ 11 a s /
5 °
3 Pa 9 27 ff
oO Pa
= 0.9 S /
< NN °
2 o 13 /
5 ® /
0.7 % J
i O 0.9

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 
  

 

 

 

N "
o 8
E >
S 05 0

-50 0 50 100 150 0 0.6 1.2 18 24 3

Ty, Junction Temperature (°C) Qg , Gate Charge (nC)

Figure 3. Normalized Vin vs. Ty Figure 4. Gate Charge Waveform
2 =

4 —
oe <
o = 1
a © 10us
: $
n »d
2 0.1 = N“ S\N N\ 100us
_ bi 0.1 — ing
© a “ Nw
E o S>
D 5 > ~N ims
< S SN
- 0.04 - = 10ms
Oo . ~~
O uy aa = on eet et 100ms
WN Dc
© car ae °
£ ___ NOTES: oO
o SINGLE PULSE DUTY FACTOR: D = t1/t2 ' Tc=25°C
= 0.001 | 0.004

0.0001 0.001 0.01 0.1 1 10 0.1 1 40

Square Wave Pulse Duration(s) -Vps, Drain to Source Voltage (V)

Figure 5. Normalized Transient Response Figure 6. Maximum Safe Operation Area

<!-- Page 4 -->

T

TECH PUBLIC SI1304BDL
oS — N-Channel Enhancement Mode MOSFET

www.sot23.com.tw

 

 

  

Gate Charge

Firgure 7. Switching Time Waveform Firgure 8. Gate Charge Waveform

<!-- Page 5 -->

7

TECH PUBLIC SI1304BDL
oS — N-Channel Enhancement Mode MOSFET

www.sot23.com.tw

Outline Drawing - SOT323(SC70-3)

 

 

 

 

 

 

SOT323
Dim | Min | Max |_ Typ
Ai |0.00]0.10} 0.05
A2 |0.90] 1.00} 0.95
b |0.25|0.40] 0.30
c |0.10/018] 0.11
D |1.80|]2.20|) 2.15
E |2.00] 2.20} 2.10
E1 |1.15]1.35] 1.30
e 0.650 BSC
e1 | 1.20] 1.40] 1.30
F |0.375|0.475| 0.425
L |0.25|0.40] 0.30
a 0° 8° --
All Dimensions in mm

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

F e1

Land Pattern - SOT323

 

 

 

 

 

 

 

 

 

 

 

 

 

 

x
A
W
Dimensions Value
(in mm)

Cc 0.650
Y¥1 G G 1.300
xX 0.470
Y 0.600
Y¥1 2.500

!

C


---

# 8. CDRH2D18/LD — SMD Power Inductor

> **Role:** Inductor — 47µH (CDRH2D18/LDNP-470NC)  
> **Covers:** `C2454210` (Inductor: 470nH/47µH)

<!-- Page 1 -->

SMD Power Inductor
CDRH2D18/LD
Page 1 of 4
Revised: 13-Nov-20
Description
• Ferrite drum core construction.
• Magnetically shielded.
• L×W×H:3.2×3.2×2.0 mm Max.
• Product weight: 65mg(Ref.)
• Moisture Sensitivity Level: 1
• RoHS compliance.
Environmental Data
• Operating temperature range: -40℃~+105℃
(including coil’s self temperature rise)
• Storage temperature range: -40℃～+105℃
• Solder reflow temperature: 260 ℃peak.
Packaging
• Carrier tape and reel packaging
• 7.0”diameter reel
• 1000pcs per reel
Applications
• Ideally used in Mobilephone,PDA,MP3,
DSC/DVC, Portable DVD, etc as DC-DC
converter inductors.
RoHS
Dimension - [mm]
Land pattern and Schematics - [mm]
※2 1.0±0.1
φ2.1
※2 3.3±0.2
2.0 Max.
※1 3.0±0.2
※1 3.0±0.2
4.5 Max.
(1.8)
Electrode
4.3
1.3
1.3
1.7
(2.2μH～6.8μH)
(10μH～47μH)
1
2
2
1
※1 Not including terminal dimension.
※2 Electrode dimension

<!-- Page 2 -->

SMD Power Inductor
CDRH2D18/LD
Page 2 of 4
Revised: 13-Nov-20
Electrical Characteristics
※1. Inductance measuring condition:  at 100kHz.
※2. Saturation current: The value of D.C. current when the inductance decreases to 65% of it’s nominal value.
※3. Temperature rise current: The value of D.C. current when the temperature rise is △t＝40℃(Ta＝20℃).
Part Name
Stamp
Inductance
(μH)
[within] ※1
D.C.R. (mΩ)
Max. (Typ.)
(at 20℃)
Saturation Current
(Ａ) ※2
Temperature
Rise Current
(A) ※3
at 20℃
at 100℃
CDRH2D18/LDNP-2R2NC
C
2.2± 30％
41(33)
0.85
0.67
2.30
CDRH2D18/LDNP-3R3NC
E
3.3± 30％
54(43)
0.75
0.55
2.10
CDRH2D18/LDNP-4R7NC
G
4.7± 30％
78(62)
0.63
0.47
1.65
CDRH2D18/LDNP-6R8NC
I
6.8± 30％
106(85)
0.52
0.40
1.32
CDRH2D18/LDNP-100NC
K
10± 30％
180(145)
0.43
0.33
1.00
CDRH2D18/LDNP-150NC
M
15± 30％
220(175)
0.35
0.28
0.80
CDRH2D18/LDNP-220NC
O
22± 30％
320(255)
0.30
0.22
0.68
CDRH2D18/LDNP-330NC
Q
33± 30％
460(370)
0.24
0.18
0.56
CDRH2D18/LDNP-470NC
S
47± 30％
660(530)
0.20
0.15
0.48

<!-- Page 3 -->

SMD Power Inductor
CDRH2D18/LD
Page 3 of 4
Revised: 13-Nov-20
0
10
20
30
40
50
60
0.0
0.1
0.2
0.3
0.4
0.5
0
10
20
30
40
50
60
0
8
16
24
32
40
48
0.0
0.1
0.2
0.3
0.4
0.5
0.6
0
10
20
30
40
50
60
0
5
10
15
20
25
30
0.0
0.2
0.4
0.6
0.8
0
10
20
30
40
50
60
0
3
6
9
12
15
18
0.0
0.2
0.4
0.6
0.8
0
10
20
30
40
50
60
0
2
4
6
8
10
12
0.0
0.2
0.4
0.6
0.8
1.0
0
10
20
30
40
50
60
0.0
1.5
3.0
4.5
6.0
7.5
9.0
0.0
0.3
0.6
0.9
1.2
1.5
0
10
20
30
40
50
60
0
1
2
3
4
5
6
0.0
0.3
0.6
0.9
1.2
1.5
1.8
0
10
20
30
40
50
60
0.0
0.6
1.2
1.8
2.4
3.0
3.6
0.0
0.4
0.8
1.2
1.6
2.0
2.4
0
10
20
30
40
50
60
0.0
0.5
1.0
1.5
2.0
2.5
3.0
0.0
0.5
1.0
1.5
2.0
2.5
0
10
20
30
40
50
60
Saturation Current & Temperature Rise  Graph
1. CDRH2D18/LDNP-2R2NC △T (℃)
L (μH)
DC (A)
DC (A)
2. CDRH2D18/LDNP-3R3NC △T (℃)
L (μH)
△T (℃)
3. CDRH2D18/LDNP-4R7NC
L (μH)
DC (A)
△T (℃)
4. CDRH2D18/LDNP-6R8NC
L (μH)
DC (A)
△T (℃)
5. CDRH2D18/LDNP-100NC
L (μH)
DC (A)
△T (℃)
6. CDRH2D18/LDNP-150NC
L (μH)
DC (A)
△T (℃)
7. CDRH2D18/LDNP-220NC
L (μH)
DC (A)
△T (℃)
8. CDRH2D18/LDNP-330NC
L (μH)
DC (A)
DC (A)
△T (℃)
9. CDRH2D18/LDNP-470NC
L (μH)
L (20℃)
△T
L (100℃)

<!-- Page 4 -->

SMD Power Inductor
CDRH2D18/LD
Page 4 of 4
Revised: 13-Nov-20
Solder Reflow Condition
170± 10 ℃,60~120s
40s
230℃
245℃PEAK
Heat Endurance
Temperature Chart
300
60
120
180
240
0
0
100
150
200
250
300
50
10
T (℃)
T (s)
60
260℃
230℃
0
100
150
200
250
300
50
T (℃)
300
120
180
240
0
T (s)
60
Please refer to the sales offices on our website  - http://www.sumida.com
Hong Kong
Shanghai
Shenzhen
Taipei
Tel.+852-2880-6781
FAX.+852-2565-9600
sales@hk.sumida.com
Tel.+86-21-5836-3299
FAX.+86-21-5836-3266
shanghai.sales@cn.sumida.com
Tel.+86-755-8291-0228
FAX.+86-755-8291-0338
shenzhen.sales@cn.sumida.com
Tel.+886-2-8751-2737
FAX.+886-2-8751-2738
sales@tw.sumida.com
Saitama(Japan)
Seoul
Singapore
San Jose
Tel.+81-48-691-7300
FAX.+81-48-691-7340
sales@jp.sumida.com
Tel.+82-2-6237-0777
FAX.+82-2-6237-0778
sales@kr.sumida.com
Tel.+65-6296-3388
FAX.+65-6841-4426
sales@sg.sumida.com
Tel.+1-408-321-9660
FAX.+1-408-321-9308
sales@us.sumida.com
Chicago
Obernzell
Neumarkt
Tel.+1-847-545-6700
FAX. +1-847-545-6720
sales@us.sumida.com
Tel.+49-8591-937-0
FAX. +49-8591-937-103
contact@eu.sumida.com
Tel.+49-9181-4509-110
FAX. +49-9181-4509-310
infocomp@eu.sumida.com


---

# 9. MBR0530 — Schottky Barrier Diode

> **Role:** Schottky diode — MBR0530 (×3)  
> **Covers:** `C77336` (Schottky diode)

<!-- Page 1 -->

JIANGSU CHANGJIANG ELECTRONICS TECHNOLOGY CO., LTD

   SOD-123 Plastic-Encapsulate Diodes

   MBR0520-MBR0580   Schottky Barrier Diode

FEATURES
z
Lead Free Finish/RoHS Compliant
z
Extremely Low Thermal Resistance
z
For Surface Mount Application and High Current Capability

MARKING:
Maximum Ratings @Ta=25℃
Parameter
Symbol
MBR
0520
MBR
0530
MBR
0540
MBR
0560
MBR
0580
Unit

Maximum recurrent peak reverse voltage
Maximum RMS voltage

VRRM
VRMS

20
14
0
30
21
3
40
28
4
60
42

80
56

V
Mean rectifying current
IO
0.5
A
Non-repetitive Peak forward surge current
@t=8.3ms

IFSM
5.5
A
Power Dissipation
Pd
410
mW
Junction temperature
Tj
125
℃
SOD-123
Storage temperature
Tstg
-55~+150
℃
Thermal Resistance Junction to Ambient                            RθJA                                                 244                                ℃/W

MBR0520:R2       MBR0530:R3              MBR0540:R4                MBR0560:R6       MBR0580:R8

                                                                    1
www.cj-elec.com
The marking bar indicates the cathode
Solid dot = Green molding compound device,if none,
the normal device.
E,Mar,2015

<!-- Page 2 -->

Parameter
Symbol
Min.
Typ.
Max.
Unit
Conditions
Forward voltage
MBR0520
MBR0530
MBR0540
MBR0560
MBR0580
VF

0.45
0.55
0.55
0.70
0.80
V
IF=500mA
Reverse current
MBR0520
MBR0530
MBR0540
MBR0560
MBR0580
IR

80
μA

VR=20V
VR=30V
VR=40V
VR=60V
VR=80V
Capacitance between terminals
CT

30

pF
VR=4V, f=1MHZ

ELECTRICAL CHARACTERISTICS
a
T =25 ℃ unless otherwise specified
www.cj-elec.com                                                                    2                                                                            E,Mar,2015

<!-- Page 3 -->

0
100
200
300
400
500
0.1
1
10
100
4
8
12
16
20
0.1
1
10
100
1000
10000
0
25
50
75
100
125
0
90
180
270
360
450
410
500
0.1
Forward    Characteristics
FORWARD VOLTAGE     VF    (mV)
FORWARD CURRENT    IF    (mA)
Ta=25℃
Ta=100℃

Reverse    Characteristics
Ta=25℃
Ta=100℃
REVERSE CURRENT   IR    (uA)
REVERSE VOLTAGE    VR    (V)

Power Derating Curve
POWER DISSIPATION    PD    (mW)

AMBIENT TEMPERATURE    Ta    (
)
℃
Typical Characteristics                                                                                                          MBR0520
www.cj-elec.com                                                                    3                                                                            E,Mar,2015

<!-- Page 4 -->

www.cj-elec.com
4
SOD-123 Package Outline Dimensions
SOD-123 Suggested Pad Layout
Min
Max
Min
Max
A
1.050
1.250
0.041
0.049
A1
0.000
0.100
0.000
0.004
A2
1.050
1.150
0.041
0.045
b
0.450
0.650
0.018
0.026
c
0.080
0.150
0.003
0.006
D
1.500
1.700
0.059
0.067
E
2.600
2.800
0.102
0.110
E1
3.550
3.850
0.140
0.152
L
L1
0.250
0.450
0.010
0.018
θ
0°
8°
0°
8°
0.500 REF
0.020 REF
Symbol
Dimensions In Millimeters
Dimensions In Inches
E,Mar,2015

<!-- Page 5 -->

www.cj-elec.com
5                                                                            E,Mar,2015
SOD-123 Tape and Reel


---

# 10. 0603 Red LED — Kuangtong (approval doc)

> **Role:** LED — Red 0603 (D2, D3, D4)  
> **Covers:** `C2286` (LED red)

<!-- Page 1 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
承认书
Specification for approval

客户名称(Customer name)：
经办者(Director)：
职称(title)：
客户料号(Customer part NO)：

版本(Revision)：

A.0
发件日期(Issue date)：
2018-12-06

回文日期(Return date)：
一、谨致执事者：兹提供敝公司产品之有关详细规格及图面数据，敬请给予办理测试认定手续，
同时敬请送返一份附有贵公司签认之测试认定后之样品认定书。

（We are please in sending you herewith our specification and drawings for your approval. ）
  （Please return to us one copy “For Approval” with your approved signatures.）

二、附件(Accessory):

□样品
□出货检验记录表
□封装尺寸图
电气特性曲线
内部线路图
焊性建议
PAD 建议
包装方式

三、客户意见栏(Customer’s Proposal)
同意(Agree)：(请于认可栏中签名)
不同意(Disagree)：

 原因(Reason)：

客户认可签章(Customer Signature):

<!-- Page 2 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
1. 产品描述/ Features

外观尺寸/ Package ( L/W/H ) :  1.6*0.8*0.6 mm

颜色/ Color:  红光 /  Red  light

胶体/ Lens:   透明平面胶体/ Transparent planar colloid

EIA规范标准包装/ EIA STD Package

环保产品，符合ROHS要求/ Meet ROHS, Green Product

适用于自动贴片机/ Compatible With SMT Automatic Equipment
   适用于红外线回流焊制程/ Compatible With Infrared Reflow Solder Process
2 . 外形尺寸及建议焊盘尺寸/ Package Profile & Soldering PAD Suggested

注/ Notes: 1.  单位 : 毫米（mm）/ All dimensions are in millimeters
2. 公差 ：如无特别标注则为± 0.1 mm Tolerance is ± 0.10 mm unless otherwise noted

3. 建议焊接温度曲线 / Soldering Profile Suggested

120sec.Max.
60sec.Max.
Above 220¡ãC
1~5¡ãC/sec.Max.
Pre-heating
180-200¡ãC
1~5¡ãC/sec.Max.
260¡ãC.Max.
10sec.Max.
1~5¡ãC/sec.Max.
lead-free solder

<!-- Page 3 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
4. 最大绝对额定值/ Absolute Maximum Ratings （Ta=25℃）
参 数/ Parameter
符号Symbol
最大额定值/ Rating
单 位/ Unit
消耗功率/ Power Dissipation
Pd
40
mW
最大脉冲电流/ Peak Forward Current
(1/10占空比, 0.1ms脉宽)
IFP
60
mA
正向直流工作电流/ DC Forward Current
IF
25
mA
反向电压/Backward Voltage
VR
5
V
工作温度范围
 Operating Temperature Range
Topr
-40°C  ~  + 85°C
存储温度范围
Storage Temperature Range
Tstg
-40°C  ~  + 85°C
焊接条件
Soldering Condition
Tsol

回流焊/ Reflow soldering : 260°C ，10s
   手动焊/ Hand soldering : 300°C ，3s
抗静电能力
Electrostatic Discharge
ESD
V
5.光电参数/ Electrical Optical Characteristics  （Ta=25℃）
参数
 Parameter
符号
Symbol
最小值
Min.
代表值
Typ.
最大值
Max.
单位
Unit
测试条件
Test Condition
光强
Light Intensity
IV
145
--
300
mcd
IF = 20mA
半光强视角
Viewing Angle
2θ1/2
---
120
---
deg
IF = 20mA
主波长
Dominant Wavelength
λd
615
630
nm
IF = 20mA
峰值波长
Peak Wavelength
λp
625
645
nm
IF = 20mA
正向电压
Forward Voltage
VF
1.8
2.4
V
IF = 20mA
反向电压
Backward Voltage
IR
---
---
5
μA
VR = 5V
半波宽
Spectral Line Half-Width
Δλ
20
nm
IF = 20mA

<!-- Page 4 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
6. 光电参数分BIN 规格/Photoelectric parameters are divided into BIN sprcifications
6.1.亮度分BIN 规格/Bin Range of Luminous Intensity
Bin
Min
Max
Unit
Condition
P22
145
175
P23
175
210
P23
210
250
P24
250
300
V
IF = 20mA
Notes: Tolerance of Luminous Intensity: ± 10%
6.2.电压分BIN 规格/ Bin Range of Forward Voltgae
Bin
Min
Max
Unit
Condition
VE
1.8
1.9
VF
1.9
2.0
VG

2.0
2.1
VH
2.1
2.2
VI
2.2
2.3
VJ
2.3
2.4
V
IF = 20mA
Notes: Tolerance of Forward Voltage: ± 0.05V

6.3.波长分BIN 规格/ Bin Range of Wavelength
Bin
Min
Max
Unit
Condition
R1
615
618
R2
618
621
R3
621
624
R4
624
627
R5
627
630
nm
IF = 20mA
Notes: Tolerance of Wavelength: ± 1nm

<!-- Page 5 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
7.光电参数代表值特征曲线/ Typical Electrical-Optical Characteristics Curves

光谱分布特性曲线
Spectrum Distribution  (Ta=25℃)
0
0.2
0.4
0.6
0.8
1
1.2
380
430
480
530
580
630
680
730
780
Wavelength (nm)
Relative Intensity

<!-- Page 6 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
8.包装载带与圆盘尺寸/ Reel And Tape Dimensions
包装数量：4000 pcs/卷  Packing quantity: 4000 PCS/rolls
注/ Notes: 1. 尺寸单位为毫米(mm)/ All dimensions are in millimeters.
2. 尺寸公差是±0.1mm/ Tolerance is ± 0.1 mm unless otherwise noted.
9.标签及标识/ Label Explanation：

                           The label
Anti-static, moisture-proof aluminum foil bag

<!-- Page 7 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
   10.信赖性测试项目及条件/Reliability Test Items And Conditions
测试项目
Test Item
Ref.Standard
参考标准
Test Condition
测试条件
Time
时间
Quantity
数量
Accepted/Rejected
接收/拒收
Reflow
回流焊
JESD22-B106
Temp:255℃max
T=10 sec
2times
22
0/1
Thermal Shock
冷热冲击
JESD22-A106
-40℃ 15min
↑↓
100℃ 15min
300
cycles
22
0/1
High Temperature Storage
高温保存
JESD22-A103
Temp:100℃
1000Hrs.
22
0/1
Low Temperature Storage
低温保存
JESD22-A119
Temp:-40℃
1000Hrs.
22
0/1
Life Test
常温通电
JESD22-A108
Ta=25℃
IF=20mA
1000Hrs.
22
0/1
失效判定标准  Criteria For Judging Damage
U.S.L: Upper standard level 规格上限
L.S.L: Lower standard level 规格下限
备注 / Note
信赖性测试基于匡通现有的测试平台
Judging For Damage
判定标准
Test Items
项目
Symbol
符号
Test Condition
测试条件
Min. 最小
Max. 最大
Forward Voltage
正向电压
VF
IF=20mA
-
U.S.L*)x1.1
Reverse Current
漏电流
IR
VR = 5V
-
U.S.L*)x2.0
光强
Luminous Intensity
Mcd
IF=20mA
L.S.L*)x0.7

<!-- Page 8 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
11.注意事项/ Cautions：
11.1. 焊接/welding
11.1.1 SMD LED 灌封胶较软，外力易损坏发光面及塑料壳，焊接时要轻拿轻放。
SMD LED is soft and easy to damage the luminous surface and plastic shell by external
force. It should be handled lightly when welding
11.1.2 建议使用易洗型的助焊剂，依照回流曲线条件回流焊接，回流次数最多两次，确保LED 发光面干净，
异物会影响发光颜色。
It is recommended to use soldering flux with tin wash type, reflow soldering according
to the condition of reflux curve, reflow twice at most, ensure the LED luminous surface
is clean, foreign matter will affect the luminous color。
11.1.3 只建议在修理和重工的情况下使用手工焊接；最高焊接温度不应超过300 度，且须在3 秒内完成（手
工焊接只可焊接一次）烙铁最大功率应不超过25W。
Manual welding is only recommended for repair and heavy industry;The maximum welding
temperature should not exceed 300 degrees, and must be completed within 3 seconds (manual
welding can only be welded once) soldering iron maximum power should not exceed 25W.
11.1.4 焊接过程中，严禁在高温情况下碰触胶体； 焊接后，禁止对胶体施加外力，禁止弯折PCB，避免元
件受到撞击。
During the soldering process, do not touch the lens at high temperature，After soldering,
any mechanical force on the lens or any excessive vibration shall not be accepted to apply,
also the circuit board shall not be bent as well.
11.1.5 请不要将不同BIN 级的LED 使用于同一个产品上，否则可能会导致产品的严重色差。
Please do not use different BIN LED on the same product, otherwise it may cause serious
color difference.
11.2. 清洗/cleaning
11.2.1 不能用超声波清洗,建议使用异丙醇（isopropyl alcohol）、纯酒精擦拭或浸渍(浸渍不超过1 分钟)
在室温下放置15 分钟再使用；清洗后,确保LED 发光面干净,异物会影响发光颜色。
/No ultrasonic cleaning. It is recommended to use isopropyl alcohol, pure alcohol to wipe
or soak, not more than 1 minute, and leave at room temperature for 15 minutes before use.
After cleaning, make sure the LED luminous surface is clean and the foreign matter will
affect the luminous color。

11.2.2 应避免接触或污染天那水,三氯乙烯、丙酮、硫化物、氮化物、酸、碱、盐类，这些物质会损伤LED.

Avoid touching or contaminating the water, trichloroethylene, acetone, sulfide, nitride,
acid, alkali, and salts that can damage leds.

<!-- Page 9 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
11.3. 灌封/enbedment
11.3.1 挥发性物质会渗透到LED 内部，在通电产生光子及热的条件下，会导致LED 变色，进而造成严重
光衰，严禁使用任何对LED 器件的性能或者可靠性有害的物质或材料，针对特定的用途和使用环境，
建议对所有的物质和材料进行相容性的测试。在贴装LED 时候，不要使用能产生有机挥发性气体的
粘结剂。
Volatile substances to leach into the LED inside, photons in electricity and heat conditions,
will lead to the LED color, thus causing serious droop, it is forbidden to use any of the
LED device performance or reliability of harmful substances or materials, for a specific
purpose and use of the environment, advice on all the material and the material
compatibility test.When attaching LED, do not use adhesive that can produce volatile
organic gas.
11.3.2 使用正常灌封胶时,建议先以少量试验，常温点亮168 小时，确定没有问题再作业。
          It is recommended to light up for 168 hours at room temperature for a small amount of test
before using normal filling and sealing glue。
11.4. 保存/save
11.4.1 打开包装前,LED 应存储在温度30℃或以下,相对湿度在RH60%以下,一年内使用。
Before opening the package, LED should be stored in a temperature 30 ℃ or below, under RH60
% relative humidity, used in a year。
11.4.2  LED 是湿度敏感元件,为避免元件吸湿,打开包装后,LED 应在温度30℃或以下,相对湿度在60%以
内,使用时间7 天。LED 吸潮后,回流焊时可能裂胶,影响发光颜色.对于未使用的散件,请去潮处理
（卷装品：烘烤60℃±5℃/24H；散装品：烘烤105℃±5℃/1H）,然后再用铝箔袋密封后保存或者
储存在氮气防潮柜内。
LED is humidity sensitive element, element to avoid moisture absorption, after open the packing,
the LED should be in temperature 30 ℃ or below, within 60% relative humidity, using time
7 days. After moisture absorption, LED may crack when reflow soldering, influence the luminous
color. For bulk is not used, please deal with the tide (for package product: bake 60 ℃ +
/ - 5 ℃ / 24 h.For bulk goods: baking 105 ℃ + 5 ℃, 1 hours), and then save after sealed
with aluminum foil bag or stored in nitrogen moistureproof enclosure
11.4.3  保存环境中避免有酸、碱以及腐蚀气体存在，同时避免强烈震动及强磁场作用。
Avoid the presence of acid, alkali and corrosive gas in the preservation environment,
and avoid strong vibration and strong magnetic field。

<!-- Page 10 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
11.5.静电/electrostatic
11.5.1  静电或峰值浪涌电压会损坏LED,避免在开灯、关灯时产生瞬时电压。
  Static electricity or peak surge voltage will damage the LED, avoiding instantaneous voltage
when the   lamp is turned on or off。
11.5.2  建议使用LED 时佩戴防静电手腕带,防静电手套,穿防静电鞋,使用的设备、仪器正确接地。LED 损坏
后,表现出漏电流明显增加,低电流正向电压变低，低电流点不亮等现象。

 It is recommended to wear anti-static wrist bands, anti-static gloves and anti-static shoes
when using LED. The equipment and instruments used are properly grounded. After the LED
was damaged, the leakage current increased obviously, the forward voltage of low current
became lower, and the low current point did not light, etc。

11.6 测试/test
11.6.1  LED 要在额定电流下驱动,同时电路中需要加限流电阻保护；否则,轻微的电压变化就会引起较大的电
流变化,从而破坏LED。

LED shall be driven at rated current, and shall be protected by current-limiting resistance
in the circuit. Otherwise, slight voltage changes will cause large current changes, which
will damage the LED.
11.6.2 在电路导通或关闭情况下,要避免瞬间浪涌电压的产生,否则LED 将被烧坏。

 When the circuit is on or off, avoid sudden surge voltage. Otherwise, the LED will be burnt
out
请参照下图示检测LED:/Please check the LED as shown
11.6.3 顺向电压VF 过高或反向电压VR 过高，均会损坏LED.
If the forward voltage VF is too high or the reverse voltage VR is too high, the LED will
be damaged.
11.6.4 点亮或测试LED 时，加在LED 两端的反向电压不得高于5V，否则容易击伤LED.

When lighting or testing the LED, the reverse voltage added on both ends of the LED shall
not be higher than 5V, otherwise it is easy to damage the LED.

<!-- Page 11 -->

湖北匡通电子股份有限公司
      (0603-0.6 红光）
11.6.5   LED 发光颜色会随着工作电流不同而有少许变化,建议设计时考虑电阻与LED 串联使用。

 LED luminous color will vary slightly with the working current. It is suggested that
resistance and LED should be used in series in the design
11.6.6  LED 容易因为自身的发热和环境的温度改变而改变，温度升高会降低LED 发光效率，影响发光颜色
在设计时应充分考虑散热问题。
LED is easy to change due to its own heat and changes in the temperature of the environment.
The increase in temperature will reduce the luminous efficiency of LED, which will affect
the luminous color. Heat dissipation should be fully considered in the design


---

# 11. Tactile Switch SW-01/SW-02 (OCR)

> **Role:** Tactile button — SW-01 / SW-02  
> **Covers:** `C720477` (Tactile button)

<!-- Page 1 -->

1 | 2 3 4 5 6 7 8 9 10 i | 12 | 13 | 14 |

 

ROHS Compliant MAPX MODIFICATION DATE DRAW APPROVE

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

A
01.80 |
1} 1 eo le B
: bod
©
c
5.00
3.90 °
ro OS ' ee
(| = FS Na
+ g e
a, | | sS 2.0 BAM ehLHE:
Crit AR:
\ 25 Rit pe 16:160g L
%D : 020:2.0H 26:260g
025:2.5H
F
EREASH HERE
The Main Thchnology Performance F £4 LOP 7 Be G
GE, BE E ah RGA 1 iat
Rate voltage.current S0mA DCT2V 2.90 D Wa REL 1 BEE
Sk 5.40 c ah Fa 2 8
< -———
Contact resistance <100ma 8 Ath LcP 1 Re, q
a | Oo A Kt #a i wa
: +50gf — ~ o We ah am ae ROME BE
Operating force @ — (2) | N ITEM DESCRIPTION MATERIAL, QTY FINSH/COLOR
te 0.2+0.1 MANUFACTURE DWG HES RARER TARARA a],
travel . .imm GongGuen xinPu Electronics Co Ltd
ee BAR PCB eA UNLESS OTHERWISE or il me TACT SWITCH
Insulated resistance #100Ma : SPECIFED TOLERANCES PAR | TS—1088—ARXXXXX |
on CIRCUIT DIAGRAM PCB.WELDING DRAWING OWN
ME, . DECIMALS: | ANGLES: CHKD J
Dielectric strength P25OVAC/1min 0.5~2£0.10 | £0.5° a Eu

   

 

 

 

2~5+£0.25 oF eal

5~10+0.30 CUSTOMER COPY SIZE:A4 | SHEET:1F1 REV:A

MS |SCALE1:1| | UNIT:MM ©

 

 

1 2 3 4 5 6 7 8 9 10 I 1 I 12 I 13 I 14 |


---

# 12. Uniroyal Thick Film Chip Resistors (0805) — generic catalog

> **Role:** Resistors (shared catalog)  
> **Covers:** `C17414` (R2,R3,R8,R9,R12,R17,R18,R19: 10k); `C23352` (R11: 24K); `C23179` (R13,R14,R15: 470); `C17521` (R16: 2.2); `C23186` (R6,R7: 5.1K  (no separate file — same catalog)); `C22978` (R10: 3.3K  (no separate file — same catalog))

<!-- Page 1 -->

DATA SHEET

Product Name

Thick Film Chip  Resistors
Part Name 01005/0201/0402/0603/0805/1206/1210/1812/2010/2512  Series

Uniroyal Electronics Global Co., Ltd.
88 Longteng Road, Economic & Technical Development Zone, Kunshan, Jiangsu, China
Tel
+86 512 5763 1411 / 22 /33
Email
marketing@uni-royal.cn
Manufacture Plant
Uniroyal Electronics Industry (kunshan) co., ltd.
Uniroyal  Electronics Industry Co., Ltd.
Uniroyal Electronics Global Co.,Ltd Shenzhen Branch
Aeon Technology Corporation
Uniroyal Electronics Global Co.,Ltd Xiamen Branch
Kunshan Foss Electronic material Co., Ltd.
Royal Electronic Factory (thailand) co., ltd
Brands
RoyalOhm       UniOhm

<!-- Page 2 -->

Feb.12,2019  V.3                                                 www.uniohm.com
Page  2/9
Thick Film Chip Resistors –Data Sheet
1.  Scope
1.1 This specification for approve relates to the Thick Film Chip Resistors manufactured by UNI-ROYAL.

1.2 Small size & light weight.
1.3 Reduction of assembly costs and matching with placement machine.
1.4 Suitable for both wave & re-flow soldering.
1.5 Applications: Navigator (GPS), Mobile Phone,Telecom, PDA, Setbox, Meter.

2.   Explanation of Part No. System
Part No. includes 14 codes shown as below:
2.1 1st~4th codes: Part name. E.g.: 01005, 0201, 0402, 0603, 0805, 1206 ,1210, 2010,1812, 2512.
2.2 5th~6th codes: Power rating.
E.g.: W=Normal Size

“1~G” = “1~16”
Wattage
1/32
3/4
1/2
1/3
1/4
1/8
1/10
1/16
1/20
1
Normal Size
WH
07
W2
W3
W4
W8
WA
WG
WM
1W
If power rating is lower or equal than 1 watt, 5th code would be “W” and 6th code would be a number or letter.
E.g.: WA=1/10W

W4=1/4W
2.3 7th code: Tolerance. E.g.: D=±0.5%      F=±1%
G=±2%
J=±5%

2.4 8th~11th codes: Resistance Value.
2.4.1 If value belongs to standard value of ≥5% series, 8th code would be zero,9th~10th codes are significant figures of the resistance and 11th code
is the power of ten.
2.4.2 If value belongs to standard value of ≤2% series, 8th~10th codes are significant figures of the resistance, and 11th code is the power of ten.
2.4.3 11th codes listed as following:
                      0=100    1=101 2=102
3=103
4=104
5=105
6=106
J=10-1
K=10-2
L=10-3
M=10-4     N=10-5       P=10-6
2.5 12th~14th codes.
2.5.1 12th code: Packaging Type. E.g.: C=Bulk

T=Tape/Reel
2.5.2 13th code: Standard Packing Quantity.
                      4=4000pcs
5=5000pcs
C=10000pcs
D=20000pcs
E=15000pcs
                      Chip Product:  BD=B/B-20000pcs           TC=T/R-10000pcs
2.5.3 14th code: Special features.
E = Environmental Protection, Lead Free, or Standard type.

3.  Ordering Procedure
(Example: 0805 1/8W ±5% 10KΩ T/R-5000)
0    8    0    5                            W     8                 J                      0      1      0      3                     T                   5                    E

Product Type:
Fill-in 4 digits with
the chip resistor
type as follows:
0105=01005
0201
0402
0603
0805
1206
1210
1812
2010
2512
Wattage:
Normal size:
WH=1/32W
WM=1/20W
WG=1/16W
WA=1/10W
W8=1/8W
W4=1/4W
W2=1/2W
07=3/4W
1W=1W
Tolerance:
D=±0.5%  F=±1%
G=±2%   J=±5%
Resistance Value:
5%(E-24 series):
The 1st digit will be “0”; the 2nd
& 3rd digits are for the significant
figures of the resistance and the
4th digit indicate the numbers of
zeros following.
≤1%(E24,E-96 series ):
The 1st to 3rd digits are for the
significant figures of the
resistance and 4th digit denotes
number of zeros following.
J=10-1; K=10-2; L=10-3
Packing Type:
T=Tape/Reel
Packing quantity:
1=1000PCS
2=2000PCS
3=3000PCS
4=4000PCS
5=5000PCS
C=10000PCS
D=20000PCS
E=15000PCS
Special Feature
E= Lead-Free

<!-- Page 3 -->

Feb.12,2019  V.3                                                 www.uniohm.com
Page  3/9
Thick Film Chip Resistors –Data Sheet
4.   Marking
(1) For 01005、0201 and 0402 size. Due to the very
01005、0201、0402 small size of the resistor’s
body, there is no marking on the body.

(2)Normally, the making of 0 0603, 0 0805,
0 1206, 0 1210, 0 1812, 0 2010,
0 2512 resistors as  following                                                                                                   0  0

(3) ±2%,5%Tolerance:The first two digits are
significant figures of resistance and the third
denotes number of zeros following                                                                                             333  33K

(4) ±0.5%、1% Tolerance: 4 digits, first three
digits are significant; forth digit is number of
zeros. Letter r is decimal point.                                                                                                    2701  2.7K

(5) More than 0805 specifications (including) 4 digits,
Product below 1Ω, show as following, the first digit
Is “R” which as decimal point.
R300  0.3

(6)  Standard E-96 series values  of 0603 ≤1% : due to the small size of the resistor’s body, 3 digits marking will be used to indicate the accurate
resistance value by using the following multiplier & resistance code.
Multiplier Code (for 0603 ≤±1% marking)
Code
A
B
C
D
E
F
G
H
X
Y
Z
Multiplier
100
101
102
103
104
105
106
107
10-1
10-2
10-3

Standard E-96 series Resistance Value code (for 0603≤±1% marking)
Value
Code
Value
Code
Value
Code
Value
Code
100
01
178
25
316
49
562
73
102
02
182
26
324
50
576
74
105
03
187
27
332
51
590
75
107
04
191
28
340
52
604
76
110
05
196
29
348
53
619
77
113
06
200
30
357
54
634
78
115
07
205
31
365
55
649
79
118
08
210
32
374
56
665
80
121
09
215
33
383
57
681
81
124
10
221
34
392
58
698
82
127
11
226
35
402
59
715
83
130
12
232
36
412
60
732
84
133
13
237
37
422
61
750
85
137
14
243
38
432
62
768
86
140
15
249
39
442
63
787
87
143
16
255
40
453
64
806
88
147
17
261
41
464
65
825
89
150
18
267
42
475
66
845
90
154
19
274
43
487
67
866
91
158
20
280
44
499
68
887
92
162
21
287
45
511
69
909
93
165
22
294
46
523
70
931
94
169
23
301
47
536
71
953
95
174
24
309
48
549
72
976
96

<!-- Page 4 -->

Feb.12,2019  V.3                                                 www.uniohm.com
Page  4/9
Thick Film Chip Resistors –Data Sheet
So the resistance value are marked as the following examples
1.96K=196101=29B
12.4=12410-1=10X

(7) Standard E-24 and not belong to E-96 series values (
±
≤1%) of 0603 size: the marking is the same as 5% tolerance but marking as underli
 333=33K
 680=68

5.  Dimension

6. Resistance Range

Resistance Range
Type
Power Rating
at 70℃
0.5%
1.0%
2.0%
5.0%
01005
1/32W
---
10Ω-10MΩ
10Ω-10MΩ
1Ω -10MΩ
0201
1/20W
---
1Ω-10MΩ
1Ω-10MΩ
1Ω-10MΩ
0402
1/16W
1Ω-10MΩ
1Ω-10MΩ
1Ω-10MΩ
1Ω-10MΩ
0603
1/10W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
1/8W
1Ω-10MΩ
0.1Ω≤R＜10MΩ
0.1Ω≤R＜10MΩ
0.1Ω≤R＜10MΩ
0805
1/4W
---
0.01Ω≤R＜0.1Ω
0.01Ω≤R＜0.1Ω
0.01Ω≤R＜0.1Ω
1/4W
1Ω-10MΩ
0.1Ω≤R＜10MΩ
0.1Ω≤R＜10MΩ
0.1Ω≤R＜10MΩ
1206
1/3W
---
0.01Ω≤R＜0.1Ω
0.01Ω≤R＜0.1Ω
0.01Ω≤R＜0.1Ω
1210
1/2W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
1812
3/4W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
2010
3/4W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
2512
1W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ

Type
Dimension(mm)

L
W
H
A
B
01005
0.40±0.02
0.20±0.02
0.13±0.02
0.10±0.05
0.10±0.03
0201
0.60±0.03
0.30±0.03
0.23±0.03
0.10±0.05
0.15±0.05
0402
1.00±0.10
0.50±0.05
0.35±0.05
0.20±0.10
0.25±0.10
0603
1.60±0.10
0.80±0.10
0.45±0.10
0.30±0.20
0.30±0.20
0805
2.00±0.15
1.25+0.15/-0.10
0.55±0.10
0.40±0.20
0.40±0.20
1206
3.10±0.15
 1.55 +0.15/-0.10
0.55±0.10
0.45±0.20
0.45±0.20
1210
3.10±0.10
2.60±0.20
0.55±0.10
0.50±0.25
0.50±0.20
1812
4.50±0.20
3.20±0.20
0.55±0.20
0.50±0.20
0.50±0.20
2010
5.00±0.10
2.50±0.20
0.55±0.10
0.60±0.25
0.50±0.20
2512
6.35±0.10
3.20±0.20
0.55±0.10
0.60±0.25
0.50±0.20

<!-- Page 5 -->

Feb.12,2019  V.3                                                 www.uniohm.com
Page  5/9
Thick Film Chip Resistors –Data Sheet
7. Ratings

Type
Max.
Working
Voltage
Max.
Overload
Voltage
Dielectric
withstanding
Voltage
Resistance Value
of Jumper
Rated Current of
Jumper
Max.
Overload Current
of Jumper
Operating
Temperature
01005
15V
30V
--
<50mΩ
0.5A
1A
-55℃~125℃
0201
25V
50V
--
<50mΩ
0.5A
1A
-55℃~155℃
0402
50V
100V
100V
<50mΩ
1A
2A
-55℃~155℃
0603
75V
150V
300V
<50mΩ
1A
2A
-55℃~155℃
0805
150V
300V
500V
<50mΩ
2A
5A
-55℃~155℃
1206
200V
400V
500V
<50mΩ
2A
10A
-55℃~155℃
1210
200V
500V
500V
<50mΩ
2A
10A
-55℃~155℃
1812
200V
500V
500V
<50mΩ
2A
10A
-55℃~155℃
2010
200V
500V
500V
<50mΩ
2A
10A
-55℃~155℃
2512
200V
500V
500V
<50mΩ
2A
10A
-55℃~155℃
8.  Recommend the size of welding plate

9. Derating Curve
Resistors shall have a power rating based on continuous load operation at an ambient temperature from -55℃ to 70℃. For temperature in excess
of 70℃, the load shall  be derated as shown in figure 1
Figure 1

Voltage rating:
Resistors shall have a rated direct-current (DC) continuous working
Voltage or an approximate sine-wave root-mean-square (RMS) alternating-current (AC) continuous working voltage at commercial-line frequency
and waveform corresponding to the power rating, as determined from the following formula:

RCWV =
R

 P 

Where: RCWV commercial-line frequency and waveform (Volt.)
P = power rating (WATT.)  R = nominal resistance (OHM)
In no case shall the rated DC or RMS AC continuous working voltage be greater than the applicable maximum value.
The overload voltage is 2.5 times RCWV or Max. Overload voltage whichever is less

Dimension(mm)
Type
A
B
C
D
01005
0.14±0.03
0.2±0.03
0.2±0.03
0.54±0.03
0201
0.25±0.05
0.35±0.05
0.4±0.05
1.0±0.05
0402
0.50±0.05
0.45±0.05
0.5±0.05
1.4±0.05
0603
0.9±0.05
0.65±0.05
0.8±0.05
2.1±0.05
0805
1.0±0.1
1.0±0.1
1.3±0.1
3.0±0.1
1206
2.0±0.1
1.1±0.1
1.6±0.1
4.2±0.1
1210
2.0±0.1
1.1±0.1
2.6±0.1
4.2±0.1
1812
3.2±0.1
1.4±0.1
3.3±0.1
5.8±0.1
2010
3.6±0.1
1.3±0.1
2.6±0.1
6.2±0.1
2512
5.0±0.1
1.6±0.1
3.3±0.1
8.2±0.1

<!-- Page 6 -->

Feb.12,2019  V.3                                                 www.uniohm.com
Page  6/9
Thick Film Chip Resistors –Data Sheet
10. Structure

11. Performance Specification

Characteristic
Limits
Test Method
(GB/T 5729&JIS-C-5201&IEC60115-1)
◎Temperature
Coefficient
01005:
1R≤R＜10: -200~+600PPM/℃
10≤R＜100: 300PPM/℃
100Ω≤R≤10M:±200PPM/℃
0201:
1≤R≤10: -100~﹢350PPM/℃
>10: 200PPM/℃
0402：
1≤R≤10: 200PPM/C
>10: 100PPM/℃
0603：
0.01Ω≤R≤0.03:1500 PPM/C
0.03Ω＜R≤0.05：1000 PPM/C
0.05Ω＜R＜1Ω: 800PPM/C
1≤R≤10: 200PPM/C
>10: 100PPM/℃
0805,1206,1210,2010,1812,2512:
0.01≤R≤0.015: 1500PPM/C
0.015＜R≤0.03: 1000PPM/C
0.03＜R＜1Ω: 800PPM/C
1≤R≤10: 200PPM/C
>10: 100PPM/℃

4.8 Natural resistance changes per temp. Degree centigrade
 R2-R1
               × 106 (PPM/℃)
R1(t2-t1)
R1: Resistance Value at room temperature （t1）;
R2: Resistance at test temperature
(Upper limit temperature or Lower limit temperature)
t1: +25°C or specified room temperature
t2:  Upper limit temperature or Lower limit temperature test
temperature

±0.5%,1%:
±(1.0%+0.05Ω)
±2%,5% :       ±(2.0%+0.05Ω)
01005:              ±(2.0%+0.05Ω)
4.13 Permanent resistance change after the application of a
potential of 2.5 times RCWV or Max. Overload Voltage
whichever less for 5 seconds..
◎ *Short-time
overload
* <50mΩ
Apply max Overload current for 0Ω
* Dielectric
withstanding
voltage
No evidence of flashover mechanical
damage, arcing or insulation breaks
down.
4.7 Resistors shall be clamped in the trough of a 90℃metallic v-
block and shall be tested at ac potential respectively specified in
the given list of each product type for 60-70 seconds.
Coverage must be over 95%.
Wave solder: Test temperature of solder: 245℃±3℃ dipping time
in solder: 2-3 seconds.
◎ *Solderability
Go up tin rate bigger than half of end
pole
Reflow:

<!-- Page 7 -->

Feb.12,2019  V.3                                                 www.uniohm.com
Page  7/9
Thick Film Chip Resistors –Data Sheet
±0.5%,1%:          ±(0.5%+0.05)
±2%,5% :             ±(1.0%+0.05)
◎ Rapid change of
temperature
01005:                   ±(1.0%+0.05Ω)
4.19 30 min at -55 °C and 30 min at 155°C; 100 cycles.
◎ Soldering
heat
±(1.0%+0.05Ω)
4.18 Dip the resistor into a solder bath having a temperature of
260℃5℃ and hold it for 10±1 seconds.
Terminal bending
±(1.0%+0.05Ω)
4.33 Twist of test board:
Y/X = 3/90 mm for 60Seconds
* Insulation
resistance
≥1,000 MΩ
4.6 The measuring voltage shall be ,measured with a direct voltage
of (100±15)V or a voltage equal to the dielectric withstanding
voltage., and apply for 1min.
±0.5%,1%:      ±(0.5%+0.05)
±2%,5%  :       ±(3.0%+0.05)
◎ Humidity
( steady state )
01005(-55℃~125℃):
±(2.0%+0.05Ω)
4.24Temporary resistance change after 240 hours exposure in a
humidity test chamber controlled at 40±2℃ and 90-95% relative
humidity,
±0.5%,1% :     ±(1.0%+0.05)
±2%,5% :        ±(3.0%+0.05)
01005:               ±(3.0%+0.05)
7.9 Resistance change after 1,000 hours (1.5 hours “ON”,0.5 hour
“OFF”) at RCWV in a humidity  chamber controlled at 40℃±2℃
and 90 to 95% relative humidity.
◎ *Load life
in humidity
* <50mΩ
Apply to rated current for 0Ω
±0.5%,1%:  ±(1.0%+0.05)
±2%,5%   :
±(3.0%+0.05)
01005:              ±(3.0%+0.05)
4.25.1 Permanent resistance change after 1,000 hours operating at
RCWV with duty cycle 1.5 hours “ON”, 0.5 hour “OFF” at
70℃±2℃ ambient.
◎ *Load life
* <50Mω
Apply to rated current for 0Ω
±0.5%,1% :     ±(1.0%+0.05)
±2%,5%    :     ±(3.0%+0.05)

4.23.4    Lower limit temperature，for 2H.
◎
*Low
Temperature
Storage
* <50mΩ
Apply to rated current for 0Ω
±0.5%,1%:      ±(1.0%+0.05)
±2%,5%   :      ±(3.0%+0.05)

4.23.2    Upper limit temperature ，for 16H.
01005:               ±(1.0%+0.05)
4.23.2    Upper limit temperature ，for 1000H.
◎ *High
Temperature
Exposure
* <50mΩ
Apply to rated current for 0Ω
◎ *Leaching
No visible damage
 J-STD-002 Test D
Samples completely immersed for 30 sec in solder bath at 260
.
℃
The resistors of 0Ω only can do the characteristic noted of *
The resistors of 01005 & 0201 only can do the characteristic noted of ◎

12.  Packing of Surface Mount Resistors
12.1 Dimension of Paper Taping :(Unit: mm)

Type
A
B
C
±0.05
+0.1
ΦD
     -0
E
±0.1
F
±0.05
G
±0.1
W
±0.2
T
01005
0.24±0.05
0.45±0.05
2.00
1.50
1.75
3.50
4.00
8.00
0.40±0.1
0201
0.40±0.05
0.70±0.05
2.00
1.50
1.75
3.50
4.00
8.00
0.42±0.1
0402
0.65±0.10
1.20±0.10
2.00
1.50
1.75
3.50
4.00
8.00
0.42±0.05

<!-- Page 8 -->

Feb.12,2019  V.3                                                 www.uniohm.com
Page  8/9
Thick Film Chip Resistors –Data Sheet

12.2 Dimension of Embossed Taping: (Unit: mm)

12.3 Dimension of Reel：(Unit: mm)

13.  Note
Type
A
 ±0.2
B
 ±0.2
C
±0.05
+0.1
ΦD
  -0
E
±0.1
F
±0.05
G
±0.1
W
±0.2
T
±0.1
0603
1.10
1.90
2.00
1.50
1.75
3.50
4.00
8.00
0.67
0805
1.65
2.40
2.00
1.50
1.75
3.50
4.00
8.00
0.81
1206
2.00
3.60
2.00
1.50
1.75
3.50
4.00
8.00
0.81
1210
2.80
3.50
2.00
1.50
1.75
3.50
4.00
8.00
0.75
Type
A
0.2
B
0.2
C
0.05
+ 0.1
D
- 0
+0.25
D1
-0
E
0.1
F
0.05
G
0.1
W
0.2
T
±0.1
2010
2.90
5.60
2.00
1.50
1.50
1.75
5.50
4.00
12.00
1.00
1812
3.50
4.80
2.00
1.50
1.50
1.75
5.50
4.00
12.00
1.00
2512
3.50
6.70
2.00
1.50
1.50
1.75
5.50
4.00
12.00
1.00
Type
Taping
Qty/Reel
A
0.5
B
0.5
C
0.5
D
1
M
2
W
1
01005
Paper
20,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
0201
Paper
15,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
0402
Paper
10,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
0603
Paper
5,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
0805
Paper
5,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
1206
Paper
5,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
1210
Paper
5,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
2010
Embossed
4,000pcs
2.0
13.0
21.0
60.0
178.0
13.8
1812
Embossed
4,000pcs
2.0
13.0
21.0
60.0
178.0
13.8
2512
Embossed
4,000pcs
2.0
13.0
21.0
60.0
178.0
13.8

<!-- Page 9 -->

Feb.12,2019  V.3                                                 www.uniohm.com
Page  9/9
Thick Film Chip Resistors –Data Sheet
13.1. UNI-ROYAL recommend the storage condition temperature: 15℃~35℃, humidity :25%~75%.
(Put condition for individual product).Even under UNI-ROYAL recommended storage condition, solderability of products over 1 year old.
(Put condition for each product) may be degraded.
13.2. Store / transport cartons in the correct direction, which is indicated on a carton as a symbol.
Otherwise bent leads may occur due to excessive stress applied when dropping of a carton.
13.3. Product performance and soldered connections may deteriorate if the products are stored in the following places:
        a. Storage in high Electrostatic.
b. Storage in direct sunshine、rain and snow or condensation.
c. Where the products are exposed to sea winds or corrosive gases, including Cl2, H2S3 NH3, SO2, NO2.
13.4. The products are used in circuit board thickness greater than 1.6mm. If customers use less than the thickness of the circuit board that you
should confirm with the company, in order to recommend a more suitable product.

14.  Record

Version
Description of amendment
Page
Date
Amended by
Checked by
1
First issue of this specification
1~7
Mar.20, 2018
Chen Haiyan
Chen Nana
2
Modify 0201 packing quantity
7
May.24, 2018
Chen Haiyan
Chen Nana
3
1. Add 0603 code mark
2. Modify the operating temperature of 01005
3. Modify the Performance Specification
3~4
5
6~7
Feb.12, 2019
Chen Haiyan
Xu Yuhua
Uniroyal Electronics Global Co., Ltd. , all rights reserved. Spec. herein would be changed at any time without prior notice.


---

# 13. Uniroyal Thick Film Chip Resistors — 0-ohm jumper

> **Role:** Resistor — 0 ohm  
> **Covers:** `C21189` (R1,R4,R5: 0)

<!-- Page 1 -->

DATASHEET

Product Name

Thick Film Chip  Resistors
Part Name
File No.

Chip Series
SMD-SP-001

Uniroyal Electronics Global Co., Ltd.
88#, Longteng Road, Economic & Technical Development Zone, Kunshan, Jiangsu, China
Tel
+86 512 5763 1411 / 22 /33
Email
marketing@uni-royal.cn
Manufacture Plant
Uniroyal Electronics Industry Co., Ltd.
Aeon Technology Corporation
Royal Electronic Factory (Thailand) Co., Ltd.
Royal Technology (Thailand) Co., Ltd.

<!-- Page 2 -->

Jun.21,2025  V.9                                                 www. uni-royal.cn
Page  2/9
Thick Film Chip Resistors
1.  Scope
1.1 This datasheet is the characteristics of Thick Film Chip Resistors manufactured by UNI-ROYAL.

1.2 Small size & light weight.
1.3 Reduction of assembly costs and matching with placement machine.
1.4 Suitable for both wave & re-flow soldering.
1.5 Applications: Navigator (GPS), Mobile Phone, Telecom, PDA, Setbox, Meter.
1.6 Compliant with RoHS directive.
1.7 Halogen free requirement.

2.   Part No. System
Part No. includes 14 codes shown as below:
2.1 1st~4th codes: Part name. E.g.: 01005, 0201, 0402, 0603, 0805, 1206 ,1210, 2010,1812, 2512.
2.2   5th~6th codes: Power rating.
E.g.: W=Normal Size

“1~G” = “1~16”
Wattage
1/32
3/4
1/2
1/3
1/4
1/8
1/10
1/16
1/20
1
Normal Size
WH
07
W2
W3
W4
W8
WA
WG
WM
1W
If power rating is equal or lower than 1 watt, 5th code would be “W” and 6th code would be a number or letter.
E.g.: WA=1/10W

W4=1/4W
2.2 7th code: Tolerance. E.g.: D=±0.5%
F=±1%
G=±2%
J=±5%

2.4 8th~11th codes: Resistance value.
2.4.1 If value belongs to standard value of E-24 series, the 8th code is zero, 9th~10th codes are the significant figures of resistance value, and the
11th code is the power of ten.
2.4.2 If value belongs to standard value of E-96 series, the 8th~10th codes are the significant figures of resistance value, and the 111th code is the
power of ten.
2.4.3 11th codes listed as following:
  0=100     1=101    2=102   3=103
4=104
5=105
6=106
J=10-1
K=10-2
L=10-3
M=10-4     N=10-5   P=10-6
2.5 12th~14th codes.
2.5.1 12th code: Packaging Type. E.g.:   T=Tape/Reel
2.5.2 13th code: Standard Packing Quantity.
                       4=4,000pcs
5=5,000pcs
C=10,000pcs
D=20,000pcs
E=15,000pc
2.5.3 14th code: Special features.
E = standard

3.  Ordering Procedure
(Example: 0805 1/8W ±5% 10KΩ T/R-5000)
0    8    0    5                            W     8                 J                      0      1      0      3                     T                     5                             E

Product Type:
Fill-in 4 digits with
the chip resistor
type as follows:
0105=01005
0201
0402
0603
0805
1206
1210
1812
2010
2512
Wattage:
Normal size:
WH=1/32W
WM=1/20W
WG=1/16W
WA=1/10W
W8=1/8W
W4=1/4W
W3=1/3W
W2=1/2W
07=3/4W
1W=1W
Tolerance:
D=±0.5%  F=±1%
G=±2%   J=±5%
Resistance Value:
5%(E-24 series):
The 1st digit will be “0”; the 2nd
& 3rd digits are for the significant
figures of the resistance and the
4th digit indicate the numbers of
zeros following.
≤1% (E-96 series):
The 1st to 3rd digits are for the
significant figures of the
resistance and 4th digit denotes
number of zeros following.
J=10-1; K=10-2; L=10-3
Packing Type:
T=Tape/Reel
Packing quantity:
01005:
D=20,000PCS
0201:
E=15,000PCS
0402:
C=10000PCS
0603,0805,1206,1210:
5=5,000PCS
2010,1812,2512:
4=4000PCS
Special Feature
E= Standard

<!-- Page 3 -->

Jun.21,2025  V.9                                                 www. uni-royal.cn
Page  3/9
Thick Film Chip Resistors
4.   Marking
4.1 For 01005、0201 and 0402 size. Due to the very
small size of the resistor’s body, there is no marking
 on the body.

4.2 Normally, the marking of 0Ω 0603, 0Ω 0805,
0Ω 1206, 0Ω 1210, 0Ω 1812, 0Ω 2010,
0Ω 2512 resistors as  following

 4.3 ±5% tolerance products (E-24 series):
3 codes.
1st~2nd codes are the significant figures of resistance value,
and the rest code is the power of ten.                                                                                       333 → 33KΩ

4.4  ±0.5%±1% tolerance products  (E-96 series):
4 codes.
1st~3rd codes are the significant figures of resistance value,
and the rest code is the power of ten.
Letter "R" in mark means decimal point.                                                                               2701 → 2.7KΩ

4.5 More than 0805 specifications (including) 4 digits,
Product below 1Ω, show as following, the first digit
Is “R” which as decimal point.
R300 → 0.3Ω
4.6  Standard E-96 series values  of 0603 ≤1% : due to the small size of the resistor’s body, 3 digits marking will be used to indicate the accurate
resistance value by using the following multiplier & resistance code.
Multiplier Code (for 0603 ≤±1% marking)
Code
A
B
C
D
E
F
G
H
X
Y
Z
Multiplier
100
101
102
103
104
105
106
107
10-1
10-2
10-3
Standard E-96 series Resistance Value code (for 0603≤±1% marking)
Value
Code
Value
Code
Value
Code
Value
Code
100
01
178
25
316
49
562
73
102
02
182
26
324
50
576
74
105
03
187
27
332
51
590
75
107
04
191
28
340
52
604
76
110
05
196
29
348
53
619
77
113
06
200
30
357
54
634
78
115
07
205
31
365
55
649
79
118
08
210
32
374
56
665
80
121
09
215
33
383
57
681
81
124
10
221
34
392
58
698
82
127
11
226
35
402
59
715
83
130
12
232
36
412
60
732
84
133
13
237
37
422
61
750
85
137
14
243
38
432
62
768
86
140
15
249
39
442
63
787
87
143
16
255
40
453
64
806
88
147
17
261
41
464
65
825
89
150
18
267
42
475
66
845
90
154
19
274
43
487
67
866
91
158
20
280
44
499
68
887
92
162
21
287
45
511
69
909
93
165
22
294
46
523
70
931
94
169
23
301
47
536
71
953
95
174
24
309
48
549
72
976
96

<!-- Page 4 -->

Jun.21,2025  V.9                                                 www. uni-royal.cn
Page  4/9
Thick Film Chip Resistors
So the resistance value are marked as the following examples
1.96KΩ=196×101Ω=29B
12.4Ω=124×10-1Ω=10X

4.7 Standard E-24 and not belong to E-96 series values (≤±1%) of 0603 size: the marking is the same as 5% tolerance but marking as underline.
 333=33KΩ
 680=68Ω

5.  Dimension

6. Resistance Range

Type
Power Rating
Resistance Range
±0.5%
±1.0%
±2.0%
±5.0%
01005
1/32W
---
1Ω-10MΩ
1Ω-10MΩ
1Ω -10MΩ
0201
1/20W
1Ω-10MΩ
1Ω-10MΩ
1Ω-10MΩ
1Ω-10MΩ
0402
1/16W
1Ω-10MΩ
0.1Ω-10MΩ
0.1Ω-10MΩ
0.1Ω-10MΩ
0603
1/10W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0805
1/8W
1Ω-10MΩ
0.1Ω≤R≤10MΩ
0.1Ω≤R≤10MΩ
0.1Ω≤R≤10MΩ
1/4W
---
0.01Ω≤R＜0.1Ω
0.01Ω≤R＜0.1Ω
0.01Ω≤R＜0.1Ω
1206
1/4W
1Ω-10MΩ
0.1Ω≤R≤10MΩ
0.1Ω≤R≤10MΩ
0.1Ω≤R≤10MΩ
1/3W
---
0.01Ω≤R＜0.1Ω
0.01Ω≤R＜0.1Ω
0.01Ω≤R＜0.1Ω
1210
1/2W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
1812
3/4W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
2010
3/4W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
2512
1W
1Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ
0.01Ω-10MΩ

Type
Dimension(mm)
L
W
H
A
B
01005
0.40±0.02
0.20±0.02
0.13±0.02
0.10±0.03
0.10±0.03
0201
0.60±0.03
0.30±0.03
0.23±0.03
0.10±0.05
0.15±0.05
0402
1.00±0.10
0.50±0.05
0.35±0.05
0.20±0.10
0.25±0.10
0603
1.60±0.10
0.80±0.10
0.45±0.10
0.30±0.20
0.30±0.20
0805
2.00±0.15
1.25+0.15/-0.10
0.55±0.10
0.40±0.20
0.40±0.20
1206
3.10±0.15
 1.55 +0.15/-0.10
0.55±0.10
0.45±0.20
0.45±0.20
1210
3.10±0.10
2.50±0.15
0.55±0.10
0.50±0.25
0.50±0.20
1812
4.50±0.20
3.20±0.20
0.55±0.20
0.50±0.20
0.50±0.20
2010
5.00±0.10
2.50±0.20
0.55±0.10
0.60±0.25
0.50±0.20
2512
6.35±0.10
3.20±0.20
0.55±0.10
0.60±0.25
0.50±0.20

<!-- Page 5 -->

Jun.21,2025  V.9                                                 www. uni-royal.cn
Page  5/9
Thick Film Chip Resistors
7. Ratings

Type
Max.
Working
Voltage
Max.
Overload
Voltage
Dielectric
withstanding
Voltage
Resistance
Value of
Jumper
Rated
Current of
Jumper
Max.
Overload
Current of
Jumper
Operating
Temperature
01005
15V
30V
--
<50mΩ
0.5A
1A
-55℃~125℃
0201
25V
50V
--
<50mΩ
0.5A
1A
-55℃~155℃
0402
50V
100V
100V
<50mΩ
1A
2A
-55℃~155℃
0603
75V
150V
300V
<50mΩ
1A
2A
-55℃~155℃
0805
150V
300V
500V
<50mΩ
2A
5A
-55℃~155℃
1206
200V
400V
500V
<50mΩ
  2A
10A
-55℃~155℃
1210
200V
500V
500V
<50mΩ
2A
10A
-55℃~155℃
1812
200V
500V
500V
<50mΩ
2A
10A
-55℃~155℃
2010
200V
500V
500V
<50mΩ
2A
10A
-55℃~155℃
2512
200V
500V
500V
<50mΩ
2A
10A
-55℃~155℃
* Note: The measurement position of the 0Ω resistance value should be based on the positive electrode
8. Derating Curve
Power rating will change based on continuous load at ambient temperature from -55 to 155℃or 125℃.
It is constant between -55 to 70℃, and derate to zero when temperature rise from 70 to 155℃or 125℃.
Voltage rating:
Resistors shall have a rated direct-current (DC) continuous working voltage or an approximate sine-wave
root-mean-square (RMS) alternating-current (AC) continuous working voltage at commercial-line
frequency and waveform corresponding to the power rating, as determined from the following formula:
                  RCWV = √𝑃× R
Remark: RCWV: Rating Continuous Working Voltage (Volt.)      P: power rating (Watt)      R: nominal resistance (Ω)
In no case shall the rated DC or RMS AC continuous working voltage be greater than the applicable maximum value.
The overload voltage is 2.5 times RCWV or Max. Overload voltage whichever is lower.

9. Structure

<!-- Page 6 -->

Jun.21,2025  V.9                                                 www. uni-royal.cn
Page  6/9
Thick Film Chip Resistors
10． Performance Specification

Characteristic
Limits
Test Methods
(GB/T 5729&JIS-C-5201&IEC60115-1)
◎Temperature
Coefficient
01005:
1ΩR≤R＜10Ω: -200~+600PPM/℃
10Ω≤R＜100Ω: ±300PPM/℃
100Ω≤R≤10MΩ:±200PPM/
℃

0201:
1Ω≤R≤10Ω: -100~﹢350PPM/℃
>10Ω: ±200PPM/℃
0402：
0.1Ω≤R＜1Ω: ±800PPM/℃
1Ω≤R≤10Ω: ±200PPM/℃
>10Ω: ±100PPM/℃
0603：
0.01Ω≤R≤0.03Ω:±1500 PPM/℃
0.03Ω＜R≤0.05Ω：±1000 PPM/℃
0.05Ω＜R＜1Ω: ±800PPM/℃
1Ω≤R≤10Ω: ±200PPM/℃
>10Ω: ±100PPM/℃
0805,1206,1210,2010,1812,2512:
0.01Ω≤R≤0.015Ω: ±1500PPM/℃
0.015Ω＜R≤0.03Ω: ±1000PPM/℃
0.03Ω＜R＜1Ω: ±800PPM/℃
1Ω≤R≤10Ω: ±200PPM/℃
>10Ω: ±100PPM/℃
4.8 Natural resistance changes per temp. Degree centigrade
 R2-R1
               × 106 (PPM/℃)
R1(t2-t1)
R1: Resistance Value at room temperature （t1）;
R2: Resistance at test temperature （t2）
t1: +25℃ or specified room temperature
t2:  Test temperature（-55℃or 125℃）
◎ *Short-time
overload
±0.5%,±1%:     ±(1.0%+0.05Ω)
4.13 Permanent resistance change after the application of a
potential of 2.5 times RCWV or Max. Overload Voltage
whichever less for 5 seconds..
±2%,±5% :       ±(2.0%+0.05Ω)
01005:              ±(2.0%+0.05Ω)
* <50mΩ
Apply max Overload current for 0Ω
* Dielectric
withstanding
voltage
No evidence of flashover mechanical
damage, arcing or insulation breaks
down.
4.7 Resistors shall be clamped in the trough of a 90°metallic v-
block and shall be tested at ac potential respectively specified in
the given list of each product type for 60-70 seconds.
◎ *Solderability
Coverage must be over 95%.
4.17 The area covered with a new, smooth, clean, shiny and
continuous surface free from concentrated pinholes. Temperature
of solder:245±3℃; Dwell time in solder: 2~3 seconds.
◎ Rapid change of
temperature
±0.5%,±1%:          ±(0.5%+0.05Ω)
4.19 30 min at -55 ℃ and 30 min at 155℃  (01005:125℃);
100 cycles.
±2%,±5% :             ±(1.0%+0.05Ω)
01005(-55
℃~125℃)
:
±(1.0%+0.05Ω)
◎ Soldering
heat
±(1.0%+0.05Ω)
4.18 Dip the resistor into a solder bath having a temperature of
260℃±5℃ and hold it for 10±1 seconds.
Terminal bending
±(1.0%+0.05Ω)
4.33 Twist of test board:
Y/X = 3/90 mm for 60Seconds
* Insulation
resistance
≥1,000 MΩ
4.6 The measuring voltage shall be ,measured with a direct voltage
of (100±15)V or a voltage equal to the dielectric withstanding
voltage., and apply for 1min.
◎ Humidity
( steady state )
±0.5%,±1%:      ±(0.5%+0.05Ω)
4.24Temporary resistance change after 240 hours exposure in a
humidity test chamber controlled at 40±2℃ and 90-95% relative
humidity,
±2%,±5%  :       ±(3.0%+0.05Ω)
01005:                ±(2.0%+0.05Ω)
◎ *Load life
in humidity
±0.5%,±1% :     ±(1.0%+0.05Ω)
7.9 Resistance change after 1000 hours (1.5hours“ON”，
0.5hours“OFF”) at RCWV or Max. Working Voltage
whichever less in a humidity test chamber controlled at 40±2℃
and 93%±3% RH.
±2%,±5% :        ±(3.0%+0.05Ω)
01005:               ±(3.0%+0.05Ω)
* <50mΩ
Apply to rated current for 0Ω
◎ *Load life
±0.5%,±1%:     ±(1.0%+0.05Ω)
4.25.1 Permanent Resistance change after 1000 hours operating at
RCWV or Max. Working Voltage whichever less with duty cycle
of 1.5 hours “ON”，0.5 hour “OFF” at 70±2℃ ambient.
±2%,±5%   :     ±(3.0%+0.05Ω)
01005:              ±(3.0%+0.05Ω)
* <50mΩ
Apply to rated current for 0Ω

<!-- Page 7 -->

Jun.21,2025  V.9                                                 www. uni-royal.cn
Page  7/9
Thick Film Chip Resistors
◎*Low
Temperature
Storage
±0.5%,±1% :     ±(1.0%+0.05Ω)
IEC 60068-2-1 (Aa)
Lower limit temperature，for 2H.
±2%,±5%    :     ±(3.0%+0.05Ω)
01005:               ±(3.0%+0.05Ω)
* <50mΩ
◎ *High
Temperature
Exposure
±0.5%,±1%:      ±(1.0%+0.05Ω)
MIL-STD-202 108A
Upper limit temperature ，for 1000H.
±2%,±5%   :      ±(3.0%+0.05Ω)
01005:               ±(3.0%+0.05Ω)
* <50mΩ
◎ *Leaching
No visible damage
 J-STD-002 Test D
Samples completely immersed for 30 sec in solder bath at 260
℃.

The resistors of 0Ω only can do the characteristic noted of *
The resistors of 01005 & 0201 only can do the characteristic noted of ◎

11. Soldering Condition
(This is for recommendation, please customer perform adjustment according to actual application)
11.1 Recommend Reflow Soldering Profile：(solder : Sn96.5 / Ag3 / Cu0.5)

Profile Feature
Lead (Pb)-Free solder
Preheat：
Temperature Min (Tsmin)
Temperature Max (Tsmax)
Time (Tsmin to Tsmax ) (ts)

150℃
200℃
60 -120 seconds
Average ramp-up rate：
(Ts max to Tp)

3℃ / second max.
Time maintained above :
Temperature (TL)
Time (tL)

217℃
60-150 seconds
Peak Temperature (Tp)
260℃
Time within +0
−5℃ of actual peak Temperature (tp)2
10 seconds
Ramp-down Rate
6℃/second max.
Time 25℃ to Peak Temperature
8minutes max.
Allowed Re-flow times : 2 times
Remark : To avoid discoloration phenomena of chip on terminal electrodes, we suggest use N2 Re-flow furnace .

<!-- Page 8 -->

Jun.21,2025  V.9                                                 www. uni-royal.cn
Page  8/9
Thick Film Chip Resistors
11.2 Recommend Wave Soldering Profile：(Apply to 0603 and above size)

11.3  Soldering pad size recommended

12. Packing
12.1 Dimension of Paper Taping:(Unit: mm)

12.2 Dimension of plastic taping: (Unit: mm)

Type
Dimension(mm)
A
B
C
D
01005
0.14±0.03
0.2±0.03
0.2±0.03
0.54±0.03
0201
0.25±0.05
0.35±0.05
0.4±0.05
1.0±0.05
0402
0.50±0.05
0.45±0.05
0.5±0.05
1.4±0.05
0603
0.9±0.05
0.65±0.05
0.8±0.05
2.1±0.05
0805
1.0±0.1
1.0±0.1
1.3±0.1
3.0±0.1
1206
2.0±0.1
1.1±0.1
1.6±0.1
4.2±0.1
1210
2.0±0.1
1.1±0.1
2.6±0.1
4.2±0.1
1812
3.2±0.1
1.4±0.1
3.3±0.1
5.8±0.1
2010
3.6±0.1
1.3±0.1
2.6±0.1
6.2±0.1
2512
5.0±0.1
1.6±0.1
3.3±0.1
8.2±0.1
Type
A
B
C
±0.05
ΦD−0
+0.1
E
±0.1
F
±0.05
G
±0.1
W
±0.2
T
01005
0.24±0.05
0.45±0.05
2.00
1.50
1.75
3.50
4.00
8.00
0.40±0.1
0201
0.40±0.05
0.70±0.05
2.00
1.50
1.75
3.50
4.00
8.00
0.42±0.1
0402
0.65±0.10
1.20±0.10
2.00
1.50
1.75
3.50
4.00
8.00
0.42±0.05
Type
A
±0.2
B
±0.2
C
±0.05
ΦD−0
+0.1
E
±0.1
F
±0.05
G
±0.1
W
±0.2
T
±0.1
0603
1.10
1.90
2.00
1.50
1.75
3.50
4.00
8.00
0.67
0805
1.65
2.40
2.00
1.50
1.75
3.50
4.00
8.00
0.81
1206
2.00
3.60
2.00
1.50
1.75
3.50
4.00
8.00
0.81
1210
2.80
3.50
2.00
1.50
1.75
3.50
4.00
8.00
0.75
Type
A
±0.2
B
±0.2
C
±0.05
ΦD−0
+0.1
ΦD1−0
+0.25
E
±0.1
F
±0.05
G
±0.1
W
±0.2
T
±0.1
2010
2.90
5.60
2.00
1.50
1.50
1.75
5.50
4.00
12.00
1.00
1812
3.50
4.80
2.00
1.50
1.50
1.75
5.50
4.00
12.00
1.00
2512
3.50
6.70
2.00
1.50
1.50
1.75
5.50
4.00
12.00
1.00

<!-- Page 9 -->

Jun.21,2025  V.9                                                 www. uni-royal.cn
Page  9/9
Thick Film Chip Resistors
12.3 Dimension of Reel：(Unit: mm)

13.  Note
13.1   UNI-ROYAL recommend products store in warehouse with temperature between 15 to 35℃ under humidity between 25 to 75%RH.
Even under storage conditions recommended above, solder ability of products will be degraded stored over 1 year old.
13.2   Cartons must be placed in correct direction which indicated on carton, otherwise the reel or wire will be deformed.
13.3   Storage conditions as below are inappropriate:
a. Stored in high electrostatic environment
b. Stored in direct sunshine, rain, snow or condensation.
c. Exposed to sea wind or corrosive gases, such as Cl2, H2S, NH3, SO2, NO2, Br etc.
13.4. The products are used in circuit board thickness greater than 1.6mm. If customers use less than the thickness of the circuit board that you
should confirm with the company, in order to recommend a more suitable product.

14.  Record

Version
Description
Page
Date
Amended by
Checked by
1
First version
1~7
Mar.20, 2018
Haiyan Chen
Nana Chen
2
Modify 0201 packing quantity
7
May.24, 2018
Haiyan Chen
Nana Chen
3
1. Add 0603 code mark
2. Modify the operating temperature of 01005
3. Modify characteristic
3~4
5
6~7
Feb.12, 2019
Haiyan Chen
Yuhua Xu
4
Modify the High Temperature  Exposure conditions
7
July.29, 2019
Haiyan Chen
Yuhua Xu
5
Modify the reflow curve and add the wave soldering
curve
7~8
Apr.22, 2020
Haiyan Chen
Yuhua Xu
6
Add the Alloy Film Resistance Range and Ordering
Procedure
4
2
Sep.05, 2022
Haiyan Chen
Yuhua Xu
7
Modify the temperature coefficient test conditions
6
Oct.13, 2022
Haiyan Chen
Yuhua Xu
8
Modify the "W" dimension of 1210
4
Apr.28, 2025
Haiyan Chen
Yuhua Xu
9
Modify the resistance value range of 01005and
0402
Add the resistance range of 0201 by 0.5%
4
Jun.21, 2025
Haiyan Chen
Yuhua Xu
© Uniroyal Electronics Global Co., Ltd. All rights reserved. Specification herein will be changed at any time without prior notice.

Type
Taping
Qty/Reel
A
±0.5
B
±0.5
C
±0.5
D
±1
M
±2
W
±1
01005
Paper
20,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
0201
Paper
15,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
0402
Paper
10,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
0603
Paper
5,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
0805
Paper
5,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
1206
Paper
5,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
1210
Paper
5,000pcs
2.0
13.0
21.0
60.0
178.0
10.0
2010
Embossed
4,000pcs
2.0
13.0
21.0
60.0
178.0
13.8
1812
Embossed
4,000pcs
2.0
13.0
21.0
60.0
178.0
13.8
2512
Embossed
4,000pcs
2.0
13.0
21.0
60.0
178.0
13.8


---

# 14. MLCC Capacitor Catalog — generic (0805 X5R/X7R)

> **Role:** Capacitors (shared MLCC catalog)  
> **Covers:** `C28233` (C1,C3,C8,C24: 0.1uF); `C19702` (C2,C11: 10uF); `C28323` (C4,C9,C10 / C18: 1uF (X5R) / 1uF X7R); `C19666` (C7,C12: 4.7uF); `C21120` (C13: 220nF); `C1653` (C14: TBD); `C15849` (C15,C16,C17,C19,C20,C21,C22,C23: 1uF X5R)

<!-- Page 1 -->

November 2015
1.86g
MLCC(02A104M) 1piece
C
a
r
b
o
n

E
m
i
s
s
i
o
n

<!-- Page 2 -->

1.86g
MLCC(02A104M) 1piece
1.86g
C
a
r
b
o
n

E
m
i
s
s
i
o
n
We declare that all our MLCCs are produced in accordance
with EU ROHS and REACH Directive.
1.RoHS Compliance and restriction of Br
The following restricted materials are not used in packaging materials as well as products in  compliance with the law and restriction.
- Cd, Pb, Hg, Cr6+, As, Br and the compounds, PCB, asbestos
2.No use of materials breaking Ozone layer
The following ODS materials are not used in our fabrication process.
- ODS material : Freon, Haron, 1-1-1 TCE, CCl4, HCFC
If you want more detailed Information,Please Visit Samsung Electro-mechanics Website
[http://www.semlcr.com]
Please, see the last page of this catalog for our environ mental certification list.

<!-- Page 3 -->

CONTENTS
Part Numbering System
Standard & High Capacitors
Medium-High Voltage Capacitors
Array Type Capacitors
Low ESL Capacitors
Reliability Test Condition
Premium Capacitors for Automotive Applications
Packaging Specification
Application Manual for Surface Mounting
Part Numbering
System
4
6
Standard &
High Capacitors
Super Small Size Capacitors
30
Super Small Size
Capacitors
High-Q Capacitors
35
High-Q
Capacitors
36
Medium-High
Voltage Capacitors
47
Array Type
Capacitors
50
Low ESL
Capacitors
76
Application Manual
for Surface Mounting
72
Packaging
Specification
60
Premium Capacitors
for Automotive
Applications
53
Reliability Test
Condition

<!-- Page 4 -->

Part Numbering
System
CL    10    A    106    M   P   8     N     N    N    C
1      2      3      4      5      6      7      8       9     10    11
8 = Cardboard Tape, 7”Reel
Z = Cardboard Type, 7”Reel (Chip aligned for horizontal SMT)
Y = Cardboard Type, 7”Reel (Chip aligned for vertical SMT)
1. SERIES CODE
CL = Multi layer Ceramic Capacitors
3. DIELECTRIC CODE
ClassⅠ
ClassⅡ
C = C0G                       A = X5R     F = Y5V
B = X7R   X = X6S
Y= X7S   Z = X7T
6. RATED VOLTAGE CODE
R = 4V      O = 16V        B = 50V           E = 250V       H = 630V            K = 3000V
Q = 6.3V      A = 25V        C = 100V         F = 350V        I = 1000V
P = 10V        L = 35V        D = 200V        G = 500V       J = 2000V
7. THICKNESS CODE
8. INNER ELECTRODE/TERMINATION/PLATING CODE
A = Normal Product Pd / Ag / Ni barrier / Sn 100%
N = Normal Product Ni / Cu / Ni barrier / Sn 100%
G = Normal Product Cu / Cu / Ni barrier / Sn 100%
L = Low profile Ni / Cu / Ni barrier / Sn 100%
S = Nomal Product Ni / Cu / Soft termination / Ni barrier / Sn100%
9. PRODUCT CODE
N = Normal
A = Array(4-element)
B = Array(4-element)
L = LICC
J = SLIC
10. CONTROL CODE
N= Reserved for future use
11. PACKAGING CODE
B = Bulk
O = Cardboard Tape, 10”Reel                                  E = Embossed Type, 7”Reel
P = Bulk Case
D= Cardboard Tape, 13”Reel (10,000ea)               G = Embossed Type, 7”Reel (3,000ea)
C= Cardboard Tape, 7”Reel
L = Cardboard Tape, 13”Reel (15,000ea)                  F = Embossed Type, 13”Reel
H = Cardboard Tape, 7”Reel (15,000ea)                                                                                         S = Embossed Type, 10”Reel
2. SIZE CODE
02 = 01005(0402)    21 = 0805(2012)      43 = 1812(4532)
03 = 0201(0603)     31 = 1206(3216)     55 = 2220(5750)
05 = 0402(1005)      32 = 1210(3225)
10 = 0603(1608)     42 = 1808(4520)
4. CAPACITANCE CODE
Capacitance expressed in . 2 significant digits plus number of zeros.
example) 106 = 10106=10000000
For Values
10
, Letter R denotes decimal point
example) 1R5 =1.5
㎊
㎊
㎊
㎊
★
★★
★★★
5. TOLERANCE CODE
B =
0.1
F =
1
, 1%
K = 10%
C =
0.25
G=
2%                     M =
20%
D =
0.5
J =
5%                     Z =80/20%
*For Values ≤ 10
, F =
1
Values
10
, F =

㎊
 ㎊



㎊



㎊

㎊
 ㎊
㎊
1%
inch(㎜)
*Size tolerance
Size
Code
S
Q
R
U
Z
9
01005(0402)
0.03
0.05
0.07
0.09
0201(0603)
0.05
0.07
0.09
0402(1005)
0.07
0.10
0.15
0.20
0.40
0.30
0603(1608)
0.07
0.15
0.20
0.25
0.30
0805(2012)
0.15
0.20
0.30
1206(3216)





















0.30
2 = 0.20
3 = 0.30
5 = 0.50
8 = 0.80
9 = 0.90
A = 0.65
F = 1.25
L = 3.20
S = 1.35
C = 0.85
H = 1.60
M = 1.15
U = 1.80
D = 1.00
I = 2.00
P = 1.15
V = 2.50
E = 1.10
J = 2.50
Q = 1.25
Y = 1.25
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜



<!-- Page 5 -->

4
★★
Class I (Temperature Compensation)
Symbol
EIA Code
Operation Temperature Range(℃)
Temperature Coefficient Range(ppm/℃)
Symbol
EIA Code
Operation Temperature Range(℃)
Capacitance Change(△℃%)
C0G
C
E-3
E-6
E-12
1.0
1.0                        1.5
1.0         1.2          1.5         1.8          2.2         2.7          3.3         3.9          4.7         5.6         6.8          8.2
2.2                       3.3
4.7                        6.8
2.2
4.7
Y5V
X5R
X7R
X6S
X7S
X7T
C0G
55 125
0 30
Capacitance Step
TC
Series
★★★
01005(0402)
0201(0603)
0402(1005)
0603(1608)
0805(2012)
1206(3216)
2
3
3
5
5
8
A
C
C
M
F
Q
Y
C
C
E
E
P
M
F
H
0.20
0.30
0.30
0.50
0.50
0.80
0.65
0.85
0.85
1.15
1.25
1.25
1.25
0.85
0.85
1.10
1.10
1.15
1.15
1.25
1.60





















0.02
0.03
0.03*
0.05
0.0/0.1*
0.10
0.10
0.10
0.10*
0.10
0.10
0.15
0.20
0.15
0.10*
0.15
0.10*
0.10*
0.15
0.15
0.20
Size
Code
Size
Code
Thickness(mm)
Thickness(mm)
Spec(mm)
Spec(mm)
C
9
F
S
H
U
I
J
V
F
H
I
F
H
I
J
L
H
I
J
L





















0.85
0.90
1.25
1.35
1.60
1.80
2.00
2.50
2.50
1.25
1.60
2.00
1.25
1.60
2.00
2.50
3.20
1.60
2.00
2.50
3.00
0.10*
0.10*
0.20
0.15
0.20
0.20*
0.20
0.20
0.30
0.20
0.20
0.20
0.20
0.20
0.20
0.20
0.30
0.20
0.20
0.20
0.30
★
Class ll (High Dielectric Constant)
X5R
X7R
X6S
Y5V
X7S
X7T
A
B
X
F
Y
Z
55   85
55 125
55 105
30   85
55 125
55 125
15
15
22
82 22
22
33 22
■*Mark is only applicable to “L”code, 12    code in part number.
th
■Please discuss with sales person with regard to Pd products.
1210(3225)
1808(4520)
1812(4532)
2220(5750)
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
5

<!-- Page 6 -->

Standard & High Capacitors
L
T
BW
W
Size Code
EIA Code
L                             W                             T                 Thickness  Code               BW
Dimension(mm)

























































0402
0603
0805
1206
1210
1808
1812
2220







05
10
21
31
32
42
43
55





























0.50
0.05
0.500.0/0.1(*)
0.80
0.10
0.85
0.10
1.15
0.10
1.25
0.10
1.25
0.15
1.25
0.20
0.60
0.10(*)
0.85
0.15
0.85
0.10(*)
1.15
0.10(*)
1.25
0.15
1.60
0.20
0.85
0.10(*)
0.90
0.10(*)
1.60
0.20
1.80
0.20(*)
2.00
0.20
2.50
0.20
2.50
0.30
1.25
0.20
1.40
0.20
2.00
0.20
1.25
0.20
2.50
0.20
3.20
0.30
2.50
0.20
3.20
0.30
5
5
8
C
M
F
Q
Y
6
C
C
P
F
H
C
9
H
U
I
J
V
F
G
I
F
J
L
J
L
0.50
0.05
0.80
0.10
0.80
0.10
1.25
0.10
1.25
0.10
1.25
0.10
1.25
0.15
1.25
0.20
1.60
0.20
1.60
0.15
1.60
0.20
1.60
0.20
1.60
0.15
1.60
0.20
2.50
0.20
2.50
0.20
2.50
0.20
2.50
0.20
2.50
0.20
2.50
0.20
2.50
0.30
2.00
0.20
2.00
0.20
2.00
0.20
3.20
0.30
3.20
0.30
3.20
0.30
5.00
0.40
5.00
0.40
0.50.2/0.3
0.25
0.10
0.30
0.20
0.50
0.30
0.60
0.30
0.80
0.30
0.80
0.30
1.00
0.30
1.00
0.05
1.60
0.10
1.60
0.10
2.00
0.10
2.00
0.10
2.00
0.10
2.00
0.15
2.00
0.20
3.20
0.20
3.20
0.15
3.20
0.20
3.20
0.20
3.20
0.15
3.20
0.20
3.20
0.30
3.20
0.30
3.20
0.30
3.20
0.30
3.20
0.30
3.20
0.30
3.20
0.40
4.50
0.40
4.50
0.40
4.50
0.40
4.50
0.40
4.50
0.40
4.50
0.40
5.70
0.40
5.70
0.40
t Wide selection of size : from 0402 to 2220
t Highly reliable tolerance and high speed automatic chip placement on PCBs
t Wide capacitance range
t Wide temperature compensation and voltage range
: from C0G to Y5V and from 6.3V to 50V
t Highly reliable performance
t Highly resistant termination metal
t Tape & reel for surface mount assembly
t HHP, DSC, DVC, LCD, TV, Memory Module, PDA, Game Machine
t Desktop PC, Note PC, HHP, DC-DC Converter, DSC
t Tuner (Product code C is suitable.)
Feature
Application
Structure and Dimensions
■* Mark is only applicable to “L”code, 12    code in part number.
th

<!-- Page 7 -->

6
7
Standard & High Capacitance (C0G)
㎋
Size(mm)
0402(1005)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
㎊
Capacitance
Vr(V)
25
50
25
50
25
50
16
25
50
50
25
50
50
0.5   1    10   22   47 100 220 330 470 560
1   2.2  3.3  4.7  6.8  10   22    27  33   47   68 100 120 150
43nF
130nF
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition

<!-- Page 8 -->

Standard & High Capacitance (X5R)
Size(mm)
0402(1005)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
Capacitance (㎌)
Vr(V)
4
6.3
10
16
25
4
6.3
10
16
25
50
4
6.3
10
16
25
50
6.3
10
16
25
50
6.3
10
16
25
0.1        0.22        0.47           1            2.2          4.7          10           22           47          100         220
15
150

<!-- Page 9 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
8
9
Capacitance (㎌)
Standard & High Capacitance-Low Profile (X5R)
Size(mm)
Vr(V)
Tmax
(mm)
1                    2.2                    4.7                    10                     22                    47
6.3
10
16
6.3
10
16
25
10
16
25
25
4
6.3
10
16
25
10
6.3
10
16
25
50
100
16
25
35
50
0.33
0.5
0.7
0.85
0.95
0.7
0.95
0.95
2.0
0402(1005)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
X6S
(Tmax=1.0)
(Tmax=0.35)
(Tmax=1.0)
X6S
X6S
(Tmax=1.0)
(Tmax=1.0)
(Tmax=1.0)

<!-- Page 10 -->

Capacitance (㎌)
Size(mm)
Vr(V)
Standard & High Capacitance (X6S)
4
0402(1005)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
6.3
10
4
6.3
10
16
25
4
6.3
10
16
25
6.3
10
16
25
6.3
10
16
25
0.1         0.22          0.47           1              2.2           4.7           10              22            47           100

<!-- Page 11 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
10
11
Capacitance (㎌)
Size(mm)
Vr(V)
0.1         0.22          0.47           1             2.2            4.7            10            22             47            100
Standard & High Capacitance (X7R)
0402(1005)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
6.3
10
16
6.3
10
16
25
50
6.3
10
16
25
35
50
6.3
10
16
25
35
50
6.3
10
16
25
50
X7S
X7S
X7T

<!-- Page 12 -->

High Capacitance Table (Y5V)
Standard & High capacitance (Y5V)
Standard & High capacitance - Low Profile (Y5V)
0.1           0.22           0.47              1               2.2              4.7             10               22              47
1                         2.2                      4.7                       10
22                        47
0805(2012)
6.3
10
(Tmax=0.95)
(Tmax=0.95)
0402(1005)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
6.3
10
16
25
6.3
10
16
25
50
6.3
10
16
25
50
10
16
25
50
6.3
10
16
25
35
50
(Tmax=1.2)
(Tmax=2.7)
(Tmax=2.0)
(Tmax=1.8)
(Tmax=1.5)
(Tmax=1.4)
(Tmax=1.6)
(Tmax=1.45)
(Tmax=1.35)
Size(mm)
Vr(V)
Size(mm)
Vr(V)
Capacitance (㎌)
Capacitance (㎌)

<!-- Page 13 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
12
13
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-C0G)


















































1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
0.5㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
0.75
1.0
1.2
1.5
1.8
2.0
2.2
2.4
2.5
2.7
3.0
3.3
3.5
3.6
3.9
4.0
4.3
4.7
5.0
5.6
6.0
6.2
6.8
7.0
8.0
8.2
9.0
9.1
10
11
12
13
15
16
18
20
22
22
24
27
27
30
33
36
39
43
47
51
56
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.5
0.5
0.5
0.5
0.5
0.5
0.5
0.5
0.5
0.5
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
25
50
50
50
25
50
50
50
50
50
50
50
50
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
1.000.50
CL05C0R5CB5NNN
CL05CR75CB5NNN
CL05C010CB5NNN
CL05C1R2CB5NNN
CL05C1R5CB5NNN
CL05C1R8CB5NNN
CL05C020CB5NNN
CL05C2R2CB5NNN
CL05C2R4CB5NNN
CL05C2R5CB5NNN
CL05C2R7CB5NNN
CL05C030CB5NNN
CL05C3R3CB5NNN
CL05C3R5CB5NNN
CL05C3R6CB5NNN
CL05C3R9CB5NNN
CL05C040CB5NNN
CL05C4R3CB5NNN
CL05C4R7CB5NNN
CL05C050DB5NNN
CL05C5R6DB5NNN
CL05C060DB5NNN
CL05C6R2DB5NNN
CL05C6R8DB5NNN
CL05C070DB5NNN
CL05C080DB5NNN
CL05C8R2DB5NNN
CL05C090DB5NNN
CL05C9R1DB5NNN
CL05C100 JB5NNN
CL05C110 JB5NNN
CL05C120 J B5NNN
CL05C130 J B5NNN
CL05C150 J B5NNN
CL05C160 J B5NNN
CL05C180 J B5NNN
CL05C200 J B5NNN
CL05C220 JA5NNN
CL05C220 J B5NNN
CL05C240 J B5NNN
CL05C270 J B5NNN
CL05C270 JA5NNN
CL05C300 J B5NNN
CL05C330 J B5NNN
CL05C360 J B5NNN
CL05C390 J B5NNN
CL05C430 J B5NNN
CL05C470 J B5NNN
CL05C510 J B5NNN
CL05C560 JB5NNN

<!-- Page 14 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
Product Lineup (Standard & High Capacitors-C0G)
62㎊
68㎊
75㎊
82㎊
91㎊
100㎊
120㎊
150㎊
180㎊
200㎊
220㎊
270㎊
330㎊
390㎊
470㎊
470㎊
680㎊
820㎊
1㎋
1㎋
1㎋
0.3㎊
0.5㎊
0.75㎊
1.0㎊
1.2㎊
1.5㎊
1.8㎊
2.0㎊
2.2㎊
2.4㎊
2.5㎊
2.7㎊
3.0㎊
3.3㎊
3.5㎊
3.6㎊
3.9㎊
4.0㎊
4.3㎊
4.7㎊
5.0㎊
5.6㎊
6.0㎊
6.2㎊
6.8㎊
7.0㎊
7.5㎊
8.0㎊
8.2㎊


















































5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.5㎊
0.5㎊
0.5㎊
0.5㎊
0.5㎊
0.5㎊
0.5㎊
0.5㎊
0.5㎊
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
16
50
50
50
25
16
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
1.000.50
1.600.80
CL05C620 J B5NNN
CL05C680 J B5NNN
CL05C750 J B5NNN
CL05C820 J B5NNN
CL05C910 J B5NNN
CL05C101 J B5NNN
CL05C121 J B5NNN
CL05C151 J B5NNN
CL05C181 J B5NNN
CL05C201 J B5NNN
CL05C221 J B5NNN
CL05C271 J B5NNN
CL05C331 J B5NNN
CL05C391 J B5NNN
CL05C471 J B5NNN
CL05C471JO5NNN
CL05C681 J B5NNN
CL05C821 J B5NNN
CL05C102 J B5NNN
CL05C102 J A5NNN
CL05C102 J O5NNN
CL10C0R3CB8NNN
CL10C0R5CB8NNN
CL10CR75CB8NNN
CL10C010CB8NNN
CL10C1R2CB8NNN
CL10C1R5CB8NNN
CL10C1R8CB8NNN
CL10C020CB8NNN
CL10C2R2CB8NNN
CL10C2R4CB8NNN
CL10C2R5CB8NNN
CL10C2R7CB8NNN
CL10C030CB8NNN
CL10C3R3CB8NNN
CL10C3R5CB8NNN
CL10C3R6CB8NNN
CL10C3R9CB8NNN
CL10C040CB8NNN
CL10C4R3CB8NNN
CL10C4R7CB8NNN
CL10C050DB8NNN
CL10C5R6DB8NNN
CL10C060DB8NNN
CL10C6R2DB8NNN
CL10C6R8DB8NNN
CL10C070DB8NNN
CL10C7R5DB8NNN
CL10C080DB8NNN
CL10C8R2DB8NNN

<!-- Page 15 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
14
15
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
1.600.80
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
Product Lineup (Standard & High Capacitors-C0G)
9.0
9.1
10
11
12
13
14
15
16
18
20
22
24
25
27
30
33
36
39
43
47
51
56
62
68
75
82
91
100
110
120
130
150
160
180
200
220
240
270
300
330
360
390
430
470
510
560
620
680
750
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊


















































0.5㎊
0.5㎊
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
CL10C090DB8NNN
CL10C9R1DB8NNN
CL10C100JB8NNN
CL10C110JB8NNN
CL10C120JB8NNN
CL10C130JB8NNN
CL10C140JB8NNN
CL10C150JB8NNN
CL10C160JB8NNN
CL10C180JB8NNN
CL10C200JB8NNN
CL10C220JB8NNN
CL10C240JB8NNN
CL10C250JB8NNN
CL10C270JB8NNN
CL10C300JB8NNN
CL10C330JB8NNN
CL10C360JB8NNN
CL10C390JB8NNN
CL10C430JB8NNN
CL10C470JB8NNN
CL10C510JB8NNN
CL10C560JB8NNN
CL10C620JB8NNN
CL10C680JB8NNN
CL10C750JB8NNN
CL10C820JB8NNN
CL10C910JB8NNN
CL10C101JB8NNN
CL10C111JB8NNN
CL10C121JB8NNN
CL10C131JB8NNN
CL10C151JB8NNN
CL10C161JB8NNN
CL10C181JB8NNN
CL10C201JB8NNN
CL10C221JB8NNN
CL10C241JB8NNN
CL10C271JB8NNN
CL10C301JB8NNN
CL10C331JB8NNN
CL10C361JB8NNN
CL10C391JB8NNN
CL10C431JB8NNN
CL10C471JB8NNN
CL10C511JB8NNN
CL10C561JB8NNN
CL10C621JB8NNN
CL10C681JB8NNN
CL10C751JB8NNN

<!-- Page 16 -->

2.001.25
1.600.80
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
Product Lineup (Standard & High Capacitors-C0G)
820
1
1.8
2.2
5.6
10
0.47
0.5
1.0
1.2
1.5
1.8
2.0
2.2
2.4
2.5
2.7
3.0
3.2
3.3
3.6
3.9
4.0
4.7
5.6
6.0
6.8
7.0
7.5
8.0
8.2
9.0
10
12
13
14
15
16
18
20
22
24
25
27
30
33
36
39
43
47
51
㎊
㎋
㎋
㎋
㎋
㎋
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
80
81
82
83
84
85
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45



















































5%
5%
5%
5%
5%
5%
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.5
0.5
0.5
0.5
0.5
0.5
0.5
0.5
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
50
50
50
50
50
25
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
0.90
0.90
0.90
0.90
0.90
0.90
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
CL10C821 J B 8NNN
CL10C102 J B 8NNN
CL10C182 J B 8NNN
CL10C222 J B 8NNN
CL10C562 J B 8NNN
CL10C103J A 8NNN
CL21CR47CBANNN
CL21C0R5CBANNN
CL21C010CBANNN
CL21C1R2CBANNN
CL21C1R5CBANNN
CL21C1R8CBANNN
CL21C020CBANNN
CL21C2R2CBANNN
CL21C2R4CBANNN
CL21C2R5CBANNN
CL21C2R7CBANNN
CL21C030CBANNN
CL21C3R2CBANNN
CL21C3R3CBANNN
CL21C3R6CBANNN
CL21C3R9CBANNN
CL21C040CBANNN
CL21C4R7CBANNN
CL21C5R6DBANNN
CL21C060DBANNN
CL21C6R8DBANNN
CL21C070DBANNN
CL21C7R5DBANNN
CL21C080DBANNN
CL21C8R2DBANNN
CL21C090DBANNN
CL21C100JBANNN
CL21C120JBANNN
CL21C130JBANNN
CL21C140JBANNN
CL21C150JBANNN
CL21C160JBANNN
CL21C180JBANNN
CL21C200JBANNN
CL21C220JBANNN
CL21C240JBANNN
CL21C250JBANNN
CL21C270JBANNN
CL21C300JBANNN
CL21C330JBANNN
CL21C360JBANNN
CL21C390JBANNN
CL21C430JBANNN
CL21C470JBANNN
CL21C510JBANNN

<!-- Page 17 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
16
17
Product Lineup (Standard & High Capacitors-C0G)
56
62
68
75
82
91
100
110
120
130
150
160
180
200
220
240
270
300
330
360
390
430
470
510
560
620
680
750
820
1
1.2
1.5
1.8
2.2
3.3
3.3
3.9
3.9
4.7
5.6
8.2
10
33
0.5
1.0
1.5
1.8
2.0
2.2
2.7
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎊
㎊
㎊
㎊
㎊
㎊
㎊


















































㎊
㎊
㎊
㎊
㎊
㎊
㎊
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
86
87
88
1
2
3
4
5
6
7
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
0.25
0.25
0.25
0.25
0.25
0.25
0.25
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
25
50
25
50
50
50
25
50
25
50
50
50
50
50
50
50
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.95
0.95
0.95
0.95
0.95
1.35
1.35
1.35
1.35
1.35
1.35
0.75
1.35
1.35
1.35
1.35
1.35
1.35
1.00
1.00
1.00
1.00
1.00
1.00
1.00
2.001.25
3.201.60
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
CL21C560JBANNN
CL21C620JBANNN
CL21C680JBANNN
CL21C750JBANNN
CL21C820JBANNN
CL21C910JBANNN
CL21C101JBANNN
CL21C111JBANNN
CL21C121JBANNN
CL21C131JBANNN
CL21C151JBANNN
CL21C161JBANNN
CL21C181JBANNN
CL21C201JBANNN
CL21C221JBANNN
CL21C241JBANNN
CL21C271JBANNN
CL21C301JBANNN
CL21C331JBANNN
CL21C361JBANNN
CL21C391JBANNN
CL21C431JBANNN
CL21C471JBANNN
CL21C511JBANNN
CL21C561JBANNN
CL21C621JBCNNN
CL21C681JBCNNN
CL21C751JBCNNN
CL21C821JBCNNN
CL21C102JBCNNN
CL21C122JBFNNN
CL21C152JBFNNN
CL21C182JBFNNN
CL21C222JBFNNN
CL21C332JAFNNN
CL21C332JBFNNN
CL21C392JAANNN
CL21C392JBFNNN
CL21C472JBFNNN
CL21C562JBFNNN
CL21C822JAFNNN
CL21C103JBFNNN
CL21C333JAFNNN
CL31C0R5CBCNNN
CL31C010CBCNNN
CL31C1R5CBCNNN
CL31C1R8CBCNNN
CL31C020CBCNNN
CL31C2R2CBCNNN
CL31C2R7CBCNNN

<!-- Page 18 -->

Product Lineup (Standard & High Capacitors-C0G)
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
25
50
50
50
25
25
50
50
50
50
50
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.40
1.40
1.40
1.80
1.40
1.80
1.80
1.80
1.80
1.80
1.45
1.45
1.80
1.80
1.80
3.201.60
3.202.50
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
1
2
3
4
5
3.0
3.3
4.0
4.7
10
12
15
18
20
22
27
30
33
39
47
51
56
68
75
82
100
120
150
180
220
270
330
390
470
560
680
820
1
1.2
1.5
1.8
2.2
2.7
3.3
4.7
6.8
10
22
33
47
68
100
4.7
10
22
33
47
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
0.25
0.25
0.25
0.25
㎊
㎊
㎊
㎊
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%



















































5%
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
CL31C030CBCNNN
CL31C3R3CBCNNN
CL31C040CBCNNN
CL31C4R7CBCNNN
CL31C100JBCNNN
CL31C120JBCNNN
CL31C150JBCNNN
CL31C180JBCNNN
CL31C200JBCNNN
CL31C220JBCNNN
CL31C270JBCNNN
CL31C300JBCNNN
CL31C330JBCNNN
CL31C390JBCNNN
CL31C470JBCNNN
CL31C510JBCNNN
CL31C560JBCNNN
CL31C680JBCNNN
CL31C750JBCNNN
CL31C820JBCNNN
CL31C101JBCNNN
CL31C121JBCNNN
CL31C151JBCNNN
CL31C181JBCNNN
CL31C221JBCNNN
CL31C271JBCNNN
CL31C331JBCNNN
CL31C391JBCNNN
CL31C471JBCNNN
CL31C561JBCNNN
CL31C681JBCNNN
CL31C821JBCNNN
CL31C102JBCNNN
CL31C122JBCNNN
CL31C152JBCNNN
CL31C182JBCNNN
CL31C222JBCNNN
CL31C272JBFNNN
CL31C332JBFNNN
CL31C472JBFNNN
CL31C682JBHNNN
CL31C103JAFNNN
CL31C223JBHNNN
CL31C333JBHNNN
CL31C473JBHNNN
CL31C683JAHNNN
CL31C104JAHNNN
CL32C472JBFNNN
CL32C103JBFNNN
CL32C223JBHNNN
CL32C333JBHNNN
CL32C473JBHNNN

<!-- Page 19 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
18
19
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X5R)
22
0.1
0.1
0.1
0.22
0.22
0.33
0.33
0.47
0.47
0.47
0.47
0.47
1
1
1
1
1
1
1
1
1
2.2
2.2
2.2
2.2
2.2
2.2
2.2
2.2
4.7
4.7
4.7
4.7
10
10
10
22
0.47
0.47
0.47
0.47
0.47
1
1
1
1
1
1
1
1
1
㎋
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
10%
20%
10%
20%
10%
20%
10%
20%
20%
20%
20%
20%
20%
20%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
16
25
16
10
25
10
25
10
25
16
10
6.3
4
25
16
16
10
10
6.3
6.3
4
4
25
16
10
10
6.3
6.3
4
4
16
10
6.3
6.3
10
6.3
4
4
50
25
10
6.3
4
50
25
25
16
16
10
10
6.3
6.3
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.60
0.55
0.33
0.55
0.33
0.55
0.33
0.55
0.33
0.70
0.60
0.57
0.33
0.55
0.33
0.55
0.33
0.70
0.65
0.65
0.35
0.70
0.70
0.65
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.50
0.90
0.90
0.50
0.90
0.50
0.90
0.50
15㎌




















































20%
4
0.70
CL05A223KO5NNN
CL05A104KA5NNN
CL05A104KO5NNN
CL05A104KP5NNN
CL05A224KA5NNN
CL05A224KP5NNN
CL05A334KA5NNN
CL05A334KP5NNN
CL05A474KA5NNN
CL05A474KO5NNN
CL05A474KP5NNN
CL05A474KQ5NNN
CL05A474KR5NNN
CL05A105KA5NQN
CL05A105KO5NNN
CL05A105KO3LQN
CL05A105KP5NNN
CL05A105KP3LNN
CL05A105KQ5NNN
CL05A105KQ3LNN
CL05A105KR5NNN
CL05A105KR3LNN
CL05A225MA5NUN
CL05A225KO5NQN
CL05A225MP5NSN
CL05A225KP3LRN
CL05A225MQ5NNN
CL05A225KQ3LRN
CL05A225MR5NNN
CL05A225KR3LRN
CL05A475MO5NUN
CL05A475MP5NRN
CL05A475MQ5NRN
CL05A475MQ3LUN
CL05A106MP5NUN
CL05A106MQ5NUN
CL05A106MR5NRN
CL05A226MR5NZN
CL10A474KB8NNN
CL10A474KA8NNN
CL10A474KP8NNN
CL10A474KQ8NNN
CL10A474KR8NNN
CL10A105KB8NNN
CL10A105KA5LNN
CL10A105KA8NNN
CL10A105KO8NNN
CL10A105KO5LNN
CL10A105KP8NNN
CL10A105KP5LNN
CL10A105KQ8NNN
CL10A105KQ5LNN
CL05A156MR5NUN
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
39
38
1
2
3
4
5
6
7
8
9
10
11
12
13
14
1.000.50
1.600.80

<!-- Page 20 -->

Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X5R)
1.600.80
2.001.25
1
1
1
2.2
2.2
2.2
2.2
2.2
2.2
2.2
2.2
2.2
2.2
3.3
3.3
4.7
4.7
4.7
4.7
4.7
4.7
4.7
4.7
10
10
10
10
10
10
10
22
22
22
22
47
1
1
1
1
1
1
1
2.2
2.2
2.2
2.2
2.2
2.2
2.2
4.7
4
4
25
25
25
16
16
10
10
6.3
6.3
4
4
6.3
4
25
16
10
10
6.3
6.3
4
4
4
4
6.3
6.3
10
16
25
4
6.3
10
10
4
50
25
25
16
16
6.3
4
50
25
16
16
10
6.3
4
50
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
10%
20%
20%
20%
20%
20%
20%
20%
20%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
0.90
0.50
0.50
0.90
0.50
0.90
0.50
0.90
0.50
0.90
0.50
0.90
0.50
0.90
0.90
0.95
0.90
0.90
0.50
0.50
0.90
0.50
0.90
0.90
0.50
0.90
0.50
0.90
0.95
1.00
1.00
1.00
1.00
1.05
1.10
1.40
1.35
0.70
1.35
0.70
1.35
1.35
1.40
1.35
0.70
1.35
1.35
1.35
1.35
1.40
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
50
47
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
6.3


















































20%
1.10
CL10A476MQ8CZN
CL10A105KR8NNN
CL10A105KR5LNN
CL10A105KA5LNN
CL10A225KA8NNN
CL10A225KA5LNN
CL10A225KO8NNN
CL10A225KO5LNN
CL10A225KP8NNN
CL10A225KP5LNN
CL10A225KQ8NNN
CL10A225KQ5LNN
CL10A225KR8NNN
CL10A225KR5LNN
CL10A335KQ8NNN
CL10A335KR8NNN
CL10A475KA8NQN
CL10A475KO8NNN
CL10A475KP8NNN
CL10A475KP5LNN
CL10A475KQ5LNN
CL10A475KQ8NNN
CL10A475KR5LNN
CL10A475KR8NNN
CL10A106KR8NNN
CL10A106MR5LRN
CL10A106KQ8NNN
CL10A106MQ5LRN
CL10A106MP8NNN
CL10A106MO8NQN
CL10A106MA8NRN
CL10A226MR8NRN
CL10A226MQ8NRN
CL10A226MP8NRN
CL10A226MP8NUN
CL10A476MR8NZN
CL21A105KBQNNN
CL21A105KAFNNN
CL21A105KA6LNN
CL21A105KOFNNN
CL21A105KO6LNN
CL21A105KQFNNN
CL21A105KRFNNN
CL21A225KBQNNN
CL21A225KAFNNN
CL21A225KO6LNN
CL21A225KOFNNN
CL21A225KPFNNN
CL21A225KQFNNN
CL21A225KRFNNN
CL21A475KBQNNN

<!-- Page 21 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
20
21
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
CL21A475KACLRN
CL21A475KOFNNN
4.7
4.7
4.7
Product Lineup (Standard & High Capacitors-X5R)
4.7
4.7
4.7
4.7
4.7
4.7
4.7
10
10
10
10
10
10
10
10
10
10
10
10
10
22
22
22
22
22
22
22
33
33
33
33
47
47
47
2.2
4.7
4.7
4.7
4.7
4.7
4.7
4.7
4.7
4.7
10
10
10
10
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌



















































10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
25
25
16
16
10
10
6.3
6.3
4
4
25
25
25
16
16
16
16
10
10
6.3
6.3
4
4
25
10
10
6.3
6.3
4
4
6.3
6.3
4
4
6.3
4
6.3
100
50
50
25
25
16
16
10
6.3
4
50
25
25
16
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
1
2
3
4
5
6
7
8
9
10
11
12
13
14
1.40
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.45
0.95
0.80
1.35
1.40
0.95
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.40
1.40
0.95
1.40
0.95
1.40
0.95
1.20
1.00
1.20
1.00
1.45
1.45
1.00
1.00
1.80
1.00
1.80
0.95
1.80
0.95
1.80
1.80
1.80
1.80
1.80
0.95
1.80
2.001.25
3.201.60
CL21A475KOCLNN
CL21A475KPFNNN
CL21A475KPCLNN
CL21A475KQFNNN
CL21A475KQCLNN
CL21A475KRFNNN
CL21A475KRCLNN
CL21A106KAYNNN
CL21A106KACLRN
CL21A106KA7LQN
CL21A106KOFNNN
CL21A106KOQNNN
CL21A106KOCLRN
CL21A106KOCL3R
CL21A106KPFNNN
CL21A106KPCLQN
CL21A106KQFNNN
CL21A106KQCLNN
CL21A106KRFNNN
CL21A106KRCLNN
CL21A226MAQNNN
CL21A226MPQNNN
CL21A226MPCLRN
CL21A226MQQNNN
CL21A226MQCLRN
CL21A226MRQNNN
CL21A226MRCLRN
CL21A336MQELNN
CL21A336MQ9LNN
CL21A336MRELNN
CL21A336MR9LNN
CL21A476MQYNNN
CL21A476MRYNNN
CL21A476MQ9LRN
CL31A225KC9LNN
CL31A475KBHNNN
CL31A475KB9LNN
CL31A475KAHNNN
CL31A475KACLNN
CL31A475KOHNNN
CL31A475KOCLNN
CL31A475KPHNNN
CL31A475KQHNNN
CL31A475KRHNNN
CL31A106KBHNNN
CL31A106KAHNNN
CL31A106KACLNN
CL31A106KOHNNN
CL21A475KAQNNN

<!-- Page 22 -->

Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X5R)
3.201.60
3.202.50
4.503.20
15
22
22
22
22
22
22
47
47
47
100
100
100
10
10
10
10
10
10
10
22
22
22
22
22
22
22
22
47
47
47
47
100
100
100
150
220
47
47
100
100
4
25
16
16
10
10
6.3
10
6.3
4
6.3
4
10
6.3
4
50
25
25
16
10
25
16
16
10
6.3
6.3
4
4
16
10
6.3
4
10
6.3
4
6.3
6.3
6.3
4
6.3
4
10%
10%
10%
10%
10%
10%
10%
10%
20%
20%
20%
20%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
10%
20%
10%
10%
20%
20%
20%
20%
20%
20%
20%
20%
20%
10%
10%
1.80
1.80
1.80
0.95
1.80
0.95
1.80
1.80
1.80
1.80
1.80
1.80
1.80
0.95
0.95
2.00
2.70
2.00
2.70
2.70
2.70
2.70
0.95
2.70
2.70
0.95
2.70
0.95
2.70
2.70
2.70
2.70
2.80
2.80
2.80
2.80
2.80
2.70
2.70
3.50
3.50
10
10
10
10
10
15
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
10%
10%
10%
10%
10%
10%
16
10
10
6.3
4
6.3
21
22
23
24
25
26
27
28
29
30
31
32
33
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
1
2
3
4
15
16
17
18
19
20
0.95
1.80
0.95
1.80
1.80
1.80
CL31A106KOCLNN
CL31A106KPHNNN
CL31A106KPCLNN
CL31A106KQHNNN
CL31A106KRHNNN
CL31A156KQHNNN
CL32A107MQVNNN
CL31A156KRHNNN
CL31A226KAHNNN
CL31A226KOHNNN
CL31A226KOCLNN
CL31A226KPHNNN
CL31A226KPCLNN
CL31A226KQHNNN
CL31A476KPHNNN
CL31A476MQHNNN
CL31A476MRHNNN
CL31A107MQHNNN
CL31A107MRHNNN
CL31A107MPHNNN
CL32A106KQCLNN
CL32A106KRCLNN
CL32A106KBULNN
CL32A106KAJNNN
CL32A106KAULNN
CL32A106KOJNNN
CL32A106KPJNNN
CL32A226KAJNNN
CL32A226KOJNNN
CL32A226KOCLNN
CL32A226KPJNNN
CL32A226KQJNNN
CL32A226MQCLNN
CL32A226KRJNNN
CL32A226MRCLNN
CL32A476KOJNNN
CL32A476KPJNNN
CL32A476MQJNNN
CL32A476MRJNNN
CL32A107MPVNNN
CL32A107MRVNNN
CL32A157MQVNNN
CL32A227MQVNNN
CL43A476MQJNNN
CL43A476MRJNNN
CL43A107KQLNNN
CL43A107KRLNNN

<!-- Page 23 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
22
23
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X6S)
0.22
0.22
0.47
0.47
0.47
0.68
1
1
1
2.2
4.7
10
0.47
0.47
0.47
0.47
0.47
1
1
1
1
1
2.2
2.2
2.2
2.2
4.7
4.7
4.7
4.7
4.7
10
10
10
1
1
1
1
1
2.2
2.2
2.2
2.2
2.2
4.7
4.7
4.7
4.7
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
10%
10%
10%
10%
20%
 5%
10%
10%
20%
20%
20%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%















































10%
10
6.3
10
6.3
4
6.3
25
10
6.3
10
6.3
4
25
16
10
6.3
4
25
16
10
6.3
4
16
10
6.3
4
25
16
10
6.3
4
10
6.3
4
25
16
10
6.3
4
25
16
10
6.3
4
25
16
10
6.3
CL05X224KP5NNN
CL05X224KQ5NNN
CL05X474KP5NNN
CL05X474KQ5NNN
CL05X474MR5NNN
CL05X684JQ5NNN
CL05X105KA5NQN
CL05X105KP5NNN
CL05X105MQ3LNN
CL05X225MP5NUN
CL05X475MQ5NUN
CL05X106MR5NUN
1
2
3
4
5
6
7
8
9
10
11
12
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
1
2
3
4
5
6
7
8
9
10
11
12
13
14
0.55
0.55
0.55
0.55
0.55
0.55
0.60
0.55
0.33
0.70
0.70
0.70
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.95
0.95
0.90
0.90
0.90
0.90
0.90
0.90
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.40
1.35
1.35
1.35
1.600.80
2.001.25
1.000.50
CL10X474KA8NNN
CL10X474KO8NNN
CL10X474KP8NNN
CL10X474KQ8NNN
CL10X474KR8NNN
CL10X105KA8NNN
CL10X105KO8NNN
CL10X105KP8NNN
CL10X105KQ8NNN
CL10X105KR8NNN
CL10X225KO8NNN
CL10X225KP8NNN
CL10X225KQ8NNN
CL10X225KR8NNN
CL10X475KA8NQN
CL10X475KO8NQN
CL10X475KP5NNN
CL10X475KQ8NNN
CL10X475KR8NNN
CL10X106MP8NNN
CL10X106KQ8NNN
CL10X106KR8NNN
CL21X105KAFNNN
CL21X105KOFNNN
CL21X105KPFNNN
CL21X105KQFNNN
CL21X105KRFNNN
CL21X225KAFNNN
CL21X225KOFNNN
CL21X225KPFNNN
CL21X225KQFNNN
CL21X225KRFNNN
CL21X475KAQNNN
CL21X475KOFNNN
CL21X475KPFNNN
CL21X475KQFNNN

<!-- Page 24 -->

Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X6S)
4.7
10
10
10
10
10
10
10
10
22
22
47
4.7
4.7
4.7
4.7
4.7
4.7
10
10
10
10
10
10
22
22
22
22
100
100
10
10
10
10
10
22
22
22
22
22
47
47
47
100
100
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
20%
20%
10%
10%
10%
10%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
10%
10%
20%












































20%
4
25
25
16
10
10
6.3
4
4
6.3
4
4
25
25
16
10
6.3
4
25
25
16
10
6.3
4
16
10
6.3
4
6.3
4
25
16
10
6.3
4
25
16
10
6.3
4
10
6.3
4
6.3
4
15
16
17
18
19
20
21
22
23
24
25
26
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
1.35
0.95
1.45
1.45
0.95
1.45
1.40
1.40
0.95
1.40
1.40
1.45
1.80
0.95
1.80
1.80
1.80
1.80
0.95
1.80
1.80
1.80
1.80
1.80
1.80
1.80
1.80
1.80
1.80
1.80
2.00
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.80
2.80
2.001.25
3.201.60
3.202.50
CL21X475KRFNNN
CL21X106KACLRN
CL21X106KAYNNN
CL21X106KOYNNN
CL21X106KPCLNN
CL21X106KPYNNN
CL21X106KQQNNN
CL21X106KRQNNN
CL21X106KRCLNN
CL21X226MQQNNN
CL21X226MRQNNN
CL21X476MRYNNN
CL31X475KAHNNN
CL31X475KACLNN
CL31X475KOHNNN
CL31X475KPHNNN
CL31X475MQHNNN
CL31X475KRHNNN
CL31X106KACLNN
CL31X106KAHNNN
CL31X106KOHNNN
CL31X106KPHNNN
CL31X106KQHNNN
CL31X106KRHNNN
CL31X226KOHNNN
CL31X226KPHNNN
CL31X226KQHNNN
CL31X226KRHNNN
CL31X107MQHNNN
CL31X107MRHNNN
CL32X106KAUNNN
CL32X106KOJNNN
CL32X106KPJNNN
CL32X106KQJNNN
CL32X106KRJNNN
CL32X226KAJNNN
CL32X226KOJNNN
CL32X226KPJNNN
CL32X226KQJNNN
CL32X226KRJNNN
CL32X476MPJNNN
CL32X476KQJNNN
CL32X476KRJNNN
CL32X107MQVNNN
NNN
CL32X107MRV

<!-- Page 25 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
24
25
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X7R, X7S)
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
1
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
CL05B151KB5NNN
CL05B181KB5NNN
CL05B221KB5NNN
CL05B271KB5NNN
CL05B331KB5NNN
CL05B391KB5NNN
CL05B471KB5NNN
CL05B561KB5NNN
CL05B681KB5NNN
CL05B102KB5NNN
CL05B122KB5NNN
CL05B152KB5NNN
CL05B182KB5NNN
CL05B222KB5NNN
CL05B272KB5NNN
CL05B332KB5NNN
CL05B472KB5NNN
CL05B562KB5NNN
CL05B682KB5NNN
CL05B822KB5NNN
CL05B103KB5NNN
CL05B123KA5NNN
CL05B153KA5NNN
CL05B223KA5NNN
CL05B273KO5NNN
CL05B333KO5NNN
CL05B393KO5NNN
CL05B473KO5NNN
CL05B563KO5NNN
CL05B683KO5NNN
CL05B823KO5NNN
CL05B104KO5NNN
CL05B224KO5NNN
CL05B474KP5NNN
CL05B105KQ5NQN
CL05Y474KP5NNN
CL10B101KB8NNN
CL10B121KB8NNN
CL10B151KB8NNN
CL10B181KB8NNN
CL10B201KB8NNN
CL10B221KB8NNN
CL10B271KB8NNN
CL10B331KB8NNN
CL10B391KB8NNN
CL10B471KB8NNN
CL10B561KB8NNN
CL10B681KB8NNN
CL10B751KB8NNN
CL10B821KB8NNN
CL10B102KB8NNN
CL10B122KB8NNN
150㎊
180㎊
220㎊
270㎊
330㎊
390㎋
470㎊
560㎊
680㎊
1㎋
1.2㎋
1.5㎋
1.8㎋
2.2㎋
2.7㎋
3.3㎋
4.7㎋
5.6㎋
6.8㎋
8.2㎋
10㎋
12㎋
15㎋
22㎋
27㎋
33㎋
39㎋
47㎋
56㎋
68㎋
82㎋
100㎋
220㎋
470㎋
1㎌
470㎋
100㎊
120㎊
150㎊
180㎊
200㎊
220㎊
270㎊
330㎊
390㎊
470㎊
560㎊
680㎊
750㎊
820㎊
1㎋
1.2㎋
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
25
25
25
16
16
16
16
16
16
16
16
16
10
6.3
10
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.60
0.55
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
1.000.50
1.000.50
1.600.80

<!-- Page 26 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X7R)
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
CL10B152KB8NNN
CL10B182KB8NNN
CL10B202KB8NNN
CL10B222KB8NNN
CL10B332KB8NNN
CL10B392KB8NNN
CL10B472KB8NNN
CL10B562KB8NNN
CL10B682KB8NNN
CL10B822KB8NNN
CL10B103JB8NNN
CL10B123KB8NNN
CL10B153KB8NNN
CL10B183KB8NNN
CL10B223KB8NNN
CL10B273KB8NNN
CL10B333JB8NNN
CL10B393KB8NNN
CL10B473KB8NNN
CL10B563KB8NNN
CL10B683KB8NNN
CL10B823KB8NNN
CL10B104KB8NNN
CL10B124KO8NNN
CL10B154KA8NNN
CL10B224KA8NNN
CL10B474KA8NNN
CL10B684KO8NNN
CL10B105KA8NNN
CL10B225KP8NNN
CL21B151KBANNN
CL21B181KBANNN
CL21B221KBANNN
CL21B331KBANNN
CL21B391KBANNN
CL21B471KBANNN
CL21B511KBANNN
CL21B561KBANNN
CL21B681KBANNN
CL21B821KBANNN
CL21B102KBANNN
CL21B122KBANNN
CL21B152KBANNN
CL21B182KBANNN
CL21B202KBANNN
CL21B222KBANNN
CL21B272KBANNN
CL21B332KBANNN
CL21B472KBANNN
CL21B562KBANNN
CL21B682KBANNN
1.5㎋
1.8㎋
2㎋
2.2㎋
3.3㎋
3.9㎋
4.7㎋
5.6㎋
6.8㎋
8.2㎋
10㎋
12㎋
15㎋
18㎋
22㎋
27㎋
33㎋
39㎋
47㎋
56㎋
68㎋
82㎋
100㎋
120㎋
150㎋
220㎋
470㎋
680㎋
1㎌
2.2㎌
150㎊
180㎊
220㎊
330㎊
390㎊
470㎊
510㎊
560㎊
680㎊
820㎊
1㎋
1.2㎋
1.5㎋
1.8㎋
2㎋
2.2㎋
2.7㎋
3.3㎋
4.7㎋
5.6㎋
6.8㎋
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
16
25
25
25
16
25
10
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
5%
10%
10%
10%
10%
10%
5%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
0.75
1.600.80
2.001.25

<!-- Page 27 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
26
27
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X7R)
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
CL21B103KBANNN
CL21B123KBANNN
CL21B153KBANNN
CL21B333KBANNN
CL21B393KBANNN
CL21B473KBANNN
CL21B563KBCNNN
CL21B683KAANNN
CL21B683JBCNNN
CL21B683KBFNNN
CL21B823KBCNNN
CL21B823KBFNNN
CL21B104KACNNN
CL21B104KBCNNN
CL21B104KBFNNN
CL21B124KBFNNN
CL21B124KACNNN
CL21B154KOANNN
CL21B154KBFNNN
CL21B224KBFNNN
CL21B334KAFNNN
CL21B474KAFNNN
CL21B684KOFNNN
CL21B105KBFNNN
CL21B155KAFNNN
CL21B225KAFNNN
CL21B475KQQNNN
CL21B475KAFNNN
CL21B106KOQNNN
CL31B221KBCNNN
CL31B331KBCNNN
CL31B471KBCNNN
CL31B561KBCNNN
CL31B152KBCNNN
CL31B222KBCNNN
CL31B332KBCNNN
CL31B472KBCNNN
CL31B473KBCNNN
CL31B562KBCNNN
CL31B682KBCNNN
CL31B822KBCNNN
CL31B103KBCNNN
CL31B123KBCNNN
CL31B153KBCNNN
CL31B223KBCNNN
CL31B333KBCNNN
CL31B683KBCNNN
CL31B104KBCNNN
CL31B154KBCNNN
CL31B224KBFNNN
CL31B334KBFNNN
10㎋
12㎋
15㎋
33㎋
39㎋
47㎋
56㎋
68㎋
68㎋
68㎋
82㎋
82㎋
100㎋
100㎋
100㎋
120㎋
120㎋
150㎋
150㎋
220㎋
330㎋
470㎋
680㎋
1㎌
1.5㎌
2.2㎌
4.7㎌
4.7㎌
10㎌
220㎊
330㎊
470㎊
560㎊
1.5㎋
2.2㎋
3.3㎋
4.7㎋
47㎋
5.6㎋
6.8㎋
8.2㎋
10㎋
12㎋
15㎋
22㎋
33㎋
68㎋
100㎋
150㎋
220㎋
330㎋
50
50
50
50
50
50
50
25
50
50
50
50
25
50
50
50
25
16
50
50
25
25
16
50
25
25
6.3
25
16
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
10%
10%
10%
10%
10%
10%
10%
10%
5%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
0.75
0.75
0.75
0.75
0.75
0.75
0.95
0.75
0.95
1.35
0.95
1.35
0.95
0.95
1.35
1.35
0.95
0.75
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.40
1.35
1.40
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.40
1.40
2.001.25
3.201.60

<!-- Page 28 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-X7R)
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
23
24
25
26
27
28
29
30
31
32
33
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
CL31B334KACNNN
CL31B474KBHNNN
CL31B474MAFNNN
CL31B684KOCNNN
CL31B684KBHNNN
CL31B105KBHNNN
CL31B225KAHNNN
CL31B335KAHNNN
CL31B475KBHNNN
CL31B106KBHNNN
CL31B226KPHNNN
CL32B104KBFNNN
CL32B154KBFNNN
CL32B224KBFNNN
CL32B334KBFNNN
CL32B474KBFNNN
CL32B105KBHNNN
CL32B225KBJNNN
CL32B225KAINNN
CL32B475KBJNNN
CL32B475KBUYNN
CL32B475KOINNN
CL32B106KLJNNN
CL32B106KAULNN
CL32B106KPINNN
CL32B226KAJNNN
CL32B476MQJNN
330㎋
470㎋
470㎋
680㎋
680㎋
1㎌
2.2㎌
3.3㎌
4.7㎌
10㎌
22㎌
100㎋
150㎋
220㎋
330㎋
470㎋
1㎌
2.2㎌
2.2㎌
4.7㎌
4.7㎌
4.7㎌
10㎌
10㎌
10㎌
22㎌
47㎌
25
50
25
16
50
50
25
25
50
50
10
50
50
50
50
50
50
50
25
50
50
16
35
25
10
25
6.3
10%
10%
20%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
1.00
1.80
1.40
1.00
1.80
1.80
1.80
1.80
1.80
1.80
1.80
1.45
1.45
1.45
1.45
1.45
1.80
2.70
2.20
2.70
2.00
2.20
2.70
2.00
2.20
2.70
2.70
3.201.60
3.202.50

<!-- Page 29 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
28
29
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Standard & High Capacitors-Y5V)
0.22
0.22
0.22
0.47
0.47
1
0.47
0.47
0.47
0.47
1
1
2.2
2.2
4.7
1
1
1
2.2
2.2
4.7
4.7
4.7
10
10
10
10
4.7
4.7
4.7
10
10
10
22
22
10
10
22
22
47
100
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
80/20%
16
10
6.3
10
6.3
6.3
50
25
16
10
16
10
10
6.3
6.3
50
25
16
25
16
6.3
16
10
10
10
6.3
6.3
16
10
6.3
16
10
6.3
10
6.3
25
16
10
10
6.3
6.3
1
2
3
4
5
6
1
2
3
4
5
6
7
8
9
1
2
3
4
5
6
7
8
9
10
11
12
1
2
3
4
5
6
7
8
1
2
3
4
5
6
0.55
0.55
0.55
0.55
0.55
0.55
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
0.95
1.35
0.95
1.40
1.40
1.40
1.80
1.80
1.80
1.80
1.80
1.80
1.20
2.70
2.70
2.20
2.70
1.000.50
2.001.25
1.600.80
3.201.60
3.202.50
CL05F224ZO5NNN
CL05F224ZP5NNN
CL05F224ZQ5NNN
CL05F474ZP5NNN
CL05F474ZQ5NNN
CL05F105ZQ5NNN
CL10F474ZB8NNN
CL10F474ZA8NNN
CL10F474ZO8NNN
CL10F474ZP8NNN
CL10F105ZO8NNN
CL10F105ZP8NNN
CL10F225ZP8NNN
CL10F225ZQ8NNN
CL10F475ZQ8NNN
CL21F105ZBFNNN
CL21F105ZAFNNN
CL21F105ZOFNNN
CL21F225ZAFNNN
CL21F225ZOFNNN
CL21F475ZQFNNN
CL21F475ZOFNNN
CL21F475ZPFNNN
CL21F106ZPFNNN
CL21F106ZPCLNN
CL21F106ZQFNNN
CL21F106ZQCLNN
CL31F475ZOFNNN
CL31F475ZPFNNN
CL31F475ZQFNNN
CL31F106ZOHNNN
CL31F106ZPHNNN
CL31F106ZQHNNN
CL31F226ZPHNNN
CL31F226ZQHNNN
CL32F106ZAHNNN
CL32F106ZOELNN
CL32F226ZPJNNN
CL32F226ZPJLNN
CL32F476ZQINNN
CL32F107ZQJNNN

<!-- Page 30 -->

U Small chip size
U 02 and 03 series (High-Q) MLCC shows very low ESR value.
U 02 and 03 Series are suited to only reflow soldering
U 02 and 03 Series are suited to miniature RF module,
portable equipment and high frequency circuit
U VCO, Tuner, RF Module
U MCM Module
U Mobile phone, Wireless LAN, Note PC
Feature
Application
Structure and Dimensions
L
T
BW
W
Code
EIA
Code
L                                   W                                  T                                  BW
Dimension (mm)
0.30.03
0.30.03
0.60.03
0201
0.150.05
0.100.03
03
0.20.02
0.20.02
0.40.02
01005
02
Super Small Size
Capacitors

<!-- Page 31 -->

30
31
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
Super Small Size Capacitance Table (C0G)
Super Small Size Capacitance Table (High-Q)
TC
Capacitance (㎊)
Vr(V)
6.3
16
25
50
25
25
50
Size
(mm)
01005(0402)
0201(0603)
01005(0402)
0201(0603)
C0G
C0G
0.5            1                10              22              47             100            220              330
TC
Capacitance (㎊)
Capacitance (㎋)
Capacitance (㎌)
Vr(V)
Size
(mm)
0.2            1                10              15              27              33              47               100
Super Small Size Capacitance Table (X7R,X6S)
Super Small Size Capacitance Table (X5R, Y5V)
TC
Vr(V)
Size
(mm)
TC
Vr(V)
Size
(mm)
6.3
10
16
4
6.3
10
16
25
6.3
01005(0402)
0201(0603)
0201(0603)
X5R
Y5V
0.01           0.1            0.22            0.47             1               2.2             4.7                 10
X5R or X6S
10
10
16
25
50
4
01005(0402)
0201(0603)
0201(0603)
X7R
0.1          0.22            0.47             1               2.2             3.3             4.7                  10
X6S

<!-- Page 32 -->

Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please  see p74.
Product Lineup (Super Small Size Capacitors-C0G)
CL02C0R5CO2ANN
CL02C010CO2ANN
CL02C1R2CO2ANN
CL02C1R5CO2ANN
CL02C1R8CO2ANN
CL02C020CO2ANN
CL02C2R2CO2ANN
CL02C2R7CO2ANN
CL02C030CO2ANN
CL02C3R3CO2ANN
CL02C3R9CO2ANN
CL02C4R7CO2ANN
CL02C5R6DO2ANN
CL02C6R8DO2ANN
CL02C8R2DO2ANN
CL02C090DO2ANN
CL02C100 J O2ANN
CL02C150J O2ANN
CL02C180J O2ANN
CL02C220J O2ANN
CL02C270J O2ANN
CL02C330J O2ANN
CL02C390J O2ANN
CL02C470J O2ANN
CL02C560J Q2ANN
CL02C680J Q2ANN
CL02C820 J Q2ANN
CL02C101J O 2ANN
CL02C101 J Q2ANN
CL02C0R5BO2GNN
CL02C010BO2GNN
CL02C1R2BO2GNN
CL02C1R5BO2GNN
CL02C1R8BO2GNN
CL02C2R2BO2GNN
CL02C2R7BO2GNN
CL02C3R3BO2GNN
CL02C3R9BO2GNN
CL02C4R7BO2GNN
CL02C5R6BO2GNN
CL02C6R8BO2GNN
CL02C8R2BO2GNN
CL02C100JO2GNN
CL02C120JO2GNN
CL02C150JO2GNN
CL02C180JO2GNN
CL02C220JO2GNN
CL02C270JO2GNN
0.5
1.0
1.2
1.5
1.8
2.0
2.2
2.7
3.0
3.3
3.9
4.7
5.6
6.8
8.2
9.0
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
10㎊
15㎊
18㎊
22㎊
27㎊
33㎊
39㎊
47㎊
56㎊
68㎊
82㎊
100㎊
100㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
0.5
1.0
1.2
1.5
1.8
2.2
2.7
3.3
3.9
4.7
5.6
6.8
8.2㎊
10㎊
12㎊
15㎊
18㎊
22㎊
27㎊
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.25
0.5
0.5
0.5
0.5
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
5%
5%
5%
5%
5%
5%
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
6.3
6.3
6.3
16
6.3
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
16
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
0.400.20
0.400.20
CL03C0R5CA3GNN
CL03C010CA3GNN
CL03C1R2CA3GNN
CL03C1R5CA3GNN
0.5㎊
1.0㎊
1.2㎊
1.5㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
25
25
25
25
1
2
3
4
0.33
0.33
0.33
0.33
High-Q
High-Q
High-Q
High-Q
0.600.30

<!-- Page 33 -->

32
33
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
Product Lineup (Super Small Size Capacitors-X7R,X6S)
CL02B101KP2NNN
CL02B221KP2NNN
CL02B271KP2NNN
CL02B331KP2NNN
CL02B391KP2NNN
CL02B471KP2NNN
CL02B681KP2NNN
CL03B151KA3NNN
CL03B221KA3NNN
CL03B271KO3NNN
CL03B331KA3NNN
CL03B471KA3NNN
CL03B561KO3NNN
CL03B681KA3NNN
100
150
㎊
220㎊
270㎊
330㎊
390㎊
470㎊
680㎊
1㎋
㎊
220㎊
270㎊
330㎊
470㎊
560㎊
680㎊
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10
10
10
10
10
10
10
25
25
16
25
25
16
25
1
2
3
4
5
6
7
1
2
3
4
5
6
7
0.22
0.22
0.22
0.22
0.22
0.22
0.22
CL02B102KP2NNN
10%
10
8
0.22
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.600.30
0.400.20
CL03B821KO3NNN
CL03B102KA3NNN
CL03B152KP3NNN
CL03B332KP3NNN
CL03B392KP3NNN
CL03B472KP3NNN
CL03B682KP3NNN
820
1
1.5
3.3
3.9
6.8
㎊
㎋
㎋
㎋
㎋
4.7㎋
㎋
10 ㎋
10%
10%
10%
10%
10%
10%
10%
16
25
10
10
10
10
10
8
9
10
11
12
13
14
0.33
0.33
0.33
0.33
0.33
0.33
0.33
CL03B103KP3NNN
CL03X104KQ3NNN
CL03X105MR3CSN
CL03X105MR3NRN
100
1
㎋
10%
20%
20%

























20%
10
6.3
4
4
15
1
2
3
0.33
0.33
0.35
0.39
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
㎌
1㎌
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
※
mark means packaging code. If you want to learn the code or quantity in detail, please  see p74.
Product Lineup (Super Small Size Capacitors-C0G)

CL03C1R8CA3GNN
CL03C020CA3GNN
CL03C2R2CA3GNN
CL03C2R7CA3GNN
CL03C030CA3GNN
CL03C3R3CA3GNN
CL03C3R9CA3GNN
CL03C4R7CA3GNN
CL03C5R6DA3GNN
CL03C6R8DA3GNN
CL03C8R2DA3GNN
CL03C090DA3GNN
CL03C100JA3GNN
CL03C150JA3ANN
CL03C180JA3ANN
CL03C220JA3ANN
CL03C270JA3ANN
CL03C330JA3ANN
CL03C390JA3ANN
CL03C470JA3ANN
CL03C101JB3ANN
CL03C101JA3ANN
1.8㎊
2.0㎊
2.2㎊
2.7㎊
3.0㎊
3.3㎊
3.9㎊
4.7㎊
5.6㎊
6.8㎊
8.2㎊
9.0㎊
10㎊
15㎊
18㎊
22㎊
27㎊
33㎊
39㎊
47㎊
100㎊
100㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.25㎊
0.5㎊
0.5㎊
0.5㎊
0.5㎊
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
25
25
25
25
25
25
25
25
25
25
25
25
25
25
25
25
25
25
25
25
50
25
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
High-Q
0.600.30

<!-- Page 34 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Super Small Size Capacitors-X5R)
0.600.30
0.400.20
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
1
2
3
4
5
6
7
8
9
10
11
12
13
14
NNN
CL02A151KQ2NNN
CL02A221KQ2NNN
CL02A331KQ2NNN
CL02A471KQ2NNN
CL02A681KQ2NNN
CL02A102KQ2NNN
CL02A152KQ2NNN
CL02A222KQ2NNN
CL02A332KQ2NNN
CL02A472KQ2NNN
CL02A682KQ2NNN
CL02A103KQ2NNN
CL02A104KQ2NNN
CL02A224MR2NNN
CL02A224MQ2NNN
CL03A103KA3NNN
CL03A223KQ3NNN
CL03A473KQ3NNN
CL03A104MA3
CL03A104KO3NNN
CL03A104KP3NNN
CL03A104KQ3NNN
CL03A224KQ3NNN
CL03A224KP3NNN
CL03A105MO3NRN
CL03A105MQ3CSN
CL03A105MP3NSN
CL03A225MR3CRN
CL03A225MQ3CRN
150
220
330
470
680
1
1.5
2.2
3.2
4.7
6.8
10
100
220
220
10
22
47
100
100
100
100
220
220
1
1
1
2.2
2.2
㎊
㎊
㎊
㎊
㎊
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎌
㎌
㎌
㎌
6.3
6.3
6.3
6.3
6.3
6.3
6.3
6.3
6.3
6.3
6.3
6.3
6.3
4
6.3
25
6.3
6.3
25
16
10
6.3
6.3
10
16
6.3
10
4
6.3
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
20%
20%
10%
10%
10%
20%
10%
10%
10%
10%
10%
20%
20%
20%
20%
20%
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.22
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.33
0.39
0.35
0.35
0.39
0.39
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 35 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
34
35
High-Q Capacitors
L
T
BW
W
Code
EIA
Code
Rated
Voltage
L                                  W                                 T                                  BW
(mm)
Dimension
0.500.05
0.800.10
0.650.10
0.850.15
0.500.05
0.800.10
0.800.15
1.250.15
1.00
0.05
1.60
0.10
1.60
0.15
2.00
0.15




50V
50/100V
250V
250V
0402
0603
0.250.10
0.300.20
0.300.20
0.500.20/0.30
05
10
0805
21
U High Q and low ESR in high frequency range
U Tight tolerance available
U High efficiency and low power consumption in RF circuit
U Can be applied to power amplifier module for base-station and
 GHz range communications
U Base Station
U Set Top Box
U Wireless Equipment
U GPS, Bluetooth
Application
Structure and Dimensions
Feature
Plating layer(Ni/Sn)
Outer electrode(Cu)
Inner electrode(Cu)
Ceramic
TC
Capacitance (    )
㎊
Vr(V)
Size(mm)
50
50
100
250
250
0402(1005)
0603(1608)
0805(2012)
COG
0.2       0.5        1          10       15         27        33        47        68       100      150      220
Capacitance Table (High-Q capacitor)

<!-- Page 36 -->

Medium-High Voltage
Capacitors
L
T
BW
W
Code
EIA
Code
L                              W                              T                 Thickness Code              BW
(mm)
Dimension
0.800.10
1.250.10
0.850.10
0.650.10
1.600.20
1.250.15
0.850.15
2.500.20
1.600.20
1.250.20
2.000.20
1.600.20
1.250.20
2.500.20
1.600.20
1.250.20
2.500.20
1.600.20
0.800.10
1.250.10
1.250.10
1.250.10
1.600.20
1.600.15
1.600.15
2.500.20
2.500.20
2.500.20
2.000.20
2.000.20
2.000.20
3.200.30
3.200.30
3.200.30
5.000.40
5.000.40
1.60
0.10
2.00
0.10
2.00
0.10
2.00
0.10
3.20
0.20
3.20
0.15
3.20
0.15
3.20
0.30
3.20
0.30
3.20
0.30
4.50
0.40
4.50
0.40
4.50
0.40
4.50
0.40
4.50
0.40
4.50
0.40
5.70
0.40
5.70

















0.40
0603
0805
1206
1210
1808
1812
2220
0.30.2
0.50.2/0.3
0.50.3
0.60.3
0.80.3
0.80.3
1.00.3
10
21
31
32
42
43
55
U Highly reliable performance
U Operating at high voltage level
U Wide voltage level: from 100V to 3000V
U High withstanding voltage
U Tape & reel surface mount assembly
U Switching Power Circuit(SMPS)
U Lighting Ballast, LCD back lighting inverter
U DC-DC converter input filter, snubber circuit
U Phone, Fax, Modem
U Network(IEEE802.3)
Application
Structure and Dimensions
Feature
8
F
C
A
H
F
C
J
H
F
I
H
F
J
H
F
J
H

<!-- Page 37 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
36
37
Feature
Medium-High Voltage capacitance Table (C0G)
100V
200V
250V
500V
630V
0603(1608)
0805(2012)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
0805(2012)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
330 390 470 560 680 820  1  1.2   1.5   1.8 2.2 2.7  3.3  3.9  4.7  5.6 6.8  8.2  10  12  15  18 22 27  33  47  56   68
(㎋)
Size(mm)
(㎊)
Capacitance
Vr(V)

<!-- Page 38 -->

Medium-High Voltage capacitance Table (C0G)
1KV
2KV
3KV
1206(3216)
1210(3225)
1812(4532)
2220(5750)
1206(3216)
1210(3225)
1808(4520)
1812(4532)
2220(5750)
1808(4520)
1812(4532)
2220(5750)
47  56 68  82 100 120  150 180 220  270  330  390 470  560  680  820  1  1.2 1.5 1.8   2.2   2.7 3.3 3.9   4.7   5.6
3.6㎋
(㎋)
Size(mm)
(㎊)
Capacitance
Vr(V)

<!-- Page 39 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
38
39
Medium-High Voltage capacitance Table (X7R)
100V
200V
250V
350V
500V
630V
0603(1608)
0805(2012)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
0805(2012)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
0805(2012)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
1206(3216)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
1206(3216)
1210(3225)
1812(4532)
2220(5750)
4.7     10      15     22
33
47
68       100    150      220
330      470      680    1000   1500    2200    4700
(Tmax=1.0)
(Tmax
=1.8)
(Tmax
=1.25)
(㎋)
Size(mm)
Capacitance
Vr(V)

<!-- Page 40 -->

Medium-High Voltage capacitance Table (X7R)
1KV
2KV
3KV
1206(3216)
1210(3225)
1812(4532)
2220(5750)
1206(3216)
1210(3225)
1808(4520)
1812(4532)
2220(5750)
1808(4520)
1      1.5     2.2     3.3     4.7     6.8     10      15       22      33      47      68    100     150    220    330
(㎋)
Size(mm)
Capacitance
Vr(V)

<!-- Page 41 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
40
41
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Medium-High Voltage Capacitors-C0G)
CL10C100JC8NNN
CL10C150JC8NNN
CL10C330JC8NNN
CL10C390JC8NNN
CL10C470JC8NNN
CL10C560JC8NNN
CL10C101JC8NNN
CL10C121JC8NNN
CL10C151JC8NNN
CL10C331JC8NNN
CL10C331JD8NNN
CL10C331JE8NNN
CL10C391JD8NNN
CL10C391JE8NNN
CL10C471JC8NNN
CL10C471JD8NNN
CL10C471JE8NNN
CL10C561JD8NNN
CL10C561JE8NNN
CL10C681JC8NNN
CL10C681JD8NNN
CL10C681JE8NNN
CL10C821JC8NNN
CL10C102JC8NNN
CL10C122JC8NNN
CL21C100JCANNN
CL21C120JCANNN
CL21C150JCANNN
CL21C150JDCNNN
CL21C180JCANNN
CL21C180JDCNNN
CL21C220JCANNN
CL21C270JCANNN
CL21C270JHFNNN
CL21C330JCANNN
CL21C330JDCNNN
CL21C330JHFNNN
CL21C390JDCNNN
CL21C470JCANNN
CL21C470JDCNNN
CL21C470JHFNNN
CL21C560JCCNNN
CL21C560JDCNNN
CL21C680JCANNN
CL21C680JDCNNN
CL21C680JHFNNN
CL21C820JCCNNN
CL21C101JCANNN
CL21C101JDCNNN
CL21C101JECNNN
10
15
33
39
47
56
100
120
150
330
330
330
390
390
470
470
470
560
560
680
680
680
820
1
1.2
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎋
㎋
10
12
15
15
18
18
22
27
27
33
33
33
39
47
47
47
56
56
68
68
68
82
100
100
100
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊


















































5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
100
100
100
100
100
100
100
100
100
100
200
250
200
250
100
200
250
200
250
100
200
250
100
100
100
100
100
100
200
100
200
100
100
630
100
200
630
200
100
200
630
100
200
100
200
630
100
100
200
250
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.75
0.75
0.75
0.95
0.75
0.95
0.75
0.75
1.35
0.75
0.95
1.35
0.95
0.75
0.95
1.35
0.95
0.95
0.75
0.95
1.35
0.95
0.75
0.95
0.95
1.600.80
2.001.25
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 42 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Medium-High Voltage Capacitors-C0G)
CL21C121JDCNNN
CL21C151JCANNN
CL21C151JHFNNN
CL21C221JCANNN
CL21C221JDCNNN
CL21C331JCANNN
CL21C471JCCNNN
CL21C561JCCNNN
CL21C561JHFNNN
CL21C681JCCNNN
CL21C102JCFNNN
CL21C102JDFNNN
CL21C272JDFNNN
CL21C272JEFNNN
CL21C472JCFNNN
CL31C150JGFNNN
CL31C180JGFNNN
CL31C220JGFNNN
CL31C220JJHNNN
CL31C270JGFNNN
CL31C330JGFNNN
CL31C390JGFNNN
CL31C470JGFNNN
CL31C470JHFNNN
CL31C470JIFNNN
CL31C470JJHNNN
CL31C560JGFNNN
CL31C680JCCNNN
CL31C680JGFNNN
CL31C680JHFNNN
CL31C680JIFNNN
CL31C820JGFNCN
CL31C101JGFNNN
CL31C101JHFNNN
CL31C101JIFNNN
CL31C101JJHNNN
CL31C121JGFNNN
CL31C151JGFNNN
CL31C181JGFNNN
CL31C221JGFNNN
CL31C271JGFNNN
CL31C271JCCNNN
CL31C331JGFNNN
CL31C331JIHNNN
CL31C391JCCNNN
CL31C471JGFNNN
CL31C471JHFNNN
CL31C471JIFNNN
CL31C561JCCNNN
CL31C561JGFNNN
CL31C681JGFNNN
CL31C821JHHNNN
120
150
150
220
220
330
470
560
560
680
1
1
2.7
2.7
4.7
15
18
22
22
27
33
39
47
47
47
47
56
68
68
68
68
82
100
100
100
100
120
150
180
220
270
270
330
330
390
470
470
470
560
560
680
820
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎋
㎋
㎋
㎋
㎋
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎌
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
200
100
630
100
200
100
100
100
630
100
100
200
200
250
100
500
500
500
2000
500
500
500
500
630
1000
2000
500
100
500
630
1000
500
500
630
1000
2000
500
500
500
500
500
100
500
1000
100
500
630
1000
100
500
500
630
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
0.95
0.75
1.35
0.75
0.95
0.75
0.95
0.95
1.35
0.95
1.35
1.35
1.35
1.35
1.35
1.40
1.40
1.40
1.80
1.40
1.40
1.40
1.40
1.40
1.40
1.80
1.40
1.00
1.40
1.40
1.40
1.40
1.40
1.40
1.40
1.80
1.40
1.40
1.40
1.40
1.40
1.00
1.40
1.80
1.00
1.40
1.40
1.40
1.00
1.40
1.80
1.80
2.001.25
3.201.60
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 43 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
42
43
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Medium-High Voltage Capacitors-C0G)
CL31C102JCCNNN
CL31C102JGHNNN
CL31C152JCCNNN
CL31C222JCCNNN
CL31C332JGHNNN
CL31C332JHHNNN
CL31C392JCHNNN
CL31C822JDHNNN
CL31C822JEHNNN
CL31C183JCHNNN
CL32C101JJFNNN
CL32C471JJJNNN
CL32C821JIJNNN
CL32C103JGJNNN
CL32C103JHJNNN
CL32C273JDJNNN
CL32C273JEJNNN
CL32C563JCJNNN
CL42C100JKFNNN
CL42C151JKINNN
CL42C221JJHNNN
CL43C391JKJNNN
CL43C102 J I HNNN
CL43

N
N
N
 I I J
2
2
1
C
CL43C182 J I J NNN
CL43C182JJJNNN
CL43C223JGJNNN
CL43C223JHJNNN
CL43C473JDJNNN
CL43C473JEJNNN
CL43C563JCJNNN
CL55C102JJJNNN
CL55C102JKJNNN
CL55C362JIJNNN
CL55C223JGJNNN
CL55C223JHJNNN
CL55C473JDJNNN
CL55C473JEJNNN
CL55C683JCJNNN
1㎋
1㎋
1.5㎋
2.2㎋
3.3㎋
3.3㎋
3.9㎋
8.2㎋
8.2㎋
18㎋
100㎊
470㎊
820㎊
10㎋
10㎋
27㎋
27㎋
56㎋
10㎊
150㎊
220㎊
390㎊
1㎋
1.2㎋
1.8㎋
1.8㎋
22㎋
22㎋
47㎋
㎋
47
56㎋
1㎋
1㎋
3.6㎋
22㎋
22㎋
47㎋
47㎋
68㎋
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%






































5%
100
500
100
100
500
630
100
200
250
100
2000
2000
1000
500
630
200
250
100
3000
3000
2000
3000
1000
1000
1000
2000
500
630
200
250
100
2000
3000
1000
500
630
200
250
100
36
37
38
39
40
41
42
43
44
45
1
2
3
4
5
6
7
8
1
2
3
1
2
3
4
5
6
7
8
9
10
1
2
3
4
5
6
7
8
1.00
1.80
1.00
1.00
1.80
1.80
1.80
1.80
1.80
1.80
1.45
2.70
2.70
2.70
2.70
2.70
2.70
2.70
1.45
2.20
1.80
2.70
1.80
2.20
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
2.70
3.201.60
3.202.50
4.502.00
4.503.20
5.705.00
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 44 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Medium-High Voltage Capacitors-X7R)
CL10B102KC8NNN
CL10B472KC8NNN
CL10B103KC8NNN
CL10B104KC8NNN
CL21B221KDCNNN
CL21B221KCANNN
CL21B331KDCNNN
CL21B471KCANNN
CL21B102KDCNNN
CL21B102KCANNN
CL21B222KDCNNN
CL21B222KCANNN
CL21B332KCANNN
CL21B472KDCNNN
CL21B472KCANNN
CL21B682KCANNN
CL21B103KDCNNN
CL21B103KCANNN
CL21B153KEFNNN
CL21B153KDFNNN
CL21B153KCCNNN
CL21B223KCFNNN
CL21B473KCFNNN
CL21B683KCFNNN
CL21B154KCFNNN
CL21B224KCFNNN
CL31B221KGFNNN
CL31B471KGFNNN
CL31B471KDCNNN
CL31B102KJHNNN
CL31B102KI FNNN
CL31B102KGFNNN
CL31B102KHFNNN
CL31B152KGFNNN
CL31B152KJHNNN
CL31B222KIFNNN
CL31B222KDCNNN
CL31B222KGFNNN
CL31B222KJHNNN
CL31B332KGFNNN
CL31B332KIFNNN
CL31B472KGFNNN
1㎋
4.7㎋
10㎋
100㎋
220㎊
220㎊
330㎊
470㎊
1㎋
1㎋
2.2㎋
2.2㎋
3.3㎋
4.7㎋
4.7㎋
6.8㎋
10㎋
10㎋
15㎋
㎋
15
15㎋
22㎋
47㎋
68㎋
150㎋
220㎋
220㎊
470㎊
470㎊
1㎋
1㎋
1㎋
1㎋
1.5㎋
1.5㎋
2.2㎋
2.2㎋
2.2㎋
2.2㎋
3.3㎋
3.3㎋
4.7㎋
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%









































10%
100
100
100
100
200
100
200
100
200
100
200
100
100
200
100
100
200
100
250
200
100
100
100
100
100
100
500
500
200
2000
1000
500
630
500
2000
1000
200
500
2000
500
1000
500
1
2
3
4
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
0.90
0.90
0.90
0.90
0.95
0.75
0.95
0.75
0.95
0.75
0.95
0.75
0.75
0.95
0.75
0.75
0.95
0.75
1.35
1.35
0.95
1.35
1.35
1.35
1.35
1.35
1.40
1.40
1.00
1.80
1.40
1.40
1.40
1.40
1.80
1.40
1.00
1.40
1.80
1.40
1.40
1.40
1.60 x 0.80
2.001.25
3.201.60
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 45 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
44
45
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Medium-High Voltage Capacitors-X7R)
CL31B472KDCNNN
CL31B682KGFNNN
CL31B103KHFNNN
CL31B103KGFNNN
CL31B103KFCSNN
CL31B153KDCNNN
CL31B153KFCSNN
CL31B153KCCNNN
CL31B153KGFNNN
CL31B153KHFNNN
CL31B223KDCNNN
CL31B223KCCNNN
CL31B223KFCSNN
CL31B223KGHNNN
CL31B223KHHNNN
CL31B333KDFNNN
CL31B333KFESNN
CL31B333KCCNNN
CL31B333KGHNNN
CL31B333KHHNNN
CL31B473KDFNNN
CL31B473KFHSNN
CL31B473KCCNNN
CL31B473KEHNNN
CL31B683KEHNNN
CL31B104KDHNNN
CL31B104KCFNNN
CL31B104KEHNNN
CL31B154KCHNNN
CL31B105KCHNNN
CL31B155KCHNNN
CL31B225KCHNNN
CL32B102KJFNNN
CL32B472KHFNNN
CL32B472KIFNNN
CL32B682KIFNNN
CL32B103KCFNNN
CL32B153KGFNNN
CL32B223KGFNNN
CL32B333KHHNNN
CL32B333KGHNNN
CL32B473KHHNNN
4.7
6.8
10
10
10
15
15
15
15
15
22
22
22
22
22
33
33
33
33
33
47
47
47
47
68
100
100
100
150
1
1.5
2.2
1
4.7
4.7
6.8
10
15
22
33
33
47
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎌
㎌
㎌
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%









































10%
200
500
630
500
350
200
350
100
500
630
200
100
350
500
630
200
350
100
500
630
200
350
100
250
250
200
100
250
100
100
100
100
2000
630
1000
1000
100
500
500
630
500
630
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
1
2
3
4
5
6
7
8
9
10
1.00
1.40
1.40
1.40
1.00
1.00
1.00
1.00
1.40
1.40
1.00
1.00
1.00
1.80
1.80
1.40
1.25
1.00
1.80
1.80
1.40
1.80
1.00
1.80
1.80
1.80
1.40
1.80
1.80
1.80
1.80
1.80
1.45
1.45
1.45
1.45
1.45
1.45
1.45
1.80
1.80
1.80
3.201.60
3.202.50
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 46 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Medium-High Voltage Capacitors-X7R)
CL32B473KDHNNN
CL32B473KGHNNN
CL32B683KDINNN
CL32B104KEJNNN
CL32B104KDINNN
CL32B154KCFNNN
CL32B154KDJNNN
CL32B154KEJNNN
CL32B224KCHNNN
CL32B224KDJNNN
CL32B224KEJNNN
CL32B334KCHNNN
CL32B474KCINNN
CL32B105KCJNNN
CL32B155KCHNNN
CL32B225KCJNNN
CL43B102KJFNNN
CL43B152KJFNNN
CL43B222KIFNNN
CL43B222KJFNNN
CL43B332KJFNNN
CL43B103KIFNNN
CL43B333KIJNNN
CL43B473KGFNNN
CL43B473KHFNNN
CL43B104KGINNN
CL43B104KDFNNN
CL43B104KHINNN
CL43B224KCFNNN
CL43B334KCFNNN
CL43B474KEJNNN
CL43B474KCHNNN
CL43B474KDJNNN
CL43B105KCJNNN
CL55B103KJHNNN
CL55B473KIINNN
CL55B224KGJNNN
CL55B224KHJNNN
CL55B105KCHNNN
CL55B105KDJNNN
CL55B105KEJNNN
CL55B475KCJNNN
47㎋
47㎋
68㎋
100㎋
100㎋
150㎋
150㎋
150㎋
220㎋
220㎋
220㎋
330㎋
470㎋
1㎌
1.5㎌
2.2㎌
1㎋
1.5㎋
2.2㎋
2.2㎋
3.3㎋
10㎋
33㎋
47㎋
47㎋
100㎋
100㎋
100㎋
220㎋
330㎋
470㎋
470㎋
470㎋
1㎌
10㎋
47㎋
220㎋
220㎋
1㎌
1㎌
1㎌
4.7㎌
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%









































10%
200
500
200
250
200
100
200
250
100
200
250
100
100
100
100
100
2000
2000
1000
2000
2000
1000
1000
500
630
500
200
630
100
100
250
100
200
100
2000
1000
500
630
100
200
250
100
1.80
1.80
2.20
2.70
2.20
1.45
2.70
2.70
1.80
2.70
2.70
1.80
2.20
2.70
1.80
2.70
1.45
1.45
1.45
1.45
1.45
1.45
2.70
1.45
1.45
2.20
1.45
2.20
1.45
1.45
2.70
1.80
2.70
2.70
1.80
2.20
2.70
2.70
1.80
2.70
2.70
2.70
3.202.50
4.503.20
5.705.00
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
1
2
3
4
5
6
7
8
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 47 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
46
47
Array Type
Capacitors
■A : ARRAY(2-element)
■B : ARRAY(4-element)
L
T
SW
BW
P
W
Ceramic Body
End Termination
SW
L
W
P
BW
T
SW
L
W
BW
P
T
Ceramic Body
End Termination
0.350.05
0.500.05
0.600.06
0.800.08
0.850.1
0.850.1
0.850.15
0.360.1
0.50.2
0.250.1
0.40.2
1.370.15
2.00.15
2.00.15
3.20.15
1.00.15
1.250.15
1.250.15
1.60.15
0.20.1
0.250.15
0.250.15
0.30.15
0.640.1
1.00.1
0.50.1
0.80.2
1410
2012
2012
3216
A
A
B
B
0.250.05
0.900.05
0.45
0.600.05
0.05
0.150.1
0.450.05
0906
Code
Size
(mm)
L                         W                         T                        BW                      SW
P
Dimension(mm)
EIA
Code
0504
0805
0805
1206
0302
A
U Reduction in required space(more than 50%)
U Reduction in cost and time for replacement of PCB
U Reduction in amount of solder joints
U Easier PCB design
U Reduced waste from tape and reel packaging process
U It protect EMI bypassing digital signal line nose
U A bypass for digital and analog signal line noise generated by telecommunication equipment and other common
electronic circuits
Feature
Application
Structure and Dimensions
Structure and Control Code

<!-- Page 48 -->

Array Type capacitance Table (C0G, X5R, X7R, Y5V)
TC
C0G
Capacitance(㎊)
Size(mm)
0504(1410)
1206(3216)
Type
2-element
4-element
Vr(V)
25
50
0.88
1.00
Tmax
(mm)
Size(mm)
Type
Vr(V)
Tmax
(mm)
TC
X5R
X7R
Y5V
2-element
2-element
2-element
4-element
4-element
4-element
0302(0906)
0504(1410)
0805(2012)
0805(2012)
1206(3216)
1206(3216)
4
6.3
10
6.3
10
16
25
6.3
10
16
10
16
16
25
50
25
50
0.50
0.88
0.66
0.55
0.40
0.88
0.66
0.55
0.40
0.88
0.66
0.55
0.40
0.88
0.66
0.55
0.95
0.95
1.00
1.00
10               22                27                47               100              470
Capacitance(㎋)
1       2.2      4.7      10       22       47      100      220    470    1000   2200

<!-- Page 49 -->

48
49
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Array Type Capacitors )
CL14C270KA6NAN
CL31C100JBCNBN
CL31C150JBCNBN
CL31C220JBCNBN
CL31C270JBCNBN
CL31C330KBCNBN
CL31C390KBCNBN
CL31C680JBCNBN
CL31C820JBCNBN
CL31C101JBCNBN
CL31C151KBCNBN
CL31C181JBCNBN
CL31C331JBCNBN
CL31C471JBCNBN
CL21B471KBCNBN
CL21B104KOCNBN
CL21B104MPCNBN
CL31B102MBCNBN
CL31B103MBCNBN
CL31B153KBCNBN
CL31B473KACNBN
CL31B104KACNBN
CL31B104KOCNBN
CL09A104KP4SAN
CL09A104KQ4SAN
CL09A105MQ4NAN
CL09A105MR4NAN
CL14A104KA6NAN
CL14A104KO6NAN
CL14A104KP6NAN
CL14A105MA5NAN
CL14A105KP8NAN
CL14A105MO3NAN
CL14A105MO8NAN
CL14A105MO5NAN
CL14A105MP3NAN
CL14A105MP5NAN
CL14A225KP8NAN
CL14A225KQ8NAN
CL21A105KOCNAN
CL21A105MPCNAN
CL31F473ZBCNBN
CL31F104ZACNBN
25
50
50
50
50
50
50
50
50
50
50
50
50
50
50
16
10
50
50
50
25
25
16
10
6.3
6.3
4
25
16
10
25
10
16
16
16
10
10
10
6.3
16
10
50
25
27㎊
10㎊
15㎊
22㎊
27㎊
33㎊
39㎊
68㎊
82㎊
100㎊
150㎊
180㎊
330㎊
470㎊
470㎊
100㎋
100㎋
1㎋
10㎋
15㎋
47㎋
100㎋
100㎋
100㎋
100㎋
1㎌
1㎌
100㎋
100㎋
100㎋
1㎌
1㎌
1㎌
1㎌
1㎌
1㎌
1㎌
2.2㎌
2.2㎌
1㎌
1㎌
47㎋
100㎋
1
1
2
3
4
5
6
7
8
9
10
11
12
13
1
2
3
1
2
3
4
5
6
1
2
3
4
1
2
3
4
5
6
7
8
9
10
11
12
1
2
1
2
10%
5%
5%
5%
5%
10%
10%
5%
5%
5%
10%
5%
5%
5%
10%
10%
20%
20%
20%
10%
10%
10%
10%
10%
10%
20%
20%
10%
10%
10%
20%
10%
20%
20%
20%
20%
20%
10%
10%
10%
20%
80/20%
80/20%
0.66
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
1.00
0.95
0.95
0.95
1.00
1.00
1.00
1.00
1.00
1.00
0.50
0.50
0.50
0.50
0.66
0.66
0.66
0.55
0.88
0.40
0.88
0.55
0.40
0.55
0.88
0.88
0.95
0.95
1.00
1.00
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
Element
Type
4-Array
4-Array
4-Array
2-Array
2-Array
2-Array
2-Array
4-Array
3.201.60
2.001.25
3.201.60
0.900.60
1.401.00
1.401.00
2.001.25
3.201.60
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition

<!-- Page 50 -->

Low ESL
Capacitors
Highly reliable tolerance and high speed automatic chip placement on PCBs
Code
Size
(mm)
Dimension(mm)
EIA
Code
Code
Size
(mm)
Dimension(mm)
EIA
Code
L
T
BW
W
L                                 W                                   T                                  BW
0.30.05
0.50.05/0.1
1.00.05
1.60.2
0.520.05
0.80.15
0204
0306
0510
0816
0.180.06
0.250.15
L5
01
U Low ESL, good for noise reduction for high frequency
U
U Highly reliable performance
U Highly resistant termination metal
U Tape & reel for surface mount assembly
U High Speed Microprocessor
U High Frequency Digital Equipment
Feature
Application
LICC(Low Inductance Ceramic Capacitors)
SLIC(Super Low Inductance Capacitors)
L                       W                       T                       BW                      SW                        P
0.5/0.050.1
0.5/0.050.1
0.250.1
0.250.150.1
1.60.1
2.00.1
0.80.1
1.250.1
0.150.1
0.20.150.1
0.40.1
0.50.1
1608
2012
0603
0805
10
21
SW
W
BW
P
T
W
L

<!-- Page 51 -->

50
51
Size(mm)
Vr(V)
Tmax(mm)
(mm)
(mm)
TC
Capacitance(㎌)
Size(mm)
Vr(V)
Tmax
TC
Capacitance(㎌)
Size(mm)
Vr(V)
Tmax
TC
Capacitance(㎌)
Low ESL capacitance Table (LICC)
X6S
/X7S
/X7T
0204(0510)
0306(0816)
0.35
0.55
2.5
4
6.3
4
0.55
6.3
10
16
25
50
0.55
0.55
4
4
6.3
16
0306(0816)
0.01   0.022   0.047     0.1       0.22     0.47       1         2.2       4.7       10
X7R
/X5R
0.01   0.022   0.047      0.1      0.22     0.47       1         2.2       4.7       10
Low ESL capacitance Table (SLIC)
X7R
/X7S
/X7T
0603(1608)
0805(2012)
0.1         0.47       0.68           1            2.2          4.7          10           22
X6S
X7S
X7T
X7S
X7S
X7S
X7R
X7S
X7R
X7R
X7R
X7R
X7R
X7R
X7R
X5R
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition

<!-- Page 52 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
Product Lineup (Low ESL Capacitors-X7R, X6S, X7S, X7T)
CL21B104MO5NJN
CL21B684MO5NJN
CL21B684MQ5NJN
CLL5X224 MR3NLN
CLL5X474MR3NLN
CLL5X105MR3NLN
CLL5Y104MQ3NLN
CL01Y105MR5NLN
CL01Y225MR5NLN
CL10Y474MR5NJN
CL10Y105MR5NJN
CL10Y225MR5NJN
CL21Y105MR5NJN
CL21Y225MR5NJN
CLL5Z105MS3NLN
100㎋
680㎋
680㎋
220㎋
470㎋
1㎌
100㎋
1㎌
2.2㎌
470㎋
1㎌
2.2㎌
1㎌
2.2㎌
1㎌
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%
20%














20%
16
16
6.3
4
4
4
6.3
4
4
4
4
4
4
4
2.5
1
2
3
1
2
3
1
1
2
1
2
3
1
2
1
0.55
0.55
0.55
0.35
0.35
0.35
0.35
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.35
2.001.25
0.501.00
0.501.00
0.801.60
1.600.80
2.001.25
0.501.00

<!-- Page 53 -->

52
53
Capacitors
Reliability Test
Apply the specified voltage* for 1~5 sec.
Charge / Discharge current limit: 50mA max.
*CLASSⅠ(Rated Voltage100V) : 300% of the rated Voltage
CLASSⅡ(Rated Voltage100V) : 250% of the rated Voltage
In the case of Vr 100V products, following condition should
be applied.
100VRated Voltage500V : 200% of the rated Voltage
500VRated Voltage1000V :150% of the rated Voltage
Rated Voltage1000V :120% of the rated Voltage
Visual Inspection throughMicroscope (x10)
Test Condition
Tan
Q
Withstanding Voltage
Insulation Resistance
Appearance
Item
Within the specified tolerance
Within the specified tolerance
No dielectric breakdown or mechanical breakdown
No abnormal exterior appearance
Performance
1
2
3
4
5
No
CLASSⅠ
CLASSⅡ
CLASSⅡ
Capacitance
1,000㎊
1,000㎊
Capacitance
10㎌
10㎌
*
Frequency
1MHz10%
1KHz10%
Frequency
1KHz10%
120Hz20%
1KHz10%
Voltage
0.5 ~ 5 Vrms
Voltage
1.00.2Vrms
0.50.1Vrms
0.50.1Vrms
Voltage
0.5 ~ 5 Vrms
Voltage
1.00.2Vrms
0.50.1Vrms
0.50.1Vrms
Capacitance
1,000㎊
1,000㎊
Capacitance
10㎌
10㎌
*
Frequency
1MHz10%
1KHz10%
Frequency
1KHz10%
120Hz20%
1KHz10%
Rated Voltage
50V /35V
25V
16V
10V
1. Characteristic : A(X5R)
Spec
0.025 max / 0.05 max*
0.025 max /
0.05 max* / 0.10 max*
0.035 max /
0.05 max* / 0.10 max*
0.05 max /0.10 max*
Rated Voltage
50V/ 35V / 25V
16V
10V
2. Characteristic : B(X7R), X(X6S), Y(X7S)
Spec
0.025 max /
0.05 max* / 0.10 max*
0.035 max / 0.10 max*
0.05 max /0.10 max*
Rated Voltage
50V / 35V / 25V
16V
10V
6.3V
3. Characteristic : F(Y5V)
Spec
0.05 max /
0.07 max* / 0.09 max*
0.07 max /
0.09 max* / 0.125 max*
0.125 max /0.16 max*
0.16 max
Capaci
tance
10,000㏁min. or 500 ㏁ · ㎌min.(or*100㏁㎌)
product whichever is smaller
(Rated voltage16V:10,000㏁min. or100㏁㎌
min. product whichever is smaller)
Apply the rated voltage for 60~120 sec.
Ratedvoltage500V: InsulationResistance shall be
measured with 50050Vdc
Capacitance 30㎊: Q 1,000
30㎊: Q400 20C
(C : Capacitance)
CLASSⅠ
You can check the specification at the web site or contact sales
people for each product with mark*
* A capacitor prior to measuring the capacitance is heat
   treated at 150℃0/10℃ and maintained in ambient
   air for 242 hours.
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
※ The conditions of measurement may be altered upon request.

<!-- Page 54 -->

6
(1) CLASS
Temperature Coefficient shall be calculated from the formula as below
Temp. Coefficient =
C1: Capacitance at step 3
C2: Capacitance at 125℃
T: 100℃(=125℃25℃)
106[ppm/℃]
C2C1
C1T
(2) CLASS
Capacitance Change shall be calculated from the formula as below
C=
C1: Capacitance at step 3
C2: Capacitance at step 2 or 4
100(%)
C2C1
C1
CLASSⅠ
CLASSⅡ
Capacitance shall be measured by the steps shown in the following table.
Step
Temperature(℃)
25 2
Min. Operating Temp. 2
25 2
Max. Operating Temp. 2
25 2
1
2
3
4
5
Temperature
Characteristics
of Capacitance
Characteristic
C
Temp.Coefficient(PPM/℃)
0 30
Characteristic
A(X5R)/ B(X7R)
X(X6S), Y(X7S)
Z(X7T)
F(Y5V)
15%
22%
22%~33%
22%~82%
Capacitance Change(%)
with No bias
Appearance
Capacitance
500g.f
Test Condition
Bending
Strength
Adhesive Strength of
Termination
Item
No indication of peeling shall occur
No indication of peeling shall occur on the terminal
electrode
Performance
7
8
9
No
Apply 500g.f* pressure for 101 sec. *200g.f for 0201
*100g.f for 01005
30.3 sec.
Sn3Ag0.5Cu
2455℃
RMA Type
at 80~120℃for 10~30 sec.
Solder
Solder Temp.
Flux
Dip time
Pre-heating
Bending Limit: 1mm  Test Speed: 1.0mm/sec.
Keep the test board at the limit point in 5 sec.
Then Measure Capacitance
A(X5R), B(X7R),
X(X6S), Y(X7S)
Z(X7T)
12.5%
30%
F(Y5V)
A(X5R), B(X7R),
X(X6S), Y(X7S)
Z(X7T)
F(Y5V)
CLASSⅡ
Characteristic
CLASSⅠ
5% or  0.5 pF
whichever is  larger
Capacitance Change
20
50
451
451
Bending limit
R=230
Solderability
More than 75% of the terminal surface is to be soldered
newly, so metal part does not come out or dissolve
No mechanical damage shall occur
10
7.5%
20%
CLASSⅡ
Characteristic
CLASSⅠ
2.5% or  0.25 pF
whichever is  larger
Capacitance Change
Leave the capacitor in ambient condition for specified time* before
measurement
*24  2 hours(CLASSⅠ
24  2 hours(CLASSⅡ)
Solder temperature: 2705℃DIP TIME:101 sec.
Each termination shall be fully immersed and preheated as below:
Capacitance
Q
(CLASSⅠ
Tan
(CLASSⅡ)
Within the specified initial value
Within the specified initial value
Within the specified initial value
Insulation
resistance
Step
1
2
Temperature(℃)
80~100
150~180
Time (sec.)
60
60
Appearance
Resistance
to Soldering
Heat
Within the specified initial value
Withstanding
voltage

<!-- Page 55 -->

54
55
Test Condition
Item
Performance
No
11
A(X5R), B(X7R)
F(Y5V)
5%
20%
X(X6S), Y(X7S)
Z(X7T)
10%
Q
(CLASS)
Tan
(CLASSⅡ)
Within the specified initial value
Within the specified initial value
Insulation
resistance
No mechanical damage shall occur
Characteristic
CLASSⅡ
CLASSⅠ
2.5% or  0.25 pF
whichever is  larger
Capacitance Change
Capacitance
Appearance
The capacitor shall be subjected to a harmonic motion having a total
amplitude of 1.5mm changing frequency from 10Hz to 55Hz and
back to 10Hz in about 1 min.
Repeat this for 2hours each in 3 mutually perpendicular directions.
Vibration
Test
Within the specified initial value
Capacitance
Moisture
Resistance
12
Applied Voltage: rated voltage
Temperature: 402℃
Humidity: 90~95% RH
Duration Time: 50012/0 Hr.
Charge/Discharge Current: 50㎃max.
Perform the initial measurement according to Note1.
Perform the final measurement according to Note2.
Characteristic
12.5%
30%
CLASSⅡ
CLASSⅠ
7.5% or  0.75pF
whichever is  larger
Capacitance Change
Q
(CLASSⅠ
Tan
(CLASSⅡ)
Capacitance30㎊: Q200
30㎊: Q100+10/3C(C: Capacitance)
1.Capacitance: A(X5R)
0.05 max / 0.075 max* (35V / 50V)
0.05 max / 0.075 max* / 0.125 max*(16V / 25V)
0.075 max / 0.125 max* (10V)
2.Capacitance: B(X7R), X(X6S)
0.05 max / 0.125 max* (16V / 25V / 35V / 50V)
0.075 max / 0.125 max* (10V)
3.Capacitance: F(Y5V)
0.09 max (50V)
0.09 max / 0.125 max* (25V / 35V)
0.09 max / 0.125 max* / 0.16 max* (16V)
0.16 max / 0.195 max* (10V)
0.195 max (4V / 6.3V)
500㏁min. or 25㏁·㎌min.
product whichever is smaller / 12.5㏁·㎌or over*
Insulation
resistance
Appearance
No mechanical damage shall occur
A(X5R), B(X7R),
X(X6S), Y(X7S)
Z(X7T)
A(X5R), B(X7R),
X(X6S), Y(X7S)
Z(X7T)
F(Y5V)
This test is only applied to Vr500V products.
You can check the specification at the web site or contact sales people
for each product with mark*
You can check the specification at the web site or contact sales people
for each product with mark*
Capacitance
13
Characteristic
12.5%
30%
CLASSⅡ
CLASSⅠ
3% or  0.3 pF
whichever is  larger
Capacitance Change
Q
(CLASSⅠ
Tan
(CLASSⅡ)
Capacitance30㎊: Q350
10Capacitance30㎊: Q2752.5C
Capacitance10㎊: Q200+10C (C: Capacitance)
1.Capacitance : A(X5R)
0.05 max / 0.075 max* (35V / 50V)
0.05 max / 0.075 max* / 0.125 max*(16V / 25V)
0.075 max / 0.125 max* (10V)
2.Capacitance : B(X7R), X(X6S)
0.05 max / 0.125 max* (16V / 25V / 35V / 50V)
0.075 max / 0.125 max* (10V)
3.Capacitance : F(Y5V)
0.09 max (50V)
0.09 max / 0.125 max* (25V / 35V)
0.09 max / 0.125 max* / 0.16 max* (16V)
0.16 max / 0.195 max* (10V)
0.195 max (4V / 6.3V)
1,000㏁min. or 50㏁·㎌min.
product whichever is smaller / 25㏁·㎌or over*
Insulation
resistance
Appearance
No mechanical damage shall occur
F(Y5V)
Temperature : max. operating temperature
Duration Time: 100048/0 Hr.
Charge/Discharge Current: 50㎃max.
Vr200V : 200% of the rated Voltage
250VVr500V: 150% of the rated Voltage
Vr630V : 120% of the rated Voltage
1000VVr3000V: 100% of the rated Voltage
* :150%  or 100% of the rated Voltage
Perform the initial measurement according to Note1 for classⅡ
Perform the final measurement according to Note2.
High Temperature Resistance
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition

<!-- Page 56 -->

Test Condition
Item
Performance
No
Temperature Cycle
14
Capacitor shall be subjected to 5 cycles.
Condition for 1 cycle:
Leave the capacitor in ambient condition for specified time*before
measurenment
*24 2 hours(CLASSⅠ)
24 2 hours(CLASSⅡ)
Capacitance
Characteristic
7.5%
20%
15%
CLASSⅡ
CLASSⅠ
2.5% or 0.25pF
whichever is  larger
Capacitance Change
Appearance No mechanical damage shall occur
Q
(CLASSⅠ
Tan
(CLASSⅡ)
Within the specified initial value
Insulation
resistance
Within the specified initial value
Within the specified initial value
Temperature(℃)
min. operating
temperature 0/3
25
max. operating
temperature 0/3
25
Time(min.)
30
2~3
30
2~3
Step
1
2
3
4
A(X5R), B(X7R)
F(Y5V)
X(X6S), Y(X7S)
Z(X7T)
Recommended Soldering Method
By Size & Capacitance
15
No
Size
inch(mm)

Class Ⅰ
Class Ⅱ
Class Ⅰ
Class Ⅱ
Array
Class Ⅰ
Class Ⅱ
Array



C 1㎌
C 1㎌

C 4.7㎌
C 4.7㎌


C 10㎌
C 10㎌















Temperature
Characteristic
Capacitance
Condition
Flow
Reflow
















Recommended Soldering Method
01005(0402)
0201 (0603)
0402 (1005)
0603(1608)
0805 (2012)
1206 (3216)
1210 (3225)
1808 (4520)
1812 (4532)
2220 (5750)
Note 1. Initial Measurement For ClassⅡ
Perform the heat treatment at 150℃0/10℃for 1 hour. Then Leave the capacitor in ambient condition for 242 hours before measurement.
Then perform the measurement.
Note 2. Latter Measurement
1. CLASSⅠ
Leave the capacitor in ambient condition for 242 hours before measurement. Then perform the measurement.
2. CLASSⅡ
Perform the heat treatment at 150℃0/10℃for 1 hour. Then Leave the capacitor in ambient condition for 242 hours before measurement.
Then perform the measurement.
Note 3. All Size in Reliability Test Condition Section is “inch”
Note 4. Camera Strobe Circuit Capacitors Should be Following a Special Reliability Test Condition.
 Please check with our sales representatives or product engineers.

<!-- Page 57 -->

Premium Capacitors for Automotive Applications

<!-- Page 58 -->

CL     10       B     104      K       B       8        W       P        N       C
1      2       3       4       5      6       7      8       9     10     11
1. SERIES CODE
CL = Multi layer Ceramic Capacitors
4. CAPACITANCE CODE
Capacitance expressed in ㎊. 2 significant digits plus number of zeros.
example) 106 =10106=10000000㎊
For Values 10㎊, Letter R denotes decimal point
example) 1R5 = 1.5㎊
★
★★
★★★
This code has only typical specifications. Please refer to individual specifications.
inch(㎜)
2. SIZE CODE
05 = 1005(0402)       10 = 1608(0603)       21 = 2012(0805)
31 = 3216(1206)       32 = 3225(1210)
3. DIELECTRIC CODE
C = C0G (ClassⅠ)                B = X7R (ClassⅡ)
5. TOLERANCE CODE
C =0.25㎊D =0.5㎊
F =1㎊, 1%*   G =2%
J =5%         K =10%     M = 20%
*For  Values 10㎊, F =1㎊, Values    10㎊, F =1%
6.RATED VOLTAGE CODE
P = 10V     O = 16V
A = 25V      B = 50V     C = 100V
7.THICKNESS CODE
5 = 0.50㎜
6 = 0.60㎜
8 = 0.80㎜
C = 0.85㎜
P = 1.15㎜
F,Q = 1.25㎜
H = 1.60㎜
J = 2.50㎜
8. DESIGN CODE
1 = Ni / Cu / Ni Barrier / Sn 100% / Standard
V = Ni / Cu+Soft termination / Ni Barrier / Sn 100% / Standard
W = Ni / Cu+Soft termination / Ni Barrier / Sn 100% / Open Mode
9. PRODUCT CODE
P = Automotive product meet AEC-Q-200.
10. GRADE CODE
N = Standard
Part Numbering System (Automotive Capacitors)
Premium Capacitors for
Automotive Applications
This code has only typical specifications. Please refer to individual specifications.
This code has only typical specifications. Please refer to individual specifications.
If orders are placed without returned specification, please allow us to judge that specification is accepted by your side.
11. PACKAGING CODE
B = Bulk                                          O = Cardboard Tape, 10”Reel                               E = Embossed Type, 7”Reel
P = Bulk Case                                  D = Cardboard Tape, 13”Reel(10,000ea)             G = Embossed Type, 7”Reel(3,000ea)
C = Cardboard Tape, 7”Reel           L = Cardboard Tape, 13”Reel(15,000ea)              F = Embossed Type, 13”Reel
H = Cardboard Tape,7”Reel(15,000ea)                                                                        S = Embossed Type, 10”Reel







<!-- Page 59 -->

58
59
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
Class I
Symbol                             EIA Code
Operation Temperature Range(℃)
Symbol                             EIA Code
Operation Temperature Range(℃)
Temperature Coefficient Range(ppm/℃)
C0G
C
E-3
E-6
E-12
E-24
1.0
1.2
1.5
1.8
2.2
2.7
3.3
3.9
4.7
5.6
6.8
8.2
1.0
1.1
1.2
1.3
2.2
2.4
2.7
3.0
4.7
5.1
5.6
6.2
1.5
1.6
1.8
2.0
3.3
3.6
3.9
4.3
6.8
7.5
8.2
9.1
55~125
55~125
0 30
Class II
Capacitance Change(△℃%)
X7R
B
0 15
Series
Capacitance Step
0402(1005)
0603(1608)
0805(2012)
1206(3216)
1210(3225)
5
8
6
C
F
Q
C
P
H
0.50
0.80
0.60
0.85
1.25
1.25
0.85
1.15
1.60
0.05
0.10
0.10
0.10
0.10
0.15
0.15
0.10
0.20
I
J
2.00
2.50
0.20
0.20
Code
Size
★
★★★
C
D
J
K
M
0.25
0.5
5%
10%
20%
C0G
C0G
C0G
X7R
X7R
E-12 series ★
E-12 series ★
E-12 series
E-3 series
E-6 series
E-3 series
E-6 series
Under 5
6.0 to 9.0
Over 10
Under 0.01
Over 0.01
Under 0.01
Over 0.01
Code                   Capacitance Tolerance
Capacitance Tolerance
Capacitance  Step
TC
Rated Capacitance
★★
★
★E-24 series is also available
1.0
1.0
1.5
2.2
3.3
4.7
6.8
7.4
2.2
Thickness(mm)
Spec(mm)
㎊
㎊
㎊
㎊
㎊
㎌
㎌
㎌
㎌

<!-- Page 60 -->

L
BW
W
0.500.05
0.800.10
1.250.10
1.250.15
1.600.20
0.500.05)
0.800.10)
0.600.10)
0.850.10)
1.250.10)
1.250.15)
0.850.15)
1.150.10)
1.600.20)
1.000.05
1.600.10
2.000.10
2.000.15
3.200.20
0402
0603
0805
1206
0.250.10
0.300.20
0.600.30
0.500.30
0.50.2/0.3
05
10
21
31
2.500.20
2.000.20)
2.500.20)
3.200.30
1210
32
U Automotive products are manufactured in state of the art facilities
recommended for registration to ISO/TS 16949:2002.
U Automotive products meet AEC-Q-200 requirements.
U Automotive products are RoHS compliant.
U Samsung terminations are suitable for all flow and reflow soldering
systems. (10/21/31 size type only)
U Automotive products meet JEDEC-020-D requirements.
U C0G dielectric components contain BME and  copper
terminations with a Ni/Sn plated overcoat.
U X7R dielectric components have BME and soft
terminations with a Ni/Sn plated overcoat.
 Automotive Electronic Equipment
(Powertrain, Safety, Body & Chassis, Convenience, Infortainment)
Feature
Structure and Dimensions
Application
T
Code
EIA
Code
L                                   W                                  T                                  BW
Dimension(mm)
Premium Capacitors for
Automotive Applications

<!-- Page 61 -->

60
61
Automotive Capacitors Table (C0G, X7R)
COG
Capacitance
Capacitance
0402(1005)
0603(1608)
0805(2012)
0.50
0.80
0.60
0.85
1.25
50
100
50
100
50
100
0.50
0.80
1.25
0.85
1.25
0.60
0.85
1.25
0.60
0.85
1.25
0.60
0.85
1.25
1.60
1.15
1.60
0.85
1.15
1.60
0.85
1.15
1.60
2.70
10
16
25
50
10
16
25
50
100
10
16
25
50
100
10
16
25
50
16
100     220      470        1        2.2       4.7       10        22        47
100
X7R
TC
Thickness
(mm)
(mm)
Vr
Size
TC
Thickness
(mm)
(mm)
Vr
Size
0402(1005)
0603(1608)
0805(2012)
1206(3216)
3225(1210)
10        22       47     100     220     470       1       2.2       4.7      10       22
271
(㎊)
(㎋)
Capacitance
Capacitance(㎌)
(㎋)
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition

<!-- Page 62 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Automotive Capacitors-COG)
CL05C4R7CB51PN
CL05C4R7CC51PN
CL05C6R8DB51PN
CL05C6R8DC51PN
CL05C100JB51PN
CL05C100JC51PN
CL05C120JB51PN
CL05C120JC51PN
CL05C150JB51PN
CL05C150JC51PN
CL05C180JB51PN
CL05C180JC51PN
CL05C220JB51PN
CL05C220JC51PN
CL05C270JB51PN
CL05C270JC51PN
CL05C330JB51PN
CL05C330JC51PN
CL05C390JB51PN
CL05C390JC51PN
CL05C470JB51PN
CL05C470JC51PN
CL05C560JB51PN
CL05C560JC51PN
CL05C680JB51PN
CL05C680JC51PN
CL05C820JB51PN
CL05C820JC51PN
CL05C101JB51PN
CL05C101JC51PN
CL05C121JB51PN
CL05C151JB51PN
CL05C221JB51PN
CL10C4R7CB81PN
CL10C4R7CC81PN
CL10C6R8DB81PN
CL10C6R8DC81PN
CL10C100JB81PN
CL10C100JC81PN
CL10C120JB81PN
CL10C120JC81PN
CL10C150JB81PN
CL10C150JC81PN
CL10C180JB81PN
CL10C180JC81PN
CL10C220JB81PN
CL10C220JC81PN
CL10C270JB81PN
CL10C270JC81PN
CL10C330JB81PN
4.7
4.7
6.8
6.8
10
10
12
12
15
15
18
18
22
22
27
27
33
33
39
39
47
47
56
56
68
68
82
82
100
100
120
150
220
4.7
4.7
6.8
6.8
10
10
12
12
15
15
18
18
22
22
27
27
33
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
1.000.50
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
50
50
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
0.25㎊
0.25㎊
0.5㎊
0.5㎊
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
0.25㎊
0.25㎊
0.5㎊
0.5㎊
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%

















































5%
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
1.600.80
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 63 -->

62
63
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Automotive Capacitors-COG)
CL10C330JC81PN
CL10C390JB81PN
CL10C390JC81PN
CL10C470JB81PN
CL10C470JC81PN
CL10C560JB81PN
CL10C560JC81PN
CL10C680JB81PN
CL10C680JC81PN
CL10C820JB81PN
CL10C820JC81PN
CL10C101JB81PN
CL10C101JC81PN
CL10C121JB81PN
CL10C151JB81PN
CL10C221JB81PN
CL10C221JC81PN
CL10C271JB81PN
CL10C331JB81PN
CL10C391JB81PN
CL10C471JB81PN
CL10C561JB81PN
CL10C681JB81PN
CL10C821JB81PN
CL10C102JB81PN
CL21C100JB61PN
CL21C100JC61PN
CL21C120JB61PN
CL21C120JC61PN
CL21C150JB61PN
CL21C150JC61PN
CL21C180JB61PN
CL21C180JC61PN
CL21C220JB61PN
CL21C220JC61PN
CL21C270JC61PN
CL21C330JB61PN
CL21C330JC61PN
CL21C390JB61PN
CL21C390JC61PN
CL21C470JB61PN
CL21C470JC61PN
CL21C560JB61PN
CL21C560JC61PN
CL21C680JB61PN
CL21C680JC61PN
CL21C820JB61PN
CL21C820JC61PN
CL21C101JB61PN
CL21C101JC61PN
33㎊
39㎊
39㎊
47㎊
47㎊
56㎊
56㎊
68㎊
68㎊
82㎊
82㎊
100㎊
100㎊
120㎊
150㎊
220㎊
220㎊
270㎊
330㎊
390㎊
470㎊
560㎊
680㎊
820㎊
1.0㎋
10㎊
10㎊
12㎊
12㎊
15㎊
15㎊
18㎊
18㎊
22㎊
22㎊
27㎊
33㎊
33㎊
39㎊
39㎊
47㎊
47㎊
56㎊
56㎊
68㎊
68㎊
82㎊
82㎊
100㎊
100㎊
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
1.600.80
100
50
100
50
100
50
100
50
100
50
100
50
100
50
50
50
100
50
50
50
50
50
50
50
50
50
100
50
100
50
100
50
100
50
100
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%

















































5%
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
2.001.25
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition

<!-- Page 64 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Automotive Capacitors-COG)
CL21C121JB61PN
CL21C121JC61PN
CL21C151JB61PN
CL21C151JC61PN
CL21C221JB61PN
CL21C221JC61PN
CL21C271JB61PN
CL21C271JC61PN
CL21C331JB61PN
CL21C331JC61PN
CL21C471JBC1PN
CL21C471JCC1PN
CL21C561JBC1PN
CL21C561JCC1PN
CL21C681JBC1PN
CL21C681JCC1PN
CL21C821JBC1PN
CL21C821JCC1PN
CL21C102JBF1PN
CL21C102JBC1PN
CL21C102JCF1PN
CL21C102JCC1PN
CL21C122JBF1PN
CL21C122JBC1PN
CL21C152JBF1PN
CL21C152JBC1PN
CL21C182JBF1PN
CL21C182JBC1PN
CL21C222JBF1PN
CL21C222JBC1PN
CL21C272JBF1PN
CL21C272JBC1PN
CL21C332JBF1PN
CL21C332JBC1PN
CL21C392JBF1PN
CL21C392JBC1PN
CL21C472JBF1PN
CL21C472JBC1PN
CL21C562JBF1PN
CL21C562JBC1PN
CL21C682JBF1PN
CL21C822JBF1PN
CL21C103JBF1PN
120
120
150
150
220
220
270
270
330
330
470
470
560
560
680
680
820
820
1.0
1.0
1.0
1.0
1.2
1.2
1.5
1.5
1.8
1.8
2.2
2.2
2.7
2.7
3.3
3.3
3.9
3.9
4.7
4.7
5.6
5.6
6.8
8.2
10
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎊
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
2.001.25
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
50
100
100
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
50
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
5%
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.95
0.95
0.95
0.95
0.95
0.95
0.95
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
0.95
1.35
1.35
1.35
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 65 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
64
65
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
Product Lineup (Automotive Capacitors-X7R)
CL05B331KB5VPN
CL05B471KB5VPN
CL05B681KB5VPN
CL05B102KA5VPN
CL05B102KB5VPN
CL05B152KA5VPN
CL05B152KB5VPN
CL05B222KA5VPN
CL05B222KB5VPN
CL05B332KA5VPN
CL05B332KB5VPN
CL05B472KA5VPN
CL05B472KB5VPN
CL05B682KA5VPN
CL05B682KB5VPN
CL05B103KA5VPN
CL05B103KB5VPN
CL05B153KA5VPN
CL05B153KB5VPN
CL05B223KA5VPN
CL05B223KB5VPN
CL05B333KO5VPN
CL05B473KO5VPN
CL05B683KO5VPN
CL05B104KO5VPN
330㎊
470㎊
680㎊
1.0㎋
1.0㎋
1.5㎋
1.5㎋
2.2㎋
2.2㎋
3.3㎋
3.3㎋
4.7㎋
4.7㎋
6.8㎋
6.8㎋
10㎋
10㎋
15㎋
15㎋
22㎋
22㎋
33㎋
47㎋
68㎋
100㎋
1.000.50
50
50
50
25
50
25
50
25
50
25
50
25
50
25
50
25
50
25
50
25
50
16
16
16
16
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
0.55
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition

<!-- Page 66 -->

※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
Product Lineup (Automotive Capacitors-X7R)
CL10B221KC8WPN
CL10B331KC8WPN
CL10B471KC8WPN
CL10B681KC8WPN
CL10B102KB8WPN
CL10B102KC8WPN
CL10B152KB8WPN
CL10B152KC8WPN
CL10B222KB8WPN
CL10B222KC8WPN
CL10B332KB8WPN
CL10B332KC8WPN
CL10B472KB8WPN
CL10B472KC8WPN
CL10B682KB8WPN
CL10B682KC8WPN
CL10B103KB8WPN
CL10B103KC8WPN
CL10B153KB8WPN
CL10B223KB8WPN
CL10B333KA8WPN
CL10B333KB8WPN
CL10B473KA8WPN
CL10B473KB8WPN
CL10B683KA8WPN
CL10B683KB8WPN
CL10B104KA8WPN
CL10B104KB8WPN
CL10B154KO8VPN
CL10B154KA8VPN
CL10B224KO8VPN
CL10B224KA8VPN
CL10B334KO8VPN
CL10B334KA8VPN
CL10B474KO8VPN
CL10B474KA8VPN
CL10B684KO8VPN
CL10B105KO8VPN
220
330
470
680
1.0
1.0
1.5
1.5
2.2
2.2
3.3
3.3
4.7
4.7
6.8
6.8
10
10
15
22
33
33
47
47
68
68
100
100
150
150
220
220
330
330
470
470
680
1.0
㎊
㎊
㎊
㎊
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎌
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
1.600.80
100
100
100
100
50
100
50
100
50
100
50
100
50
100
50
100
50
100
50
50
25
50
25
50
25
50
25
50
16
25
16
25
16
25
16
25
16
16
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
0.90
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%





































10%
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)

<!-- Page 67 -->

66
67
Product Lineup (Automotive Capacitors-X7R)
CL21B102KC6WPN
CL21B152KC6WPN
CL21B222KC6WPN
CL21B332KC6WPN
CL21B472KC6WPN
CL21B682KC6WPN
CL21B103KC6WPN
CL21B153KC6WPN
CL21B223KC6WPN
CL21B333KCCWPN
CL21B473KCCWPN
CL21B683KCCWPN
CL21B104KBFWPN
CL21B104KBCWPN
CL21B104KCFWPN
CL21B104KCCWPN
CL21B154KAFVPN
CL21B154KBFVPN
CL21B224KAFVPN
CL21B224KBFVPN
CL21B334KAFVPN
CL21B334KBFVPN
CL21B474KOFVPN
CL21B474KAFVPN
CL21B474KBFVPN
CL21B684KOFVPN
CL21B684KAFVPN
CL21B105KOFVPN
CL21B105KAFVPN
CL21B225KPFVPN
CL21B225KOFVPN
CL21B335KPQVPN
CL21B475KPQVPN
CL31B104KBPWPN
CL31B104KBCVPN
CL31B154KBPWPN
CL31B224KBPWPN
CL31B334KBHWPN
CL31B474KBHWPN
CL31B684KBHWPN
CL31B105KAPWPN
CL31B105KBHWPN
CL31B155KAHVPN
CL31B155KBHVPN
CL31B225KOHVPN
CL31B225KAHVPN
CL31B225KBHVPN
CL31B335KOHVPN
CL31B335KAHVPN
CL31B475KOHVPN
CL31B475KAHVPN
1.0
1.5
2.2
3.3
4.7
6.8
10
15
22
33
47
68
100
100
100
100
150
150
220
220
330
330
470
470
470
680
680
1.0
1.0
2.2
2.2
3.3
4.7
100
100
150
220
330
470
680
1.0
1.0
1.5
1.5
2.2
2.2
2.2
3.3
3.3
4.7
4.7
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎌
㎌
㎌
㎌
㎌
㎌
㎋
㎋
㎋
㎋
㎋
㎋
㎋
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
㎌
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
1
2.001.25
100
100
100
100
100
100
100
100
100
100
100
100
50
50
100
100
25
50
25
50
25
50
16
25
50
16
25
16
25
10
16
10
10
50
50
50
50
50
50
50
25
50
25
50
16
25
50
16
25
16
25
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.70
0.95
0.95
0.95
1.35
0.95
1.35
0.95
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.35
1.40
1.40
1.25
1.00
1.25
1.25
1.80
1.80
1.80
1.25
1.80
1.80
1.80
1.80
1.80
1.80
1.80
1.80
1.80
1.80
3.201.60
3.202.50
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%
10%





















































10%
※
mark means packaging code. If you want to learn the code or quantity in detail, please see p74.
CL31B685KOHVPN
CL31B106KOHVPN
6.8
22
10.0
16
16
16
1.80
1.80
2.70
10%
10%
10%
Part Number
Thickness
Max.(mm)
Rated
Voltage
(Vdc)
Capacitance
Tolerance
Capacitance
Size L x W
(mm)
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
CL32B226KOJVPN

<!-- Page 68 -->

※*1) : Indicates typical specification. Please refer to individual specifications.
Reliability Test Condition (Automotive Capacitors)
Test Condition
Q
Tan
High Temperature
Exposure
Appearance
Capacitance
Change
Pre-and Post-Stress
Electrical Test
Destructive Physical
Analysis
Item
No abnormal exterior appearance
No defects or abnormalities
Within 10%
Within 2.5% or 0.25    ,
(Whichever is larger)
More than 10,000
or 500
(Whichever is smaller)

Performance
1
2
4
No
CLASSⅡ
CLASSⅡ
Unpowered, 1000hrs@T=125℃
Measurement at 242hrs after test conclusion
Capacitance 30㎊
㎊
: Q 1,000
30㎊: Q 400 20

C
( C : Capacitance)
Rated Voltage  25V : 0.03 max
16V : 0.05 max
10V : 0.075 max
CLASSⅠ
CLASSⅠ
IR
Q
Tan
Temperature
Cycling
Appearance
Capacitance
Change
No abnormal exterior appearance
Within 10%
Within 2.5% or 0.25pF,
(Whichever is larger)
More than 10,000
or 500
(Whichever is smaller)
3
CLASSⅡ
CLASSⅡ
1000Cycles
Measurement at 242hrs after test conclusion
10Cycles, t=24hrs/cycle
Heat (25~65℃) and humidity (80~98%), Unpowered
measurement at 242hrs after test conclusion
Capacitance 30㎊: Q 1,000
30㎊: Q 400 20C
( C : Capacitance)
Rated Voltage 25V : 0.03 max
16V : 0.05 max
10V : 0.075max
CLASSⅠ
CLASSⅠ
IR
Q
Tan
Moisture Resistance
Appearance
Capacitance
Change
No abnormal exterior appearance
Within 12.5%
Within2.5% or 0.25pF,
(Whichever is larger)
More than 10,000
or 500
(Whichever is smaller)
5
CLASSⅡ
CLASSⅡ
Capacitance  30㎊: Q 350
10Capacitance30㎊: Q275(5/2)C
Capacitance10㎊: Q 20010C
( C : Capacitance)
Rated Voltage  25V : 0.03 max
 16V : 0.05 max
 10V : 0.075max
CLASSⅠ
CLASSⅠ
IR
Per EIA 469
Time[Hours]
Temperature(℃)
Min. operating
Temp.2
252
Max. operating
Temp. 2
252
Time(min.)
153
1
153
1
Step
1
2
3
4
90~100%
RH
90~100%
RH
90~100%
RH
80~100%
RH
80
75
70
65
60
55
50
45
40
35
30
25
20
15
10
5
0 0   1    2    3    4   5    6    7   8   9  10  1112  13  14  15  16 17 18  19  20  21  22  23  24
*1)
*1)
*1)
*1)
*1)
*1)
㏁
㏁
㎌

㏁
㏁
㎌

㏁
㏁
㎌
Initial Measurement
Perform a heat treatment at 1500/10℃ for 1hr after
soldering process. And then let sit for 242hrs at room
temperature. Perform the initial measurement.
Final Measurement
Let sit for 242hrs at room temperature after test conclusion,
then measure.
Initial Measurement
Perform a heat treatment at 1500/10℃  for 1hr after
soldering process. And then let sit for 242hrs at room
temperature. Perform the initial measurement.
Final Measurement
Let sit for 242hrs at room temperature after test conclusion,
then measure.

<!-- Page 69 -->

68
69
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
※*1) : Indicates typical specification. Please refer to individual specifications.
*2) : Some of the parts are applicable in rated voltagex150%, Please refer to individual specifications.
*1)
*1)
*1)
*1)
*1)
*1)
Test Condition
Item
Performance
No
Q
Tan
Biased Humidity
Appearance
Capacitance
Change
No abnormal exterior appearance
Within 12.5%
Within 2.5% or 0.25pF,
(Whichever is larger)
More than 500
or 25
(Whichever is Smaller)
6
CLASSⅡ
CLASSⅡ
Capacitance 30㎊: Q 200
30㎊: Q 100(10/3)C
( C : Capacitance)
Rated Voltage  25V : 0.035 max
 16V : 0.05 max
 10V : 0.075max
CLASSⅠ
CLASSⅠ
IR
Q
Tan
Mechanical Shock
Appearance
Capacitance
Change
No abnormal exterior appearance
Within 10%
Within 2.5% or 0.25pF,
(Whichever is larger)
More than 10,000
or 500
(Whichever is smaller)
10
CLASSⅡ
CLASSⅡ
Three shocks in each direction should be applied along
3 mutually perpendicular axes of the test specimen (18 shocks)
Capacitance 30㎊: Q 1,000
30㎊: Q 400 20C
( C : Capacitance)
Rated Voltage  25V : 0.025 max
 16V : 0.035 max
 10V : 0.05 max
CLASSⅠ
CLASSⅠ
IR
Q
Tan
High Temperature
Operating Life
External Visual
Physical Dimensions
Appearance
Capacitance
Change
No abnormal exterior appearance
No abnormal exterior appearance
Microscope (x10)
Within the specified dimensions
Using the calipers
Within 12.5%
Within 3.0% or 0.3pF,
(Whichever is larger)
More than 1,000
or 50
(Whichever is smaller)
7
8
9
CLASSⅡ
CLASSⅡ
Capacitance 30㎊: Q 350
10㎊: Q275(5/2)C
10㎊: Q20010C
( C : Capacitance)
Rated Voltage 25V : 0.035 max
16V : 0.05 max
10V : 0.075max
CLASSⅠ
CLASSⅠ
IR
Peakvalue
1,500G
Duration
0.5ms
Wave
Half sine
1000hrs @ TA=125℃, 200% Rated Voltage,*2)

㏁
㏁
㎌

㏁
㏁
㎌

㏁
㏁
㎌
1000hrs 85℃/85%RH, Rated Voltate and 1.3~1.5V,
(add 100kohm resistor)
Initial Measurement
Perform a heat treatment at 1500/10℃ for 1hr after
soldering process. And then let sit for 242hrs at room
temperature. Perform the initial measurement.
Final measurement
Perform a heat treatment at 1500/10℃ for 1hr
after soldering process. And then let sit for 242hrs at room
temperature. Perform the initial measurement.
Perform the initial measurement.
Measurement at 242hrs after test conclusion
The charge/discharge current is less than 50mA
Initial Measurement
Perform a heat treatment at 1500/10℃ for 1hr after
soldering process. And then let sit for 242hrs at room
temperature. Perform the initial measurement.
Final measurement
Perform a heat treatment at 1500/10℃ for 1hr after
soldering process. And then let sit for 242hrs at room
temperature. Perform the initial measurement.
Perform the initial measurement.
Measurement at 242hrs after test conclusion
The charge/discharge current is less than 50mA.
Initial Measurement
Perform a heat treatment at 1500/10℃ for 1hr after
soldering process. And then let sit for 242hrs at room
temperature. Perform the initial measurement.
Final measurement
Let measure within 24hrs at room temperature after
test conclusion.

<!-- Page 70 -->

Test Condition
Item
Performance
No
Q
Tanδ
Vibration
Appearance
Capacitance
Change
No abnormal exterior appearance
Within ±10%
Within±2.5% or 0.25pF,
(Whichever is larger)
More than 10,000
or 500
(Whichever is smaller)
11
CLASSⅡ
CLASSⅡ
5g's for 20min., 12cycles each of 3 orientations,
Use 8" 5" PCB 0.031" Thick 7 secure points on one long side
and 2 secure points at corners of opposite sides. Parts mounted
within 2" from any secure point. Test from 10~2000
.
Solder pot : 260±5℃, 10±1sec.
Capacitance ≥30㎊: Q ≥1,000
＜30㎊: Q ≥400+20×
×
C
( C : Capacitance)
Rated Voltage ≥25V : 0.025 max
≥16V : 0.035 max
≥
㎐
×㎌
㏁
㏁
×㎌
㏁
㏁
×㎌
㏁
㏁
×㎌
㏁
㏁
10V : 0.05max
CLASSⅠ
CLASSⅠ
IR
Q
Tanδ
Resistance to
Solder Heat
Appearance
Capacitance
Change
No abnormal exterior appearance
Within ±10%
Within ±2.5% or 0.25pF,
(Whichever is larger)
More than 10,000
or 500
(Whichever is smaller)
12
CLASSⅡ
CLASSⅡ
Capacitance ≥30㎊: Q ≥1,000
＜30㎊: Q ≥400+20×C
(C : Capacitance)
Rated Voltage ≥25V : 0.025 max
≥16V : 0.035 max
≥10V : 0.05max
CLASSⅠ
CLASSⅠ
IR
Q
Tanδ
Thermal Shock
Appearance
Capacitance
Change
No abnormal exterior appearance
Within ±10%
Within ±2.5% or 0.25pF,
(Whichever is larger)
More than 10,000
or 500
(Whichever is smaller)
13
CLASSⅡ
CLASSⅡ
-55℃/+125℃
Note: Number of cycles required-300,
Maximum transfer time-20 sec,
Dwell time-15min. Air-Air
AEC-Q200-002
Capacitance ≥30㎊: Q ≥1,000
＜30㎊: Q ≥400+20×C
(C : Capacitance)
Rated Voltage ≥25V : 0.025 max
≥16V : 0.035 max
≥10V : 0.05max
CLASSⅠ
CLASSⅠ
IR
Q
Tanδ
ESD
Appearance
Capacitance
Change
No abnormal exterior appearance
Within ±10%
Within±2.5% or 0.25pF,
(Whichever is larger)
More than 10,000
or 500
(Whichever is smaller)
14
CLASSⅡ
CLASSⅡ
Capacitance ≥30㎊: Q ≥1,000
＜30㎊: Q ≥400+20×C
(C : Capacitance)
Rated Voltage ≥25V : 0.025 max
≥16V : 0.035 max
≥10V : 0.05max
CLASSⅠ
CLASSⅠ
IR
※*1) : Indicates typical specification. Please refer to individual specifications.
*1)
*1)
*1)
*1)
*1)
*1)
*1)
*1)
Initial Measurement
Perform a heat treatment at 150+0/-10℃ for 1hr after
soldering process. And then let sit for 24±2hrs at room
temperature. Perform the initial measurement.
Final measurement
Let measure within 24hrs at room temperature after
test conclusion.
Initial Measurement
Perform a heat treatment at 150+0/-10℃ for 1hr after
soldering process. And then let sit for 24±2hrs at room
temperature. Perform the initial measurement.
Final Measurement
Let sit for 24±2hrs at room temperature after test conclusion,
then measure.
Initial Measurement
Perform a heat treatment at 150+0/-10℃  for 1hr after
soldering process. And then let sit for 24±2hrs at room
temperature. Perform the initial measurement.
Final measurement
Perform a heat treatment at 150+0/-10℃ for 1hr after
soldering process. And then let sit for 24±2hrs at room
temperature. Perform the initial measurement.
Perform the initial measurement.

<!-- Page 71 -->

70
71
×㎌
㏁
㏁
×㎌
㏁
㏁
×㎌
㏁
㏁
×㎌
㏁
㏁
Test Condition
Q
Tanδ
Electrical
Characterization
Capacitance
Solderability
Item
Within specified tolerance
No abnormal exterior appearance
No dielectric breakdown or mechanical
breakdown
No abnormal exterior appearance
More than 100,000
or 1,000
(Whichever is smaller)
More than 10,000
or 500
(Whichever is smaller)
More than 10,000
or 100
(Whichever is smaller)
More than 1,000
or 10
(Whichever is smaller)
I.R. should be measured with a DC voltage not exceeding
Rated Voltage @25℃, @125℃for  60~120 sec.
Dielectric Strength : 250% of the rated voltage for 1~5 seconds
The charge/discharge current is less than 50mA.
a) Preheat at 155℃for 4 hrs, Immerse in solder for 5s at 235±5℃
b) Steam aging for 8 hrs, Immerse in solder for 5s at 235±5℃
c) Steam aging for 8 hrs, Immerse in solder for 120s at 260±
±
±
±
±
±
㎒
↓
↓
↑
↑
㎑
㎑
㎌
㎌
㎐
±
±
5℃
solder : a solution ethanol and rosin
Beam speed
Chip Length
2.5
, 0.5±0.05
/sec
Chip Length ≥3.2
, 2.5±0.25
/sec
Bending to the limit for 60 seconds
Limit : ClassⅠ-3mm
18N, for 60±1 sec.
* 0603(1608) -10N,
Performance
15
16
18
No
CLASSⅡ
CLASSⅡ
95% of the terminations is to be soldered
evenly and continuously
Capacitance ≥30㎊: Q ≥1,000
＜30㎊: Q ≥400+20×C
( C: Capacitance)
Rated Voltage≥25V : 0.025 max
≥16V : 0.035 max
≥10V : 0.05max
CLASSⅠ
CLASSⅠ
CLASSⅡ
CLASSⅠ
CLASSⅡ
CLASSⅠ
CLASSⅡ
CLASSⅠ
CLASSⅡ
CLASSⅠ
CLASSⅠ
CLASSⅠ
Board Flex
Terminal
Strength(SMD)
IR@25℃
IR@125℃
17
Dielectric Strength
Appearance
Appearance
Beam Load
Capacitance
Temperature
Characteristics
19
20
Destruction value should be exceed
Chip Length
2.5
a) Chip Thickness   0.5
: 20N
b) Chip Thickness
0.5
: 8N
Chip Length ≥
≤
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
㎜
≤
≤
＜
3.2
a) Chip Thickness ≥1.25
: 54.5N
b) Chip Thickness＜1.25
: 15N
Capacitance
Change
Capacitance
Change
Capacitance
Change
Capacitance
Drift
Temperature
Coefficient
Within ±5.0% or 0.5pF,
(Whichever is larger)
Within ±2.5% or 0.25pF,
(Whichever is larger)
Within  ±0.2% or 0.05pF,
(Whichever is larger)
Within ±10%
Within ±10%
Within ±15%
0±30 ppm/℃
0±30 ppm/℃
Class
ClassⅠ
ClassⅡ
Capacitance
1000pF
1000pF
10
10
Frequency
1
10%
1
10%
1
10%
120
20%
Vrms
0.5~5Vrms
1.0
0.2Vrms
1.0
0.2Vrms
0.5
0.1Vrms
Step
Temperature(℃)
25 ± 2
Min. Operating Temp. ±2
25 ± 2
Max. Operating Temp. ±2
25 ± 2
1
2
3
4
5
※*1) : Indicates typical specification. Please refer to individual specifications.
*1)
*If you want more detaiedl imformation, Please Visit Samsung Electro-mechanics website ( www.semlcr.com )
Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
The Capacitance /D.F. should be measured at 25℃,
*A capacitor prior to measuring the capacitance is heat
  treated at 150+0/-10℃ and maintained in ambient air for
  24±2hrs.
Initial measurement
Perform a heat treatment at 150+0/-10℃ for one hour after
soldering process. And then let sit for 24±2hrs at room
temperature. Perform the initial measurement.
The figure indicates typical specification.
Please refer to individual specifications
Initial Measurement
Perform a heat treatment at 150+0/-10℃ for 1hr after
soldering process. And then let sit for 24±2hrs at room
temperature. Perform the initial measurement.
Final measurement
Let measure within 24hrs at room temperature after test
conclusion.
Initial Measurement
Perform a heat treatment at 150+0/-10℃ for 1hr after
soldering process. And then let sit for 24±2hrs at room
temperature. Perform the initial measurement.
Final measurement
Let measure within 24hrs at room temperature after test
conclusion.
Class Ⅱ- 3mm
 0402(1005) -2N

<!-- Page 72 -->

2.0
±0.05
1.3
±0.2
1.1
±0.2
1.6
±0.2
2.0
±0.2
1.7
±0.2
1.9
±0.2
2.4
±0.2
3.6
±0.2
8.0
±0.3
3.5
±0.05
1.75
±0.1
4.0
±0.1
Ø1.5
+0.1/-0
1.1
Below
4.0
±0.1
Feeding Hole
Chip inserting Hole
P2
P0
t
Unit: inch(mm)
0603    0306
(1608)  (0816)
0504
(1410)
0805    0508
(2012)  (1220)
1206    0612
(3216)  (1632)
Type
Dimension
Symbol
A                 B               W               F                 E                P1               P2                P0                D                 t
Unit: inch(mm)
01005
(0402)
0.45
±0.02
0.25
±0.02
Type
Dimension
Symbol
A                 B                 W                 F                 E                  P1                P2               P0                 D                 t
E
F W
P1
D
2.0
±0.05
0.37
±0.03
0.37
±0.05
0.60
±0.05
0.37
±0.03
8.0
±0.3
3.5
±0.05
1.75
±0.1
4.0
±0.1
Ø1.5
+0.1
0.03
2.0
±0.05
Feeding Hole
Chip inserting Hole
P2
P0
t
E
F
W
A
B
P1
D
Cardboard Paper Tape(4mm)
Cardboard Paper Tape(2mm)
Packaging
Specifications
0201
(0603)
0402
(1005)
0204
(0510)
0.25
±0.02
0.38
±0.03
0.62
±0.05
0.62
+0.05
0.10
0.68
±0.03
1.12
±0.05
1.12
+0.05
/-
/-
/-
0.10
B
A

<!-- Page 73 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
72
73
Peeling off of Cover Tape
Embossed Plastic Tape
Unit: inch(mm)
01005
(0402)
0603
(1608)
0805
(2012)
1206
(3216)
1210
(3225)
1808
(4520)
1812
(4532)
2220
(5750)
0204
(5010)
0306
(0816)
0508
(1220)
0612
(1632)
1.05
±0.15
1.45
±0.2
1.9
±0.2
2.8
±0.2
2.3
±0.2
3.6
±0.2
5.5
±0.2
0.62
+0.05
/- 0.10
1.1
±0.2
1.45
±0.2
2.0
±0.2
0.25
±0.02
0.45
±0.02
4.0
±0.05
1.8
±0.02
0.9
±0.05
1.0
±0.02
1.0
±0.02
2.0
±0.04
Ø0.8
±0.04
0.25
±0.02
0.5
max
1.9
±0.15
2.3
±0.2
3.5
±0.2
3.6
±0.2
4.9
±0.2
4.9
±0.2
6.2
±0.2
1.12
+0.05
- /0.10
1.9
±0.2
2.3
±0.2
3.6
±0.2
Type
Dimension
Symbol
A
B
W
F
E
P1
P2
P0
D
t1
t0
12.0
±0.3
8.0
±0.3
5.60
±0.05
3.5
±0.05
1.75
±0.1
8.0
±0.1
0.8
±0.3
3.5
±0.05
4.0
±0.1
4.0
±0.1
2.0
±0.05
4.0
±0.1
Ø1.5
+0.1/
- 0.03
3.8
max
2.5
max
2.9
max
0.6
Below
Feeding Hole
Chip Inserting Hole
P2
P0
t0
E
F W
A
t1
B
P1
D
Cover Tape
Cover Tape’s  Pulling Strength
300mm / min
Paper or Plastic Tape
Unreeling Direetion
165~180。
•10 g.f≤Peel off force ≤70 g.f

<!-- Page 74 -->

Taping Size
Empty Section 200mm
Empty Section 280mm
Loading Section
240mm
Start
END
Packed Part
•The chip is only use for identifying the label and packaged products.
Please don’t use the chip.
2
3
3
5
8
5
8
D
A, C
E, F, Q
C
E, F, P
H
9, D, C, O
E, F, M
H, T
I, U
J, V
S
F
F, H, I
L, J
H, I, J
20
10
10
10
4
4
4
-
4
-
4
-
-
-
-
-
-
-
-
-
-
-
-
100
50
50
50
10
10
10
-
10
-
10
-
-
-
-
-
-
-
-
-
-
-
-
50
-
-
40
15
-
15
-
15
-
15
-
-
-
-
-
-
-
-
-
-
-
-
50
-
-
-
-
-
3
3
-
2
-
2
2
2
2
2
2
1
2
2
1
-
-
-
-
-
-
-
-
-
-
-
3
-
3
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
10
-
10
-
10
8
10
10
8
4
4
8
-
4
2
2
-
-
-
-
-
-
-
6
-
6
-
6
4
-
-
4
-
-
-
-
-
-
-
-
30
30
30
10
10
10
-
10
-
10
-
-
-
-
-
-
-
-
-
-
-
-
-
15
15
15
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
01005(0402)
0201(0603)
0402(1005)
0504(1410)
0603(1608)
0604(1610)
0805(2012)
1206(3216)
1210(3225)
1808(4520)
1812(4532)
2220(5750)
Cardboard Paper Type
Embossed Plastic Type
C
(7”reel)
-
-
-
8
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
8
(7”reel)
H
(7”reel)
O
(10”reel)
D
(13”reel)
L
(13”reel)
E
(7”reel)
G
(7”reel)
F
(13”reel)
S
(10”reel)
Size
T code
Quantity & Packing Code
Unit: kpcs

<!-- Page 75 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
74
75
•QUANTITY
0805(2012)
T≥1.0mm
T≤0.85mm
0603(1608)
0402(1005)
5,000
10,000
10,000 or 15,000
50,000
Quantity
Size
L
F
H
W
G
T
B
A
C
D
E
I
•Bulk case packaging can reduce the stock space and transportation costs.
•The bulk feeding system can increase the productivity.
•It can eliminate the components loss.
A
B
T
C
D
E
Dimension
6.8±0.1
3.0+0.2/-0
2+0/- 0.1
1.5+0.1/- 0
12±0.1
8.8±0.1
Symbol
Unit: inch(mm) and pcs
Unit: mm
F
W
G
H
L
I
Dimension
31.5+0.2/- 0
5±0.35
110±0.7
7±0.35
19±0.35
36+0/- 0.2
Symbol
E
C
C B
A
D
W
t
Unit: mm
Tape Width               A
B
C
D
Symbol
7" Reel
10" Reel
13" Reel
8mm
12mm
8mm
12mm
8mm
12mm
Ø180+0/-3
Ø180+0/-3
Ø258+0/-3
Ø258+0/-3
Ø330±2.0
Ø330±2.0
Ø60±1.0
Ø60+1/-0
Ø80+1/-0
Ø80+1/-0
Ø80±1.0
Ø80±1.0
Ø13±0.3
Ø13±0.3
Ø13±0.3
Ø13±0.3
Ø13±0.3
Ø13±0.3
4±0.2
4±0.2
4±0.2
4±0.2
4±0.2
4±0.2
Tape Width                     E
W
t
Symbol
7" Reel
10" Reel
13" Reel
8mm
12mm
8mm
12mm
8mm
12mm
2.0±0.5
2.0±0.5
2.0±0.5
2.0±0.5
2.0±0.5
2.0±0.5
9±0.5
13±0.5
9±0.5
13±0.5
9±0.5
13±0.5
1.2±0.2
1.2±0.2
1.8±0.2
1.8±0.2
2.2±0.2
2.2±0.2
Reel Dimensions
Bulk Case Packaging

<!-- Page 76 -->

1-1. Storage Environment
Tape packing materials are designed to withstand long-term storage, but they will degrade more rapidly in the presence of high
temperature or high humidity, Therefore, the products must be stored in an ambient 5~40℃with a relative humidity of 20~70%.
Allowable storage period is within 6 months from the outgoing date of delivery.
1-2. Corrosive Gases
Since sulfur and chlorine may degrade the solderability of the end termination, it is important to store the capacitors in an
environment free of these gases
1-3. Temperature Fluctuations
Since dew condensation may occur by the differences in temperature when the products are taken out of storage, it is
important to maintain a temperature-controlled environment.
When designing printed circuit boards, the shape and size of the solder lands must allow for the proper amount of solder on
the capacitor. The amount of solder at the end terminations has a direct effect on the
probability that the chip will crack. The greater amount of solder, the larger amount of stress on the chip, and the more likely
that it will break. Use the following illustrations as guidelines for proper Solder land design.
MLCCs generally require the use of an adhesive to position the chips to the circuit board prior to soldering.
3-1. Requirements for Adhesives
They must have enough adhesion so that the chips will not fall off or move during the handling of the circuit board.
They must maintain their adhesive strength when exposed to soldering temperatures.
They should not spread or run when applied to the circuit board.
They should have a long pot life.
They should harden quickly.
They should not corrode the circuit board or chip material.
They should be a good insulator.
They should be non-toxic, and not produce harmful gases, nor be harmful when touched.
3-2. Application Method
It is important to use the proper amount of adhesive. Too little will cause poor adhesion to the circuit board, and too much may
strain theconductor pattern, thereby causing defective soldering. The following illustrations show the proper quantity of adhesive.
Recommendation of solder Land Shape and Size
Type
a
b
c
0.2min
70~100μm
>0
0.2min
70~100μm
>0
21
31
Unit: mm
w
b
Solder Resist
2 / 3W < b < W
a
Solder
Land
Solder Resist
2 / 3T < a < T
T
b
a
a
c
c
Land
PCB
Solder Resist
1.Storage of products
2.Design of Solder Land Pattern
3.Adhesives
3-3. Adhesive hardening Characteristics
To prevent oxidation of the terminations, the adhesive must harden at 160℃ or less, within 2 minutes or less.
Application Manual for
Surface Mounting

<!-- Page 77 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
76
77
Since a multilayer ceramic chip capacitor comes into direct contact with melted solder during soldering, it is exposed to potentially mechanical
stress caused by the sudden temperature change. The capacitor may also be subject to silver migration, and to contamination by the flux.
Because of these factors, soldering technique is critical.
6-1. Soldering Methods
4-1. Mounting Head Pressure
Excessive pressure will cause chip capacitors to crack. The pressure between nozzle and chip capacitor will be 300g maximum during mounting.
4-2. Bending Stress
Bending of printed circuit board by mounting head when double-sided circuit boards are used, chip capacitors first are mounted and soldered onto
one side of the board. When the capacitors are mounted onto the other side, it is important to support the board as shown in the illustration.
If the circuit board is not supported, it may bend, causing the already-installed capacitors to crack.
Although highly-activated flux gives better solderability, substances which increase activity may also degrade the insulation of the chip
capactiors, To avoid such degradation, it is recommended that a mildly activated rosin flux ( less than 0.2% chlorine ) be used
.
Method
Reflow slodering
· Overall heating
· Infrared rays
· Hot plate
· VPS (Vapor phase)
· Air heater
· Laser
· Light beam
· Local heating
· Single wave
· Double wave
Flow slodering
Classification
nozzle
force
support pin
6-2. Soldering Profile
To avoid the crack problem by sudden temperature change, follow the temperature profile in the adjacent graph.
4. Mounting
5. Flux
6. Soldering

<!-- Page 78 -->

6-2-1 Pb-Free (Sn 100%) Plating
FLOW SOLDERING
Pre-heating
Time(sec.)
Soldering
Temp.(℃)
Pre-heating
Temp.(℃
℃
℃
℃
℃
)
Gradual Cooling
in the air
260±3℃
5 sec. max.
△T
REFLOW SOLDERING
Pre-heating
Soldering
Temp.(℃)
217℃
200℃
150℃
Gradual Cooling
in the air
260+0/-5℃
10 sec. max.
Time(sec.)
260+
+
0/-5℃
℃
SolderingTemp.
(
)
150
~
60
0
2
1
~
0
6
Pre-heating Time
(
, sec.)
Soldering Time
(
, sec.)
≤150
(1206 and below size)
△T (
)
≥120
≤5
Pre-heatingTime
(
, sec.)
SolderingTime
(
, sec.)
260±3
Soldering Temp.
(
)
△T≤130
Variation of
Temp.(
)
300±10℃max.
Soldering
Temp(
)
≥60 sec.
≤4 sec.
-             20W max.
3mm max.
4 sec max.
Pre-heating
Time(sec.)
Soldering
Time(sec.)
Cooling
Time(sec.)
Condition of Iron Facilities
Wattage
Tip
Diameter
Soldering
Time
SOLDER IRON(Hand Soldering)
Caution - Iron tip should not contact with ceramic body directly
①
①
②
①
②
①
②
③
③
②
※

<!-- Page 79 -->

Part Numbering
System
Standard &
High Capacitors
Super Small Size
Capacitors
High-Q
Capacitors
Medium-High
Voltage Capacitors
Array Type
Capacitors
Low ESL
Capacitors
Application Manual
for Surface Mounting
Packaging
Specification
Premium Capacitors
for Automotive
Applications
Reliability Test
Condition
78
79
6-3. Manual Soldering
Manual soldering can pose a great risk of creating thermal cracks in chip capacitors. The hot soldering iron tip comes into direct contact with the end
terminations, and operator’ s carelessness may cause the tip of the soldering iron to come into direct contact with the ceramic body of the capacitor.
Therefore the soldering iron must be handled carefully, and close attention must be paid to the selection of the soldering iron tip and to temperature
control of the tip.
6-5. Cooling
Natural cooling using air is recommended. If the chips are dipped into solvent for cleaning, the temperature difference (△T) must be less than 100℃
6-6. Cleaning
If rosin flux is used, cleaning usually is unnecessary. When strongly activated flux is used, chlorine in the flux may dissolve into some types of cleaning
fluids, thereby affecting the chip capacitors. This means that the cleaning fluid must be carefully selected, and should always be new.
A multi-PC board is separated into many individual circuit boards after soldering has been completed. If the board is bent or distorted
at the time of separation, cracks may occur in the chip capacitors. Carefully choose a separation method that minimizes the bending
of the circuit board.
6-4. Amount of Solder
Too much Solder
Not enough solder
Cracks tend to occur
due to large stress.
Weak holding force may cause
bad connections or
detaching of the capacitor
7. Notes for Separating Multiple, Shared PC Boards

<!-- Page 80 -->

Attention
1. This catalogue is valid only to the products purchased either from us or through our official distri-
butors.
2. Product specifications included in this catalogue are effective as of Nov 1, 2015.
Please be advised that they are standard product specifications for reference only.
We may change, modify or discontinue the product specifications without notice at any time.
So, you need to approve the product specifications before placing an order. Should you have any
question regarding our product specifications, please contact our sales personnel or application
engineers.
3. We may modify or cease to produce the products listed in this catalogue without notice. Should
you have any question, please contact our sales personnel or application engineers.
4. Without obtaining our permission, you should not be allowed to reproduce, copy, use or transfer
any content or information contained this catalogue in any manner whatsoever for any purpose.
5. In no event, will we be responsible for any claim, dispute, damage or liability whatsoever arising
from, relating to or in connection with your misuse of the products or/and information included in
this catalogue.
We will also not assume any responsibilities whatsoever for any claim, dispute, damage or liability
with regards to the intellectual property rights or other related rights of ours or any third party as-
sociated with your use of our products and/or information contained in this catalogue. Weexpres-
sly disclaim that no license is granted regarding the aforementioned rights.
6. Please note that the products in this catalogue are not designed or intended to use for the appoli-
cations set forth below. So, if you intend to use the products in this catalogue for the applications
listed below,you should contact our sales personnel or application engineers before using.
Please be aware that any misuse of the products deviating from product specifications or informa-
tion provided in this catalogue may cause a serious property damage or a personal injury.
①Aerospace/Aviation equipment
②Transportation equipment (vehicles, trains, ships, etc)
③Medical equipment
④Military equipment
⑤Disaster prevention/crime prevention equipment
⑥Any other applications with the same as or similar complexity or reliability to the applications set
forth above.

<!-- Page 81 -->

Sony Green Partner
QC 080000 IECQ HSPM
ISO/TS 16949
ISO 14001
OHSAS18001
80
81
Certifications

<!-- Page 82 -->

ISO / TS 16949
ISO 14001
OHSAS 18001
Sony Green Partner
QC 080000
Quality System Certification status for each factory site
BSI
TS 91430 - 000
2013-10-25
~2016-10-24
BSI
TS 91430 - 001
2013-08-08
~2016-08-07
2012-06-01
~2014-05-31
BSI
TS 91430 - 005
2012-08-03
~2015-08-02
BSI
EMS 585363
2012-04-17
~2015-04-16
BSI
OHS 585364
2012-04-17
~2015-04-16
BSI
EMS 77354
2012-07-13
~2015-07-12
BSI
OHS 568723
2013-10-14
~2016-10-13
BSI
EMS 599427
2013-06-25
~2016-06-24
BSI
OHS 599428
2013-06-25
~2016-06-24
BSI
EMS 599427
2013-06-25
~2016-06-24
BSI
OHS 599428
2013-06-25
~2016-06-24
UL
KR-HSPM-1012
2013-06-27
~2016-07-19
UL
PI-HSPM-1001
2013-06-27
~2016-07-04
UL
PRC-HSPM-1767
2013-07-08
~2016-07-26
UL
PRC-HSPM-1767-2
2013-07-08
~2016-07-26
UL
KR-HSPM-1011
2013-06-17
~2016-07-01
BSI
TS 91430 - 007
2011-11-29
~2014-11-28
Suwon
(Korea)
Certification
Busan
(Korea)
Calamba
(Philippines)
Tianjin
(China)
BSI
TS 91430 - 007
2011-11-29
~2014-11-28
Binhai
(China)
BSI
EMS 585363
2012-04-17
~2015-04-16
BSI
OHS 585364
2012-04-17
~2015-04-16
2012-06-01
~2014-05-31
2012-06-01
~2014-05-31
2012-06-01
~2014-05-31
2012-06-01
~2014-05-31
Date
Validity
Date
Validity
Date
Validity
Date
Validity
Date
Validity

<!-- Page 83 -->

Note
82
83

<!-- Page 84 -->

All information indicated in this catalog is as of November. 2015
●Head office
●Manufacturing sites
●Asia sales offices
●America sales office
●Europe sales offices
●Domestic Distributors
Passive components sales offices
150,Meayoungro(Maetan-dong)
Yeongtong-gu, Suwon-city,
Gyeonggi province, Korea,443-743
Tel : +82-31-210-5114
Europe
Tel : +82-31-210 -6328
E-mail : james.pyun@samsung.com
America
Tel : +82-31-210 -6803
E-mail : wesley.roh@samsung.com
China
Tel : +82-31-210-3476
E-mail : james.h.lee@samsung.com
Japan
Tel : +82-31-210-6304
E-mail : jdkim1@samsung.com
Domestic
Tel : +82-31-210-3692
E-mail : jeongki.um@samsung.com
Irvine office
3333 Michelson Drive, Suite 500, Irvine, CA
92612, USA
Tel : +1-949-797-8016
E-mail : andrew.skelly@samsung.com
San Jose office
601, McCarthy Blvd.,  San Jose, CA 95035, USA
Tel : +1-408-544-4552
E-mail : jay.pauer@samsung.com
Chicago office
1870 West Winchester Rd, Suite 247,
Libertyville IL 60048, USA
Tel : +1-847-549-9424
E-mail : sweety@samsung.com
Frankfurt office
Samsung, Haus, Am Kronberger Hang 6,
D-65824 Schwalbach/Ts. Germany
Tel : +49-6196-66-7255
E-mail : frank.goebel@samsung.com
London office
KT130NY 2nd floor, No 5. No 5. The Heights,
Brooklands,  Weybridge Surrey, England
Tel : +44-1932-826-811
E-mail : river.lee@samsung.com
Helsinki office
 02600, Lars Sonckin Kaari 14, Espoo, Finland
Tel : +358-9-853-1132
 E-mail : jouni.riuttanen@samsung.com
Korchip Corporation
359, Manan-ro, Manan-gu, Anyang-si,
Gyeonggi-do, Korea
Tel :+82-31-361-8100
E-mail : parts@korchip.com
SAMT
315, Yeongdong-daero, Gangnam-gu, Seoul,
Korea
Tel : +82-2-3458-9000
E-mail : info@isamt.com
CHUNGMAC
40-3, Gokseon-ro 49beon-gil, Gwonseon-gu,
Suwon-si, Gyeonggi-do, Korea
Tel : +82-31-234-2367
E-mail : webmaster@chungmac.co.kr
YOUNGDUK
632, Seobusaet-gil, Geumcheon-gu, Seoul,
Korea
Tel : +82-2-2107-7860
E-mail : dryblood@hanmail.net
Shenzhen office
46 F, New World Center, Yitian Road, Futian
District,Shenzhen, China 518026
Tel : +86-755-8608-5579
E-mail : andy.li@samsung.com
Shanghai office
Rm. 1211, Shanghai International Trade
CenterNo.2201 Yan An(W) Rd., Shanghai, China
200335
Tel : +86-21-2231-4341
E-mail : koogi@samsung.com
Beijing office
'12/F China Merchants Tower No. 118, Jian Guo
Lu, Chao Yang District, Beijing, China
Tel : +86-10-6566-8100-6606
E-mail : kiko.wang@samsung.com
Qingdao Office
Rm 1201. Growne Plaza Qingdao 76,
Xiang Gang Zhong Rd, Qingdao,
266071 China
Tel : +86-532-85779102
E-mail : zhengguo.cui@samsung.com
Taipei Office
9F-1, Np. 399 Ruey Kuang Rd., Neihu
District, Taipei City, Taiwan, 114
Tel : +886-2-2656-8350
E-mail : kevin0130.wang@samsung.com
Singapore office
Samsung Electro-Mechanics Private LimitedÞ
3 Church Street Samsung Hub #23-01
Singapore 049483
Tel : +65-6933-2630
E-mail : alvin.koh@samsung.com

Bangkok office
24180 Wellgrow Industrial Estate, 93 Moo 5,
Bangsamak A. Bangpakong, Chachoensao,
Thailand
Tel : +66-38-562-110
E-mail : kyunghoon1.lee@samsung.com

Japan office
108-0075 Minato-ku Tokyo Kounan 2-16-4
Shinagawa Grand Cnetral Tower 9F, Japan
Tel : +81-3-6369-6452
E-mail : hikota.suga@samsung.com
Suwon Plant(Korea)
150,Meayoungro(Maetan-dong)
Yeongtong-gu, Suwon-city,
Gyeonggi province, Korea,443-743
Tel : +82-31-210-5114
Busan Plant (Korea)
333,Noksan Sanupjoongro(Songjeong-
dong,)Gangseo-gu, Busan, Korea,
618-270
Tel : +82-51-970-7114
Tianjin Plant (China)
27, Heiniucheng-Road,Tianjin,
China 300210
Tel : +86-22-2830-3333
Binhai Plant(China)
No 80 xiaqing road,
TEDA west District, China
Tel : +86-22-6686-3333
Philippines Plant (Philippines)
Block 5 Calamba Premiere Industrial Park
Calamba City, Philippines
Tel : +63-49-508-8311
 * The specifications and designs contained herein may be subject to change without notice.

# 15. JST PH Series — S2B-PH-SM4-TB (J2 Battery Connector)

*LCSC/JLCPCB: C295747 · datasheet: `C295747.pdf` (JST PH connector, 3 pp.) · added 2026-08-01*

Thin, low-profile 2.0 mm pitch disconnectable crimp-style connector; side-entry (horizontal) SMT model, fully shrouded header with PCB retention mechanism. S2B-PH-SM4-TB = 2-position, surface-mount, tin-plated.

**Key specs (from datasheet):**
- Current rating: 2 A AC/DC (AWG #24) — battery charge/discharge currents (≤ ~500 mA) well within rating
- Voltage rating: 100 V AC/DC · withstanding 800 VAC/min
- Temperature range: −25 °C to +85 °C (including current-induced rise)
- Contact resistance: 10 mΩ max initial, 20 mΩ max after environmental tests
- Insulation resistance: 1,000 MΩ min · applicable wire AWG #32–#24 · PCB 0.8–1.6 mm
- Mounted height 8.0 mm, width 4.5 mm — record for case design
- UL E60389 / R75087 · RoHS2

**Assembly notes (project-specific):** silkscreen "+" polarity marker present beside J2 pin 1 on B.SilkS; JST-PH plug polarity is not universal — verify battery lead polarity with a multimeter against J2 before first connection (battery: Uxney 503035, 1S 500 mAh, built-in protection).

