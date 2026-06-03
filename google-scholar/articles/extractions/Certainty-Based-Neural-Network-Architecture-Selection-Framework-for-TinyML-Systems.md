## Paper ID: Certainty-Based-Neural-Network-Architecture-Selection-Framework-for-TinyML-Systems

TinyML classification: Strict TinyML — Explicitly targets MCU-class TinyML deployment on an STM32L476RG ARM Cortex-M4 device with reported memory and latency constraints.

### Basic Info

* Authors: Joanna Komorniczak, Tobiasz Puślecki, Paweł Ksieniewicz, Krzysztof Walkowiak
* Year: 2024
* Title: Certainty-Based Neural Network Architecture Selection Framework for TinyML Systems
* Source: IEEE Access
* Type: Methodological

### Problem & Context

* Task: Classification
* Objective: Select CNN architectures dynamically according to data-stream difficulty to balance inference time and recognition quality.
* Application domain: Computer vision data streams with time-varying difficulty
* Scenario: TinyML, embedded, IoT, edge
* TinyML relevance: Yes
* TinyML justification: The paper targets TinyML systems with memory, energy, and latency constraints and evaluates models on an STM32 Cortex-M microcontroller.

### Model / Method

* Model: Certainty-based Architecture Selection framework using multiple CNN architectures
* Architecture family: CNN
* Techniques: Certainty-based dynamic architecture switching, Mean Predictive Support, neural architecture search, INT8 quantization
* Framework: PyTorch, STM32Cube.AI, TensorFlow Lite Converter
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: NUCLEO-L476RG
* Hardware type: MCU
* Processor / microcontroller: STM32L476RG, ARM Cortex-M4
* Clock frequency: 80 MHz
* SRAM / RAM: 128 kB SRAM
* Flash / ROM / Storage: 1 MB Flash
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, latency, compute, MACC

### Dataset

* Name: MNIST, SVHN
* Type: Public
* Dataset size: MNIST stream used 60,000 objects; SVHN stream used 73,257 objects; training used 10,000 MNIST objects and 26,000 SVHN objects
* Number of classes: 10
* Input resolution: Not reported
* Data modality: Monochromatic digit images for MNIST; color digit images for SVHN

### Metrics

* Accuracy: MNIST CAS accuracy approximately 0.934–0.941; SVHN CAS accuracy approximately 0.800–0.808
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 10.821–83.646 ms for MNIST models; 25.012–146.475 ms for SVHN models
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: 83,175–1,987,995 MACC for MNIST models; 310,741–4,011,611 MACC for SVHN models
* RAM usage: 4,144–15,308 B for MNIST models; 8,260–16,948 B for SVHN models
* Flash usage: 30,765–61,997 B for MNIST models; 33,784–67,022 B for SVHN models
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Dynamic architecture selection, certainty-based switching, Pareto architecture selection, INT8 quantization
* Quantization: INT8
* Pruning: No
* Knowledge distillation: Not reported
* Compression method: 32-bit floating-point weights quantized to 8-bit integers
* Hardware-specific optimization: STM32Cube.AI balanced optimization mode
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: 4,144–16,948 B RAM usage depending on architecture
* Flash usage reported: 30,765–67,022 B depending on architecture
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 10.821–146.475 ms depending on architecture and dataset
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Yes
* Reason: The paper evaluates CNN inference on an STM32L476RG ARM Cortex-M4 microcontroller and reports MCU-level RAM, Flash, latency, and MACC metrics.

### Benchmarking / Standardization

* Benchmark used: MNIST and SVHN data streams
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: MNIST, SVHN
* Comparison with baseline models: Yes
* Comparison with previous works: Not reported
* Reproducibility artifacts available: Code

### Results

* Summary: The CAS framework reduced inference cost by dynamically selecting simpler or more complex CNN architectures according to model certainty. MNIST streams showed very small accuracy loss with large estimated latency and MACC reductions, while SVHN streams showed larger accuracy loss of about two percentage points.

### Limitations

* Model-switching thresholds were manually calibrated and require knowledge of the recognition task.
* Some architecture ordering based on desktop experiments did not fully match TinyML device metrics.
* The relationship between stream difficulty and selected architecture was less clear for SVHN streams.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a certainty-based CNN architecture selection framework for TinyML computer vision data streams that dynamically switches models to reduce inference time while preserving classification accuracy.

| Paper              | Year | Task           | Model                       | Technique                                                          | Device                      | Dataset     | Main Metric                                   | Latency           | Model Size | SRAM/RAM       | Flash           | Energy | Framework                                        | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------------ | ---- | -------------- | --------------------------- | ------------------------------------------------------------------ | --------------------------- | ----------- | --------------------------------------------- | ----------------- | ---------- | -------------- | --------------- | ------ | ------------------------------------------------ | -------- | ------------- | ------------- |
| Komorniczak et al. | 2024 | Classification | CAS framework with CNN pool | Certainty-based dynamic architecture selection + INT8 quantization | STM32L476RG / NUCLEO-L476RG | MNIST, SVHN | Accuracy: MNIST 0.934–0.941; SVHN 0.800–0.808 | 10.821–146.475 ms | N/A        | 4,144–16,948 B | 30,765–67,022 B | N/A    | PyTorch, STM32Cube.AI, TensorFlow Lite Converter | INT8     | None          | Yes           |
