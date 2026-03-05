---
title: Appendix - Module's Major Components Selection Process
---

## Module's Major Components Selection Process

This appendix documents the evaluation process used to select the major components used in the wireless communication module of the subterranean rover. Multiple candidate components were researched and compared based on surface-mount compatibility, electrical performance, cost, reliability, and compatibility with the ESP32 wireless system.

# Power Management

## 3.3V Voltage Regulator Options

### LM3671MF-3.3/NOPB Switching Regulator

(Surface-mount buck converter)

![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/756/409/296%7E4073253-4%7EDBV%7E5_sml.jpg)

$1.98 / each
[link to product](https://www.digikey.com/en/products/detail/texas-instruments/LM3671MF-3-3-NOPB/1590062?gclsrc=aw.ds&gad_source=1&gad_campaignid=17922795960&gbraid=0AAAAADrbLliDAFBPIpsEES-o8UC2Dme-g&gclid=Cj0KCQiA8KTNBhD_ARIsAOvp6DJnM3wgCy8xsaToPEs4HE0GOc8U7AVAgJ4YRaFPrXa1BJDfsKKr5fwaAkz1EALw_wcB)

| Pros-----------------------------------| Cons----------------------------------------------|
| High efficiency (>90%)	             | Requires external inductor and capacitors         |
| Handles ESP32 WiFi current spikes      | Switching noise requires careful PCB layout       |
| Low heat dissipation	                 | Slightly more complex circuit                     |
| Supports wide input voltage range	     |

### AMS1117-3.3 Linear Regulator

![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/235/273/MFG_5272%7ESOT89-3%7E%7E3_sml%28200x200%29.jpg)

$0.50 / each
[link to product](https://www.digikey.com/en/products/detail/evvo/AMS1117-3-3S/24370078?gclsrc=aw.ds&gad_source=1&gad_campaignid=17922795960&gbraid=0AAAAADrbLliDAFBPIpsEES-o8UC2Dme-g&gclid=Cj0KCQiA8KTNBhD_ARIsAOvp6DI2IhmWDFCgX9ksx3NhxcHgdUPOD4v7ir565-CsROMOD6mb5j4FEIEaAlsTEALw_wcB)

| Pros-----------------------------------| Cons----------------------------------|
| Very simple design	                 | Low efficiency                        |
| Requires few external components       | Generates significant heat            |
| Low cost	                             | Not ideal for battery-powered systems |

### TPS62162 Buck Switching Regulator

![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/010/108/920/296%7E4208210%7EDSG%7E8_sml.jpg)

$2.30 / each
[link to product](https://www.digikey.com/en/products/detail/texas-instruments/TPS62162QDSGTQ1/8106150?gclsrc=aw.ds&gad_source=1&gad_campaignid=17922795960&gbraid=0AAAAADrbLliDAFBPIpsEES-o8UC2Dme-g&gclid=Cj0KCQiA8KTNBhD_ARIsAOvp6DLx5XmkVX2FrJnzuIlevHkoFduS_uO5RTDUoJW4m4uVXjfv4GV_AdMaAkc4EALw_wcB)

| Pros-----------------------------------| Cons-----------------------------------|
| High efficiency	                     | Slightly higher cost                   |
| Good load transient response           | Requires additional external components|
| Compact surface mount package	         |

## Choice
Option 1: LM3671MF-3.3/NOPB Switching Regulator

# Rationale

The LM3671MF-3.3 switching regulator was selected because it provides high power efficiency and stable voltage regulation for the ESP32 wireless module. WiFi communication can cause short bursts of high current demand, and the switching regulator can handle these loads without significant voltage drop or heat generation. This makes it ideal for a battery-powered embedded system such as the subterranean rover.

# Sensor

## Digital Temperature Sensor Options

### TC74A0-3.3VCT Digital Temperature Sensor

![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/003/223/402/150%7EC04-036%7EAT%7E5_sml%28200x200%29.jpg)

$1.00 / each
[link to product](https://www.digikey.com/en/products/detail/microchip-technology/TC74A0-3-3VAT/442720?gclsrc=aw.ds&gad_source=1&gad_campaignid=17922795960&gbraid=0AAAAADrbLliDAFBPIpsEES-o8UC2Dme-g&gclid=Cj0KCQiA8KTNBhD_ARIsAOvp6DKDDLrsjWwRMtZbUEAXxpQFr-3JsbeAibw74nSM7nxL7fNa2rCyds0aAnCREALw_wcB)

| Pros-----------------------| Cons-----------------------------|
| Simple I2C communication	 | Limited temperature resolution   |
| Direct 3.3V operation	     | Requires pull-up resistors       |
| Low power consumption	     | Not sealed for harsh environments|
| Small surface mount package|

### MCP9808 High Accuracy Temperature Sensor

![](https://www.microchip.com/_images/ics/medium-MCP9808-MSOP-8.png)

$1.40 / each
[link to product](https://www.microchipdirect.com/product/MCP9808T-E/MS)

| Pros-------------------------------| Cons--------------------------|
| Very high accuracy                 | Higher cost                   |
| Wide temperature measurement range | More complex configuration    |
| I2C communication                  |

## Choice

Option 1: TC74A0-3.3VCT Temperature Sensor

# Rationale

The TC74 temperature sensor was selected because it provides simple digital temperature measurement through the I2C interface while operating directly from a 3.3V supply. It consumes very little power and has a small surface-mount footprint, making it well suited for embedded monitoring of thermal conditions near the wireless electronics.

# Wifi + Bluetooth Module

## Wireless Communication Module Options

### ESP32-S3-WROOM-1-N4 WiFi + Bluetooth Module

![](https://mm.digikey.com/Volume0/opasdata/d220001/derivates/1/300/773/504/MFG_Attachment-2-ESP32-S3-WROOM-1_sml.jpg)

$5.06 / each
[link to product](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)

| Pros--------------------------------| Cons---------------------------------------|
| Integrated WiFi and Bluetooth LE	  | High current draw during WiFi transmission |
| Powerful dual-core processor	      | Requires careful RF PCB layout             |
| Large development ecosystem	      | More complex firmware                      |
| Multiple communication interfaces   |

### ESP8266 WiFi Module

![](https://www.sparkfun.com/media/catalog/product/cache/a793f13fd3d678cea13d28206895ba0c/1/7/17146-WiFi_Module_-_ESP8266__4MB_-01.jpg)

$3.00 / each
[link to product](https://www.sparkfun.com/wifi-module-esp8266-4mb-flash.html)

| Pros-----------------------| Cons---------------------------|
| Low cost	                 | Limited processing capability  |
| Large community support    | Fewer GPIO pins                |
| Simple WiFi communication  | No Bluetooth support           |

### NRF24L01+ RF Transceiver

![](https://www.addicore.com/cdn/shop/files/ad278_nRF24L0_20240818a.jpg?v=1724012277&width=1125)

$2.55 / each
[link to product](https://www.addicore.com/products/nrf24l01-2-4ghz-wireless-transceiver?srsltid=AfmBOoqfbH9sKmAq8AilJjdrx20fNIxioTzZX3aVyGXYEaLgCYxhrLwV)

| Pros-------------------------| Cons-----------------------------|
| Very low power consumption   | Requires external microcontroller|
| Low cost	                   | Limited communication range      |
| Simple SPI interface	       | No built-in WiFi networking      |

## Choice

Option 1: ESP32-S3-WROOM-1-N4 Wireless Module

# Rationale

The ESP32-S3-WROOM-1-N4 module was selected because it integrates WiFi communication, Bluetooth connectivity, and a powerful microcontroller in a single surface-mount module. This significantly simplifies the system architecture by eliminating the need for a separate wireless transceiver and microcontroller. The module also provides extensive community support, libraries, and development tools that reduce development risk and speed up implementation.
