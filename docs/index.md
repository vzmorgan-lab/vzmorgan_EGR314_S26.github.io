---
title: Welcome
tags:
- tag1
- tag2
---
<center>
<font size= "6">Vanessa Morgan Datasheet</font><br>
as part of<br>
<font size= "8"> Project: Subterranian Rover</font><br>
for<br>
<font size= "5"> Team 306 </font><br>

**Submission: January, 15, 2026**
</center>

## Introduction

My name is Vanessa Morgan, and I am a Robotics Engineering student. This datasheet documents the design and implementation of the wireless communication subsystem developed as part of a larger engineering team project. The purpose of this datasheet is to provide a detailed overview of the hardware components, schematic design, and system functionality used to establish wireless communication for the rover platform.

The subsystem is built around the ESP32-WROOM-32 microcontroller module, which provides integrated WiFi capabilities and sufficient processing power to support communication between the rover and an external control system. This document explains the design choices, supporting circuitry, and hardware components used to enable reliable communication within the system. It also includes supporting information such as schematics, component descriptions, and a bill of materials to assist readers in understanding or reproducing the design.

### Project Summary

The wireless communication subsystem is a critical component of the subterranean rover, enabling reliable real-time data exchange between the rover and the surface operator during underground operation. It is responsible for transmitting sensor data, including magnetic field measurements and system status, while also receiving control commands that guide movement and drilling functions. This subsystem utilizes the ESP32-WROOM-32 to provide integrated WiFi connectivity and support MQTT-based communication for efficient data transfer. Power is regulated using the LM2576HVS-3.3, which converts the input supply to a stable 3.3 V required for consistent operation of the ESP32 and associated components. This datasheet focuses on the design and implementation of the wireless communication hardware within the rover system, while a more detailed overview of full subsystem integration can be found in the [team project report.](https://egr314-s-2026-306.github.io/Team306.github.io/)

### My Contribution

My primary responsibility was the development and integration of the rover’s wireless communication subsystem, which enables reliable data exchange between the rover and the surface operator by transmitting real-time sensor data and receiving control commands that guide system operation. My work focused on the electrical design, component selection, and integration of the communication hardware to ensure compatibility with the rover’s control electronics. My contributions include selecting key components such as the ESP32-WROOM-32 and the LM2576HVS-3.3, and implementing supporting circuitry including resistors, capacitors, connectors, and an OLED display used for real-time debugging and system feedback instead of traditional indicator LEDs. I also developed subsystem documentation, including schematic descriptions and component justifications, to ensure clarity and reproducibility of the design. This work directly supports the rover’s ability to communicate sensor data, receive operator input, and function as part of a coordinated system, and readers interested in embedded communication systems, hardware integration, or subsystem design will find this module particularly relevant.

To review the details listed of the material used to construct the subsection, you can review it in the ["BOM"](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/04-BOM/BOM/) section of the datasheet.

>Continue for all the remaining/missing sections.
