# 🧠 Edge Gateway: AMD Kria™ KV260 AI Hub

## 📌 Overview
The Edge Gateway is the "Intelligence Layer" of OmniSense. It acts as a local server that offloads the heavy computational burden of Deep Learning from the handheld nodes. By utilizing the **AMD Kria™ KV260**, we achieve industrial-grade reliability without requiring a constant cloud connection.

## ⚡ Hardware Acceleration via AMD DPU
This project leverages the **Xilinx Deep Learning Processor Unit (DPU)**, a programmable engine dedicated to convolutional neural networks.
- **Model Architecture:** 1D-CNN (Convolutional Neural Network) optimized for sequence-based spectral data.
- **Vitis™ AI Integration:** The model is quantized to **INT8** using the Vitis™ AI Quantizer, allowing the Kria to perform parallel mathematical operations on 18 spectral channels simultaneously.
- **Performance:** Inference latency is reduced by ~40x compared to standard ARM-only execution.

## 📡 Local MQTT Broker
- **Orchestration:** Runs a Mosquitto MQTT broker to aggregate data from multiple Perception Nodes.
- **Security:** Implements local authentication to ensure only authorized handhelds can transmit quality data.

## ⚙️ Setup Instructions
1. Load the Kria KV260 with the **Vitis AI 3.0** SD card image.
2. Clone this folder into the `/home/petalinux/` directory.
3. Run `python3 kria_inference.py` to start the inference engine and cloud bridge.
