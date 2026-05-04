---
title: Module's Selected Major Components
---

## Module's Selected Major Components

The final major components selected for the wireless communication subsystem support reliable data transmission, stable power delivery, and improved system-level debugging for the subterranean rover. These components were refined throughout the design process to align with system integration requirements, power constraints, and feedback received during development. The subsystem enables wireless communication with a remote control station using MQTT over WiFi, while also supporting wired communication with other rover subsystems and providing real-time debugging feedback through an onboard display.

### Power Management

**3.3V Switching Voltage Regulator**

### LM2596S-3.3/NOPB

![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/251/656/MFG_296%7E4200577-4%7EKTT%7E5_sml%28200x200%29.jpg)

   * $7.18 / each
   * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/LM2596S-3-3-NOPB/363704?gclsrc=aw.ds&gad_source=1&gad_campaignid=9265913509&gbraid=0AAAAADrbLlj3xs4UbSWPRhxAYtzibYndB&gclid=CjwKCAjw5NvPBhAoEiwA_2egflJdngoicV4xFI1DlxoIQZ_o1QBQ-Qoijo-tjerjWbnI-r_JC2vjpBoCxLkQAvD_BwE)

   |**Pros**                           |**Cons**                               |
   |-----------------------------------|---------------------------------------|
   | Simple and reliable switching regulator design  | Larger package compared to compact regulator  |
   | High current capability (up to 3A output)  | Higher cost than some alternatives     |
   | Requires relatively few external component | Lower efficiency than newer regulators |
   | Well-documented and widely used in power supply designs | Larger PCB footprint      |
   | Wide input voltage range (4.5V-40V) | Produces output ripple/noise compared to modern regulators |
   | Easy to us in DIY and prebuilt modules | Less efficient when stepping down from high voltages |

 **Final Choice:** LM2576HVS-3.3V/NOPB

**Rationale:**The LM2576HVS-3.3 was selected for its reliability, high current capability, and ease of implementation. It provides a stable 3.3 V output required by the ESP32 and peripheral devices, ensuring consistent operation during peak loads such as WiFi transmission. While more modern regulators exist, this device offers a robust and well-documented solution that simplifies integration into the rover’s power system.

For more details, review the [Appendix-Component Selection Process-Power Management](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#power-management) 

### Power Source

**Battery**

1. 5V External Input (Barrel Jack Interface)

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/194/516/MFG_PJ-007_sml%28200x200%29.jpg)

   * $0.73 / each
   * [link to product](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices-/PJ-007/263523?gclsrc=aw.ds&gad_source=1&gad_campaignid=17336967819&gbraid=0AAAAADrbLlj4e2rkxYeNE6Sysj6X7B6l9&gclid=Cj0KCQjw1ZjOBhCmARIsADDuFTCADD1jQP-6756QURgUNsW43VM7cNSta41hyIuoQc7dlILhTU_IFmIaAqB-EALw_wcB)

   |**Pros**                                |**Cons**                                  |
   |----------------------------------------|------------------------------------------|
   | Simple and reliable power input method | Requires external regulated source       |
   | Easily replaceable and test-friendly   | Less portable than battery-only systems  |
   | Compatible with lab power supplies     |

**Final Choice:** 5V External Input (Barrel Jack Interface)

**Rationale:** A barrel jack power interface was selected to provide a stable and accessible input power source during development and testing. This allows the subsystem to be powered from regulated lab supplies or external adapters, improving reliability and simplifying debugging compared to battery-only operation.

### Wifi + Bluetooth

**Wifi + Bluetooth Module**

1. ESP32-WROOM-32-N8

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/302/ESP32-WROOM-32-%288MB%29_View1_sml.jpg)

    * $5.06/each
    * [link to product](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-WROOM-32-N8/9381712)

    | **Pros**                                       | **Cons**                                          |
    | -----------------------------------------------| ------------------------------------------------- |
    | Integrated Wifi and processing                 | High current draw during wifi transmission        |
    | Supports MQTT Communication                    | Requires careful power design                     |
    | Multiple GPIO interfaces (UART, I²C, GPIO)     | RF performance depends on layout               |
    | LArge development ecosystem                    |

**Final Choice:** ESP32-WROOM-32-N8

**Rationale:** The ESP32-WROOM-32 was selected as the central controller due to its integrated WiFi capability and support for MQTT-based communication, eliminating the need for an external communication module. It supports multiple communication interfaces, allowing seamless integration with rover subsystems via UART and with the debugging display via I²C.

For more details, review the [Appendix-Component Selection Process- Wifi+Bluetooth Module](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/Appendix/01-Componet-Selection/Component-Selection-Process/#wifi-bluetooth-module)

### Communication Interface

**UART Serial Communication**

1. Custom connector interface to rover controller/ laptop

    | **Pros**                                  | **Cons**                     |
    | ----------------------------------------- | ---------------------------- |
    | Simple and reliable communication         | Limited distance             |
    | Widely supported across microcontrollers  | Requires dedicated pins      |
    | Low implementation complexity             |                     



### Debugging Interface

1. SSD1306 OLED Display

   ![](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/2642/MFG_OLED-128x64-0.96-I2C.jpg?hidebanner=true)

   * $4.99/ each
   * [link to product](https://www.digikey.com/en/products/detail/canaduino-/26095/16822116?gclsrc=aw.ds&gad_source=1&gad_campaignid=20228387720&gbraid=0AAAAADrbLlhpQ4d9FArsR6uA83jTMT7J0&gclid=CjwKCAjw5NvPBhAoEiwA_2egfk7zlAVK1k0b8f6uiH7KLjBmWb7mtO4CJhif04-advz03sf9HDDLVRoC_2AQAvD_BwE)

 | **Pros**                                     | **Cons**                               |
    | ----------------------------------------- | -------------------------------------- |
    | Provides detailed real-time feedback      | Slightly higher complexity than LEDs   |
    | Reduces need for multiple indicator LEDs  | Requires I²C configuration             |
    | Improves debugging and observability      |
    
**Final Choice:** SSD1306 OLED Display (I²C)

**Rationale:** The OLED display was added as a design improvement to replace traditional LED indicators and provide more detailed system feedback. It displays real-time debugging information such as WiFi connection status, MQTT activity, and message transmission events. This significantly improves system observability and simplifies troubleshooting during development and testing. 
