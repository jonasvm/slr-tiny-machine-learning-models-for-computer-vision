## Paper ID: A-lightweight-object-detection-algorithm-for-resource-constrained-UAVs-via-multi-module-optimization-and-channel-pruning

TinyML classification: Near-TinyML — The work targets resource-constrained UAV/edge object detection but evaluates on GPU-based experimental hardware rather than explicit MCU-class deployment.

### Basic Info
- Authors: Wenfeng Wang; Chaomin Wang; Wenhong Wei; Yuming Tang; Bin Zeng
- Year: 2025
- Title: A lightweight object detection algorithm for resource-constrained UAVs via multi-module optimization and channel pruning
- Source: Journal of King Saud University - Computer and Information Sciences, 37:339
- Type: Methodological

### Problem & Context
- Task: Object detection
- Objective: To design a lightweight YOLO-based object detection algorithm for UAV images that balances detection accuracy, real-time speed, and low resource consumption.
- Application domain: UAV image object detection and remote sensing object detection
- Scenario: Resource-constrained UAVs, edge computing, terminal devices
- TinyML relevance: Partial
- TinyML justification: The paper targets resource-constrained UAV/edge object detection and reports lightweight optimization, pruning, FLOPs, parameters, model size, and FPS, but does not report MCU-class deployment or TinyML-specific runtime constraints.

### Model / Method
- Model: UAV-YOLO and pruned LUAV-YOLO, with LUAV-YOLOn and LUAV-YOLOs variants
- Architecture family: CNN
- Techniques: C2Faster module, GSConv, Slim-Neck, EfficientHead, shared-parameter detection head, CGLU, F-MPDIoU loss, LAMP channel pruning, Progressive Unfreezing Fine-tuning
- Framework: Torch 2.1.1 + CUDA 12.1
- Training type: Not reported
- Inference type: Not reported

### Hardware
- Device: NVIDIA GeForce RTX 4080 16 GB experimental platform
- Hardware type: GPU
- Processor / microcontroller: Intel i7-13700KF
- Clock frequency: Not reported
- SRAM / RAM: 32 GB system memory
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Not reported
- Constraints mentioned: Computational complexity, parameters, model size, inference speed, FPS, storage capacity, network communication capability, resource-constrained edge devices

### Dataset
- Name: DOTAv1.0; NWPU VHR-10
- Type: Public
- Dataset size: DOTAv1.0 has 2,806 original images split into 21,046 images; NWPU VHR-10 has 650 target images and 150 background images
- Number of classes: DOTAv1.0 has 15 classes; NWPU VHR-10 has 10 classes
- Input resolution: 640 × 640 for training; DOTAv1.0 images divided into 1024 × 1024 patches
- Data modality: Remote sensing / UAV images

### Metrics
- Accuracy: Not reported as standalone accuracy
- mAP: LUAV-YOLOn achieved 69.1% mAP50 and 47.3% mAP50:95 on DOTAv1.0 validation; LUAV-YOLOs achieved 73.2% mAP50 and 51.4% mAP50:95 on DOTAv1.0 validation; LUAV-YOLOs achieved 94.6% mAP50 on NWPU VHR-10
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported as exact final latency
- FPS: LUAV-YOLOn achieved 211 FPS; LUAV-YOLOs achieved 206 FPS on DOTAv1.0 experiments
- Throughput: 211 FPS for LUAV-YOLOn; 206 FPS for LUAV-YOLOs
- Model size: 2.60 MB for LUAV-YOLOn; 6.71 MB for LUAV-YOLOs
- Parameters: 1.2 M for LUAV-YOLOn; 3.3 M for LUAV-YOLOs
- MACs / FLOPs: 3.6 G FLOPs for LUAV-YOLOn; 10.7 G FLOPs for LUAV-YOLOs
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Lightweight backbone optimization, Slim-Neck design, efficient detection head, custom loss function, LAMP channel pruning
- Quantization: None
- Pruning: Yes
- Knowledge distillation: No
- Compression method: LAMP channel pruning
- Hardware-specific optimization: Resource-constrained UAV/edge-oriented lightweight model design, but no specific target-device optimization reported
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: 2.60 MB for LUAV-YOLOn; 6.71 MB for LUAV-YOLOs
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported
- Runs without full operating system: No
- Fully on-device inference: Not reported
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper targets lightweight UAV/edge object detection but evaluates on an Ubuntu GPU workstation and does not report MCU-class deployment, SRAM/Flash constraints, TensorFlow Lite Micro, CMSIS-NN, or energy measurements.

### Benchmarking / Standardization
- Benchmark used: DOTAv1.0; NWPU VHR-10
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: DOTAv1.0; NWPU VHR-10
- Comparison with baseline models: YOLOv8n; YOLOv8s
- Comparison with previous works: Faster-RCNN, SSD, YOLOv3-tiny, YOLOv5s, YOLOv7-tiny, YOLOv9t, YOLOv10n, YOLOv11n
- Reproducibility artifacts available: code / dataset details upon reasonable request

### Results
- Summary: LUAV-YOLOn reduced FLOPs by 56.1% and parameters by 60% compared with YOLOv8n while slightly improving validation mAP50 to 69.1%. LUAV-YOLOs reduced FLOPs by 62.5% and parameters by 70.3% compared with YOLOv8s with 73.2% mAP50 on DOTAv1.0 validation and 94.6% mAP50 on NWPU VHR-10.

### Limitations
- The paper does not report explicit limitations; future work mentions knowledge distillation and extension to dynamic operational environments such as low-light scenarios or rapidly changing backgrounds.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a lightweight YOLOv8-based UAV object detection algorithm with multi-module optimization and LAMP channel pruning to reduce FLOPs, parameters, and model size while preserving real-time detection performance.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Wang et al. | 2025 | Object detection | LUAV-YOLO | Multi-module optimization + LAMP channel pruning | NVIDIA GeForce RTX 4080 16 GB | DOTAv1.0; NWPU VHR-10 | 73.2% mAP50 on DOTAv1.0 validation; 94.6% mAP50 on NWPU VHR-10 | N/A | 2.60 MB / 6.71 MB | N/A | N/A | N/A | Torch | N/A | None | No |
