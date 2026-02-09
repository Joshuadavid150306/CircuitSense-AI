# CircuitSense AI – Requirements Document

## 1. Project Overview

CircuitSense AI is a hybrid AI-powered embedded hardware debugging system designed for Arduino and ESP32 developers. It combines Large Language Model (LLM) reasoning with deterministic electrical validation to provide reliable and structured troubleshooting assistance.

---

## 2. Problem Statement

Embedded system debugging is challenging due to:

- Hardware-software coupling
- Electrical constraints (voltage, current, logic levels)
- Peripheral communication dependencies (I2C, UART, SPI)
- Bootloader and firmware upload issues

Developers often rely on forums and trial-and-error methods, which increases debugging time and reduces productivity.

---

## 3. Objectives

- Reduce embedded debugging time
- Provide structured hardware-aware diagnostics
- Validate electrical constraints deterministically
- Improve learning efficiency for students and developers
- Minimize AI hallucination using physics-based validation

---

## 4. Functional Requirements

### 4.1 Error Log Analysis
- Accept embedded system error messages
- Identify probable root causes
- Rank possible failure scenarios
- Provide structured troubleshooting steps

---

### 4.2 Code Debugging Support
- Accept Arduino/ESP32 code snippets
- Detect incorrect pin configuration
- Identify baud rate mismatch
- Detect missing libraries
- Suggest corrected code structure

---

### 4.3 Electrical Validation Module
- Accept voltage input parameters (Vin, R1, R2)
- Compute expected Vout using voltage divider formula
- Compare with measured value
- Detect mismatch beyond tolerance range (±5%)
- Generate electrical anomaly warnings

---

### 4.4 Module-Specific Diagnostics
Support for common embedded modules:
- HC-05 Bluetooth (UART mismatch detection)
- L298N Motor Driver (logic vs motor supply validation)
- I2C LCD (address and pull-up detection)
- Voltage Sensors (divider ratio validation)

---

## 5. Non-Functional Requirements

- Response latency under 5 seconds
- Modular backend architecture
- Scalable and extensible knowledge base
- Secure API communication
- Input validation against malformed requests

---

## 6. Target Users

- Engineering students
- Robotics teams
- IoT developers
- Academic laboratories
- Hackathon participants

---

## 7. Future Enhancements

- IDE plugin integration (VS Code / Arduino IDE)
- Real-time serial monitor analysis
- Circuit image-based wiring validation
- Edge-deployable rule engine
- Cloud-based collaborative debugging

---

## 8. Success Metrics

- Reduction in average debugging time
- Improved learning efficiency
- Structured diagnostic output reliability
- Reduced AI-generated hallucinated solutions
