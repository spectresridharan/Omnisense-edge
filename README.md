#OmniSense Edge: Handheld Spice Toxin Detection 🌿🔬
A Laboratory-at-the-Gate for International Spice Safety.

Built for the AMD Slingshot Hackathon 2026.

📌 Overview
OmniSense Edge is a multimodal, AI-powered handheld scanner designed to prevent the $200M annual loss faced by Indian spice exporters due to contamination recalls. By combining Optical Fluorescence and Gas Resistance sensor fusion with AMD Kria™ KV260 edge acceleration, we enable real-time detection of Aflatoxins, Sudan Dyes, and Ethylene Oxide (EtO) at the warehouse gate.

🚀 Key Features
Multimodal Sensor Fusion: Synchronized data capture from AS7265x (18-channel spectral) and BME688 (Gas/VOC) sensors.

AMD Edge Acceleration: Real-time AI inference using the AMD DPU for sub-5 second toxin classification.

C++ Embedded Firmware: High-performance, deterministic sensing built on the ESP32-S3.

Digital Quality Passport: Instant cloud logging and QR code generation via Blynk IoT for global batch traceability.

🛠️ Tech Stack
Hardware: * AMD Kria™ KV260 Vision AI Starter Kit (Edge Gateway)

ESP32-S3 (Perception Node)

AS7265x Tri-Spectral Sensor & BME688 Gas Sensor

Software & AI:

AMD Vitis™ AI (Model Quantization & DPU Deployment)

C++ (Standard 17) for firmware and hardware-level logic

Python for edge-gateway automation

Cloud:

Blynk IoT Enterprise (Real-time Dashboard & Mobile Alerts)

🏗️ Architecture
The system operates in three distinct layers to ensure scalability and reliability:

Perception Node: An ESP32-S3 polls sensors via I2C and transmits data via MQTT.

AMD Edge Hub: The Kria KV260 receives telemetry, runs an INT8-quantized 1D-CNN via the Vitis AI DPU, and determines the "Pass/Fail" status.

Cloud Layer: Results are pushed to Blynk for instant visualization and "Digital Quality Passport" generation.

📂 Repository Structure

├── firmware/           # C++ source code for the ESP32-S3 Perception Node
├── edge_gateway/       # Python/C++ scripts for the AMD Kria KV260
├── ai_model/           # 1D-CNN model architecture and Vitis AI quantization scripts
├── docs/               # Technical diagrams, Pitch Deck, and hardware schematics
├── assets/             # Screenshots of Blynk Dashboard and prototype photos
└── README.md           # You are here!
🔧 Installation & Setup
Firmware: Open the /firmware folder in VS Code with PlatformIO. Update config.h with your Wi-Fi and MQTT credentials, then flash the ESP32-S3.

Edge Hub: Deploy the pre-built DPU image to your AMD Kria KV260. Install dependencies via:

pip install paho-mqtt vitis-ai-library

Cloud: Import the OmniSense.json template into your Blynk Dashboard.

📈 Future Roadmap
Azure Migration: Transitioning backend services to Azure Dasv6 VMs powered by AMD EPYC™ for confidential computing.

On-Device Training: Utilizing the Kria's processing power for local model fine-tuning.

Expansion: Extending detection capabilities to Coffee, Cocoa, and Herbal Medicines.

⚖️ License
Distributed under the MIT License. See LICENSE for more information.
