# CircuitSense AI – Design Document

---

## 1. System Overview

CircuitSense AI is designed as a hybrid diagnostic framework that combines:

1. LLM-based semantic reasoning
2. Deterministic electrical validation
3. Module-specific troubleshooting knowledge graphs

The system separates probabilistic AI reasoning from physics-based validation to improve reliability and reduce hallucinated debugging suggestions.

---

## 2. High-Level Architecture

User Interface (Web)
        |
REST API Layer (Flask Backend)
        |
------------------------------------------------
|  LLM Diagnostic Engine                      |
|  Electrical Rule Engine                     |
|  Module Knowledge Base                      |
------------------------------------------------
        |
Response Synthesizer
        |
Structured Debug Report

---

## 3. Component Design

### 3.1 Frontend Layer

Responsibilities:
- Accept user inputs:
  - Error logs
  - Code snippets
  - Voltage parameters
  - Module selection
- Send structured JSON request to backend
- Display formatted diagnostic report

Technologies:
- HTML5
- CSS3
- JavaScript

---

### 3.2 Backend API Layer

Responsibilities:
- Input schema validation
- Request routing
- Parallel execution of diagnostic modules
- Merge results into structured output

Technology:
- Python 3.x
- Flask REST API

---

### 3.3 LLM Diagnostic Engine

Purpose:
Handles semantic understanding of embedded system issues.

Functions:
- Parse error logs
- Interpret board-specific messages
- Rank probable root causes
- Generate corrective guidance

Example Patterns:
- `resp=0x00` → Bootloader or UART issue
- `I2C device not detected` → Address or pull-up problem
- `Brownout detector was triggered` → Power supply instability

Output:
Structured hypothesis list with confidence ranking.

---

### 3.4 Electrical Rule Engine

Purpose:
Ensure electrical consistency using deterministic formulas.

#### Implemented Validations

Voltage Divider:
Vout = Vin × (R2 / (R1 + R2))

ADC Scaling:
ADC_value = (Vin / Vref) × 1023

Tolerance Validation:
If |Measured - Expected| > 5% → Flag anomaly

Logic Level Validation:
5V ↔ 3.3V compatibility checks

This module prevents AI from suggesting physically impossible fixes.

---

### 3.5 Module Knowledge Base

Structured troubleshooting graphs for:

- HC-05 Bluetooth
- L298N Motor Driver
- I2C LCD
- Voltage Sensors

Each module contains:
- Known failure states
- Dependency mapping
- Sequential validation steps
- Recommended corrections

This ensures domain-specific accuracy.

---

## 4. Data Flow Execution

1. User submits diagnostic request.
2. Backend validates JSON schema.
3. Request split into parallel tasks:
   - Semantic analysis (LLM)
   - Deterministic computation (Rule Engine)
4. Module knowledge constraints applied.
5. Results merged.
6. Structured response returned.

---

## 5. Reliability Strategy

Problem:
LLMs may hallucinate hardware solutions.

Mitigation Strategy:
- Physics-based validation layer
- Root cause ranking
- Module constraint enforcement
- Structured output formatting

This hybrid design increases trustworthiness in embedded diagnostics.

---

## 6. Scalability Plan

Future expansion includes:

- IDE plugin integration
- WebSocket-based real-time serial monitoring
- Circuit image recognition module
- Edge-deployable lightweight rule engine
- Cloud-based multi-user deployment

---

## 7. Security Considerations

- Input sanitization
- Rate limiting
- Secure API key storage
- Validation against malformed requests

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

Probabilistic reasoning (LLM)
+
Deterministic physical validation
+
Domain-specific knowledge graphs

This layered approach ensures structured, reliable, and technically sound embedded debugging assistance.
