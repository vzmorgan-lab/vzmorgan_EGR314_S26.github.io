---
title: Module's Selected Major Components
---

## Module's Selected Major Components

The final major components chosen to establish dependable wireless communication for the Subterranian Rover are described in the following sections. These components meet the embedded system’s surface-mount design requirements and power constraints while enabling reliable WiFi communication between the rover electronics and the external control station. The selected components support wireless data transmission using MQTT over WiFi, provide system power regulation, and include user interface indicators for system status and diagnostics.

### Power Management

**3.3V Switching Voltage Regulator**

1. Buck Switching Regulator IC Positive Fixed 3.3V (Surface-Mount)
   LM3671MF-3.3/NOPB

    ![](<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/1558fada-5f01-4d3a-b844-272d979f7099" />)

    * $1.98/each
    * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/LM2576HVS-3-3-NOPB/363648)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | High efficiency ( about greater than 90%) improves power efficiency and reduces heat generation | Switching noise requires careful PCB layout |
    | Handles ESP32 peak current during WiFi bursts | Requires inductor and external passives                      |
    | Wide input voltage range supports battery input | More complex than Linear regulators                        |
    | Surface-mount compatible |

**Rationale:** During WiFi communication bursts, the ESP32 can draw short but significant current spikes. A linear regulator could experience voltage drop or excessive heat dissipation under these conditions. The LM3671MF-3.3/NOPB switching regulator was selected because it provides a stable and efficient 3.3V output, improves overall power efficiency, and supports dynamic current loads from wireless communication activities.

For more details, review the [Appendix-Component Selection Process-Power Management](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#power-management) 

### User Interface

**Status Indicator LEDs**

2. Surface-Mount LED Indicator
   IN-P32ATB

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/223/402/150%7EC04-036%7EAT%7E5_sml%28200x200%29.jpg)

    * $0.15/each
    * [link to product](https://www.digikey.com/en/products/detail/microchip-technology/TC74A0-3-3VAT/442720?gclsrc=aw.ds&gad_source=1&gad_campaignid=22289277771&gbraid=0AAAAADrbLlhDBa9FUIBwdcd7VYLPN3OB6&gclid=Cj0KCQiA7rDMBhCjARIsAGDBuECtTMQsLWFRmIdZ15_uIujRWbpkOhHiUt6Rx7rgtrCE274AA2dsC8gaApvJEALw_wcB)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Compact surface-mount package             | Requires current-limiting resistor                               |
    | Low power comsumption                     | Limited brightness compared to larger LEDs                       |
    | Easy integration with ESP32 GPIO pins     |
    | Provides visual system status indication  |

**Rationale:** Status LEDs were included to provide visual feedback about system operation, including power status, communication activity, and diagnostic signals. The IN-P32ATB LED offers a small footprint, low current consumption, and compatibility with 3.3V logic, making it suitable for embedded system indicators.

For more details, review the [Appendix-Component Selection Process-User Interface](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/Appendix/01-Componet-Selection/Component-Selection-Process/#sensor)

### User Input

**Tactile Push Button Switch**

1. Surface-Mount Momentary Push Button
   PTS636SM43SMTR LFS

    ![](<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/f33dfd12-a93a-4857-9a74-1a6e3bc8c7f4" />)

    * $0.40/each
    * [link to product](https://www.digikey.com/en/products/detail/c-k/PTS636SM43SMTR-LFS/10071723)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Compact surface-mount design              | Requires pull-up or pull-down resistor                           |
    | Reliable tactile feedback | Limited mechanical lifetime compared to larger switches                          |
    | Simple digital interface to ESP32 GPIO    | 
    | Useful for testing and manual control input |

**Rationale:** The push button switch allows manual user interaction with the wireless subsystem, such as initiating test communication events or resetting system functions. The selected tactile switch provides a compact surface-mount footprint and reliable actuation, making it well suited for embedded electronics in a constrained rover environment.

For more details, review the [Appendix-Component Selection Process- User Input](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/Appendix/01-Componet-Selection/Component-Selection-Process/#wifi-bluetooth-module)
      
### Wifi + Bluetooth

**Wifi + Bluetooth Module**

1. ESP32-S3-WROOM-1-N4 (Surface-Mount RF Module)

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/773/504/MFG_Attachment-2-ESP32-S3-WROOM-1_sml.jpg)

    * $5.06/each
    * [link to product](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Integrated Wifi and Bluetooth connectivity          | High current draw during wifi transmission                       |
    | Large software ecosystem and community support | RF performance depends on antenna layout                    |
    | Multiple GPIO pins for LEDs, sensors, and control | Requires careful RF PCB layout                            |
    | Supports UART communication with rover controller | More complex firmware than the simple radios                    |

**Rationale:** The ESP32-S3-WROOM-1-N4 module was selected because it integrates WiFi connectivity, processing capability, and multiple communication interfaces into a single surface-mount module, reducing PCB complexity. The module supports UART communication with the rover controller and WiFi communication with the MQTT server, allowing real-time telemetry transmission and command reception. Its extensive software ecosystem and development tools significantly reduce development risk.

For more details, review the [Appendix-Component Selection Process- Wifi+Bluetooth Module](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/Appendix/01-Componet-Selection/Component-Selection-Process/#wifi-bluetooth-module)

### Communication Interface

**Digital Serial Communication Connection**

1. Custom connector interface to rover controller/ laptop

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Simple and reliable serial communication  | Requires additional pins                                         |
    | Compatible with both ESP32 and PIC microcontrollers | Limited communication distance                         |
    | Low hardware complexity                   |                     

**Rationale:** UART was selected as the communication interface between the wireless subsystem and the rover controller board. This protocol is widely supported by embedded systems and provides simple bidirectional communication using only two signal lines (TX and RX). It is ideal for transmitting telemetry data and receiving control commands from other rover subsystems.

For more details, review the [Appendix-Component Selection Process- Communication Interface](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/Appendix/01-Componet-Selection/Component-Selection-Process/#wifi-bluetooth-module)

