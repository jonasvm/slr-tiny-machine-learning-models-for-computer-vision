## Paper ID: Efficient-crack-and-surface-type-recognition-via-CNN-block-development-mechanism-and-edge-profiling

TinyML classification: Near-TinyML — The paper targets lightweight edge vision and reports Raspberry Pi 4 latency, but does not explicitly demonstrate microcontroller-class deployment.

### Basic Info
- Authors: Ali Raza, Fareeha Hanif, Heba Abdelgader Mohammed
- Year: 2025
- Title: Efficient crack and surface-type recognition via CNN-block development mechanism and edge profiling
- Source: Scientific Reports, 15:40073
- Type: Experimental / Methodological

### Problem & Context
- Task: Classification
- Objective: Multi-class crack and surface-type recognition across cracked and uncracked concrete, plaster/wall, pavement, and deck surfaces.
- Application domain: Structural health monitoring and civil infrastructure inspection.
- Scenario: Edge deployment, UAV/vehicle/handheld inspection, resource-constrained monitoring.
- TinyML relevance: Partial
- TinyML justification: The paper targets lightweight edge vision and reports Raspberry Pi 4 latency and compact model size, but does not demonstrate MCU-class deployment.

### Model / Method
- Model: Lite-V2
- Architecture family: CNN
- Techniques: CNN-Block Development Mechanism, lightweight CNN design, domain-driven augmentation, Batch Normalization, Dropout, weight decay, INT8 quantization, Grad-CAM, edge profiling.
- Framework: TensorFlow Lite compatibility reported; specific deployment framework not reported.
- Training type: From scratch
- Inference type: On-device edge inference

### Hardware
- Device: Raspberry Pi 4
- Hardware type: SoC / CPU edge device
- Processor / microcontroller: Not reported
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, latency, compute, edge deployment, resource-constrained environments.

### Dataset
- Name: SDNET2018; cross-domain validation on CrackForest Dataset and DeepCrack.
- Type: Public
- Dataset size: SDNET2018 reported as over 56,000 annotated images; balanced training set reported as 14,957 images per class.
- Number of classes: 6
- Input resolution: 224 × 224 RGB reported in preprocessing; Table 5 also reports 256 × 256.
- Data modality: RGB image

### Metrics
- Accuracy: 0.957 test accuracy
- mAP: Not reported
- Precision: Macro precision 0.939; weighted precision 0.949
- Recall: Macro recall 0.929; weighted recall 0.951
- F1-score: Macro-F1 0.928 reported in abstract/comparison; 0.934 reported in per-class SDNET-6 table; CFD F1-score 0.975; DeepCrack F1-score 0.96
- Latency: 11 ms on Raspberry Pi 4
- FPS: Roughly 90 FPS
- Throughput: Not reported
- Model size: Approximately 1.1 MB
- Parameters: 0.28 million
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Lightweight CNN architecture, CNN-BDM iterative design, Batch Normalization, Dropout, weight decay, domain-driven augmentation, INT8 quantization, edge profiling.
- Quantization: INT8
- Pruning: No
- Knowledge distillation: No
- Compression method: Lightweight architecture and INT8 quantization
- Hardware-specific optimization: Edge profiling on Raspberry Pi 4
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Approximately 1.1 MB
- Energy per inference reported: Not reported
- Latency on target device reported: 11 ms on Raspberry Pi 4
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The deployment evidence is based on Raspberry Pi 4 edge inference, with no explicit MCU-class platform, SRAM/Flash constraints, TensorFlow Lite Micro, CMSIS-NN, bare-metal, or RTOS deployment.

### Benchmarking / Standardization
- Benchmark used: SDNET2018 / SDNET-6; CFD; DeepCrack.
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: CrackForest Dataset and DeepCrack.
- Comparison with baseline models: MobileNetV2, EfficientNet-B0, ResNet-18.
- Comparison with previous works: EDNet, ensemble CNN, Dual Flow Fusion, DeepCrack, CrackCTFuse.
- Reproducibility artifacts available: Dataset; code/model not reported.

### Results
- Summary: Lite-V2 achieved 0.957 test accuracy and macro-F1 values reported as 0.928/0.934 with only 0.28M parameters and 11 ms latency on Raspberry Pi 4. It outperformed MobileNetV2, EfficientNet-B0, and ResNet-18 in accuracy-efficiency trade-off and showed cross-domain F1-scores of 0.975 on CFD and 0.96 on DeepCrack.

### Limitations
- Performance degradation was observed under extreme brightness and heavy blur.
- The model relies only on RGB visual features and does not use multispectral or depth information.
- Field-level images from diverse geographic regions were not included.
- Detailed energy consumption analysis on embedded hardware was not provided.

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
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a lightweight CNN developed through the CNN-Block Development Mechanism for six-class crack and surface-type recognition with edge profiling on Raspberry Pi 4.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Raza et al. | 2025 | Classification | Lite-V2 | CNN-BDM lightweight CNN + INT8 quantization | Raspberry Pi 4 | SDNET2018 / SDNET-6 | Accuracy 0.957; Macro-F1 0.928/0.934 | 11 ms | ~1.1 MB | N/A | N/A | N/A | TensorFlow Lite-compatible | INT8 | None | No |
