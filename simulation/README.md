# 💻 Virtual Prototyping: Proteus 8 Professional

## 📌 Overview
To ensure 100% hardware reliability, the OmniSense Perception Node was first developed as a "Digital Twin" in **Proteus 8 Professional**. This allowed us to verify the electrical integrity and communication protocols before physical prototyping.

## 🔬 Simulation Methodology
1. **I2C Protocol Analysis:** Using the Proteus **I2C Debugger**, we simulated the exact hexadecimal responses of the AS7265x sensors. This verified that our C++ buffers could handle the 18-channel data load without crashing.
2. **Power Rail Stability:** Simulated the current draw during the "UV Flash" event to ensure the LDO regulator wouldn't brown-out the ESP32.
3. **Firmware Verification:** The `.hex` file generated from PlatformIO was loaded directly into the Proteus ESP32 model to confirm the MQTT state machine logic.

## 📁 Files Included
- `OmniSense_S3_Final.pdsprj`: The complete electrical schematic and VSM simulation.
- `Logic_Analyzer_Capture.png`: Proves the timing synchronization between the UV LED trigger and the I2C Start condition.
