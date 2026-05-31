## Paper ID: PhiNets-A-Scalable-Backbone-for-Low-power-AI-at-the-Edge

TinyML classification: Strict TinyML — Explicitly targets MCU-class computer vision deployment with reported Flash/RAM constraints, latency/energy behavior, and STM32H743 implementation.

### Basic Info
- Authors: Francesco Paissan, Alberto Ancilotto, Elisabetta Farella
- Year: 2022
- Title: PhiNets: A Scalable Backbone for Low-power AI at the Edge
- Source: ACM Transactions on Embedded Computing Systems, Vol. 21, No. 5, Article 53
- Type: Methodological

### Problem & Context
- Task: Object detection and multi-object tracking
- Objective: Propose a scalable CNN backbone optimized for low-power image processing on resource-constrained platforms.
- Application domain: Embedded vision, IoT monitoring, smart-city visual tracking
- Scenario: Edge, embedded, IoT, MCU-based visual node
- TinyML relevance: Yes
- TinyML justification: The paper explicitly targets MCU-scale inference and demonstrates deployment on an STM32H743 MCU with 2 MB Flash, 1 MB RAM, and measured low-power operation.

### Model / Method
- Model: PhiNets backbone with YOLOv2 detection head and SORT tracker
- Architecture family: CNN
- Techniques: Hardware-aware scaling, decoupled optimization of MACs, working memory and parameter memory, inverted residual blocks, squeeze-and-excitation blocks, skip connections, architecture scaling
- Framework: STMicroelectronics-Cube-AI, TensorFlow profiler, arm-eabi-none-gcc
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: Prototype hardware board based on STM32H743 microcontroller
- Hardware type: MCU
- Processor / microcontroller: STM32H743
- Clock frequency: 300 MHz for reported power measurements
- SRAM / RAM: 1 MB RAM
- Flash / ROM / Storage: 2 MB internal Flash
- Power consumption: 13 mW at 10 fps for the 1.23 MMAC network; 162 mW for the 6.1 MMAC network at approximately 14 fps; 13 mW to 118 mW for 10 fps operation depending on model complexity
- Energy per inference: Under 1.3 mJ for the 1.2 MMAC PhiNet and 11.8 mJ for the 9.8 MMAC PhiNet
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, power, latency, compute, MAC count, working memory, parameter memory, real-time operation

### Dataset
- Name: COCO subset, VOC2012 subset, MOT15
- Type: Public
- Dataset size: Not reported
- Number of classes: 1 class for detection benchmarks, using the “person” class
- Input resolution: 96 × 96, 128 × 128, and 160 × 160 depending on model/task
- Data modality: Images and video frames

### Metrics
- Accuracy: Not reported
- mAP: 53.7/60.3 mAP on COCO/VOC2012 for the 1.2 MMAC PhiNet; 64.1/73.9 mAP on COCO/VOC2012 for the 9.8 MMAC PhiNet
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Approximately 15 ms to 120 ms per inference depending on model complexity
- FPS: Over 50 fps possible on the proposed hardware; approximately 14 fps for the 6.1 MMAC network at 100% duty cycle; 10 fps low-power operation reported
- Throughput: Not reported
- Model size: Not reported as file size
- Parameters: 14.3K to 61.2K parameters for detection PhiNets; 21.6K to 39.9K parameters for tracking PhiNets
- MACs / FLOPs: 1.23M to 10.42M MACs
- RAM usage: Approximately 80 KB to 120 KB working memory shown for the default network across tested expansion-factor values
- Flash usage: Approximately 26 KB to 36 KB Flash shown for the default network across tested shape-factor values
- Energy per inference: Under 1.3 mJ for the 1.2 MMAC PhiNet and 11.8 mJ for the 9.8 MMAC PhiNet
- Power consumption: 13 mW at 10 fps for the 1.23 MMAC network; 118 mW at 10 fps for the higher-performance configuration

### Optimization
- Techniques used: Hardware-aware network scaling, scalable CNN architecture, decoupled MAC/RAM/Flash optimization, parameter-efficient inverted residual blocks
- Quantization: INT8
- Pruning: No
- Knowledge distillation: No
- Compression method: Parameter-efficient scalable architecture
- Hardware-specific optimization: STMicroelectronics-Cube-AI runtime and hardware-aware scaling for MCU resource constraints
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Approximately 80 KB to 120 KB working memory shown for the default network; target MCU has 1 MB RAM
- Flash usage reported: Approximately 26 KB to 36 KB Flash shown for the default network; target MCU has 2 MB internal Flash
- Model size reported: Not reported as file size; parameter counts are reported
- Energy per inference reported: Under 1.3 mJ for the 1.2 MMAC PhiNet and 11.8 mJ for the 9.8 MMAC PhiNet
- Latency on target device reported: Approximately 15 ms to 120 ms per inference depending on model complexity
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly demonstrates MCU-class computer vision inference on an STM32H743 with reported memory constraints, MAC counts, latency, energy, and power consumption.

### Benchmarking / Standardization
- Benchmark used: COCO subset, VOC2012 subset, MOT15
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: COCO, Pascal VOC2012, MOT15
- Comparison with baseline models: Yes, compared with MobileNetV2 and EfficientNet
- Comparison with previous works: Yes
- Reproducibility artifacts available: Code

### Results
- Summary: PhiNets achieved higher object detection and tracking performance than MobileNetV2 and EfficientNet in the 1M–10M MAC range. The deployed MCU prototype achieved low-power operation, including 10 fps tracking at approximately 13 mW for the smallest configuration.

### Limitations
- Not reported

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes PhiNets, a scalable CNN backbone for MCU-class low-power object detection and multi-object tracking that decouples compute, working memory, and parameter memory constraints.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Paissan et al. | 2022 | Object detection; multi-object tracking | PhiNets + YOLOv2 + SORT | Hardware-aware scalable CNN backbone | STM32H743 MCU prototype | COCO subset; VOC2012 subset; MOT15 | 64.1/73.9 mAP on COCO/VOC2012 and 60.8 MOTA on MOT15 for the 9.8 MMAC PhiNet | 15–120 ms | N/A; 14.3K–61.2K parameters reported | 1 MB RAM; approx. 80–120 KB WM plotted | 2 MB Flash; approx. 26–36 KB Flash plotted | 1.3 mJ for 1.2 MMAC; 11.8 mJ for 9.8 MMAC | STMicroelectronics-Cube-AI | INT8 | None | Yes |
