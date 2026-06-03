## Paper ID: Alternatives-for-Locating-People-Using-Cameras-and-Embedded-AI-Accelerators-A-Practical-Approach

TinyML classification: Near-TinyML — Uses embedded edge AI acceleration for camera-based person detection/localization, but the platform is Google Coral Edge TPU rather than an MCU-class target.

### Basic Info
- Authors: Ángel Carro-Lagoa, Valentín Barral, Miguel González-López, Carlos J. Escudero, Luis Castedo
- Year: 2021
- Title: Alternatives for Locating People Using Cameras and Embedded AI Accelerators: A Practical Approach
- Source: Eng. Proc. 2021, 7, 53 / 4th XoveTIC Conference
- Type: Experimental

### Problem & Context
- Task: Person detection, pose estimation, indoor localization
- Objective: Evaluate indoor person localization using cameras and embedded edge devices with AI accelerators.
- Application domain: Indoor localization, surveillance, activity monitoring, healthcare
- Scenario: Edge, embedded AI, smart camera
- TinyML relevance: Partial
- TinyML justification: The paper targets embedded edge AI acceleration using Google Coral Edge TPU, but does not report MCU-class deployment or microcontroller-level constraints.

### Model / Method
- Model: PoseNet with ResNet50 backbone
- Architecture family: CNN
- Techniques: Pose estimation, post-processing of keypoints, homography-based projection to 2D map
- Framework: Not reported
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: Embedded device with Google Coral Edge TPU
- Hardware type: NPU
- Processor / microcontroller: Google Coral Edge TPU
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Low-power inference and edge processing

### Dataset
- Name: CamLoc; ICG Lab6
- Type: Public
- Dataset size: Not reported
- Number of classes: 1 person class
- Input resolution: 416×288
- Data modality: Video / RGB camera images

### Metrics
- Accuracy: Not reported
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
- Techniques used: Embedded AI acceleration, pose-based localization, post-processing of keypoints
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Not reported
- Hardware-specific optimization: Google Coral Edge TPU deployment
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
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper uses embedded Edge TPU acceleration but does not provide evidence of MCU-class deployment, bare-metal execution, or microcontroller-level memory and energy constraints.

### Benchmarking / Standardization
- Benchmark used: CamLoc; ICG Lab6
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: The proposed pose-based indoor localization system achieved lower mean error than CamLoc on the CamLoc dataset for all reported cameras. On ICG Lab6, results were competitive in some scenarios but affected by close-person interactions and limited tracking.

### Limitations
- The method struggles when people are close together because the pose estimator can mix keypoints from different people.
- Complex multi-person scenarios require a stronger tracking algorithm that uses appearance information.

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
- This paper proposes a camera-based indoor person localization method using pose estimation and embedded AI acceleration with a Google Coral Edge TPU.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Carro-Lagoa et al. | 2021 | Person detection / indoor localization | PoseNet ResNet50 | Pose estimation and keypoint post-processing | Google Coral Edge TPU | CamLoc; ICG Lab6 | Mean localization error | N/A | N/A | N/A | N/A | N/A | N/A | N/A | None | No |
