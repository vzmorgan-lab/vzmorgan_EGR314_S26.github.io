## Overview

The wireless subsystem transmits messages between the operator, motor subsystem, and sensor subsystem. The wireless connection broadcasts commands to all devices, but:

  * Each device only acts on messages intended for it.
  * Messages not addressed to a device or malformed are ignored.
  * Turn-based operation is maintained — only one device acts at a time.
  * Commands use simple 1/0 values for easy processing.

Wireless Command — Message Types
|               |Byte 2           |Byte 3         |
|---------------|-----------------|---------------|
|Variable Name  |Move Command     |Sensor Request |
|Variable Type  |uint8_t          |uint8_t        |
|Min Value      |0                |0              |
|Max Value      |1                |1              |
|Example        |1                |0              |

### Motor Start (Byte 1)
  * 0 = stop, 1 = start moving.
  * Sent wirelessly from operator → motor subsystem.
### Sensor Start (Byte 2)
  * 0 = idle, 1 = take sensor reading.
  * Sent wirelessly from operator → sensor subsystem.
### Operation Done (Byte 3)
  * 0 = in progress, 1 = completed.
  * Sent wirelessly from motor/sensor subsystem → operator.
