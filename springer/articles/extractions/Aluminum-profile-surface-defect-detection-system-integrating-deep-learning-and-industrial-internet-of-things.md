## Paper ID: Aluminum-profile-surface-defect-detection-system-integrating-deep-learning-and-industrial-internet-of-things

TinyML classification: Near-TinyML — The work discusses lightweight models and edge/IIoT deployment relevance, but the reported evaluation uses laptop/GPU-class hardware rather than explicit MCU-class constraints.

### Basic Info
- Authors: Lei Che
- Year: 2025
- Title: Aluminum profile surface defect detection system integrating deep learning and industrial internet of things
- Source: Discover Applied Sciences, 7:1073
- Type: Benchmark

### Problem & Context
- Task: Classification
- Objective: Compare ten deep learning models for aluminum profile surface defect recognition and identify efficient solutions for industrial inspection.
- Application domain: Industrial quality inspection / aluminum profile manufacturing
- Scenario: Industrial Internet of Things, edge-oriented industrial inspection
- TinyML relevance: Partial
- TinyML justification: The paper discusses lightweight models and IIoT/edge deployment, but reports experiments on laptop CPU/GPU hardware and does not provide MCU-class deployment evidence.

### Model / Method
- Model: DarkNet-19, DarkNet-53, EfficientNet-b0, GoogLeNet, MobileNetv2, NasNet-Mobile, Places365-GoogLeNet, ResNet-50, ShuffleNet, SqueezeNet
- Architecture family: CNN
- Techniques: Lightweight CNN model comparison; data augmentation; normalization; grayscale conversion
- Framework: OpenCV reported for median filtering; deep learning framework not reported
- Training type: Not reported
- Inference type: Not reported

### Hardware
- Device: Intel Core i9-14900HX laptop with NVIDIA GeForce RTX 4060 Laptop GPU
- Hardware type: CPU / GPU
- Processor / microcontroller: Intel(R) Core(TM) i9-14900HX @ 2.20 GHz
- Clock frequency: 2.20 GHz
- SRAM / RAM: 32 GB RAM
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Not reported
- Constraints mentioned: Accuracy, training time, real-time industrial requirements, edge deployment, computational cost, hardware cost

### Dataset
- Name: 2018 Guangdong Industrial Intelligence Big Data Intelligent Algorithm Challenge dataset on Tianchi Feiyue Cloud Platform
- Type: Public
- Dataset size: 2137 images; 1119 defective images and 1018 defect-free images
- Number of classes: 27 defect types plus defect-free samples
- Input resolution: Not reported
- Data modality: Industrial surface images; grayscale conversion applied during preprocessing

### Metrics
- Accuracy: GoogLeNet 68.23%; MobileNetv2 66.20%; ResNet-50 64.63%; EfficientNet-b0 64.48%; ShuffleNet 64.01%; DarkNet-53 63.07%; DarkNet-19 46.79%; SqueezeNet 11.58%
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported
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
- Techniques used: Grayscale conversion, normalization, random rotation, horizontal/vertical flipping, brightness adjustment, noise removal, median filtering
- Quantization: Not reported
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
- Latency on target device reported: Not reported
- Runs without full operating system: Not reported
- Fully on-device inference: Not reported
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The study discusses lightweight models for IIoT/edge-oriented industrial inspection, but does not report MCU-class deployment, TensorFlow Lite Micro/CMSIS-NN use, memory footprint, energy, or latency on a microcontroller-class target.

### Benchmarking / Standardization
- Benchmark used: Internal benchmark comparing ten CNN models on the same aluminum profile defect dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes
- Comparison with previous works: Not reported
- Reproducibility artifacts available: Not reported

### Results
- Summary: GoogLeNet achieved the highest validation accuracy at 68.23%, followed by MobileNetv2 at 66.20%. Lightweight models such as MobileNetv2 and ShuffleNet are presented as more suitable for edge-oriented industrial inspection scenarios, while heavier models face computational deployment challenges.

### Limitations
- Dataset covers only 27 defect types and may not generalize to novel or cross-enterprise defects.
- Real-time versus accuracy trade-offs remain unresolved for high-speed industrial lines.
- The paper reports limited deployment-specific metrics such as latency, model size, memory, energy, and power.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a benchmark and model-selection framework for aluminum profile surface defect recognition by comparing ten deep learning models under an industrial IIoT-oriented inspection context.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Che et al. | 2025 | Classification | GoogLeNet, MobileNetv2, ShuffleNet, EfficientNet-b0, ResNet-50, DarkNet-19, DarkNet-53, NasNet-Mobile, Places365-GoogLeNet, SqueezeNet | Lightweight CNN comparison | Intel Core i9-14900HX + NVIDIA RTX 4060 Laptop GPU | 2018 Guangdong Industrial Intelligence Big Data Intelligent Algorithm Challenge aluminum defect dataset | Accuracy: 68.23% best with GoogLeNet | N/A | N/A | 32 GB RAM | N/A | N/A | N/A | N/A | None | No |
