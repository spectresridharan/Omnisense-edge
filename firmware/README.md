# 🔌 Firmware: OmniSense Perception Node (ESP32-S3)

## 📌 Overview
This directory houses the low-latency, deterministic firmware for the handheld scanning unit. Developed in **C++17**, this firmware is optimized for the **ESP32-S3** dual-core architecture to handle high-speed I2C polling and real-time data serialization.

## 🛠️ Technical Specifications
- **Real-Time Task Management:** Utilizes FreeRTOS tasks to separate "Sensing" from "Communication," ensuring sensor timing is never interrupted by Wi-Fi latency.
- **Protocol:** MQTT over WebSockets for lightweight, asynchronous data transfer to the AMD Kria Gateway.
- **Data Structure:** Custom JSON payloads using `ArduinoJson` to encapsulate 18-channel spectral matrices and BME688 gas resistance arrays.

## 🔬 Sensor Fusion Logic
1. **The Sync-Flash Capture:** To detect Aflatoxins, the firmware triggers a 365nm UV LED interrupt. Within 50ms, it initiates a global capture across the AS7265x Triad to catch the specific fluorescence peak.
2. **Environmental Compensation:** Raw gas data from the BME688 is normalized against ambient temperature and humidity before being packaged.

## 📂 File Manifest
- `src/main.cpp`: Main execution loop and I2C ISR (Interrupt Service Routine).
- `src/SensorManager.h`: Hardware abstraction layer for the AS72651/2/3 chipset.
- `platformio.ini`: Dependency management for the ESP32-S3 build environment.

## 🚀 Deployment
1. Install **PlatformIO** in VS Code.
2. Copy `src/secrets.example.h` to `src/secrets.h` and enter credentials.
3. Use `PIO Build & Upload` to flash the target hardware.
