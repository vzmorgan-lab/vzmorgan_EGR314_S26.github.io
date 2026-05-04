---
title: Module Schematic
---

## Overview

The wireless communication subsystem is designed around the ESP32-WROOM-32, which serves as the central controller for processing, wireless communication, and peripheral interfacing. Through its integrated WiFi capability, the ESP32 enables communication with an external MQTT server, allowing the rover to transmit sensor data and receive control commands in real time. The system is powered through an external DC input, including both a barrel jack and USB interface, which is stepped down to a stable 3.3 V supply using the LM2576HVS-3.3. Supporting components such as an inductor, Schottky diode, capacitors, and a fuse ensure proper regulation, filtering, and circuit protection for reliable operation.

A key feature of the final design is the inclusion of an SSD1306 OLED display connected via the I²C interface (GPIO21 and GPIO22), which provides real-time debugging and system feedback such as communication status and message activity. A push-button switch is included for manual control and system interaction, while connector headers expose UART (TX/RX) and GPIO pins for integration with other rover subsystems. Together, these elements create a robust, modular, and easily debuggable wireless communication platform that meets the rover’s requirements for reliable data transmission, power stability, and system observability.

## Wireless Connection Schematic

The image below shows the wireless communication schematic implemented in KiCad. The ESP32 module interfaces with external devices through its GPIO pins and communicates wirelessly with an MQTT server over WiFi. The regulated 3.3 V supply powers the ESP32 and supporting components, ensuring stable operation of the communication system.

<img width="1097" height="753" alt="Screenshot 2026-05-03 155334" src="https://github.com/user-attachments/assets/e287f5b0-3bd0-4a17-962a-5d2eb32035a5" />

## Resources

The schematic as a PDF download is available [*Here*](https://github.com/vzmorgan-lab/vzmorgan_EGR314_S26.github.io/blob/main/WirelessConnection_1.pdf), and the Zip folder of the project [Wireless Connection Zip File]()

