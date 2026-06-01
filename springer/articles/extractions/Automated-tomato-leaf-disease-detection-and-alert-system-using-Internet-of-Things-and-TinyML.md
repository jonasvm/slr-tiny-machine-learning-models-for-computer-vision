## Paper ID: Automated-tomato-leaf-disease-detection-and-alert-system-using-Internet-of-Things-and-TinyML

TinyML classification: Strict TinyML — The work explicitly targets MCU-class deployment on an ESP32-S3 with reported 1.1 MB RAM usage, 2.3/2.4 MB flash, inference latency, and low-power operation.

### Basic Info

* Authors: Timothy Malche, Mukesh Joshi, Govind Murari Upadhyay, Pramod Kumar Soni
* Year: 2026
* Title: Automated tomato leaf disease detection and alert system using Internet of Things and TinyML
* Source: Discover Internet of Things, 6:8
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Detect five tomato leaf disease classes in real time using an embedded TinyML IoT system.
* Application domain: Precision agriculture / crop disease monitoring
* Scenario: Embedded, IoT, edge, field monitoring
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets microcontroller-class on-device inference using an ESP32-S3-based node with reported RAM, flash, latency, power, and field-deployment metrics.

### Model / Method

* Model: TinyLeafNet-IoT / TinyMLLeafNet
* Architecture family: CNN
* Techniques: Transfer learning, fine-tuning, quantization, MobileNetV2 width multiplier, dropout, L2 regularization, image resizing
* Framework: Not reported
* Training type: Transfer learning and fine-tuning
* Inference type: On-device

### Hardware

* Device: Seeed Studio XIAO ESP32S3 Sense / ESP32S3CAM-based node
* Hardware type: MCU
* Processor / microcontroller: ESP32-S3 dual-core Xtensa LX7 32-bit processor
* Clock frequency: 240 MHz
* SRAM / RAM: 8 MB PSRAM; model RAM usage 1.1 MB
* Flash / ROM / Storage: 8 MB Flash; model flash usage reported as 2.3 MB / 2.4 MB
* Power consumption: < 140 mW during inference
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, latency, power, compute, communication, field connectivity

### Dataset

* Name: PlantVillage plus field images captured using ESP32S3CAM
* Type: Public + private field images
* Dataset size: 13,365 tomato leaf images
* Number of classes: 5
* Input resolution: 96 × 96 × 3 after preprocessing
* Data modality: RGB image

### Metrics

* Accuracy: 94.6% test accuracy; 93.9% validation accuracy
* mAP: Not reported
* Precision: 94.8% overall; per-class precision reported
* Recall: 94.7% overall; per-class recall reported
* F1-score: 94.7% overall; macro F1-score 0.94
* Latency: 500 ms benchmark; < 15 ms per image on microcontroller; 8–11 ms reported in extended on-device validation
* FPS: Not reported
* Throughput: Not reported
* Model size: 2.3 MB / 2.4 MB flash footprint
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: 1.1 MB
* Flash usage: 2.3 MB / 2.4 MB
* Energy per inference: Not reported
* Power consumption: < 140 mW during inference

### Optimization

* Techniques used: Quantization, MobileNetV2 α = 0.35, reduced 96 × 96 input resolution, two-stage transfer learning, fine-tuning, dropout, L2 regularization
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Quantization and lightweight MobileNetV2 width scaling
* Hardware-specific optimization: MobileNetV2 width multiplier benchmarked for ESP32-S3 memory and latency constraints
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: 1.1 MB RAM usage
* Flash usage reported: 2.3 MB / 2.4 MB
* Model size reported: 2.3 MB / 2.4 MB flash footprint
* Energy per inference reported: Not reported
* Latency on target device reported: 500 ms benchmark; < 15 ms per image; 8–11 ms in extended validation
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No, MQTT/Wi-Fi is used for transmitting results after local inference
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly deploys a quantized CNN on an ESP32-S3 microcontroller with reported RAM, flash, latency, and power constraints.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: PlantVillage dataset
* Comparison with baseline models: Yes, comparison with different MobileNetV2 unfreezing configurations and width multiplier choices
* Comparison with previous works: Yes
* Reproducibility artifacts available: code

### Results

* Summary: The proposed TinyLeafNet-IoT achieved 94.6% test accuracy and macro F1-score of 0.94 for five tomato leaf disease classes. The model was deployed on an ESP32-S3 microcontroller with 1.1 MB RAM usage, 2.3/2.4 MB flash usage, sub-second or sub-15 ms reported inference depending on benchmark context, and < 140 mW inference power.

### Limitations

* Future work notes the need to handle extreme lighting conditions, improve the communication system, extend detection to more crops and diseases, integrate federated or continual learning, add multi-sensor data, and compare against other lightweight architectures.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a fully embedded TinyML-IoT system for real-time tomato leaf disease classification and alerting using an ESP32-S3 microcontroller, a lightweight quantized CNN, and MQTT-based cloud reporting.

| Paper         | Year | Task           | Model                           | Technique                                              | Device                                     | Dataset                                | Main Metric    | Latency                                                         | Model Size | SRAM/RAM | Flash      | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---: | -------------- | ------------------------------- | ------------------------------------------------------ | ------------------------------------------ | -------------------------------------- | -------------- | --------------------------------------------------------------- | ---------- | -------- | ---------- | ------ | --------- | -------- | ------------- | ------------- |
| Malche et al. | 2026 | Classification | TinyLeafNet-IoT / TinyMLLeafNet | Quantization + MobileNetV2 width scaling + fine-tuning | ESP32-S3 / Seeed Studio XIAO ESP32S3 Sense | PlantVillage + ESP32S3CAM field images | Accuracy 94.6% | 500 ms benchmark; <15 ms per image; 8–11 ms extended validation | 2.3/2.4 MB | 1.1 MB   | 2.3/2.4 MB | N/A    | N/A       | N/A      | N/A           | Yes           |
