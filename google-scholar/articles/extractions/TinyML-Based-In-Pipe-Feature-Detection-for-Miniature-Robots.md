## Paper ID: TinyML-Based-In-Pipe-Feature-Detection-for-Miniature-Robots

TinyML classification: Strict TinyML — The work explicitly targets MCU-class deployment on an ESP32 with 520 kB RAM and reports peak RAM, flash usage, and latency.

### Basic Info
- Authors: Manman Yang; Andrew Blight; Hitesh Bhardwaj; Nabil Shaukat; Linyan Han; Robert Richardson; Andrew Pickering; George Jackson-Mills; Andrew Barber
- Year: 2025
- Title: TinyML-Based In-Pipe Feature Detection for Miniature Robots
- Source: Sensors 2025, 25, 1782
- Type: Experimental

### Problem & Context
- Task: Classification
- Objective: Identify pipeline features such as elbows, joints, left turns, right turns, and T-junctions for miniature robot navigation.
- Application domain: Autonomous in-pipe exploration and inspection
- Scenario: Embedded miniature autonomous robot
- TinyML relevance: Yes
- TinyML justification: The paper targets resource-constrained deployment on an ESP32 microcontroller and reports RAM usage, flash usage, and inference latency.

### Model / Method
- Model: Custom five-layer CNN
- Architecture family: CNN
- Techniques: 8-bit quantization, custom CNN architecture selection, sliding window smoothing
- Framework: Edge Impulse; exported as an Arduino library
- Training type: From scratch
- Inference type: On-device

### Hardware
- Device: Joey miniature in-pipe robot with OV2640 camera and ESP32 board
- Hardware type: MCU
- Processor / microcontroller: ESP32
- Clock frequency: 240 MHz
- SRAM / RAM: 520 kB RAM; 195.1 kB peak RAM usage
- Flash / ROM / Storage: 4 MB flash; 427.9 kB flash usage
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, flash, latency, compute, resource-constrained deployment

### Dataset
- Name: Custom pipeline feature dataset
- Type: Private
- Dataset size: 4629 unique images; 958 test images
- Number of classes: 5
- Input resolution: 96 × 96
- Data modality: Grayscale image

### Metrics
- Accuracy: 97.1%
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Approximately 0.95 weighted average F1-score between thresholds 0.1 and 0.5
- Latency: 1693 ms
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: 195.1 kB peak RAM
- Flash usage: 427.9 kB
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: 8-bit quantization, custom CNN architecture selection, sliding window smoothing
- Quantization: INT8
- Pruning: No
- Knowledge distillation: No
- Compression method: 8-bit quantization
- Hardware-specific optimization: CNN architecture selected according to ESP32 RAM and flash constraints
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: 195.1 kB
- Flash usage reported: 427.9 kB
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: 1693 ms
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: Yes
- Reason: The method is deployed on an ESP32 microcontroller with explicit RAM, flash, and latency measurements.

### Benchmarking / Standardization
- Benchmark used: Custom pipeline feature dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes, multiple CNN and MobileNetV1/MobileNetV2 variants were compared.
- Comparison with previous works: Related works are discussed, but no direct standardized quantitative comparison is reported.
- Reproducibility artifacts available: Not reported

### Results
- Summary: The selected five-layer CNN achieved 97.1% accuracy, macro-average AUC of 0.96, 195.1 kB peak RAM usage, 427.9 kB flash usage, and 1693 ms inference time. The sliding window smoothing strategy reduced transient misclassifications during robot testing.

### Limitations
- Joint and T-junction classes showed lower separability and higher uncertainty than stronger classes such as elbow and right turn.
- The paper identifies depth information or range sensing as future improvements for spatial perception and localization.

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
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a TinyML-based resource-efficient in-pipe feature detection method using a custom five-layer CNN deployed on an ESP32-equipped miniature robot.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Yang et al. | 2025 | Classification | Custom five-layer CNN | INT8 quantization + sliding window smoothing | ESP32 / Joey miniature robot | Custom pipeline feature dataset, 4629 images | Accuracy 97.1% | 1693 ms | N/A | 195.1 kB peak RAM | 427.9 kB | N/A | Edge Impulse / Arduino library | INT8 | N/A | Yes |
