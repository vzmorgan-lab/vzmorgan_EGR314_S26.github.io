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

The overall team project focuses on designing and developing a subterranean rover capable of performing multiple coordinated functions while operating underground. The rover integrates several subsystems, including sensing technologies, wireless communication, user interface controls, and a drilling mechanism. Each subsystem works together to support the rover’s ability to explore, collect data, and communicate with operators at the surface.

The wireless communication subsystem plays a critical role in enabling the rover to transmit sensor data and receive commands from an external control station. This subsystem uses the ESP32-WROOM-32 to provide WiFi connectivity and communicate with a remote server using MQTT messaging protocols. Power regulation for the system is provided through a LM2576HVS-3.3 switching voltage regulator, which converts the input supply to the stable 3.3 V required by the ESP32 and supporting components.

This datasheet focuses specifically on the design and implementation of the wireless communication circuitry. For a more detailed explanation of the overall rover architecture and the integration of all subsystems, readers can refer to the [team project report link.](https://egr314-s-2026-306.github.io/Team306.github.io/)

### My Contribution

In team 306, I contributed to the development of the rover’s wireless communication subsystem. My work focused on designing the hardware schematic, selecting appropriate electronic components, and ensuring that the communication system could reliably interface with the rover’s control electronics.

Specifically, my contributions included:

  * Designing the wireless communication schematic using KiCad.

  * Selecting key hardware components such as the ESP32-WROOM-32 WiFi module and the LM2576HVS-3.3 voltage regulator.

  * Implementing supporting circuitry including resistors, capacitors, connectors, LEDs, and protection components required for stable system operation.

  * Developing documentation for the subsystem, including schematic descriptions and component explanations.

This datasheet is organized to help readers quickly locate relevant information about the subsystem. For example, readers interested in the specific components used in the design can review the Bill of Materials (BOM) section, which lists all components, manufacturers, and reference designators used in the schematic. Additional sections provide supporting resources such as schematic diagrams and project files.

Together, these sections provide a clear overview of the subsystem design and allow readers to understand how the wireless communication module contributes to the overall rover system.

To review the details listed of the material used to construct the subsection, you can review it in the ["BOM"](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/04-BOM/BOM/) section of the datasheet.

>Continue for all the remaining/missing sections.
