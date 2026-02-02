---
title: Module's Requirements
---

## Module Requirements
The following sections document the requirements that the this module need to fulfills to provide reliable wireless communication between the subterranean rover and the remote operator, enabling command control, telemetry data transmission, and integration with the rover’s main control system.

| **Requirement Description** | **Measure of<br> Threshold** | **Target<br>Measure** |**Stretch<br>Requirement<br>(Y-N)**|
|-----------------------------| ----------------- | ----------------- | :-----: |
| Surface mounted, 3.3V switching power regulatore | 3.2 Volts | 3.3 Volts | No |
| Surface mounted microcontroller | 1 PIC or ESP | 8-bit PIC | No |
| Wireless Communication | Able to send or receive a Wi-Fi data | Send and receive Wi-Fi Data to MQTT | Yes |
| Antenna| Antenna provides basic connectivity | The external antenna positioned for improved underground signal strength | Yes |
| Data transmission | Can transmit at least one sensor or command value | Mulitple telemetry and command values trasnmitted reliably | Yes |
| System integration with Rover Controller | Wireless module can communicate with rover controller | Commands and telemetry reliably exchanged without data loss | No |
|Range/Reliability | Maintains communication at a short range | Maintains reliable communication through obstacles | Yes |
