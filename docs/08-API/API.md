# Overview

The wireless communication module receives messages from the Human Interface subsystem. When a message is received, the system confirms successful reception before processing and forwarding it.

The received data is then published to the MQTT broker, where it can be monitored in real time using MQTT Explorer. This allows verification of message structure, payload accuracy, and transmission reliability during system operation.

After validation, the message is forwarded to the next subsystem in the rover’s communication pipeline for further processing. This ensures a continuous and reliable flow of data from the Human Interface through the wireless network to downstream modules.

| Message Type | Full Message Format | Payload Description                          | Byte Count                                           | Purpose                              |
| ------------ | ------------------- | -------------------------------------------- | ---------------------------------------------------- | ------------------------------------ |
| Sensor Data  | AZTCvalueYB         | Current magnetic field reading as a string   | 2 bytes AZ + 2 bytes TC + N bytes value + 2 bytes YB | Periodic transmission of sensor data |
| Data Request | AZTCREQYB           | “REQ” indicates a request for sensor data    | 2 bytes AZ + 2 bytes TC + 3 bytes REQ + 2 bytes YB   | Requests current reading             |
| Response     | AZTCvalueYB         | Requested magnetic field reading as a string | 2 bytes AZ + 2 bytes TC + N bytes value + 2 bytes YB | Reply to a request                   |
