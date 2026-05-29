## Paper ID: <to be filled manually>

TinyML classification: Strict TinyML — explicitly targets MCU-class deployment with GAP9 RISC-V MCU, low-power on-device inference, INT8 quantization, and reported latency and energy constraints.

### Basic Info
- Authors: Liam Boyle; Julian Moosmann; Nicolas Baumann; Seonyeong Heo; Michele Magno
- Year: 2024
- Title: DSORT-MCU: Detecting Small Objects in Real Time on Microcontroller Units
- Source: IEEE Sensors Journal, Vol. 24, No. 24, 15 December 2024
- Type: Experimental / Methodological

### Problem & Context
- Task: Object detection
- Objective: Improve real-time small object detection on microcontroller units using adaptive tiling for lightweight object detection networks.
- Application domain: Carpark monitoring / drone-based car detection
- Scenario: Edge, embedded, IoT, MCU
- TinyML relevance: Yes
- TinyML justification: The paper targets low-power, memory-constrained MCUs and deploys quantized object detection models on the GAP9 RISC-V microcontroller.

### Model / Method
- Model: FOMO and TinyissimoYOLOv1.3 with adaptive tiling
- Architecture family: CNN
- Techniques: Adaptive tiling, overlapping tiles, prediction fusion, soft F1 loss, INT8 quantization, hardware-accelerated inference
- Framework: NNTool and Autotiler
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: GAP9 evaluation kit
- Hardware type: MCU / SoC with ML accelerator
- Processor / microcontroller: GAP9 RISC-V MCU with nine RISC-V cores, one fabric controller, and NE16 accelerator
- Clock frequency: 370 MHz
- SRAM / RAM: 1.6 MB on-chip RAM
- Flash / ROM / Storage: 2 MB on-chip nonvolatile memory
- Power consumption: Not reported
- Energy per inference: Approximately 0.03–1.27 mJ/inference
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, power, latency, computation, FLASH, RAM, object size, input resolution

### Dataset
- Name: CARPK
- Type: Not reported
- Dataset size: Close to 1500 images and more than 90,000 cars
- Number of classes: Not reported
- Input resolution: FOMO: 48×48, 96×96, 192×192; TinyissimoYOLOv1.3: 256×256
- Data modality: Drone imagery

### Metrics
- Accuracy: Not reported
- mAP: Not reported
- Precision: FOMO + tiling + F1 loss: 0.99; TinyissimoYOLO + tiling: up to 0.93
- Recall: FOMO + tiling + F1 loss: 0.85; TinyissimoYOLO + tiling: up to 0.89
- F1-score: FOMO + tiling + F1 loss: 0.91; TinyissimoYOLO + tiling: up to 0.91
- Latency: 0.6–16.2 ms/inference
- FPS: FOMO full-image inference: 33.4 FPS; TinyissimoYOLO full-image inference: 2.8 FPS
- Throughput: Not reported
- Model size: Not reported
- Parameters: FOMO: 19K; TinyissimoYOLO + tiling: 403K
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Approximately 0.03–1.27 mJ/inference
- Power consumption: Not reported

### Optimization
- Techniques used: Adaptive tiling, prediction fusion, soft F1 loss, INT8 quantization, graph optimization, C-code generation with Autotiler, NE16 acceleration
- Quantization: INT8
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: INT8 quantization and lightweight CNN architectures
- Hardware-specific optimization: NNTool optimization and Autotiler code generation for GAP9 / NE16
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: FOMO: 19K parameters; TinyissimoYOLO + tiling: 403K parameters
- Energy per inference reported: Approximately 0.03–1.27 mJ/inference
- Latency on target device reported: 0.6–16.2 ms/inference
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: Yes
- Reason: The paper deploys INT8 object detection models fully on an MCU-class RISC-V device with reported latency, energy, RAM capacity, nonvolatile memory capacity, and real-time inference results.

### Benchmarking / Standardization
- Benchmark used: CARPK
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: MS COCO mentioned for contextual comparison of small-object detection performance
- Comparison with baseline models: Standard FOMO, modified FOMO without fusion, FOMO with tiling, FOMO with tiling and soft F1 loss, TinyissimoYOLO with tiling
- Comparison with previous works: YOLO, YOLOv4, and previous CARPK object counting methods
- Reproducibility artifacts available: Code

### Results
- Summary: Adaptive tiling improves small-object detection on MCUs, increasing FOMO F1-score by 225% and reducing object count error by 76%. TinyissimoYOLOv1.3 with tiling reaches 6.2 MAE and 0.91 F1 on CARPK while running on GAP9.

### Limitations
- Tiling increases processing time because multiple tiles must be processed per image.
- FOMO performance stagnates at higher target object size and 192×192 input resolution.
- TinyissimoYOLO performance decreases at target NBA 6% because many objects are intersected by tile boundaries.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes an adaptive tiling and prediction fusion method for real-time small object detection on MCU-class devices using lightweight CNN-based detectors.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Boyle et al. | 2024 | Object detection | FOMO + TinyissimoYOLOv1.3 | Adaptive tiling + prediction fusion + INT8 quantization | GAP9 RISC-V MCU with NE16 accelerator | CARPK | MAE 6.2 / F1 0.91 | 0.6–16.2 ms/inference | 19K–403K parameters | 1.6 MB on-chip RAM | 2 MB on-chip NVM | 0.03–1.27 mJ/inference | NNTool + Autotiler | INT8 | None | Yes |
