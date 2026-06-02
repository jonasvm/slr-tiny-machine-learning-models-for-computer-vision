## Paper ID: Design-of-multi-mode-intelligent-system-architecture-for-surface-defect-detection-of-steel-based-on-cloud-technology

TinyML classification: Near-TinyML — it is relevant to edge/on-device vision through lightweight YOLOv5 and mobile/edge integration, but the evidence is for cloud/mobile/edge architecture rather than microcontroller-class deployment.

### Basic Info
- Authors: Fei Ren, LiBing Xu, Jiajie Fei, John Paul Q. Tomas, HongSheng Li, Bonifacio T. Doma Jr.
- Year: 2025
- Title: Design of multi-mode intelligent system architecture for surface defect detection of steel based on cloud technology
- Source: Scientific Reports, 15:39735
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: Automated detection and real-time monitoring of steel surface defects.
- Application domain: Steel manufacturing quality inspection.
- Scenario: Edge-cloud-mobile industrial monitoring system.
- TinyML relevance: Partial
- TinyML justification: The paper uses lightweight YOLOv5 variants and edge/cloud/mobile integration, but does not report MCU-class deployment or strict TinyML constraints.

### Model / Method
- Model: YOLOv5, YOLOv5-EfficientNet-B1 to B8, YOLOv5-MobileNet-large, YOLOv5-MobileNet-small
- Architecture family: CNN
- Techniques: Lightweight backbone replacement using EfficientNet and MobileNet, depth-wise separable convolution, local-cloud-mobile result distribution.
- Framework: PyQt, Qiniu Cloud, REST API, JSON serialization, WeChat, email, iMessage, Android application notifications.
- Training type: Not reported
- Inference type: Hybrid

### Hardware
- Device: Local detection node not specifically reported; Huawei Honor V8 and iPhone 12 used for mobile result push.
- Hardware type: Mobile / Cloud / Other
- Processor / microcontroller: Hisilicon Kirin 955 CPU; Apple A14 CPU
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: 128GB ROM reported for Huawei Honor V8 and iPhone 12
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Not reported
- Constraints mentioned: Real-time processing, detection speed, cloud scalability, communication reliability, system robustness.

### Dataset
- Name: Northeastern University steel surface defect dataset; self-built real steel defect dataset
- Type: Public and private/internal
- Dataset size: 472 defects reported for the self-built dataset
- Number of classes: 6
- Input resolution: Not reported
- Data modality: Steel surface images, video streams, real-time camera acquisition

### Metrics
- Accuracy: Not reported
- mAP: mAP@0.5 reported in Fig. 10; best visible value is 0.38
- Precision: Precision reported in Fig. 10; best visible value is 0.56
- Recall: Recall reported in Fig. 10; best visible value is 0.42
- F1-score: Not reported
- Latency: Inference time reported from 1.60 ms to 12.70 ms across tested models
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: EfficientNet backbone replacement, MobileNet backbone replacement, lightweight YOLOv5 variants.
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Lightweight CNN backbone replacement
- Hardware-specific optimization: Not reported
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Inference time reported, but target inference hardware is not specified
- Runs without full operating system: No
- Fully on-device inference: Not reported
- Communication required during inference: Not reported; communication is required for cloud/mobile result distribution
- Candidate for Strict TinyML: No
- Reason: The paper does not provide MCU-class deployment, bare-metal/RTOS execution, TensorFlow Lite Micro use, or SRAM/Flash/energy evidence.

### Benchmarking / Standardization
- Benchmark used: Northeastern University steel surface defect dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Northeastern University steel surface defect dataset
- Comparison with baseline models: Yes, YOLOv5 is compared with YOLOv5-EfficientNet and YOLOv5-MobileNet variants.
- Comparison with previous works: Yes, but detailed quantitative previous-work comparison is not reported.
- Reproducibility artifacts available: Dataset available from corresponding author on reasonable request; code and model not reported.

### Results
- Summary: The proposed system integrates improved lightweight YOLOv5 models with a local-cloud-mobile architecture for steel surface defect detection and result delivery. Reported inference times range from 1.60 ms to 12.70 ms, with precision, recall, and mAP@0.5 values shown for YOLOv5 and lightweight variants.

### Limitations
- The paper states that generalization ability may face challenges as dataset scale and complexity increase.
- The self-built dataset is not openly released and is available only by request.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: No
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a cloud-native local-cloud-mobile intelligent system architecture using lightweight YOLOv5 variants for automated steel surface defect detection and multi-channel real-time result distribution.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Ren et al. | 2025 | Object Detection | YOLOv5, YOLOv5-EfficientNet, YOLOv5-MobileNet | Lightweight backbone replacement | Local detection node; Huawei Honor V8 and iPhone 12 for result push | NEU steel surface defect dataset + self-built steel defect dataset | mAP@0.5 up to 0.38 | 1.60-12.70 ms | N/A | N/A | N/A | N/A | PyQt + Qiniu Cloud | N/A | None | No |
