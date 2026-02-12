---
title: Module's Selected Major Components
---

# Module's Selected Major Components

The final major components chosen to establish dependable wireless connection for the subsurface rover are described in the following sections. These parts meet the embedded system's power and surface-mount restrictions while allowing WiFi-based data transfer between the rover and the surface station.

### Power Management

**3.3V Switching Voltage Regulator**

1. TPS62162 Step-Down Buck Converter (Surface-Mount)

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/108/920/296%7E4208210%7EDSG%7E8_sml.jpg)

    * $1.98/each
    * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/TPS62162DSGT/2782703)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | High efficiency ( about greater than 90%) extends battery life | Switching noise requires careful PCB layout |
    | Handles ESP32 peak current during WiFi bursts | Requires inductor and external passives                      |
    | Wide input voltage range supports battery input | More complex than Linear regulators                        |
    | Surface-mount compatible |

**Rationale:** During WiFi transmission, the ESP32 draws significant sudden currents that, if powered by a linear regulator, may result in voltage drop. For battery-powered operation, a switching buck converter was used to minimize heat loss, improve overall power efficiency, and offer a steady 3.3V rail under changing loads.

For more details, review the [Appendix-Component Selection Process-Power Management](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#power-management) 

### Sensor

**Digital Temperature Sensor**

2. TC74A0-3.3VCT (I2C Temperature Sensor, Surface-Mount)

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/223/402/150%7EC04-036%7EAT%7E5_sml%28200x200%29.jpg)

    * $1/each
    * [link to product](https://www.digikey.com/en/products/detail/microchip-technology/TC74A0-3-3VAT/442720?gclsrc=aw.ds&gad_source=1&gad_campaignid=22289277771&gbraid=0AAAAADrbLlhDBa9FUIBwdcd7VYLPN3OB6&gclid=Cj0KCQiA7rDMBhCjARIsAGDBuECtTMQsLWFRmIdZ15_uIujRWbpkOhHiUt6Rx7rgtrCE274AA2dsC8gaApvJEALw_wcB)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Simple I2C interface to ESP32             | It limits the temperature solution                               |
    | Low power comsumption                     | Requires I2C pull-up resistors                                   |
    | Direct 3.3V operation                     | It isn't sealed for harsh conditions/environment                 |
    | Small surface-mount footprint             |

**Rationale:** To keep an eye on the local thermal conditions close to the wireless electronics, the TC74 temperature sensor was chosen. System stability and RF performance might be impacted by temperature variations. Because of its low power consumption, 3.3V operation, and easy setup, the TC74 is a good choice for continuous monitoring in a small embedded system.

For more details, review the [Appendix-Component Selection Process-Sensor](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/Appendix/01-Componet-Selection/Component-Selection-Process/#sensor)

### Wifi + Bluetooth

**Wifi + Bluetooth Module**

1. ESP32-S3-WROOM-1-N4 (Surface-MOunt RF Module)

    ![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/773/504/MFG_Attachment-2-ESP32-S3-WROOM-1_sml.jpg)

    * $5.06/each
    * [link to product](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Integrated Wifi and Bluetooth LE          | High current draw during wifi transmission                       |
    | Large software ecosystem and community support | RF performance depends on antenna layout                    |
    | USB support simplifies programming and debugging | Requires careful RF PCB layout                            |
    | FCC-certified module simplifies compliance | More complex firmware than the simple radios                    |

**Rationale:** Because it combines Bluetooth and fast WiFi connectivity into a single surface-mount module, the ESP32-S3-WROOM-1-N4 was chosen to cut down on PCB complexity and development time. Technical danger is decreased by the amount of community help and accessible libraries. For real-time telemetry and debugging in a Subterranian Rover application, communication dependability and performance are crucial, despite WiFi's increased power use.

For more details, review the [Appendix-Component Selection Process- Wifi+Bluetooth Module](https://vzmorgan-lab.github.io/vzmorgan_EGR314_S26.github.io/Appendix/01-Componet-Selection/Component-Selection-Process/#wifi-bluetooth-module)
