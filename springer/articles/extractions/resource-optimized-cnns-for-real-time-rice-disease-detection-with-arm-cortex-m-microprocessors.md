## Paper ID: resource-optimized-cnns-for-real-time-rice-disease-detection-with-arm-cortex-m-microprocessors

TinyML classification: Strict TinyML — The study explicitly targets ARM Cortex-M/STM32H747i microcontroller deployment with MCU-level RAM, flash, latency, and model optimization constraints.

### Basic Info

* Authors: Hermawan Nugroho; Jing Xan Chew; Sivaraman Eswaran; Fei Siang Tay
* Year: 2024
* Title: Resource-optimized CNNs for real-time rice disease detection with ARM Cortex-M microprocessors
* Source: Plant Methods, 20:159
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Detect rice plant diseases in real time using CNN models deployed on ARM Cortex-M microprocessor hardware.
* Application domain: Smart agriculture / rice disease detection
* Scenario: Embedded, edge, on-device, microcontroller-based agricultural monitoring
* TinyML relevance: Yes
* TinyML justification: The paper targets ARM Cortex-M/STM32 microcontroller deployment with constrained RAM, flash memory, latency, and model optimization requirements.

### Model / Method

* Model: MobileNetV2; FD-MobileNet; MobileNetV1; ResNetV1; SqueezeNetV1.1
* Architecture family: CNN
* Techniques: Post-training quantization, model compression, resource optimization, hyperparameter tuning, width multiplier adjustment
* Framework: TensorFlow, TensorFlow Lite, STM32Cube.AI, X-Cube-AI, STM32CubeIDE
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: STM32H747i-Disco board
* Hardware type: MCU
* Processor / microcontroller: ARM Cortex-M-based STM32H747i
* Clock frequency: Not reported
* SRAM / RAM: 1 MB RAM
* Flash / ROM / Storage: 2 MB flash memory
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, flash storage, inference latency, computational resources, image processing resources, camera/LCD resource sharing

### Dataset

* Name: Dataset 1 from Sethy et al.; Dataset 2 from Paddy Doctor / Kaggle
* Type: Public
* Dataset size: Dataset 1: 5,932 images; Dataset 2: 10,407 images
* Number of classes: Dataset 1: 4 classes; Dataset 2: 10 classes
* Input resolution: 224 × 224 for MobileNetV2 architecture; deployment input also reported as 128 × 128 in STM32Cube.AI screenshot
* Data modality: RGB image

### Metrics

* Accuracy: MobileNetV2 97.5% hardware validation for 4 classes; FD-MobileNet 90% hardware validation for 4 classes; MobileNetV2 99% quantized simulation accuracy; FD-MobileNet 99% quantized simulation accuracy
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: FD-MobileNet 134.6 ms; MobileNetV2 289.8 ms; optimized MobileNetV2 377.8 ms
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: FD-MobileNet 3.96M MACCs; MobileNetV2 19.10M MACCs; ResNetV1 depth 8 200.64M MACCs; SqueezeNetV1.1 81.21M MACCs; MobileNetV1 alpha 0.25 13.61M MACCs
* RAM usage: FD-MobileNet 206.88 KiB; MobileNetV2 717 KiB; optimized MobileNetV2 713 KiB
* Flash usage: FD-MobileNet 550 KiB; MobileNetV2 525 KiB; optimized MobileNetV2 519 KiB
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Post-training quantization, resource optimization for RAM, model architecture comparison, hyperparameter tuning, dropout adjustment, learning-rate policy tuning
* Quantization: INT8 PTQ
* Pruning: No
* Knowledge distillation: No
* Compression method: TensorFlow Lite conversion and quantization; STM32Cube.AI optimization
* Hardware-specific optimization: STM32Cube.AI / X-Cube-AI model conversion, benchmarking, C-code generation, RAM-focused optimization
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: RAM activations up to 717 KiB for MobileNetV2; 206.88 KiB for FD-MobileNet; optimized MobileNetV2 713 KiB
* Flash usage reported: 550 KiB for FD-MobileNet; 525 KiB for MobileNetV2; optimized MobileNetV2 519 KiB
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Yes, 134.6 ms for FD-MobileNet and 289.8 ms for MobileNetV2
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No cloud or communication required during inference reported
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly deploys CNN inference on an ARM Cortex-M STM32H747i microcontroller with reported RAM, flash, latency, quantization, and resource optimization constraints.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: MobileNetV2 achieved the best 4-class hardware validation accuracy at 97.5%, while FD-MobileNet was more resource-efficient but reached 90% under hardware validation. Accuracy dropped sharply as the number of classes increased on STM32H747i, showing strong MCU resource limitations.

### Limitations

* Hardware deployment accuracy degraded compared with simulation due to constrained RAM/flash, limited processing capability, lighting variation, camera distance, camera angle, and image processing limitations.
* Performance declined substantially when the number of classes increased beyond six on STM32H747i.
* Energy and power consumption were not reported.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes resource-optimized CNN deployment for real-time rice disease classification on ARM Cortex-M STM32 microcontroller hardware using TensorFlow Lite quantization and STM32Cube.AI-based optimization.

| Paper          | Year | Task           | Model                     | Technique                                  | Device           | Dataset                                               | Main Metric    | Latency                                     | Model Size | SRAM/RAM                                     | Flash                                     | Energy | Framework                     | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | -------------- | ------------------------- | ------------------------------------------ | ---------------- | ----------------------------------------------------- | -------------- | ------------------------------------------- | ---------- | -------------------------------------------- | ----------------------------------------- | ------ | ----------------------------- | -------- | ------------- | ------------- |
| Nugroho et al. | 2024 | Classification | MobileNetV2; FD-MobileNet | PTQ and STM32Cube.AI resource optimization | STM32H747i-Disco | Rice disease datasets: 5,932 images and 10,407 images | 97.5% accuracy | 134.6 ms FD-MobileNet; 289.8 ms MobileNetV2 | N/A        | 206.88 KiB FD-MobileNet; 717 KiB MobileNetV2 | 550 KiB FD-MobileNet; 525 KiB MobileNetV2 | N/A    | TensorFlow Lite; STM32Cube.AI | INT8 PTQ | None          | Yes           |
