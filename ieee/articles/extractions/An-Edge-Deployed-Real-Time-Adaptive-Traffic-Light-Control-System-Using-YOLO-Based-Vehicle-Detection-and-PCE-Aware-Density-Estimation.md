## Paper ID: An-Edge-Deployed-Real-Time-Adaptive-Traffic-Light-Control-System-Using-YOLO-Based-Vehicle-Detection-and-PCE-Aware-Density-Estimation

TinyML classification: Near-TinyML — the vision model is deployed on Jetson Nano/Xavier NX edge GPU hardware rather than explicit MCU-class TinyML deployment.

### Basic Info
- Authors: Mehwish Raza, Majida Kazmi, Hamza Munir Kidwai, Hashim Raza Khan, Saad Ahmed Qazi, Kamran Arshad, Khaled Assaleh
- Year: 2025
- Title: An Edge-Deployed Real-Time Adaptive Traffic Light Control System Using YOLO-Based Vehicle Detection and PCE-Aware Density Estimation
- Source: IEEE Access
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: Develop an edge-deployed real-time adaptive traffic light control system using YOLO-based vehicle detection, PCE-aware density estimation, and adaptive signal scheduling.
- Application domain: Intelligent transportation systems and smart traffic management
- Scenario: Edge, embedded, IoT, roadside traffic monitoring
- TinyML relevance: Partial
- TinyML justification: The system performs on-device edge inference using Jetson Nano/Xavier NX and deploys the ATLC module on Portenta H7, but the computer vision inference is not demonstrated on MCU-class TinyML hardware.

### Model / Method
- Model: YOLOv7-tiny, YOLOv8-nano, YOLOv8-small, YOLO-NAS-small
- Architecture family: CNN
- Techniques: Lightweight YOLO models, context-based data augmentation, TensorRT optimization, hyperparameter tuning, PCE-aware traffic density estimation, rule-based adaptive traffic light control
- Framework: PyTorch 1.8.1, TensorRT, SUMO, TraCI
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: Jetson Nano, Jetson Xavier NX, Portenta H7
- Hardware type: GPU / SoC / MCU
- Processor / microcontroller: Jetson Nano: Quad Core ARM Cortex A57 MP Core processor; Jetson Xavier NX: 6-core NVIDIA Carmel ARM v8.2 64-bit CPU; Portenta H7: ARM Cortex-M7 and ARM Cortex-M4
- Clock frequency: Portenta H7: 480 MHz, 240 MHz; Jetson Nano and Jetson Xavier NX clock frequency not reported
- SRAM / RAM: Jetson Nano: 4 GB 64-bit LPDDR4 25.6 GB/s; Jetson Xavier NX: 8 GB 128-bit LPDDR4 51.2 GB/s; Portenta H7: 8 MB SDRAM
- Flash / ROM / Storage: Portenta H7: 16 MB Flash; Jetson storage not reported
- Power consumption: Jetson Nano: 5 W–10 W nominal power envelope; Jetson Xavier NX: 10 W–15 W nominal power envelope; Portenta H7: 3.7–5 V Li-Po cell, 700 mAh
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Model size, FPS, edge deployment, real-time latency, power consumption, communication, computational complexity

### Dataset
- Name: Custom Karachi traffic dataset; KITTI; PASCAL VOC; DAWN
- Type: Private and public
- Dataset size: 1,373 source images before augmentation; 2,726 images after augmentation; 2,182 training, 272 validation, 272 testing
- Number of classes: 8
- Input resolution: 1280 × 738 pixels
- Data modality: Traffic video and images; RGB image, grayscale image, greenscale image

### Metrics
- Accuracy: YOLOv8-nano achieved 89.30% mAP in RGB, 90.20% in Gray, and 94.90% in Green; YOLO-NAS-small achieved 95.40% mAP in Gray
- mAP: Up to 90% reported for the deployed YOLO-based vehicle detection system; edge deployment mAP reached 83.7% on Allama Shabbir Usmani and 81.45% on Teen Talwar using YOLOv8-nano
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported
- FPS: Up to 74 FPS reported; YOLOv8-nano achieved 74.67 FPS in RGB on the GPU workstation; on Jetson Xavier NX, YOLOv8-nano achieved 35 FPS on Allama Shabbir Usmani and 33.5 FPS on Teen Talwar
- Throughput: Not reported
- Model size: YOLOv8-nano: 6.0 MB; YOLOv7-tiny: 11.8 MB; YOLOv8-small: 21.5 MB; YOLO-NAS-small: 244.4 MB
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Jetson Nano: 5 W–10 W nominal power envelope; Jetson Xavier NX: 10 W–15 W nominal power envelope

### Optimization
- Techniques used: Lightweight YOLO selection, TensorRT optimization, context-based augmentation, hyperparameter grid search, PCE-aware density estimation
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Lightweight model selection
- Hardware-specific optimization: TensorRT optimization on Jetson edge GPUs
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Portenta H7 flash specification reported as 16 MB; model flash usage not reported
- Model size reported: YOLOv8-nano: 6.0 MB; YOLOv7-tiny: 11.8 MB; YOLOv8-small: 21.5 MB; YOLO-NAS-small: 244.4 MB
- Energy per inference reported: Not reported
- Latency on target device reported: FPS reported on Jetson Nano and Jetson Xavier NX; latency in milliseconds not reported
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: RSEN nodes communicate traffic density to the ATLC scheduling node through Wi-Fi; cloud communication is not reported
- Candidate for Strict TinyML: No
- Reason: The computer vision inference is deployed on Jetson Nano/Xavier NX edge GPU/SoC hardware rather than MCU-class or TensorFlow Lite Micro/CMSIS-NN-based TinyML hardware.

### Benchmarking / Standardization
- Benchmark used: KITTI, PASCAL VOC, DAWN, SUMO
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: KITTI, PASCAL VOC, DAWN
- Comparison with baseline models: YOLOv7-tiny, YOLOv8-nano, YOLOv8-small, YOLO-NAS-small
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: YOLOv8-nano provided the best trade-off between model size, accuracy, and speed, achieving up to 74.67 FPS and competitive mAP while requiring only 6 MB. The edge-deployed adaptive traffic control system reduced traffic density by up to 33.38% and waiting time by up to 23.4% compared with fixed-time control.

### Limitations
- High energy consumption of the Road Side Edge Node is reported as a limitation.
- The current detection models are statically trained and deployed on edge nodes.
- The framework is predominantly vision-centric and may be affected by camera failures or degraded visual conditions.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: Yes
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes an edge-deployed adaptive traffic management framework that combines YOLO-based vehicle detection, PCE-aware traffic density estimation, and rule-based adaptive traffic light control for undisciplined urban traffic scenarios.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Raza et al. | 2025 | Object detection | YOLOv8-nano / YOLOv7-tiny | TensorRT optimization and lightweight YOLO selection | Jetson Nano / Jetson Xavier NX / Portenta H7 | Custom Karachi traffic dataset; KITTI; PASCAL VOC; DAWN | Up to 90% mAP; 83.7% mAP on Jetson Xavier NX | N/A | 6.0 MB | 8 GB RAM on Jetson Xavier NX; 4 GB RAM on Jetson Nano; 8 MB SDRAM on Portenta H7 | 16 MB Flash on Portenta H7 | N/A | PyTorch 1.8.1 / TensorRT / SUMO / TraCI | N/A | N/A | No |
