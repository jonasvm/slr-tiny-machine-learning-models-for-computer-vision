## Paper ID: TinyML-and-IoT-enabled-system-for-automated-chicken-egg-quality-analysis-and-monitoring

TinyML classification: Strict TinyML — It explicitly deploys an int8 MobileNetV1 model on Arduino Nano 33 BLE Sense with KB-scale RAM/Flash usage and on-device inference.

### Basic Info

* Authors: Omoy Kombe Hélène; Martin Kuradusenge; Louis Sibomana; Ipyana Issah Mwaisekwa
* Year: 2025
* Title: TinyML and IoT-enabled system for automated chicken egg quality analysis and monitoring
* Source: Smart Agricultural Technology 12 (2025) 101162
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Automate chicken egg quality analysis and monitoring using TinyML-based image classification and IoT sensing.
* Application domain: Poultry farming / smart agriculture
* Scenario: Embedded IoT system for rural and off-grid agricultural monitoring
* TinyML relevance: Yes
* TinyML justification: The system deploys a TinyML image classification model on Arduino Nano 33 BLE Sense for offline, on-device inference under memory, latency, and power constraints.

### Model / Method

* Model: MobileNetV1 quantized model
* Architecture family: CNN
* Techniques: INT8 quantization, lightweight model selection, Edge Impulse EON Tuner optimization
* Framework: TensorFlow/Keras; Edge Impulse
* Training type: Transfer learning / fine-tuning
* Inference type: On-device

### Hardware

* Device: Arduino Nano 33 BLE Sense; ESP32; OV7675 camera; DHT22 sensor; OLED display
* Hardware type: MCU
* Processor / microcontroller: ARM Cortex-M4 CPU
* Clock frequency: Not reported
* SRAM / RAM: 124.8 KB peak RAM usage for selected quantized MobileNetV1
* Flash / ROM / Storage: 303.8 KB flash usage for selected quantized MobileNetV1
* Power consumption: Arduino active mode estimated at 120–150 mA; idle mode around 30 mA
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, latency, power, compute, communication, offline operation

### Dataset

* Name: Chicken egg candling image dataset
* Type: Public + private
* Dataset size: 5700 images
* Number of classes: 4
* Input resolution: 96 × 96 pixels for deployment
* Data modality: Candling images + environmental sensor data

### Metrics

* Accuracy: 95.79% on-device accuracy; 98.86% testing accuracy reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: 97.4% for quantized TinyML classification
* Latency: 65 ms for quantized MobileNetV1; approximately 6 s end-to-end image processing and classification
* FPS: Not reported
* Throughput: Not reported
* Model size: 303.8 KB flash usage for selected deployed model
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: 124.8 KB peak RAM usage
* Flash usage: 303.8 KB
* Energy per inference: Not reported
* Power consumption: 120–150 mA active mode; around 30 mA idle mode

### Optimization

* Techniques used: INT8 quantization, EON Tuner model selection, image resizing to 96 × 96, lightweight MobileNetV1 deployment
* Quantization: INT8
* Pruning: No
* Knowledge distillation: No
* Compression method: INT8 quantization
* Hardware-specific optimization: Edge Impulse optimization for Arduino Nano 33 BLE Sense deployment
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: 124.8 KB peak RAM usage
* Flash usage reported: 303.8 KB
* Model size reported: 303.8 KB flash usage
* Energy per inference reported: Not reported
* Latency on target device reported: 65 ms for quantized MobileNetV1
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: Yes
* Reason: The paper deploys an INT8 MobileNetV1 model on an Arduino Nano 33 BLE Sense MCU with KB-scale RAM/Flash usage and fully offline on-device inference.

### Benchmarking / Standardization

* Benchmark used: Custom chicken egg candling dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: model

### Results

* Summary: The selected INT8 MobileNetV1 model achieved 97.4% F1-score and 95.79% on-device accuracy. The deployed model used 124.8 KB RAM and 303.8 KB flash, with reported model latency around 65 ms.

### Limitations

* Full-scale field deployment is still pending.
* End-to-end processing takes approximately 6 s, which may limit high-throughput industrial use.
* Formal k-fold validation, ROC analysis, and statistical significance testing were not implemented.

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

* This paper proposes a TinyML and IoT-enabled embedded system for automated chicken egg quality classification and incubation monitoring using offline on-device inference on Arduino Nano 33 BLE Sense.

| Paper         | Year | Task           | Model       | Technique                                  | Device                    | Dataset                            | Main Metric                     | Latency | Model Size | SRAM/RAM | Flash    | Energy | Framework    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | -------------- | ----------- | ------------------------------------------ | ------------------------- | ---------------------------------- | ------------------------------- | ------- | ---------- | -------- | -------- | ------ | ------------ | -------- | ------------- | ------------- |
| Hélène et al. | 2025 | Classification | MobileNetV1 | INT8 quantization + Edge Impulse EON Tuner | Arduino Nano 33 BLE Sense | Chicken egg candling image dataset | Accuracy 95.79%; F1-score 97.4% | 65 ms   | 303.8 KB   | 124.8 KB | 303.8 KB | N/A    | Edge Impulse | INT8     | N/A           | Yes           |
