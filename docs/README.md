# 📄 Documentation: OmniSense Strategy & Design

This directory contains the high-level design documents, research papers, and pitch materials that form the foundation of the **OmniSense Edge** project.

## 📁 Contents

### 1. Pitch Deck
- `OmniSense_Pitch_Slingshot.pdf`: The complete 12-slide presentation covering the Problem Statement, AMD Solution, and Business Model.

### 2. Hardware Schematics
- `Perception_Node_Schematic.pdf`: High-resolution circuit diagram of the ESP32-S3 interfaced with the AS7265x Triad and BME688.
- `BOM_List.csv`: Bill of Materials including part numbers for LCSC and DigiKey.

### 3. Architecture Diagrams
- `System_Architecture.png`: A multi-layer diagram showing the flow from the physical spice sample to the Azure Cloud.
- `Data_Flow_Logic.png`: Visualization of the 1D-CNN inference pipeline on the AMD Kria DPU.

## 🔬 Research References
- **Aflatoxin Detection:** Based on spectroscopic analysis research indicating fluorescence peaks at ~450nm under 365nm UV excitation.
- **Ethylene Oxide Monitoring:** Utilizing BME688 gas resistance shifts to detect chemical residues in sealed warehouse environments.
