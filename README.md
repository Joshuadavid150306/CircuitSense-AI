# CircuitSense AI
## Hybrid AI-Based Embedded Hardware Debugging Framework

---

## 1. Abstract

CircuitSense AI is a hybrid diagnostic framework designed for embedded systems such as Arduino and ESP32. The system integrates Large Language Model (LLM) reasoning with deterministic electrical validation to provide reliable, structured, and hardware-aware debugging assistance.

Unlike generic AI chat systems, CircuitSense AI separates probabilistic reasoning from physics-based validation to reduce hallucinated outputs and improve technical reliability.

---

## 2. Problem Context

Embedded debugging involves:

- Hardware-software coupling
- Electrical constraints (voltage, current, logic levels)
- Peripheral communication protocols (I2C, UART, SPI)
- Firmware flashing and bootloader dependencies

Traditional debugging relies on:
- Manual datasheet lookup
- Forum search
- Trial-and-error

This increases debugging latency and reduces productivity.

---

## 3. Core Innovation

CircuitSense AI introduces a hybrid architecture:

LLM-Based Semantic Reasoning  
+  
Deterministic Electrical Rule Engine  
+  
Module-Specific Knowledge Graph  

This layered approach ensures structured and reliable embedded diagnostics.

---

## 4. System Architecture

User Interface  
↓  
Flask REST API  
↓  
Parallel Diagnostic Layer  
→ LLM Diagnostic Engine  
→ Electrical Validation Engine  
→ Module Knowledge Base  
↓  
Response Synthesizer  
↓  
Structured Debug Report

---

## 5. Key Components

### 5.1 LLM Diagnostic Engine
- Parses embedded error logs
- Identifies probable root causes
- Generates structured troubleshooting steps
- Ranks failure hypotheses

### 5.2 Electrical Validation Engine
Implements deterministic validation:

Voltage Divider:
Vout = Vin × (R2 / (R1 + R2))

ADC Scaling:
ADC_value = (Vin / Vref) × 1023

Tolerance:
Flags anomaly if deviation > ±5%

This prevents physically impossible AI suggestions.

### 5.3 Module Knowledge Base
Includes structured troubleshooting for:
- HC-05 Bluetooth
- L298N Motor Driver
- I2C LCD
- Voltage Sensors

Each module defines:
- Failure states
- Dependency relationships
- Corrective sequences

---

## 6. Reliability Strategy

To mitigate AI hallucination:

- Physics-based validation layer
- Root cause ranking
- Structured output formatting
- Module constraint enforcement

This increases diagnostic trustworthiness.

---

## 7. Scalability Roadmap

Phase 1 – Web Prototype  
Phase 2 – IDE Plugin Integration  
Phase 3 – Real-Time Serial Monitor Analysis  
Phase 4 – Circuit Image Recognition  

---

## 8. Repository Structure

CircuitSense-AI/
│
├── README.md
├── requirements.md
├── design.md
└── (future implementation files)

---

## 9. Design Philosophy

CircuitSense AI follows a hybrid intelligence model:

Probabilistic reasoning  
+  
Deterministic physical validation  
+  
Domain-specific constraint graphs  

This ensures structured, reliable, and technically sound embedded debugging.

---

## 10. Current Status

✔ Documentation Completed  
✔ System Architecture Defined  
✔ Hybrid AI Framework Designed  
⬜ Prototype Under Development  
⬜ AI Integration Planned  

This repository represents the architectural and conceptual foundation of CircuitSense AI for the idea submission stage.
