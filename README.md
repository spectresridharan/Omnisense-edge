# OmniSense Edge: Handheld Spice Toxin Detection 🌿🔬
### **A Laboratory-at-the-Gate for International Spice Safety**

**Built for the AMD Slingshot Hackathon 2026.**

---

## 📌 Overview
**OmniSense Edge** is a multimodal, AI-powered handheld scanner designed to prevent the **$200M annual loss** faced by Indian spice exporters due to contamination recalls. By combining **Optical Fluorescence** and **Gas Resistance** sensor fusion with **AMD Kria™ KV260** edge acceleration, we enable real-time detection of Aflatoxins, Sudan Dyes, and Ethylene Oxide (EtO) at the warehouse gate.



---

## 🚀 Key Features
* **Multimodal Sensor Fusion:** Synchronized data capture from **AS7265x** (18-channel spectral) and **BME688** (Gas/VOC) sensors.
* **AMD Edge Acceleration:** Real-time AI inference using the **AMD DPU** for sub-5 second toxin classification.
* **C++ Embedded Firmware:** High-performance, deterministic sensing built on the **ESP32-S3**.
* **Digital Quality Passport:** Instant cloud logging and QR code generation via **Blynk IoT** for global batch traceability.

---

## 🛠️ Tech Stack

### **Hardware**
* **AMD Kria™ KV260** Vision AI Starter Kit (Edge Gateway)
* **ESP32-S3** (Perception Node)
* **AS7265x** Tri-Spectral Sensor Array
* **BME688** AI-Enabled Gas Sensor

### **Software & AI**
* **AMD Vitis™ AI:** Model Quantization & DPU Deployment
* **C++ (Standard 17):** Firmware and hardware-level logic
* **Python:** Edge-gateway automation and cloud bridging
* **Proteus 8 Professional:** Electrical simulation and "Digital Twin" verification

### **Cloud & UI**
* **Blynk IoT Enterprise:** Real-time Dashboard & Mobile Alerts
* **MQTT:** Lightweight telemetry protocol

---

## 🏗️ Architecture
The system operates in three distinct layers to ensure scalability and reliability:

1. **Perception Layer:** An ESP32-S3 unit polls sensors via I2C, triggers the **365nm UV excitation**, and transmits normalized data via MQTT.
2. **Edge Intelligence Layer:** The **AMD Kria KV260** receives telemetry, runs an **INT8-quantized 1D-CNN** via the Vitis AI DPU, and determines the "Pass/Fail" status.
3. **Cloud Trust Layer:** Results are pushed to Blynk for instant visualization and the generation of a **"Digital Quality Passport."**



---

## 📂 Repository Structure
```text
├── firmware/       # C++ source code for the ESP32-S3 Perception Node
├── edge_gateway/   # Python/C++ scripts for the AMD Kria KV260
├── dashboard/      # Web UI configuration and Digital Quality Passport logic
├── simulation/     # Proteus 8 Professional schematics and VSM files
├── docs/           # Technical diagrams, Pitch Deck, and hardware schematics
├── assets/         # Screenshots of Blynk Dashboard and prototype photos
└── README.md       # Executive Summary (You are here!)
