## Paper ID: ZIP-CNN-Design-Space-Exploration-for-CNN-Implementation-within-a-MCU

TinyML classification: Strict TinyML — It explicitly evaluates MCU-class Cortex-M platforms with Flash/SRAM constraints and on-device latency/energy measurements.

### Basic Info
- Authors: Thomas Garbay, Khalil Hachicha, Petr Dobias, Andrea Pinna, Karim Hocine, Wilfried Dron, Pedro Lusich, Imane Khalis, Bertrand Granado
- Year: 2024
- Title: ZIP-CNN: Design Space Exploration for CNN Implementation within a MCU
- Source: ACM Transactions on Embedded Computing Systems, Vol. 24, No. 1, Article 1
- Type: Methodological

### Problem & Context
- Task: Image classification
- Objective: Propose a design space exploration methodology to estimate CNN latency, energy consumption, Flash memory, and SRAM usage for implementation within MCUs.
- Application domain: Embedded AI and TinyML deployment of CNNs
- Scenario: Edge, embedded, IoT, MCU-based systems
- TinyML relevance: Yes
- TinyML justification: The paper explicitly targets CNN implementation within microcontroller units and evaluates MCU-level memory, latency, and energy constraints.

### Model / Method
- Model: ZIP-CNN methodology with EST primitive-based inference-cost estimation model; evaluated using LeNet5, ResNet8, and ResNet26
- Architecture family: CNN
- Techniques: INT8 quantization, convolution filter pruning, knowledge distillation, design space exploration, hardware-aware inference-cost estimation
- Framework: TensorFlow; TensorFlow Lite library for INT8 quantization; ARM compiler; Wisebatt for energy simulation
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: STM32L496ZG, STM32F446ZE, STM32F746ZG
- Hardware type: MCU
- Processor / microcontroller: STM32L496ZG with Cortex-M4; STM32F446ZE with Cortex-M4; STM32F746ZG with Cortex-M7
- Clock frequency: STM32L496ZG: 100 kHz to 80 MHz; STM32F446ZE: 16 MHz to 180 MHz; STM32F746ZG: 200 kHz to 216 MHz
- SRAM / RAM: STM32L496ZG: 320 KB; STM32F446ZE: 132 KB; STM32F746ZG: 320 KB
- Flash / ROM / Storage: STM32L496ZG: 1 MB Flash; STM32F446ZE: 512 KB Flash; STM32F746ZG: 1 MB Flash
- Power consumption: MCU current measured using ARM-Keil UlinkPlus probe; specific power values not reported
- Energy per inference: Reported through estimation and on-device measurement across frequencies, but exact tabular energy values are not reported
- Execution without full OS: Yes
- Fully on-device inference: Yes
- Constraints mentioned: Flash memory, SRAM/RAM, latency, energy consumption, power consumption, operating frequency, battery-powered operation, compute constraints

### Dataset
- Name: MNIST; CIFAR-10
- Type: Public
- Dataset size: MNIST: 60,000 training images and 10,000 test images; CIFAR-10: 50,000 training images and 10,000 test images
- Number of classes: MNIST: 10; CIFAR-10: 10
- Input resolution: MNIST: 28 × 28 grayscale images padded to 32 × 32; CIFAR-10: 32 × 32 RGB images
- Data modality: Grayscale image; RGB image

### Metrics
- Accuracy: LeNet5: 99.02% on MNIST; ResNet26: 90.54% on CIFAR-10; ResNet8: 70.95% on CIFAR-10; distilled ResNet8: 79.39% on CIFAR-10; 70% pruned ResNet8: 71.47% on CIFAR-10
- mAP: N/A
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Estimation error ranges from 3.29% to 15.23%; LeNet5 average latency estimation difference is 5.78%; ResNet26 latency reduction is 5.96% with INT8 quantization, 72.86% with 50% pruning, 98.13% with 90% pruning, and 75% with knowledge distillation
- FPS: Not reported
- Throughput: Not reported
- Model size: ResNet26 has 372,330 parameters; ResNet8 has 78,666 parameters
- Parameters: ResNet26: 372,330; ResNet8: 78,666
- MACs / FLOPs: Not reported
- RAM usage: LeNet5 FP32 peak SRAM: 23.52 KB; LeNet5 INT8 peak SRAM: 5.88 KB; LeNet5 pruned peak SRAM: 11.760 KB at 50%/60% pruning, 7.84 KB at 70%/80% pruning, and 3.92 KB at 90% pruning; ResNet8 with 50% pruning on STM32F446ZE: 131.07 KB RAM
- Flash usage: LeNet5 FP32 estimated Flash: 248.31 KB; LeNet5 INT8 estimated Flash: 63.90 KB; ResNet26 FP32 Flash reported as insufficient for the three MCUs
- Energy per inference: Energy estimation error ranges from 3.12% to 10.34%; LeNet5 average energy estimation difference is 4.85%; ResNet26 energy reduction is 7.11% with INT8 quantization, 72.86% with 50% pruning, 98.13% with 90% pruning, and 75% with knowledge distillation
- Power consumption: MCU current measured with ARM-Keil UlinkPlus probe; specific values not reported

### Optimization
- Techniques used: INT8 quantization, convolution filter pruning, knowledge distillation, design space exploration, primitive-based hardware characterization
- Quantization: INT8
- Pruning: Yes
- Knowledge distillation: Yes
- Compression method: Post-training INT8 quantization, structured convolution filter pruning, teacher-student knowledge distillation
- Hardware-specific optimization: MCU-specific primitive characterization for latency, energy consumption, Flash memory, and SRAM estimation
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence
- SRAM peak reported: Yes; LeNet5 FP32 peak SRAM is 23.52 KB, INT8 peak SRAM is 5.88 KB, and pruned LeNet5 ranges from 11.760 KB to 3.92 KB
- Flash usage reported: Yes; LeNet5 FP32 estimated Flash is 248.31 KB and INT8 estimated Flash is 63.90 KB
- Model size reported: Yes; ResNet26 has 372,330 parameters and ResNet8 has 78,666 parameters
- Energy per inference reported: Yes; energy consumption is estimated and measured on target MCUs, with estimation error from 3.12% to 10.34%
- Latency on target device reported: Yes; latency is estimated and measured on STM32L496ZG, STM32F446ZE, and STM32F746ZG
- Runs without full operating system: Yes
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly targets MCU-class Cortex-M platforms with Flash/SRAM constraints, bare-metal suitability, and on-device latency and energy measurements.

### Benchmarking / Standardization
- Benchmark used: MNIST; CIFAR-10
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: CIFAR-10; MNIST
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Code and supplementary results

### Results
- Summary: ZIP-CNN estimates CNN latency, energy consumption, Flash memory, and SRAM usage on three STM32 MCUs with reported estimation errors of 3.29% to 15.23% for latency, 3.12% to 10.34% for energy consumption, and 1.95% to 6.31% for memory space. The methodology evaluates LeNet5, ResNet8, and ResNet26 under INT8 quantization, pruning, and knowledge distillation for MCU deployment.

### Limitations
- The paper evaluates CNN inference cost rather than the complete embedded system processing chain.
- Accuracy after reduction is evaluated after training the reduced model, while early accuracy prediction for reduced models is identified as a possible extension.
- Future work is needed to explore complete systems integrating CNNs and recent tiny transformer models.

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
- This paper proposes ZIP-CNN, a design space exploration methodology that quantitatively estimates CNN latency, energy consumption, Flash memory, and SRAM usage for implementing reduced and unreduced CNNs within MCUs.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Garbay et al. | 2024 | Image classification | LeNet5; ResNet8; ResNet26 | Design space exploration with INT8 quantization, pruning, and knowledge distillation | STM32L496ZG; STM32F446ZE; STM32F746ZG | MNIST; CIFAR-10 | Accuracy: LeNet5 99.02%, ResNet26 90.54%, ResNet8 70.95% | Estimation error 3.29%–15.23%; reductions up to 98.13% | ResNet26: 372,330 parameters; ResNet8: 78,666 parameters | LeNet5 FP32: 23.52 KB; LeNet5 INT8: 5.88 KB | LeNet5 FP32: 248.31 KB; LeNet5 INT8: 63.90 KB | Estimation error 3.12%–10.34%; reductions up to 98.13% | TensorFlow; TensorFlow Lite; ARM-Keil; Wisebatt | INT8/PTQ | N/A | Yes |
