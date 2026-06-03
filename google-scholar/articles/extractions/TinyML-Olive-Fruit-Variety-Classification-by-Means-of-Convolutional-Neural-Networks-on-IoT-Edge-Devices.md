## Paper ID: TinyML-Olive-Fruit-Variety-Classification-by-Means-of-Convolutional-Neural-Networks-on-IoT-Edge-Devices

TinyML classification: Strict TinyML — the paper explicitly reports MCU-class deployment on ESP32-S3 with memory footprint, model size, quantization, and inference-rate constraints.

### Basic Info

* Authors: Ali M. Hayajneh; Sahel Batayneh; Eyad Alzoubi; Motasem Alwedyan
* Year: 2023
* Title: TinyML Olive Fruit Variety Classification by Means of Convolutional Neural Networks on IoT Edge Devices
* Source: AgriEngineering, 5, 2266–2283
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Classify olive fruit variety and quality using CNN models deployed on low-cost edge devices.
* Application domain: Smart agriculture; post-harvest olive fruit sorting.
* Scenario: Edge IoT, embedded MCU, smart farming.
* TinyML relevance: Yes
* TinyML justification: The paper deploys quantized CNN models on an ESP32-S3 MCU and reports model size, memory arena size, and edge inference rate.

### Model / Method

* Model: Custom CNN variants: CNN(128,64,32), CNN(64,32,16), and CNN(32,16,16)
* Architecture family: CNN
* Techniques: Morphological image segmentation, data augmentation, model compression, uint8 quantization, TensorFlow Lite conversion.
* Framework: TensorFlow Lite; TinyML libraries
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: ESP32-S3 MCU
* Hardware type: MCU
* Processor / microcontroller: ESP32-S3
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory footprint, model size, inference rate, computational constraints, edge deployment limitations.

### Dataset

* Name: Not reported
* Type: Private
* Dataset size: More than 16,500 individually labeled olive fruits
* Number of classes: 4
* Input resolution: 50 × 50 pixels and 25 × 25 pixels
* Data modality: RGB images converted to grayscale images for classification

### Metrics

* Accuracy: 94.88% to 97.43% for TinyML inference
* mAP: Not reported
* Precision: Up to 0.9743 for TinyML inference
* Recall: Up to 0.9746 for TinyML inference
* F1-score: Up to 0.9743 for TinyML inference
* Latency: Not reported
* FPS: 5.93 to 55.56 inferences per second
* Throughput: 5.93 to 55.56 inferences per second
* Model size: 14.45 KB to 332.3 KB
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Minimum arena size from 22.33 KB to 368.6 KB
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Model compression, uint8 quantization, TensorFlow Lite conversion, reduced input resolution, smaller CNN architectures.
* Quantization: INT8 / uint8
* Pruning: No
* Knowledge distillation: No
* Compression method: TensorFlow Lite quantization and compact CNN architecture selection
* Hardware-specific optimization: Optimization for ESP32-S3 MCU memory and inference constraints
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported; minimum arena size from 22.33 KB to 368.6 KB is reported
* Flash usage reported: Not reported
* Model size reported: 14.45 KB to 332.3 KB
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported; inference rate from 5.93 to 55.56 Hz is reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No cloud service or internet connectivity is required for the edge solution
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly evaluates CNN inference on an ESP32-S3 MCU with KB-scale model size, memory arena constraints, uint8 quantization, and measured edge inference rates.

### Benchmarking / Standardization

* Benchmark used: Custom olive fruit dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes; multiple CNN architectures and input resolutions are compared
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset available on request

### Results

* Summary: The best TinyML inference accuracy reported is 97.43%, with compact CNN models achieving feasible deployment on the ESP32-S3 MCU. The smallest reported model is 14.45 KB with a 22.33 KB minimum arena size and 55.56 Hz inference rate.

### Limitations

* Dataset is limited to selected Jordanian olive varieties.
* The largest 50 × 50 CNN(128,64,32) model caused stack overflow on the ESP32-S3.
* The paper suggests future work with more olive varieties and additional compression methods such as pruning, knowledge distillation, and low-rank factorization.

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

* This paper proposes an end-to-end TinyML framework for olive fruit variety and quality classification using compressed CNN models deployed on an ESP32-S3 MCU for low-cost smart agriculture.

| Paper           | Year | Task           | Model      | Technique                                | Device       | Dataset                     | Main Metric     | Latency  | Model Size | SRAM/RAM               | Flash | Energy | Framework                          | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---: | -------------- | ---------- | ---------------------------------------- | ------------ | --------------------------- | --------------- | -------- | ---------- | ---------------------- | ----- | ------ | ---------------------------------- | -------- | ------------- | ------------- |
| Hayajneh et al. | 2023 | Classification | Custom CNN | uint8 quantization and model compression | ESP32-S3 MCU | Private olive fruit dataset | Accuracy 97.43% | 55.56 Hz | 14.45 KB   | 22.33 KB minimum arena | N/A   | N/A    | TensorFlow Lite / TinyML libraries | INT8     | N/A           | Yes           |
