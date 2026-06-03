## Paper ID: TinyML-Based-Concept-System-Used-to-Analyze-Whether-the-Face-Mask-Is-Worn-Properly-in-Battery-Operated-Conditions

TinyML classification: Strict TinyML — explicitly targets MCU-class deployment on STM32F411 with low-power battery operation and constrained embedded resources.

### Basic Info
- Authors: Dominik Piątkowski; Krzysztof Walkowiak
- Year: 2022
- Title: TinyML-Based Concept System Used to Analyze Whether the Face Mask Is Worn Properly in Battery-Operated Conditions
- Source: Applied Sciences, 12, 484
- Type: Experimental

### Problem & Context
- Task: Classification; face detection
- Objective: Verify whether a face mask is worn properly using a battery-operated TinyML system.
- Application domain: COVID-19 face-mask compliance monitoring
- Scenario: Embedded, IoT, battery-operated, low-power intelligent sensor
- TinyML relevance: Yes
- TinyML justification: The paper explicitly targets TinyML on low-cost, low-power microcontrollers with battery operation and constrained memory, latency, and power requirements.

### Model / Method
- Model: K-means classifier with sliding window face detection and preprocessing filters
- Architecture family: Classical ML
- Techniques: Sliding window, feature extraction, image downscaling, thresholding, squared Euclidean distance optimization
- Framework: Not reported
- Training type: From scratch
- Inference type: On-device

### Hardware
- Device: STM32F411CE / Blackpill board
- Hardware type: MCU
- Processor / microcontroller: STM32F411, 100 MHz ARM Cortex-M4 with FPU
- Clock frequency: 100 MHz
- SRAM / RAM: 128 KB RAM
- Flash / ROM / Storage: 512 KB Flash
- Power consumption: 33 mW during operation; 10 mA at 3.3 V
- Energy per inference: 0.037 J to 0.120 J depending on sliding-window size
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, power, latency, compute, battery life, cost

### Dataset
- Name: MaskedFace-Net; Natural images
- Type: Public
- Dataset size: MaskedFace-Net: 137,013 images; Natural images: 6,899 images
- Number of classes: MaskedFace-Net: 2 main classes and 4 subclasses; Natural images: 8 original classes treated as person vs non-person
- Input resolution: Original MaskedFace-Net images 1024 × 1024 px; processed images 32 × 32 px; target camera 640 × 480 px
- Data modality: RGB image

### Metrics
- Accuracy: Masked-face classifier 96.86% correctly masked and 96.40% incorrectly masked; total system 79.51% correctly masked and 79.13% incorrectly masked
- mAP: Not reported
- Precision: Masked-face classifier 96.40%; face detection 82.09%
- Recall: Masked-face classifier 96.58%; face detection 80.29%
- F1-score: Not reported
- Latency: Total system time 1113.55 ms to 3642.75 ms depending on window size
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: 128 KB RAM available; external RAM required for 640 × 480 RGB565 image storage
- Flash usage: 512 KB Flash available
- Energy per inference: 0.037 J to 0.120 J depending on window size
- Power consumption: 33 mW during operation

### Optimization
- Techniques used: Lightweight K-means, preprocessing filters, 32 × 32 downscaling, sliding window tuning, squared Euclidean distance instead of Euclidean distance
- Quantization: Not reported
- Pruning: No
- Knowledge distillation: No
- Compression method: Not reported
- Hardware-specific optimization: Squared Euclidean distance reduces computation time and energy on MCU
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: 0.037 J to 0.120 J
- Latency on target device reported: 1113.55 ms to 3642.75 ms total system time
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: Yes
- Reason: The system is deployed on an STM32F411 ARM Cortex-M4 microcontroller with 128 KB RAM, 512 KB Flash, 33 mW operation, and battery-life evaluation.

### Benchmarking / Standardization
- Benchmark used: Not reported
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: Yes
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: The masked-face classifier achieved over 96% accuracy, precision, recall, TPR, and TNR. The full system achieved over 79% accuracy and up to 145.48 days of estimated battery uptime using a 2500 mAh 18650 battery.

### Limitations
- Face detection accuracy and face detection speed still require improvement.
- Future work may evaluate other classification algorithms, preprocessing methods, and hardware platforms.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a battery-operated TinyML system using K-means, sliding-window face detection, and lightweight preprocessing to verify whether a face mask is worn properly on an STM32F411 microcontroller.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Piątkowski et al. | 2022 | Classification; face detection | K-means with sliding window | Lightweight preprocessing and squared Euclidean distance optimization | STM32F411CE / Blackpill | MaskedFace-Net; Natural images | Accuracy 96.86% correctly masked; total system accuracy 79.51% | 1113.55–3642.75 ms | N/A | 128 KB RAM | 512 KB Flash | 0.037–0.120 J | N/A | N/A | N/A | Yes |
