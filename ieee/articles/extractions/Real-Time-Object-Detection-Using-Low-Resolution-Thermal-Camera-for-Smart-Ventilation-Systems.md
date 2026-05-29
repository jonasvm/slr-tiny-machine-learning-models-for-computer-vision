## Paper ID: Real-Time-Object-Detection-Using-Low-Resolution-Thermal-Camera-for-Smart-Ventilation-Systems

### Basic Info
- Authors: Jun-Hee Lee and Eung-Tea Kim
- Year: 2025
- Title: Real-Time Object Detection Using Low-Resolution Thermal Camera for Smart Ventilation Systems
- Source: IEEE Access, Volume 13, 2025
- Type: Experimental / Methodological

### Problem & Context
- Task: Object detection
- Objective: Develop a lightweight real-time object detection model for low-resolution thermal images in smart ventilation systems.
- Application domain: Smart ventilation systems, occupancy detection, thermal imaging.
- Scenario: Embedded, edge, MCU-based smart ventilation system.
- TinyML relevance: Yes
- TinyML justification: The paper targets real-time object detection on an STM32 MCU with explicit Flash, RAM, latency, and MAC constraints.

### Model / Method
- Model: FLARE (Fast and Lightweight Architecture for Real-time Estimation)
- Architecture family: CNN
- Techniques: Feature Compression Block, Spatial Denoise Block, Feature Pyramid Network, TOI data augmentation, parameter quantization, computation optimization.
- Framework: ST X-CUBE-AI
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: STM32F767ZIT6 MCU; Raspberry Pi 4B used for additional comparison with YOLOv8n.
- Hardware type: MCU; CPU/SoC for Raspberry Pi comparison.
- Processor / microcontroller: ARM Cortex-M7 STM32F767ZIT6
- Clock frequency: 216 MHz
- SRAM / RAM: 512 KB SRAM on STM32F767ZIT6; reported RAM usage 256.00 KiB for FLARE 1-channel.
- Flash / ROM / Storage: 2 MB Flash on STM32F767ZIT6; reported Flash usage 281.30 KiB for FLARE 1-channel.
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, latency, compute, MAC operations, low-resolution sensor noise, embedded resource constraints.

### Dataset
- Name: Not reported
- Type: Private
- Dataset size: 10,000 collected images; training 8,000, validation 1,000, test 1,000; training expanded to 50,000 images using TOI augmentation.
- Number of classes: Not reported
- Input resolution: 32 × 24 thermal sensor resolution; model input reported as 256 × 256 × 1 or 256 × 256 × 3 depending on configuration.
- Data modality: Low-resolution thermal image.

### Metrics
- Accuracy: Not reported
- mAP: 95.03% on STM32F767ZIT6 for FLARE 1-channel; 95.62% on Raspberry Pi 4B.
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: 303.537 ms on STM32F767ZIT6 for FLARE 1-channel; 10.14 ms on Raspberry Pi 4B.
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: 44,331,902 MACs for FLARE 1-channel.
- RAM usage: 256.00 KiB on STM32F767ZIT6 for FLARE 1-channel; 280.00 KiB on Raspberry Pi 4B.
- Flash usage: 281.30 KiB on STM32F767ZIT6 for FLARE 1-channel; 281.65 KiB on Raspberry Pi 4B.
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Lightweight CNN architecture, Feature Compression Block, Spatial Denoise Block, Feature Pyramid Network, TOI thermal data augmentation, parameter quantization, computation optimization.
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Feature map compression through Feature Compression Block.
- Hardware-specific optimization: Optimized for STM32 MCU deployment using ST X-CUBE-AI.
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: 281.30 KiB on STM32F767ZIT6 for FLARE 1-channel.
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: 303.537 ms on STM32F767ZIT6 for FLARE 1-channel.
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: Yes
- Reason: The model is deployed and evaluated on an STM32F767ZIT6 MCU with explicit Flash, RAM, MAC, and latency measurements, targeting real-time embedded inference.

### Benchmarking / Standardization
- Benchmark used: Not reported
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: MobileNetv2-SSD, YOLOv1, YOLOv8n.
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: FLARE achieved 95.03% mAP on STM32F767ZIT6 using 281.30 KiB Flash, 256.00 KiB RAM, 44.3M MACs, and 303.537 ms inference time. On Raspberry Pi 4B, FLARE achieved 95.62% mAP and 10.14 ms inference time, outperforming YOLOv8n in memory usage and speed.

### Limitations
- The paper does not report energy per inference or power consumption.
- The paper does not report public dataset availability, code availability, or model artifacts.
- Execution without a full operating system is not explicitly reported.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes FLARE, an ultra-lightweight CNN-based thermal object detection model optimized for real-time MCU deployment in smart ventilation systems.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Lee et al. | 2025 | Object detection | FLARE | Feature Compression Block, Spatial Denoise Block, TOI augmentation | STM32F767ZIT6 MCU | Private low-resolution thermal dataset | 95.03% mAP on STM32F767ZIT6 | 303.537 ms | N/A | 256.00 KiB | 281.30 KiB | N/A | ST X-CUBE-AI | N/A | N/A | Yes |
