## Paper ID: SCTNet-NAS-efficient-semantic-segmentation-via-neural-architecture-search-for-cloud-edge-collaborative-perception

TinyML classification: Near-TinyML — The work is relevant to edge AI computer vision through lightweight NAS-based semantic segmentation, but the evidence is limited to generic edge/cloud-edge deployment rather than MCU-class constraints.

### Basic Info
- Authors: Ruyu Liu; Lin Wang; Zhihao Yu; Haoyu Zhang; Xiufeng Liu; Bo Sun; Xv Huo; Jianhua Zhang
- Year: 2025
- Title: SCTNet-NAS: efficient semantic segmentation via neural architecture search for cloud-edge collaborative perception
- Source: Complex & Intelligent Systems, 11:365
- Type: Methodological

### Problem & Context
- Task: Segmentation
- Objective: To design an efficient semantic segmentation framework with improved accuracy-efficiency trade-off for cloud-edge collaborative perception.
- Application domain: Semantic scene understanding, autonomous driving, robotics, smart surveillance, cloud-edge perception
- Scenario: Edge, cloud-edge collaborative perception, autonomous system
- TinyML relevance: Partial
- TinyML justification: The paper targets resource-constrained edge devices and real-time edge segmentation, but does not report MCU-class deployment, MCU memory constraints, TensorFlow Lite Micro, CMSIS-NN, or bare-metal/RTOS execution.

### Model / Method
- Model: SCTNet-NAS
- Architecture family: Hybrid CNN / Transformer
- Techniques: Neural architecture search, knowledge distillation, feature alignment, MobileNetV2-based search space, NSGA-II multi-objective optimization, attention-based decoder design
- Framework: PyTorch
- Training type: Fine-tuning
- Inference type: On-device edge inference described; cloud used for NAS and knowledge distillation

### Hardware
- Device: Generic resource-constrained edge devices; cloud server used for NAS and knowledge distillation
- Hardware type: Other
- Processor / microcontroller: Not reported
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes, described for the compact edge-deployed student model, but no specific target hardware is reported
- Constraints mentioned: Processing power, memory capacity, energy budget, FLOPs, latency, parameter size

### Dataset
- Name: Cityscapes; CVRG-Pano; CARLA panoramic dataset
- Type: Public; public; synthetic
- Dataset size: Cityscapes has 2,975 training images, 500 validation images, and 500 testing images; CVRG-Pano has 600 images with 524 training and 76 testing images; CARLA has 4,141 images with 3,313 training and 828 testing images
- Number of classes: Cityscapes has 19 classes; CVRG-Pano has 7 classes; CARLA has 27 classes
- Input resolution: Cityscapes evaluated at 1024 × 512 and 1536 × 768; other dataset input resolutions not reported
- Data modality: RGB image and panoramic RGB image with semantic segmentation labels

### Metrics
- Accuracy: Cityscapes mAcc 82.18% at 1024 × 512 and 84.77% at 1536 × 768; CVRG-Pano mAcc 82.14%; CARLA mAcc 76.62%
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: 4.34M on Cityscapes; 4.56M on CVRG-Pano; 4.46M on CARLA
- MACs / FLOPs: FLOPs used as an optimization objective, but numeric FLOPs are not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Neural architecture search, NSGA-II, knowledge distillation, feature-based alignment, MobileNetV2 block search space, lightweight decoder design
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Yes
- Compression method: Lightweight NAS-based architecture design and feature-based knowledge distillation
- Hardware-specific optimization: Edge-aware NAS using FLOPs and latency constraints, but no specific deployment hardware is reported
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported
- Runs without full operating system: Not reported
- Fully on-device inference: Yes, described for edge-deployed inference, but not demonstrated on a specific MCU-class device
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper targets generic edge/cloud-edge semantic segmentation but does not provide MCU-class deployment evidence, SRAM/Flash usage, energy per inference, TensorFlow Lite Micro, CMSIS-NN, or bare-metal/RTOS execution.

### Benchmarking / Standardization
- Benchmark used: Cityscapes; CVRG-Pano; CARLA panoramic dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Cityscapes
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Dataset

### Results
- Summary: SCTNet-NAS achieved 73.15% mIoU and 82.18% mAcc on Cityscapes at 1024 × 512 with 4.34M parameters, and 76.76% mIoU at 1536 × 768. It also achieved 76.50% mIoU on CVRG-Pano and 68.11% mIoU on CARLA, showing improved accuracy-efficiency trade-offs for edge-oriented semantic segmentation.

### Limitations
- Real-world deployment on specific edge devices is not reported.
- MCU-level memory, latency, energy, and power measurements are not reported.
- Future work states the need to evaluate SCTNet-NAS on a wider range of edge devices and conditions.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: No
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes SCTNet-NAS, a cloud-edge collaborative semantic segmentation framework that combines neural architecture search, feature-based knowledge distillation, and specialized decoder heads to improve accuracy-efficiency trade-offs on resource-constrained edge devices.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Liu et al. | 2025 | Segmentation | SCTNet-NAS | NAS + knowledge distillation | Generic edge device / cloud-edge system | Cityscapes; CVRG-Pano; CARLA panoramic | 76.76% mIoU on Cityscapes at 1536 × 768 | N/A | 4.34M parameters | N/A | N/A | N/A | PyTorch | N/A | N/A | No |
