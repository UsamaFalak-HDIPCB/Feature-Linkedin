https://github.com/user-attachments/assets/3615b124-c129-42b4-890e-0ba765d850c5

##

6-layer USB 3.1 to UFS/eMMC diagnostic programmer based on SM3350M and ATSAM3X8E, featuring MIPI M-PHY routing, dynamic power control, current monitoring, JTAG/debug access, and UFS/eMMC headers.


# USB 3.1 to UFS/eMMC Diagnostic Programmer

This repository contains the hardware design files for a 6-layer USB 3.1 to UFS/eMMC diagnostic programmer built around the SM3350M bridge controller and ATSAM3X8E microcontroller.

The board is designed to interface UFS and eMMC storage devices through dedicated headers and expose diagnostic/programming access over USB. The SM3350 family supports USB 3.1 SuperSpeed operation, UFS 2.1, MIPI M-PHY HS-Gear3 single-lane operation, SD UHS-I, and eMMC 4.5 HS200 compatibility.

The design includes high-speed UFS/MIPI M-PHY signal routing, eMMC data/control routing, USB 3.0 connectivity, programmable power rails, current-sense monitoring, I2C-controlled analog/power configuration, JTAG/debug access, secure element support, and onboard status indication. The schematic includes SM3350M, ATSAM3X8EA-AU, USB 3.0 Type-A connector, UFS and eMMC headers, INA180 current-sense amplifiers, MCP4728 DAC, SY8088 regulators, ATECC508A secure element, JTAG headers, and WS2812C status LEDs. 



## Project Work

- Designed a 6-layer PCB for a USB 3.1 to UFS/eMMC diagnostic programmer.
- Integrated SM3350M USB-to-UFS/eMMC bridge controller and ATSAM3X8E microcontroller.
- Routed high-speed USB 3.x and UFS/MIPI M-PHY differential signals.
- Designed eMMC and UFS header interfaces for external storage-device connection.
- Implemented programmable power rails using switching regulators and control circuitry.
- Added current-sense monitoring using INA180 amplifiers on key supply rails.
- Integrated MCP4728 DAC for I2C-controlled analog/power configuration.
- Added JTAG/debug headers, secure element support, and onboard status LEDs.



## Key Design Features

- 6-layer PCB design
- SM3350M USB-to-UFS/eMMC bridge controller
- ATSAM3X8EA-AU ARM Cortex-M3 microcontroller
- USB 3.0 Type-A host interface
- UFS header interface
- eMMC header interface
- High-speed MIPI M-PHY signal routing
- eMMC 8-bit data/control signal routing
- Dynamic power-rail generation and enable control
- I2C-controlled voltage/reference configuration
- Real-time current monitoring using shunt resistors and INA180 current-sense amplifiers
- JTAG headers for SM3350M and microcontroller debug access
- ATECC508A secure element
- WS2812C addressable status LEDs
- Multiple onboard voltage rails including 5V, 3.3V, 2.5V, 1.8V, and 1.1V domains



## SM3350M Bridge Controller

The SM3350M is used as the main USB-to-storage bridge controller. It provides the high-speed bridge between USB and UFS/eMMC storage interfaces. The controller supports USB 3.1 SuperSpeed and UFS 2.1 operation, including MIPI M-PHY HS-Gear3 single-lane support up to 5.8 Gbps.

## ATSAM3X8E Microcontroller

The ATSAM3X8EA-AU microcontroller is used for board-level control, monitoring, GPIO handling, power sequencing, and communication with peripheral control devices. The ATSAM3X8E is an ARM Cortex-M3 microcontroller running up to 84 MHz with 512 KB Flash, USB support, I2C, SPI, UART/USART, and multiple peripheral interfaces.

## Storage Interfaces

The board includes two dedicated external storage interfaces:
- UFS header
- eMMC header
The UFS section routes high-speed differential MIPI M-PHY TX/RX signals, while the eMMC section routes clock, command, reset, and 8-bit data signals. The schematic includes separate UFS and eMMC headers for device connection and testing.

## USB Interface

The board includes a USB 3.0 Type-A connector for host-side communication. USB SuperSpeed differential pairs and USB 2.0 D+/D− lines are routed between the connector and the SM3350M bridge controller. 


## Power Architecture

The design includes multiple regulated voltage rails for the bridge controller, microcontroller, storage device interfaces, and support circuitry. The schematic includes SY8088 switching regulators, AP2138 2.5V LDO, current-sense shunt resistors, INA180 current-sense amplifiers, and enable-controlled voltage rails.

Key rails include:
- 5V input/system rail
- 3.3V logic rail
- 2.5V rail
- 1.8V rail
- 1.1V rail
- Storage interface rails such as VCC, VCCQ, VCCQ2, PVIO, SVIO, and VSYS


## Current Monitoring

Current monitoring is implemented using low-value shunt resistors and INA180 current-sense amplifiers. The schematic shows monitored rails including VSYS, VCC, VCCQ, and VCCQ2, allowing the board to measure current behavior on key storage-device supply rails.

## I2C-Controlled Voltage / Analog Control

The design includes an MCP4728 quad DAC connected through I2C. The DAC outputs are labeled as VR1, VR2, VR3, and VR4, allowing firmware-controlled voltage/reference configuration for the board’s power/control network. 

## Debug and Security

The board includes JTAG headers for debugging and programming access. The schematic also includes an ATECC508A secure element connected through I2C, which can be used for authentication or secure key-related functions depending on firmware implementation. 


## Functionality and Usage

This board is intended to work as a diagnostic and programming interface for UFS and eMMC storage devices. It connects to a host computer through USB 3.0 / USB 3.1 and provides hardware-level access to storage devices through dedicated UFS and eMMC headers.

The SM3350M acts as the main USB-to-storage bridge controller, while the ATSAM3X8E microcontroller manages board-level control, power sequencing, monitoring, GPIO control, I2C communication, and debug-related tasks.

The board can be used for:
- UFS device access and diagnostic testing
- eMMC device access and programming support
- USB-based storage bridge evaluation
- Power-rail control and monitoring for storage devices
- Current measurement on key supply rails
- Hardware debugging through JTAG headers
- Development and testing of UFS/eMMC interface hardware

##
<img width="1576" height="1609" alt="Image" src="https://github.com/user-attachments/assets/cc8fac2b-79ca-474e-8af4-c753b07ababc" />
<img width="1576" height="1609" alt="Image" src="https://github.com/user-attachments/assets/b90f6610-e1b4-472a-8498-596a2c43b7b4" />

##
<img width="956" height="776" alt="Image" src="https://github.com/user-attachments/assets/b406f884-2b61-48cb-ab64-e2b69460a24f" />
<img width="1061" height="868" alt="Image" src="https://github.com/user-attachments/assets/3c429220-5740-487b-98e5-8cc1dc02ba7a" />
<img width="851" height="796" alt="Image" src="https://github.com/user-attachments/assets/a21e3f44-6ce3-40a0-84f8-3a9841c84ed7" />
<img width="866" height="778" alt="Image" src="https://github.com/user-attachments/assets/cf9758c5-531c-4ed8-841e-a8e10d10157b" />
