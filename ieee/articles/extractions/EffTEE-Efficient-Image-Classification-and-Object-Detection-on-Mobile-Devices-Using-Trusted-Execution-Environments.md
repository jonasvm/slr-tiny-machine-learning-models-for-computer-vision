## Paper ID: EffTEE-Efficient-Image-Classification-and-Object-Detection-on-Mobile-Devices-Using-Trusted-Execution-Environments

TinyML classification: Near-TinyML — evaluated on mobile/TEE edge hardware including Raspberry Pi 3 Model B+ and ARM TrustZone-style TEEs, but without explicit MCU-class deployment evidence.

### Basic Info
- Authors: Bin Hu, Junyong You, Kuan Huang, Meng Xu, Dan Liu, Sugang Ma
- Year: 2025
- Title: EffTEE: Efficient Image Classification and Object Detection on Mobile Devices Using Trusted Execution Environments
- Source: IEEE Access
- Type: Experimental

### Problem & Context
- Task: Image classification and object detection
- Objective: Enable secure and efficient DNN inference inside mobile Trusted Execution Environments under limited memory and computation constraints.
- Application domain: Autonomous driving, security, UAV navigation, robotics, augmented reality, mobile applications
- Scenario: Mobile, embedded, resource-constrained edge device with mobile TEE
- TinyML relevance: Partial
- TinyML justification: The paper targets resource-constrained mobile TEEs with memory, latency, compression, and energy-efficiency concerns, but deployment is on Raspberry Pi 3 B+ / ARM TrustZone-style mobile TEE rather than explicit MCU-class hardware.

### Model / Method
- Model: EffTEE framework applied to MobileNet-V1, VGG-16, SqueezeNet, TinyNet, GoogLeNet, ResNet-50, AlexNet, YOLOV3, YOLOV4, YOLOV5
- Architecture family: CNN
- Techniques: Structured pruning, dynamic suppression, dynamic transformed regularization, neuron restructuring, memory reallocation, dynamic slicing, composite layer integration and loading
- Framework: Darknet, DarkneTZ, OP-TEE
- Training type: Not reported
- Inference type: On-device within mobile TEE

### Hardware
- Device: Raspberry Pi 3 Model B+
- Hardware type: Mobile / SoC / CPU / TEE
- Processor / microcontroller: ARM TrustZone Cortex-A referenced; Raspberry Pi 3 Model B+ used for deployment
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: SSD storage mentioned for partitioned model storage
- Power consumption: Not directly measured
- Energy per inference: Not directly measured
- Execution without full OS: No
- Fully on-device inference: Yes
- Constraints mentioned: Mobile TEE memory, secure memory, latency, computation, loading iterations, model size, energy efficiency, battery life

### Dataset
- Name: CIFAR-10, ImageNet, MS COCO
- Type: Public
- Dataset size: Not reported
- Number of classes: Not reported
- Input resolution: Not reported
- Data modality: RGB image / object detection image datasets

### Metrics
- Accuracy: Accuracy drop reported for classification; exact per-model values reported in tables
- mAP: mAP loss reported for object detection; average mAP loss of 2.3 ± 0.5% on MS COCO
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Inference time reduced by 2–60×; ImageNet inference time reduced by 33.2 ± 1.4%; CIFAR-10 inference time reduced by 29.6 ± 1.2%; COCO inference time reduced by 35.1 ± 1.5%
- FPS: CIFAR-10 22.7 ± 0.7 FPS; ImageNet 18.5 ± 0.6 FPS; COCO 12.8 ± 0.5 FPS
- Throughput: Not reported
- Model size: Reported in tables for evaluated models after pruning
- Parameters: Not reported
- MACs / FLOPs: FLOPs compression ratio reported; ImageNet average FLOPs CR 85.7 ± 1.0%; COCO FLOPs CR 81.4 ± 1.3%
- RAM usage: Mobile TEE secure memory allocation of 16 MB, with 14 MB for Trusted Application and 2 MB for TEE runtime
- Flash usage: Not reported
- Energy per inference: Not directly measured
- Power consumption: Not directly measured

### Optimization
- Techniques used: Dynamic suppression structured pruning, foundational neuron restructuring, memory reallocation, dynamic slicing, composite layer integration and loading
- Quantization: Not reported
- Pruning: Yes
- Knowledge distillation: No
- Compression method: Structured pruning using dynamic transformed regularization and one-shot pruning
- Hardware-specific optimization: Optimization for mobile TEEs with limited secure memory
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Yes
- Energy per inference reported: Not directly measured
- Latency on target device reported: Yes
- Runs without full operating system: No
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: No
- Reason: The paper targets secure mobile TEE deployment on Raspberry Pi 3 B+ / ARM TrustZone-style platforms with 16 MB secure memory, but it does not report MCU-class deployment, bare-metal/RTOS execution, TensorFlow Lite Micro, or MCU-level SRAM/Flash constraints.

### Benchmarking / Standardization
- Benchmark used: CIFAR-10, ImageNet, MS COCO
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: CIFAR-10, ImageNet, MS COCO
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: EffTEE achieves substantial compression and inference acceleration for image classification and object detection while maintaining comparable accuracy to secure DNN execution baselines. Reported reductions include 2–60× inference time improvement, ImageNet average Weight CR of 82.3 ± 1.2%, FLOPs CR of 85.7 ± 1.0%, and COCO Weight CR of 78.6 ± 1.5%.

### Limitations
- The framework does not specifically address side-channel attacks.
- Power consumption and energy per inference are inferred from FLOPs/loading-iteration reductions rather than directly measured.
- Cross-platform compatibility across different TEE architectures requires further evaluation.
- Training and pruning inside the mobile TEE are not implemented.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: No
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes EffTEE, a secure and efficient DNN inference framework that combines dynamic suppression pruning, neuron restructuring, memory reallocation, and dynamic slicing to execute image classification and object detection models within resource-constrained mobile Trusted Execution Environments.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Hu et al. | 2025 | Classification and object detection | MobileNet-V1, VGG-16, SqueezeNet, TinyNet, GoogLeNet, ResNet-50, AlexNet, YOLOV3, YOLOV4, YOLOV5 | Structured pruning, neuron restructuring, dynamic slicing, TEE-aware loading | Raspberry Pi 3 Model B+ with mobile TEE | CIFAR-10, ImageNet, MS COCO | ImageNet FLOPs CR 85.7 ± 1.0%; COCO mAP loss 2.3 ± 0.5% | 2–60× inference time reduction | Reported in tables | 16 MB secure TEE memory; 14 MB TA + 2 MB runtime | N/A | N/A | Darknet, DarkneTZ, OP-TEE | N/A | None | No |
