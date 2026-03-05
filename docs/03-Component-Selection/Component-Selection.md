---
title: Module's Selected Major Components
---

## Module's Selected Major Components

The final major components chosen to establish dependable wireless communication for the Subterranian Rover are described in the following sections. These components meet the embedded system’s surface-mount design requirements and power constraints while enabling reliable WiFi communication between the rover electronics and the external control station. The selected components support wireless data transmission using MQTT over WiFi, provide system power regulation, and include user interface indicators for system status and diagnostics.

### Power Management

**3.3V Switching Voltage Regulator**

1. Buck Switching Regulator IC Positive Fixed 3.3V (Surface-Mount)
   LM3671MF-3.3/NOPB

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/756/409/296%7E4073253-4%7EDBV%7E5_sml.jpg)

    * $1.98/each
    * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/LM3671MF-3-3-NOPB/1590062)

    | **Pros**                                  | **Cons**                                                         |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | High efficiency ( about greater than 90%) improves power efficiency and reduces heat generation | Switching noise requires careful PCB layout |
    | Handles ESP32 peak current during WiFi bursts | Requires inductor and external passives                      |
    | Wide input voltage range supports battery input | More complex than Linear regulators                        |
    | Surface-mount compatible |

2. AMS1117-3.3 Linear Regulator

![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/002/141/970/MFG_AMS1117-3.3_sml.jpg)

   * $0.60 / each
   * [AMS1117-3.3 Linear Regulator](https://www.digikey.com/en/products/detail/umw/AMS1117-3-3/17635254)

|**Pros**             |**Cons**                          |
|Very simple circuit  | Low efficiency                   |
|Low cost	          | Generates heat                   |
|Minimal external components | Not ideal for battery-powered systems|

 **Final Choice:** LM3671MF-3.3/NOPB

**Rationale:** The LM3671MF-3.3 switching regulator was selected because it provides high efficiency, supports the peak current requirements of the ESP32 WiFi module, and operates well from a battery input. Although switching regulators require additional passive components, the improved power efficiency is important for extending battery life in the rover system.

For more details, review the [Appendix-Component Selection Process-Power Management](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#power-management) 

### Sensor

**Temperature Sensor**

1. TC74A0-3.3VCT

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/223/402/150%7EC04-036%7EAT%7E5_sml%28200x200%29.jpg)

   * $1.00 / each
   * [link to product](https://www.digikey.com/en/products/detail/microchip-technology/TC74A0-3-3VAT/442720?gclsrc=aw.ds&gad_source=1&gad_campaignid=17922795960&gbraid=0AAAAADrbLliDAFBPIpsEES-o8UC2Dme-g&gclid=Cj0KCQiA8KTNBhD_ARIsAOvp6DI4xecToUI6zJUDKrKnRQKlIwXQnsmLM6Yfcl943HMkYQdVr3-PV1UaAg2TEALw_wcB)

|**Pros**               |**Cons**                   |
|-----------------------|---------------------------|
| Simple I2C interface  | Limited resolution        |
| Direct 3.3V operation | Requires pull-up resistors|

2. LM35DZ/NOPB

![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/001/201/567/296%7EZ03A%7E%7E3_sml%28200x200%29.jpg)

   * $1.67/each
   * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/LM35DZ-NOPB/32489)

|**Pros**             |**Cons**              |
| Simple analog output|	Requires ADC         |
| Good accuracy	    | More noise sensitive |
| Easy interface	    | Requires calibration |

**Final Choice:** TC74A0-3.3VCT

**Rationale:** The TC74 sensor was selected because it provides simple I2C communication, operates directly from a 3.3V supply, and has low power consumption, making it well suited for monitoring thermal conditions near the wireless electronics.

### Power Source

**Battery**

1. 18650 Lithium-Ion Battery

    ![](https://www.18650batterystore.com/cdn/shop/files/52q45634564526.jpg?v=1738986702&width=900)

$4.99 / each
[link to product](https://www.18650batterystore.com/products/samsung-25r-18650)

|**Pros**             |**Cons**                    |
|---------------------|----------------------------|
| High energy density | Requires charging circuitry|
| Rechargeable	       | Safety considerations      |

2. LiPo Battery Pack (3.7V)

   ![](https://cdn-shop.adafruit.com/970x728/328-06.jpg)

   * $14.95
   * [Link of Product](https://www.adafruit.com/product/328?srsltid=AfmBOooP7JS0PpX0v6VQ8-9dQ1CtpmQ5a4_LUi1XBD5sqMhyAZ_wtQyy)

|**Pros**            |**Cons**                  |
| Lightweight	      | Shorter lifespan         |
| Rechargeable       | Requires protection circuitry|
| Compact            | Higher cost              | 

## Final Choice: 18650 Lithium-Ion Battery

**Rationale:** The 18650 lithium-ion battery provides high energy density, rechargeable operation, and sufficient current capacity to support the ESP32 and other electronics. This makes it well suited for portable embedded systems such as the subterranean rover.

### Wifi + Bluetooth

**Wifi + Bluetooth Module**

1. ESP32-S3-WROOM-1-N4 (Surface-Mount RF Module)

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/773/504/MFG_Attachment-2-ESP32-S3-WROOM-1_sml.jpg)

    * $5.06/each
    * [link to product](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)

    | **Pros**                                  | **Cons**                                                           |
    | -----------------------------------------------| ------------------------------------------------------------- |
    | Integrated Wifi and Bluetooth connectivity     | High current draw during wifi transmission                    |
    | Large software ecosystem and community support | RF performance depends on antenna layout                      |
    | Multiple GPIO pins for LEDs, sensors, and control | Requires careful RF PCB layout                             |
    | Supports UART communication with rover controller | More complex firmware than the simple radios               |

2. ESP8266 (4MB Flash)
   
   ![](https://www.sparkfun.com/media/catalog/product/cache/a793f13fd3d678cea13d28206895ba0c/1/7/17146-WiFi_Module_-_ESP8266__4MB_-01.jpg)

   * $7.50/each
   * [Link of Product](https://www.sparkfun.com/wifi-module-esp8266-4mb-flash.html)

|**Pros**          |**Cons**                 |
| Low cost	       | No Bluetooth            |
| Large community support | Lower processing power|
| Simple WiFi connectivity |	Fewer peripherals|

3. NRF52840 Module

![](https://www.sparkfun.com/media/catalog/product/cache/a793f13fd3d678cea13d28206895ba0c/2/1/21605-_WRL-_01.jpg)

   * $7.00 / each
   * [Link to Product](https://www.sparkfun.com/nordic-nrf52840-ble-module-mdbt50q-1mv2.html)

|**Pros**            |**Cons**            |
| Low power wireless	| Higher cost        |
| Bluetooth support	| No integrated WiFi |
| Good documentation | Smaller ecosystem  |

## Final Choice: ESP32-S3-WROOM-1-N4

**Rationale:** The ESP32-S3-WROOM-1-N4 module was selected because it integrates WiFi connectivity, processing capability, and multiple communication interfaces into a single surface-mount module, reducing PCB complexity. The module supports UART communication with the rover controller and WiFi communication with the MQTT server, allowing real-time telemetry transmission and command reception. Its extensive software ecosystem and development tools significantly reduce development risk.

For more details, review the [Appendix-Component Selection Process- Wifi+Bluetooth Module](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/Appendix/01-Componet-Selection/Component-Selection-Process/#wifi-bluetooth-module)

### Communication Interface

**Digital Serial Communication Connection**

1. Custom connector interface to rover controller/ laptop

    | **Pros**                                  | **Cons**                                                         |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Simple and reliable serial communication  | Requires additional pins                                         |
    | Compatible with both ESP32 and PIC microcontrollers | Limited communication distance                         |
    | Low hardware complexity                   |                     

**Rationale:** UART was selected as the communication interface between the wireless subsystem and the rover controller board. This protocol is widely supported by embedded systems and provides simple bidirectional communication using only two signal lines (TX and RX). It is ideal for transmitting telemetry data and receiving control commands from other rover subsystems.
