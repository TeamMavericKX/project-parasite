# PARASITE: Polymorphic Adaptive Response And Sentinel for Infrastructure Threat Elimination

**PARASITE** is a complete, end-to-end security ecosystem designed to protect the firmware of embedded systems within Critical National Infrastructure (CNI). It features a hyper-efficient, 1.2KB on-device agent that provides real-time threat detection, hardware-enforced containment, and cryptographically secure reporting to a scalable cloud backend.

![Project Parasite Infographic](https://raw.githubusercontent.com/KishoreMuruganantham/project-parasite/refs/heads/main/Project%20Parasite%20Infographic.png "Project Parasite Infographic")
---
This repository contains the complete design documentation for the PARASITE project, developed for the RIFT'26 Hackathon. The documentation spans 16 phases, covering the entire project lifecycle from initial research and threat modeling to detailed hardware, firmware, and cloud architecture, culminating in a final presentation and packaging plan.

---

## 🚀 Key Features

-   **Hyper-Efficient Agent:** A sub-1.5KB firmware agent written in Rust, designed to run on resource-constrained microcontrollers with less than 0.1% CPU overhead.
-   **Zero-Day Threat Detection:** Employs a behavior-based **Sentinel** engine that uses entropy analysis to detect polymorphic and unknown malware, bypassing the need for traditional signatures.
-   **Hardware-Enforced Containment:** The **Guardian** engine uses the MCU's native Memory Protection Unit (MPU) to instantly quarantine threats in microseconds, preventing lateral movement or damage without crashing the device.
-   **Secure, Actionable Intelligence:** The **Reporter** module transmits anonymized, cryptographically signed threat reports to a cloud backend, transforming vulnerable endpoints into a distributed national threat intelligence network.
-   **Robust Security Foundation:** The system is built on a foundation of a secure bootloader (MCUBoot), a hardware-backed key hierarchy using a Secure Element, and a fail-safe, standards-aligned (IETF SUIT) OTA update mechanism.
-   **Comprehensive Design:** The project is documented across 16 phases, providing a professional-grade blueprint for a real-world deployment.

---


## 📂 Project Structure & Documentation

This repository is structured as a series of detailed design documents, each representing a phase in the project's development. The best place to start is the master index, `00_Index_and_Summary.md`.

-   **`[00_Index_and_Summary.md](./00_Index_and_Summary.md)`**: The master index, project roadmap, and executive summary.

### Part 1: Research & Architecture (Phases 01-03)
-   **`[01_Research_and_Validation.md](./01_Research_and_Validation.md)`**: Deep dive into the firmware threat landscape and prior art.
-   **`[02_Threat_Modeling.md](./02_Threat_Modeling.md)`**: STRIDE/DREAD analysis, attack surface mapping, and security requirements.
-   **`[03_System_Architecture.md](./03_System_Architecture.md)`**: The high-level design of the firmware, hardware, and cloud components.

### Part 2: Hardware Design (Phases 04-07)
-   **`[04_Bill_of_Materials.md](./04_Bill_of_Materials.md)`**: Component selection, cost analysis, and procurement strategy.
-   **`[05_Circuit_Design.md](./05_Circuit_Design.md)`**: Detailed schematics and electronic design for the prototype.
-   **`[06_Bootloader_Design.md](./06_Bootloader_Design.md)`**: Design of the secure boot chain of trust.
-   **`[07_Hardware_Prototype.md](./07_Hardware_Prototype.md)`**: Plan for PCB fabrication, assembly, and hardware bring-up.

### Part 3: Software & Protocol Design (Phases 08-12)
-   **`[08_Firmware_Core_Development.md](./08_Firmware_Core_Development.md)`**: Detailed implementation plan for the Sentinel, Guardian, and Reporter modules in Rust.
-   **`[09_Attestation_Protocol.md](./09_Attestation_Protocol.md)`**: Design of the remote integrity verification protocol.
-   **`[10_Secure_OTA_Update.md](./10_Secure_OTA_Update.md)`**: Design of the secure, fail-safe firmware update mechanism.
-   **`[11_Key_Management.md](./11_Key_Management.md)`**: The complete lifecycle plan for all cryptographic keys.
-   **`[12_Verifier_Backend.md](./12_Verifier_Backend.md)`**: Architecture of the scalable, Go-based cloud backend.

### Part 4: Integration & Finalization (Phases 13-16)
-   **`[13_System_Integration.md](./13_System_Integration.md)`**: The plan for combining all components into a functional end-to-end system.
-   **`[14_Testing_and_Certification.md](./14_Testing_and_Certification.md)`**: The comprehensive strategy for validation, penetration testing, and compliance mapping.
-   **`[15_Troubleshooting_Guide.md](./15_Troubleshooting_Guide.md)`**: A practical guide for debugging and failure analysis.
-   **`[16_Final_Packaging_and_Pitch.md](./16_Final_Packaging_and_Pitch.md)`**: The final project summary, pitch deck outline, and prototype packaging design.

---

## 🛠️ Technology Stack

-   **On-Device Firmware:**
    -   **Language:** Embedded Rust (`no_std`)
    -   **Key Crates:** `cortex-m`, `heapless`, `p256`, `chacha20poly1305`, `defmt`
    -   **Bootloader:** MCUBoot
-   **Hardware Prototype:**
    -   **MCU:** STMicroelectronics STM32L562QE (ARM Cortex-M33 with TrustZone)
    -   **Secure Element:** Infineon OPTIGA™ Trust M
-   **Cloud Backend:**
    -   **Language:** Go
    -   **Framework:** Gin
    -   **Databases:** PostgreSQL with TimescaleDB extension
    -   **Deployment:** Docker & Kubernetes

---

This project was created by princetheprogrammer for the RIFT'26 Hackathon.
