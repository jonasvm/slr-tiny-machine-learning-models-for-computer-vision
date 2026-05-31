## Paper ID: XimSwap-Many-to-Many-Face-Swapping-for-TinyML

TinyML classification: Strict TinyML — The paper explicitly targets MCU-class deployment and reports execution on an STM32H743 microcontroller with constrained RAM/Flash, latency, and energy measurements.

### Basic Info

* Authors: Alberto Ancilotto, Francesco Paissan, Elisabetta Farella
* Year: 2024
* Title: XimSwap: Many-to-Many Face Swapping for TinyML
* Source: ACM Transactions on Embedded Computing Systems, Vol. 23, No. 3, Article 49
* Type: Methodological

### Problem & Context

* Task: Face swapping / face anonymization
* Objective: Enable real-time face anonymization directly on edge devices while preserving pose and facial expression.
* Application domain: Privacy-preserving video analytics and smart city surveillance
* Scenario: Edge, embedded, IoT, microcontroller-based deployment
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets resource-constrained embedded devices and evaluates deployment on an STM32H743 microcontroller.

### Model / Method

* Model: XimSwap / XiNet-based face-swapping architecture
* Architecture family: CNN
* Techniques: Hardware-aware scaling, architecture compression, style transfer layer fusion into convolutional blocks, RAM reduction, operator selection, quantization-aware architectural design
* Framework: ONNXRuntime v1.14.1 for Raspberry Pi 4; STM32Cube.AI v6.0.0 for STM32H743
* Training type: Trained on VGGface for 300K steps; initialization not reported
* Inference type: On-device

### Hardware

* Device: Raspberry Pi 4; STM32H743 microcontroller
* Hardware type: CPU / MCU
* Processor / microcontroller: STM32H743; Raspberry Pi 4 ARM64 device
* Clock frequency: 480 MHz for STM32H743; not reported for Raspberry Pi 4
* SRAM / RAM: STM32H743 has 1 MB RAM; model RAM ranges from 480 KB to 2.40 MB
* Flash / ROM / Storage: STM32H743 has 2 MB Flash memory
* Power consumption: Not reported
* Energy per inference: 263 mJ to 5025 mJ on Raspberry Pi 4; 105 mJ to 194 mJ on STM32H743
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, Flash, RAM, latency, energy, MAC count, parameters, operator support, runtime compatibility

### Dataset

* Name: VGGface
* Type: Public
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: 224 × 224 generally; 112 × 112 on STM32H743 due to memory constraints
* Data modality: Face images

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 52 ms, 108 ms, 308 ms, and 994 ms on Raspberry Pi 4; 818 ms and 1512 ms on STM32H743
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: 0.44M to 11.12M
* MACs / FLOPs: 250 MMAC to 6712 MMAC
* RAM usage: 0.48 MB to 2.40 MB
* Flash usage: Not reported
* Energy per inference: 263 mJ to 5025 mJ on Raspberry Pi 4; 105 mJ to 194 mJ on STM32H743
* Power consumption: Not reported

### Optimization

* Techniques used: Hardware-aware scaling, compressed Conv2D blocks, attention module optimization, skip-connection broadcasting, style transfer fusion, operator selection for embedded devices
* Quantization: INT8 / uint8
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Architectural compression and fusion of adaptive instance normalization into convolutional weights
* Hardware-specific optimization: Yes, hardware-aware scaling for parameter count, RAM usage, and MAC count
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: 480 KB to 2.40 MB RAM usage depending on model scale
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: 105 mJ and 194 mJ on STM32H743 for the two smallest models
* Latency on target device reported: 818 ms and 1512 ms on STM32H743
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly evaluates XimSwap on an STM32H743 microcontroller with RAM, latency, energy, parameters, and MAC constraints.

### Benchmarking / Standardization

* Benchmark used: VGGface
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: SimSwap, MobileFaceSwap, FaceShifter
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: XimSwap reduces operations and parameters by over 98% compared with state-of-the-art face-swapping architectures while preserving anonymization performance. The two smallest XiNet variants run on STM32H743 with 818 ms / 105 mJ and 1512 ms / 194 mJ inference results.

### Limitations

* The two largest XiNet models could not run on STM32H743 due to memory constraints.
* STM32H743 evaluation used 112 × 112 input resolution instead of 224 × 224 due to memory constraints.
* Networks smaller than α = 0.4 were not evaluated because of increased keypoint position error.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes XimSwap, a hardware-aware many-to-many face-swapping architecture for privacy-preserving video anonymization on resource-constrained edge devices including microcontrollers.

### Comparative Table

| Paper            | Year | Task                               | Model           | Technique                                        | Device                    | Dataset | Main Metric                    | Latency                       | Model Size | SRAM/RAM                                | Flash | Energy                       | Framework                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---: | ---------------------------------- | --------------- | ------------------------------------------------ | ------------------------- | ------- | ------------------------------ | ----------------------------- | ---------- | --------------------------------------- | ----- | ---------------------------- | ------------------------- | -------- | ------------- | ------------- |
| Ancilotto et al. | 2024 | Face anonymization / face swapping | XimSwap / XiNet | Hardware-aware scaling and style transfer fusion | STM32H743; Raspberry Pi 4 | VGGface | Anonymization rate up to 99.14 | 818 ms / 1512 ms on STM32H743 | N/A        | 0.48 MB / 0.60 MB on STM32H743 variants | N/A   | 105 mJ / 194 mJ on STM32H743 | STM32Cube.AI; ONNXRuntime | INT8     | N/A           | Yes           |
