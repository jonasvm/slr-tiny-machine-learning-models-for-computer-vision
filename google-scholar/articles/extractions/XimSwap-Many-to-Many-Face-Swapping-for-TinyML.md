## Paper ID: XimSwap-Many-to-Many-Face-Swapping-for-TinyML

TinyML classification: Strict TinyML — explicitly targets microcontroller-class deployment, including STM32H743 MCU execution under tight memory and energy constraints.

### Basic Info
- Authors: Alberto Ancilotto, Francesco Paissan, Elisabetta Farella
- Year: 2024
- Title: XimSwap: Many-to-Many Face Swapping for TinyML
- Source: ACM Transactions on Embedded Computing Systems, Vol. 23, No. 3, Article 49
- Type: Methodological

### Problem & Context
- Task: Face swapping / video anonymization
- Objective: Enable real-time face anonymization directly on resource-constrained edge devices while preserving pose and facial expression.
- Application domain: Smart city video surveillance and privacy-preserving visual analytics
- Scenario: Edge, embedded, IoT, microcontroller
- TinyML relevance: Yes
- TinyML justification: The paper explicitly targets tiny edge devices and microcontrollers, including STM32H743 deployment with RAM, latency, and energy measurements.

### Model / Method
- Model: XimSwap / XiNet
- Architecture family: CNN
- Techniques: Hardware-aware scaling, convolutional block redesign, fused adaptive instance normalization, style transfer fusion, skip connection broadcasting, quantization-aware architectural design
- Framework: ONNX Runtime v1.14.1; STM32Cube.AI v6.0.0
- Training type: From scratch
- Inference type: On-device

### Hardware
- Device: Raspberry Pi 4; STM32H743 microcontroller
- Hardware type: CPU / MCU
- Processor / microcontroller: STM32H743
- Clock frequency: 480 MHz
- SRAM / RAM: STM32H743 has 1 MB RAM
- Flash / ROM / Storage: STM32H743 has 2 MB Flash
- Power consumption: Not reported
- Energy per inference: Raspberry Pi 4: 263–5025 mJ; STM32H743: 105–194 mJ
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, power, latency, compute, operator efficiency, runtime compatibility

### Dataset
- Name: VGGFace
- Type: Public
- Dataset size: Not reported
- Number of classes: Not reported
- Input resolution: 224 × 224; 112 × 112 on STM32H743 due to memory constraints
- Data modality: RGB face images

### Metrics
- Accuracy: Not reported
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Raspberry Pi 4: 52 ms, 108 ms, 308 ms, 994 ms; STM32H743: 818 ms, 1512 ms
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: 0.44M, 0.54M, 3.28M, 11.12M
- MACs / FLOPs: 250 MMAC, 460 MMAC, 1266 MMAC, 6712 MMAC
- RAM usage: 0.48 MB, 0.60 MB, 1.20 MB, 2.40 MB
- Flash usage: Not reported
- Energy per inference: Raspberry Pi 4: 263 mJ, 546 mJ, 1557 mJ, 5025 mJ; STM32H743: 105 mJ, 194 mJ
- Power consumption: Not reported

### Optimization
- Techniques used: Hardware-aware scaling, compressed convolutional blocks, operator selection for embedded devices, adaptive instance normalization fusion, RAM-efficient skip connection broadcasting
- Quantization: INT8
- Pruning: No
- Knowledge distillation: No
- Compression method: Architectural compression and fusion of style transfer layers into convolutional blocks
- Hardware-specific optimization: Yes
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: 0.48 MB and 0.60 MB for STM32H743-capable models
- Flash usage reported: Not reported
- Model size reported: Parameters reported; file size not reported
- Energy per inference reported: STM32H743: 105 mJ and 194 mJ
- Latency on target device reported: STM32H743: 818 ms and 1512 ms
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly deploys XimSwap on an STM32H743 microcontroller with reported RAM, latency, and energy constraints.

### Benchmarking / Standardization
- Benchmark used: VGGFace-based evaluation
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: VGGFace
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: XimSwap achieves comparable anonymization performance to larger face-swapping models while reducing operations and parameters by over 98%. The smallest deployed models run on STM32H743 with 0.48–0.60 MB RAM and 105–194 mJ per inference.

### Limitations
- The STM32H743 evaluation required 112 × 112 input resolution instead of 224 × 224, and the two largest models could not run on the microcontroller due to memory constraints.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a TinyML-oriented many-to-many face-swapping architecture that enables privacy-preserving video anonymization on resource-constrained embedded devices and microcontrollers.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Ancilotto et al. | 2024 | Face swapping / video anonymization | XimSwap / XiNet | Hardware-aware scaling + fused identity injection | Raspberry Pi 4; STM32H743 MCU | VGGFace | Anonymization rate up to 99.14% | STM32H743: 818–1512 ms; Raspberry Pi 4: 52–994 ms | N/A | 0.48–2.40 MB | N/A | STM32H743: 105–194 mJ; Raspberry Pi 4: 263–5025 mJ | ONNX Runtime; STM32Cube.AI | INT8 | None | Yes |
