---
title: Module Schematic
---

## Overview

This schematic supports a wireless embedded system built around the ESP32-WROOM-32 microcontroller module. The ESP32 functions as the primary controller for the system, performing onboard processing, managing WiFi communication, and interfacing with external peripherals. The design enables the ESP32 to transmit and receive data wirelessly, allowing the rover system to communicate with an external server using MQTT over WiFi.

Power for the circuit is supplied through a 9 V input source, which is regulated down to 3.3 V using the LM2576HVS-3.3 buck switching voltage regulator. This regulator provides a stable voltage required for proper ESP32 operation and helps maintain reliable system performance. Supporting power components, including a Schottky diode, fuse, inductor, and filtering capacitors, are included to improve efficiency, protect the circuit, and reduce voltage ripple.

Additional components are included to improve system usability and monitoring. Several LED indicators provide visual feedback for power and system status, while a push-button switch allows manual control or reset functionality. The schematic also includes connector headers that expose multiple ESP32 GPIO pins, allowing sensors, actuators, or other external devices to be connected easily. UART pins are available for programming and debugging the ESP32 during development.

Overall, the schematic integrates power regulation, wireless communication, system control, and peripheral connectivity into a compact embedded design suitable for the rover’s wireless communication subsystem.

## Wireless Connection Schematic

The image below shows the wireless communication schematic implemented in KiCad. The ESP32 module interfaces with external devices through its GPIO pins and communicates wirelessly with an MQTT server over WiFi. The regulated 3.3 V supply powers the ESP32 and supporting components, ensuring stable operation of the communication system.

<img width="1097" height="753" alt="Screenshot 2026-05-03 155334" src="https://github.com/user-attachments/assets/e287f5b0-3bd0-4a17-962a-5d2eb32035a5" />

## Resources

The schematic as a PDF download is available [*Here*](https://github.com/vzmorgan-lab/vzmorgan_EGR314_S26.github.io/blob/main/WirelessConnection_1.pdf), and the Zip folder of the project [Wireless Connection Zip File](https://github.com/user-attachments/files/25811621/WirelessConnection_1-2026-03-06_221520.zip)

