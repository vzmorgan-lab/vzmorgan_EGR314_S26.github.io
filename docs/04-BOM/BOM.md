---
title: Module Bill of Materials
tags:
- tag1
- tag2
---

## Overview
The wireless communication subsystem is designed to support a small embedded system built around the ESP32-WROOM-32 microcontroller module. The ESP32 serves as the primary controller for the system, managing onboard processing, wireless communication, and interaction with connected peripherals. Through its integrated WiFi capability, the ESP32 enables the rover system to communicate with an external control station or MQTT server for transmitting sensor data and receiving commands.

The system is powered through a 9 V input supply, which is converted to a stable 3.3 V operating voltage using the LM2576HVS-3.3 switching voltage regulator. This regulator ensures that the ESP32 and other components receive a consistent and reliable voltage while improving efficiency compared to linear regulation. Supporting components such as capacitors, an inductor, a diode, and a fuse are included to provide voltage filtering, circuit protection, and proper switching regulator operation.

Additional elements in the design include LED indicators for visual system status feedback and push-button switches for manual control or reset functions. Connector headers are also provided to expose several ESP32 GPIO pins, allowing external sensors, actuators, or other modules to be connected to the system. Together, these components create a compact and reliable wireless communication platform suitable for integration into the rover’s control and monitoring system.

| **Part Name/Description**             | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer**  | **Manufacturer #** | **Vendor Link** | **Datasheet Link**     | **Schematic Reference Designators** |
| ------------------------------------- | ------- | ------------- | -------------- | ----------------- | ------------------ | --------------- | ---------------------- | ----------------------------------- |
| ESP32 WiFi Microcontroller Module     | 1       | —             | —              | Espressif         | ESP32-WROOM-32     | DigiKey         | Espressif Datasheet    | U1                                  |
| 3.3V Buck Switching Voltage Regulator | 1       | —             | —              | Texas Instruments | LM2576HVS-3.3      | DigiKey         | TI Datasheet           | U3                                  |
| Schottky Diode                        | 1       | —             | —              | —                 | 1N5822             | DigiKey         | Manufacturer Datasheet | D6                                  |
| Inductor                              | 1       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | L1                                  |
| LED Indicator                         | 5       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | D1, D2, D3, D4, D5                  |
| Resistors (1kΩ)                       | 5       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | R1, R2, R3, R4, R5                  |
| Resistor (10kΩ)                       | 1       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | R6                                  |
| Capacitor 0.1 µF                      | 1       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | C1                                  |
| Capacitor 1000 µF                     | 1       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | C2                                  |
| Capacitor 1 µF                        | 1       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | C3                                  |
| Push Button Switch                    | 1       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | SW1                                 |
| Fuse                                  | 1       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | F1                                  |
| Connector Header                      | 2       | —             | —              | —                 | —                  | DigiKey         | Manufacturer Datasheet | J3, J4                              |


## Resouce

The Bill of Material as a PDF download is available [*here*](PDF_For_BOM_EXAMPLE.pdf).
