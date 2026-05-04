# Reflection

## Review of Module’s Success

Overall, the wireless communication subsystem successfully met its primary design requirements for enabling reliable data exchange between the subterranean rover and an external control station. The system was able to transmit sensor data and receive control commands using WiFi communication through the ESP32-WROOM-32, and the integration of MQTT messaging allowed structured and efficient communication between subsystems. The power regulation system using the LM2576HVS-3.3 successfully provided a stable 3.3 V rail, ensuring reliable operation under varying load conditions. One requirement that required refinement during development was improving system observability, which was resolved by replacing basic LED indicators with an OLED debugging display. Overall, the subsystem achieved stable wireless communication, functional power delivery, and effective debugging capability.

---

## Microcontroller / Module Startup Tips

Several key lessons were learned during the initial setup and debugging of the subsystem:

1. Ensure the ESP32 is powered with a stable 3.3 V supply before attempting WiFi initialization.
2. Always verify ground continuity between all subsystem modules to prevent communication failures.
3. Confirm correct I²C pin assignments (GPIO21 and GPIO22) before connecting the OLED display.
4. Test UART communication separately before integrating with the full system.
5. Use serial monitoring early in development to isolate firmware and hardware issues.
6. Add pull-up resistors for I²C devices unless already included on the module.
7. Avoid powering the ESP32 directly from unstable USB or unregulated sources.
8. Verify MQTT broker connectivity before debugging higher-level communication logic.
9. Implement incremental testing instead of full system integration from the start.
10. Double-check pin conflicts between peripherals before final PCB design.

---

## Lessons Learned

1. One of the most important lessons learned was how critical power regulation stability is for wireless embedded systems, especially during high-current WiFi transmission events.
2. I learned how the ESP32 integrates multiple communication protocols (WiFi, UART, I²C) and how careful pin management is required to avoid conflicts.
3. I gained experience designing systems that balance hardware simplicity with functional complexity, especially when choosing between LEDs and an OLED display for debugging.
4. I learned how MQTT improves structured communication between distributed embedded systems.
5. I improved my understanding of switching regulators and how component selection affects efficiency and stability.
6. I learned the importance of modular system design to allow easier debugging and subsystem isolation.
7. I developed stronger PCB design awareness, especially in routing power and communication lines.
8. I learned how real-world debugging often requires both hardware and software troubleshooting simultaneously.
9. I gained experience in translating system requirements into functional block diagrams and hardware architecture.
10. I learned how iterative design feedback significantly improves final system reliability and performance.

---

## Recommendations for Future Students

1. Students should begin by thoroughly testing each subsystem individually before attempting full system integration, as this greatly reduces debugging time later in the project.
2. It is important to carefully plan power distribution early in the design process to avoid instability issues during wireless communication.
3. Students should become familiar with ESP32 pin mapping and peripheral conflicts before finalizing schematic and PCB designs.
4. Using structured communication protocols such as MQTT early in development can simplify system integration and debugging.
5. Future students should document every design decision during development, as this greatly improves the quality of the final report and reflection sections.
