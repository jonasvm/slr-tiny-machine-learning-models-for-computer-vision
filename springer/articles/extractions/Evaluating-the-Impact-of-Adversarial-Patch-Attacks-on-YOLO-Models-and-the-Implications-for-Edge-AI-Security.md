## Paper ID: Evaluating-the-Impact-of-Adversarial-Patch-Attacks-on-YOLO-Models-and-the-Implications-for-Edge-AI-Security

TinyML classification: Near-TinyML — It is relevant to edge AI computer vision but uses edge AI hardware rather than explicit microcontroller-class deployment.

### Basic Info
- Authors: D. L. Gala; J. Molleda; R. Usamentiaga
- Year: 2025
- Title: Evaluating the Impact of Adversarial Patch Attacks on YOLO Models and the Implications for Edge AI Security
- Source: International Journal of Information Security, 24:154
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: Evaluate naturalistic adversarial patch attacks against recent Ultralytics YOLO object detectors and analyze implications for edge AI security.
- Application domain: Edge AI security, adversarial machine learning, pedestrian/person detection
- Scenario: Edge AI
- TinyML relevance: Partial
- TinyML justification: The paper evaluates inference on an edge AI device and reports latency and memory, but it does not target MCU-class or ultra-low-power microcontroller deployment.

### Model / Method
- Model: Ultralytics YOLOv5, YOLOv8, YOLOv9, YOLOv10; BigGAN used for naturalistic adversarial patch generation
- Architecture family: CNN / Other
- Techniques: Naturalistic adversarial patches, GAN latent-space optimization, adversarial attack transferability evaluation, edge inference benchmarking
- Framework: Ultralytics
- Training type: Not reported for detector training; adversarial patches optimized with Adam
- Inference type: On-device

### Hardware
- Device: Edge AI device; workstation; server
- Hardware type: GPU / SoC
- Processor / microcontroller: Edge AI device uses ARM Cortex-A57 CPU and NVIDIA GM20B Maxwell 2.0 GPU
- Clock frequency: ARM Cortex-A57 at 1.43 GHz
- SRAM / RAM: 4 GB LPDDR4 shared with CPU on the edge AI device
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Limited computational resources, latency, memory, compute constraints, smaller models on edge devices

### Dataset
- Name: INRIA Person dataset; MPII Human Pose dataset
- Type: Public
- Dataset size: Not reported
- Number of classes: 1 class, Person
- Input resolution: Not reported
- Data modality: RGB image

### Metrics
- Accuracy: Not reported
- mAP: Best adversarial patches on INRIA at scale 0.20 reached average mAP values of 55.72% for patch17, 55.09% for patch26, 51.43% for patch27, and 51.47% for patch38 across evaluated YOLO models
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Edge AI device inference time ranged from 158.56 ms to 798.94 ms depending on YOLO model
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: YOLOv8m has 25.9M parameters, YOLOv9m has 20.0M parameters, and YOLOv10m has 15.4M parameters
- MACs / FLOPs: Not reported
- RAM usage: Edge AI device memory ranged from 33.48 MB to 164.92 MB depending on YOLO model
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: GAN-based naturalistic adversarial patch generation with latent-vector optimization; smaller YOLO model evaluation for edge latency
- Quantization: not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Not reported
- Hardware-specific optimization: Not reported
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Yes, 158.56 ms to 798.94 ms on the edge AI device
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The deployment hardware is an edge AI GPU/SoC platform with 4 GB shared memory, not a microcontroller-class platform, and the paper does not report MCU-level SRAM, Flash, OS-free execution, or TensorFlow Lite Micro/CMSIS-NN deployment.

### Benchmarking / Standardization
- Benchmark used: INRIA Person dataset; MPII Human Pose dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: ImageNet-1k used for BigGAN pretraining
- Comparison with baseline models: Yes, white patch, grey patch, random patch, patch-v4, patch-v4t, Faster R-CNN-based patch, advyolo, and advyolo-up
- Comparison with previous works: Yes
- Reproducibility artifacts available: code

### Results
- Summary: The generated naturalistic adversarial patches substantially reduced YOLO person-detection mAP, with smaller YOLO models generally more vulnerable than larger variants. Edge-device inference experiments showed that smaller models reduce latency and memory use but may increase adversarial vulnerability.

### Limitations
- The paper focuses on evaluating vulnerability to naturalistic adversarial patches rather than implementing defense mechanisms.
- Future work is needed on lightweight, resource-efficient defenses suitable for edge devices.
- Energy consumption and MCU-class deployment metrics are not reported.

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
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes an adaptation of naturalistic adversarial patch generation for recent Ultralytics YOLO detectors and evaluates the security impact of these attacks on object detection models deployed on edge AI hardware.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Gala et al. | 2025 | Object Detection | YOLOv5, YOLOv8, YOLOv9, YOLOv10 | Naturalistic adversarial patch generation | Edge AI device with NVIDIA GM20B Maxwell 2.0 GPU and ARM Cortex-A57 CPU | INRIA Person; MPII Human Pose | mAP, best patches averaged 51.43% to 55.72% on INRIA | 158.56-798.94 ms | N/A | 33.48-164.92 MB | N/A | N/A | Ultralytics | N/A | None | No |
