## Paper ID: Design-and-development-of-an-AI-based-real-time-road-sign-detection-system-for-automatic-speed-control

TinyML classification: Near-TinyML — The vision inference runs on Raspberry Pi 4B rather than an explicitly MCU-class TinyML platform, while the ESP32 is used for speed-control actuation.

### Basic Info
- Authors: Shruti S. Mohite, Dadaso D. Mohite, Arati J. Vyavahare, Kiran Challke, Tanmayee Kale
- Year: 2025
- Title: Design and development of an AI-based real-time road sign detection system for automatic speed control
- Source: Discover Electronics
- Type: Experimental

### Problem & Context
- Task: Object detection and classification
- Objective: Design and validate a real-time road sign detection system with automatic vehicle speed regulation.
- Application domain: Intelligent transportation systems and road safety
- Scenario: Embedded edge vehicular prototype
- TinyML relevance: Partial
- TinyML justification: The system uses embedded edge hardware, but visual inference is deployed on a Raspberry Pi 4B rather than an explicitly MCU-class TinyML platform.

### Model / Method
- Model: R-CNN for road sign detection and localization; CNN for road sign classification
- Architecture family: Hybrid CNN
- Techniques: RGB-to-HSV preprocessing, resizing, normalization, data augmentation, CNN + R-CNN two-stage pipeline
- Framework: OpenCV; deep learning framework not reported
- Training type: Fine-tuning for R-CNN with ResNet-50 backbone pretrained on ImageNet; CNN training type not explicitly reported
- Inference type: On-device

### Hardware
- Device: Raspberry Pi 4B, ESP32-WROOM-32, Raspberry Pi Camera v2, L298N motor driver, 16×2 LCD
- Hardware type: CPU / MCU / Other
- Processor / microcontroller: Raspberry Pi 4B for image processing; ESP32-WROOM-32 for speed control and actuation
- Clock frequency: Not reported
- SRAM / RAM: Raspberry Pi 4B with 4 GB RAM
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Resource-constrained hardware, latency, computational demand, cost-effectiveness, real-time response

### Dataset
- Name: Custom traffic sign dataset
- Type: Private
- Dataset size: 1,500 labeled images; 1,200 training images and 300 testing images
- Number of classes: 5
- Input resolution: Images resized to 128×128 pixels; camera capture reported at 640×480 pixels and 30 FPS
- Data modality: RGB image and video

### Metrics
- Accuracy: 94.6% average detection accuracy; 95.3% School Zone, 94.7% Hospital Zone, 96.1% Speed Breaker, 92.8% Construction Zone, 94.2% Railway Crossing
- mAP: Not reported
- Precision: 91.7% reported in comparative table
- Recall: 90.4% reported in comparative table
- F1-score: Not reported
- Latency: Approximately 200 ms sign detection/classification time; 298±18 ms total end-to-end latency; 200±20 ms end-to-end response time; 210 ms reported in comparative table
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: CNN per-layer parameters reported as 896, 18,496, 73,856, 262,272, and 645; total not explicitly reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Image preprocessing, data augmentation, compact CNN design, two-stage CNN/R-CNN pipeline selection for embedded feasibility
- Quantization: None reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Not reported
- Hardware-specific optimization: Deployment on Raspberry Pi 4B with ESP32-based PWM control
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Approximately 200 ms sign detection/classification time; 298±18 ms total end-to-end latency
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: UART communication between Raspberry Pi and ESP32 is used; no cloud communication is reported
- Candidate for Strict TinyML: No
- Reason: The inference hardware is Raspberry Pi 4B with 4 GB RAM, while the ESP32 is used for actuation, so the paper does not demonstrate MCU-class visual inference or report MCU-level memory, flash, or energy constraints.

### Benchmarking / Standardization
- Benchmark used: Custom dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: ImageNet used for ResNet-50 pretraining
- Comparison with baseline models: No direct experimental baseline comparison reported
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: The proposed embedded system achieved 94.6% average road sign detection accuracy across five traffic sign classes and demonstrated real-time speed regulation using Raspberry Pi 4B and ESP32. Reported latency values include approximately 200 ms for sign detection/classification and 298±18 ms for the full detection-to-speed-control loop.

### Limitations
- Limited dataset and controlled testing conditions.
- Heavy occlusion, extreme noise, and complex real-world traffic conditions remain future challenges.
- The system does not introduce a new detection algorithm and future work is needed for lightweight or quantized model deployment.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes an embedded AI-based real-time road sign detection and automatic speed control prototype combining Raspberry Pi-based CNN/R-CNN vision inference with ESP32-based PWM motor control.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Mohite et al. | 2025 | Object detection and classification | CNN + R-CNN | RGB-HSV preprocessing, augmentation, embedded deployment | Raspberry Pi 4B + ESP32-WROOM-32 | Custom traffic sign dataset | 94.6% accuracy | 298±18 ms end-to-end latency | N/A | 4 GB RAM | N/A | N/A | OpenCV | N/A | None | No |
