## Paper ID: TinyML-Classification-for-Agriculture-Objects-with-ESP32

TinyML classification: Strict TinyML — explicitly targets ESP32 microcontroller deployment with quantized CNNs, constrained memory, and measured on-device latency.

### Basic Info

* Authors: Danila Donskoy, Valeria Gvindjiliya, Evgeniy Ivliev
* Year: 2025
* Title: TinyML Classification for Agriculture Objects with ESP32
* Source: Digital 2025, 5, 48
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Create a hardware–software complex for local energy-efficient image classification with IoT protocol support.
* Application domain: Smart agriculture / weed monitoring / crop-field surface classification
* Scenario: Embedded, IoT, microcontroller-based edge vision
* TinyML relevance: Yes
* TinyML justification: The paper deploys quantized CNN image classification locally on an ESP32-CAM microcontroller under memory, power, and latency constraints.

### Model / Method

* Model: Two CNN architectures, with the second CNN architecture selected for deployment.
* Architecture family: CNN
* Techniques: INT8 quantization, lightweight CNN design, input-resolution reduction, embedded deployment
* Framework: TensorFlow, TensorFlow Lite Micro, ArduTFLite
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: ESP32-CAM
* Hardware type: MCU
* Processor / microcontroller: ESP32 with dual 32-bit Xtensa LX6 cores
* Clock frequency: Not reported
* SRAM / RAM: 4 MB PSRAM; selected deployed configuration reports 562 KB memory usage at 80 × 60 input resolution.
* Flash / ROM / Storage: External MicroSD card supported; Flash / ROM not reported.
* Power consumption: Peak current does not exceed 500 mA; approximately 1 W reported for ESP32 comparison.
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, latency, compute, image resolution, hardware cost

### Dataset

* Name: Custom ESP32-CAM field images combined with external crop/weed datasets, including Crop and Weed Detection Data with Bounding Boxes, CropAndWeed, Weed-Datasets, Global Wheat Head Detection, and DeepWeeds.
* Type: Mixed private and public
* Dataset size: 12,272 photos before augmentation
* Number of classes: 3
* Input resolution: 32 × 32 to 800 × 600 investigated; selected deployed resolution was 80 × 60.
* Data modality: RGB image

### Metrics

* Accuracy: Selected quantized second CNN achieved 87.50% at 80 × 60, 92.86% at 160 × 120, and 96.15% at 320 × 240.
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Selected deployed configuration reported maximum classification time up to 8 s; web-interface implementation reported 4 to 15 s.
* FPS: Not reported
* Throughput: Not reported
* Model size: First CNN architecture: 3.20 MB; second CNN architecture: 2.36 MB.
* Parameters: First CNN architecture: 838,723; second CNN architecture: 618,987.
* MACs / FLOPs: Not reported
* RAM usage: Second CNN architecture used 562 KB at 80 × 60, 2304 KB at 160 × 120, and 5120 KB at 320 × 240.
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Approximately 1 W for ESP32; peak current does not exceed 500 mA.

### Optimization

* Techniques used: INT8 quantization, lightweight CNN architecture selection, reduced input resolution, TensorFlow Lite conversion for embedded C++ deployment
* Quantization: INT8 / PTQ
* Pruning: No
* Knowledge distillation: No
* Compression method: Quantization and input-resolution reduction
* Hardware-specific optimization: Memory-aware deployment on ESP32-CAM using TensorFlow Lite Micro / ArduTFLite
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: Yes
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported as peak; memory usage reported as 562 KB for the selected second CNN at 80 × 60.
* Flash usage reported: Not reported
* Model size reported: 2.36 MB for the selected second CNN architecture.
* Energy per inference reported: Not reported
* Latency on target device reported: Yes, up to 8 s for the selected deployed configuration.
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No; Wi-Fi/WebSocket is used for user interaction, not cloud inference.
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly deploys a quantized CNN on an ESP32-CAM microcontroller with reported memory usage, latency, model size, and power-constrained operation.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes, comparison between two CNN architectures, quantized and non-quantized versions, and multiple input resolutions.
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset on request

### Results

* Summary: The quantized second CNN architecture achieved the best reported results, reaching 87.50% accuracy at the selected 80 × 60 deployed resolution with 562 KB memory usage. Higher resolutions improved accuracy but exceeded or stressed the ESP32 memory constraints, making the 80 × 60 configuration the practical deployment choice.

### Limitations

* Higher-resolution models improved accuracy but exceeded available microcontroller memory.
* Low-resolution inputs reduced visual feature quality and limited classification performance.
* Classification latency remained high for real-time use, with the selected system requiring up to 8 s.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a TinyML ESP32-CAM hardware–software complex using quantized CNNs for local energy-efficient crop-field image classification with IoT support.

| Paper          | Year | Task           | Model         | Technique                           | Device    | Dataset                                                     | Main Metric                | Latency   | Model Size | SRAM/RAM | Flash | Energy | Framework                          | INT8/QAT   | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | -------------- | ------------- | ----------------------------------- | --------- | ----------------------------------------------------------- | -------------------------- | --------- | ---------- | -------- | ----- | ------ | ---------------------------------- | ---------- | ------------- | ------------- |
| Donskoy et al. | 2025 | Classification | Quantized CNN | INT8 quantization + lightweight CNN | ESP32-CAM | Mixed crop/weed datasets, 12,272 images before augmentation | Accuracy 87.50% at 80 × 60 | Up to 8 s | 2.36 MB    | 562 KB   | N/A   | N/A    | TensorFlow Lite Micro / ArduTFLite | INT8 / PTQ | TFLM          | Yes           |
