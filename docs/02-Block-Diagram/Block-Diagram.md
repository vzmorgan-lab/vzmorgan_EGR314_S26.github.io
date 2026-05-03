---
title: Module's Block Diagram
tags:
- tag1
- tag2
---

## Wireless Communication Block Diagram

The block diagram was developed by first identifying the core functional requirements of the wireless communication subsystem, including reliable data transmission, stable power delivery, and clear system-level debugging feedback. 

The ESP32-WROOM-32 was selected as the central processing and communication unit due to its integrated WiFi capability and compatibility with MQTT-based communication, allowing seamless data exchange with the remote server and operator interface. 

Power is provided through a regulated 3.3 V supply using the LM2576HVS-3.3, ensuring stable operation of the microcontroller and connected peripherals. Communication between subsystems is handled through UART connections and external connectors, enabling integration with other rover modules. 

An SSD1306 OLED display is connected via GPIO21 and GPIO22 using the I²C protocol and is included specifically for real-time debugging, providing visual feedback such as connection status and message transmission activity. 

The structure of the block diagram reflects a modular design approach, where power, communication, and debugging functions are clearly separated but interconnected, allowing the subsystem to meet product requirements for reliability, real-time data exchange, and ease of troubleshooting during operation.

## Block Diagram 

The diagram shown below is the wireless connection for the Subterranian Rover.  

<img width="931" height="701" alt="WC(update) drawio" src="https://github.com/user-attachments/assets/97d948c1-246c-4c12-9457-3ee38e05da9a" />


