---
title: Module Bill of Materials
tags:
- tag1
- tag2
---

## Overview
The wireless communication subsystem is designed to support a compact embedded system built around the ESP32-WROOM-32, which serves as the primary controller for onboard processing, wireless communication, and interaction with connected peripherals. Utilizing its integrated WiFi capability, the ESP32 enables the rover to communicate with an external control station or MQTT server for real-time transmission of sensor data and reception of control commands. The system is powered through an external DC input provided via a barrel jack interface, which is regulated to a stable 3.3 V supply using the LM2576HVS-3.3. This regulator ensures consistent and efficient power delivery to the ESP32 and all supporting components, with additional elements such as capacitors, an inductor, a Schottky diode, and a fuse included for filtering, protection, and proper switching operation.

A key improvement in the final design is the replacement of traditional LED indicators with an SSD1306 OLED display connected via the I²C interface, which provides real-time debugging and system status feedback such as WiFi connectivity and message transmission activity. Push-button switches are retained for manual control and reset functionality, while connector headers expose UART and GPIO pins to allow integration with other rover subsystems. Together, these components form a reliable, modular, and easily debuggable wireless communication platform that supports the rover’s control, monitoring, and data exchange requirements.


| Part Name / Description                      | Qty | Unit Cost | Total Cost | Manufacturer      | Manufacturer # | Vendor Link      | Datasheet Link         | Schematic Reference |
| -------------------------------------------- | --- | --------- | ---------- | ----------------- | -------------- | ---------------- | ---------------------- | ------------------- |
| WiFi Microcontroller Module                  | 1   | —         | —          | Espressif         | ESP32-WROOM-32 | DigiKey          | Espressif Datasheet    | U1                  |
| 3.3V Buck Switching Voltage Regulator        | 1   | —         | —          | Texas Instruments | LM2576HVS-3.3  | DigiKey          | TI Datasheet           | U3                  |
| Schottky Diode                               | 1   | —         | —          | —                 | 1N5822         | DigiKey          | Manufacturer Datasheet | D6                  |
| Power Inductor                               | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | L1                  |
| Capacitor 0.1 µF                             | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | C1                  |
| Capacitor 330 µF                             | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | C2                  |
| Capacitor 1 µF                               | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | C3                  |
| Resistor (1kΩ)                               | 4   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | R1–R4               |
| Resistor (10kΩ)                              | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | R5                  |
| OLED Display (I²C Debug Display)             | 1   | —         | —          | —                 | SSD1306        | DigiKey / Amazon | SSD1306 Datasheet      | —                   |
| I²C Pull-up Resistors (4.7kΩ)                | 2   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | R6, R7              |
| Barrel Jack Connector (Power Input)          | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | J1                  |
| USB Micro-B Connector (Optional Power/Debug) | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | J2                  |
| Connector Header (Subsystem Interface)       | 2   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | J3, J4              |
| Push Button Switch (Reset/Debug)             | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | SW1                 |
| Fuse                                         | 1   | —         | —          | —                 | —              | DigiKey          | Manufacturer Datasheet | F1                  |
