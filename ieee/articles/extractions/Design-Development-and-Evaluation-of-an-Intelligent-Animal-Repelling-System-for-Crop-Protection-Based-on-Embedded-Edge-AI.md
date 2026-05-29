## Paper ID: Design-Development-and-Evaluation-of-an-Intelligent-Animal-Repelling-System-for-Crop-Protection-Based-on-Embedded-Edge-AI

TinyML classification: Near-TinyML — it targets edge-AI vision deployment on Raspberry Pi, Movidius-NCS, Jetson, CPU, and GPU platforms, but does not provide explicit MCU-class or bare-metal/RTOS TinyML deployment evidence.

TinyML classification: Near-TinyML — the deployment uses Raspberry Pi, Intel Movidius NCS, and NVIDIA Jetson Nano rather than MCU-class TinyML inference.

### Basic Info
- Authors: Davide Adami, Mike O. Ojo, Stefano Giordano
- Year: 2021
- Title: Design, Development and Evaluation of an Intelligent Animal Repelling System for Crop Protection Based on Embedded Edge-AI
- Source: IEEE Access, Volume 9, DOI: 10.1109/ACCESS.2021.3114503
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: Detect and recognize ungulates in real time and trigger species-specific ultrasound signals for crop protection.
- Application domain: Smart agriculture / crop protection
- Scenario: Embedded edge AI, IoT, rural deployment, low-power edge computing
- TinyML relevance: Partial
- TinyML justification: The paper targets embedded edge-AI deployment on low-power devices such as Raspberry Pi 3B+, Raspberry Pi 3B+ with Intel Movidius NCS, and NVIDIA Jetson Nano, but the DNN inference is not demonstrated on an MCU-class TinyML platform.

### Model / Method
- Model: YOLOv3 and Tiny-YOLOv3
- Architecture family: CNN
- Techniques: Lightweight detector selection, data augmentation, hardware platform comparison, hardware acceleration with Intel Movidius NCS
- Framework: OpenCV selected as benchmark; YOLO Darknet annotation format used
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: NVIDIA Jetson Nano; Raspberry Pi 3B+; Raspberry Pi 3B+ with Intel Movidius NCS; Animal Repelling Device based on ATSAMD21G18A
- Hardware type: SoC / CPU / GPU / VPU / MCU
- Processor / microcontroller: ATSAMD21G18A 32-bit ARM Cortex-M0+; NVIDIA Jetson Nano quad-core ARM A57 @ 1.43 GHz with 128-core NVIDIA Maxwell GPU; Raspberry Pi 3B+ quad-core Cortex-A53; Intel Movidius NCS Myriad 2 VPU
- Clock frequency: ATSAMD21G18A at 48 MHz; NVIDIA Jetson Nano CPU at 1.43 GHz; others not reported
- SRAM / RAM: ATSAMD21G18A has 32 KB RAM; NVIDIA Jetson Nano has 4 GB LPDDR4; Raspberry Pi 3B+ has 1 GB LPDDR2; Intel Movidius NCS has 4 GB LPDDR3
- Flash / ROM / Storage: ATSAMD21G18A has 512 KB flash memory; storage for edge devices not reported
- Power consumption: NVIDIA Jetson Nano: 17.32 W / 12.94 W / 8.5 W for YOLOv3 at 20 W / 15 W / 10 W modes; 16.70 W / 12.68 W / 8.3 W for Tiny-YOLOv3 at 20 W / 15 W / 10 W modes; Raspberry Pi 3B+ Tiny-YOLOv3: 3.2 W; Raspberry Pi 3B+ + NCS Tiny-YOLOv3: 3.2 W
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory footprint, power consumption, latency, computational capability, energy supply, network connectivity, rural deployment constraints

### Dataset
- Name: Not reported
- Type: Private / custom-collected
- Dataset size: 1,000 images collected; expanded to 10,000 images using data augmentation
- Number of classes: 2
- Input resolution: 416 × 416 for Tiny-YOLOv3; YOLO original configuration resizes input to 416 × 416 while preserving aspect ratio
- Data modality: Digital camera images

### Metrics
- Accuracy: Not reported
- mAP: YOLOv3: 82.5%; Tiny-YOLOv3: 62.41%
- Precision: Not reported
- Recall: YOLOv3 mean Recall: 64%; Tiny-YOLOv3 mean Recall: 49%
- F1-score: Not reported
- Latency: Not reported
- FPS: YOLOv3 on NVIDIA Jetson Nano: 4 FPS at 20 W, 3.2 FPS at 15 W, 3.2 FPS at 10 W; Tiny-YOLOv3 on NVIDIA Jetson Nano: 14.8 FPS at 20 W, 12.8 FPS at 15 W, 10 FPS at 10 W; Tiny-YOLOv3 on Raspberry Pi 3B+: 0.8 FPS; Tiny-YOLOv3 on Raspberry Pi 3B+ with NCS: 4 FPS
- Throughput: Same as FPS
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported for model deployment
- Energy per inference: Not reported
- Power consumption: Reported as average platform power during detector execution

### Optimization
- Techniques used: Data augmentation; Tiny-YOLOv3 as lightweight detector; hardware acceleration using Intel Movidius NCS; GPU-based embedded inference using NVIDIA Jetson Nano
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Tiny-YOLOv3 lightweight architecture
- Hardware-specific optimization: Evaluation on NVIDIA Jetson Nano GPU and Intel Movidius NCS VPU
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported for model deployment; 512 KB flash reported for the animal repelling MCU
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported; FPS reported
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No for DNN inference; communication is used for triggering, control, and monitoring
- Candidate for Strict TinyML: No
- Reason: The paper evaluates embedded edge-AI inference on Raspberry Pi-class and Jetson Nano-class platforms, including an external neural compute stick, but does not demonstrate MCU-class DNN inference, TensorFlow Lite Micro, CMSIS-NN, SRAM/Flash model footprint, or energy per inference.

### Benchmarking / Standardization
- Benchmark used: Custom ungulate detection dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: YOLOv3 compared with Tiny-YOLOv3; multiple hardware platforms compared
- Comparison with previous works: Related works discussed qualitatively
- Reproducibility artifacts available: Not reported

### Results
- Summary: YOLOv3 achieved the best detection performance with 82.5% mAP and 64% mean Recall, while Tiny-YOLOv3 achieved 62.41% mAP and 49% mean Recall. NVIDIA Jetson Nano running Tiny-YOLOv3 achieved the best real-time performance, reaching 14.8 FPS at 20 W, while Raspberry Pi 3B+ alone reached only 0.8 FPS.

### Limitations
- Raspberry Pi 3B+ running Tiny-YOLOv3 achieved less than 1 FPS and was not suitable for real-time applications.
- Raspberry Pi 3B+ with Intel Movidius NCS reached 4 FPS, but suitability for soft real-time applications was considered arguable.
- NVIDIA Jetson Nano at 10 W switched off after a short time when peripherals were attached.
- Raspberry Pi 3B+ with NCS reached high CPU temperature without a fan, with a peak of 93 °C and average of 70 °C.
- Deployment of innovative Edge-AI and IoT applications is described as still far from easy and straightforward.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: No
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes an embedded Edge-AI and IoT-based intelligent animal repelling system that detects ungulates using YOLOv3/Tiny-YOLOv3 on low-power edge devices and triggers species-specific ultrasound signals for crop protection.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Adami et al. | 2021 | Object detection | YOLOv3; Tiny-YOLOv3 | Lightweight Tiny-YOLOv3; hardware acceleration | NVIDIA Jetson Nano; Raspberry Pi 3B+; Raspberry Pi 3B+ + Intel Movidius NCS | Custom wild boar/deer dataset, 1,000 images augmented to 10,000 | YOLOv3: 82.5% mAP; Tiny-YOLOv3: 62.41% mAP | N/A; up to 14.8 FPS | N/A | N/A | N/A | N/A | OpenCV / Darknet YOLO format | N/A | None | No |
