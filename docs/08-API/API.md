1. Introduction

Each subsystem has its own microcontroller and communicates using structured packets over a wireless connection (WiFi/Bluetooth/ESP-NOW). The human interface sends commands, the wireless subsystem forwards them, the motor subsystem executes movement/drilling commands, and the soil sensor subsystem takes measurements when requested and sends the results back through wireless to the operator.

Wireless transmission does not alter the message format, byte types, or values. Each device uses the destination ID field to determine whether to process or ignore a message.
