## Paper ID: Flood-Detection-with-UAV-Imagery-using-Embedded-AI

TinyML classification: Strict TinyML — Explicit STM32F411RE ARM Cortex-M microcontroller deployment with reported 31.5 KB RAM and 87.3 KB Flash usage.

### Basic Info

* Authors: Pranav Chaudhari; Savitri N. Jadhav
* Year: 2025
* Title: Flood Detection with UAV Imagery using Embedded AI
* Source: Grenze International Journal of Engineering and Technology, January Issue
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Detect flooded and non-flooded areas from UAV imagery using an embedded AI model deployed on a microcontroller.
* Application domain: Flood detection and disaster response
* Scenario: Embedded, UAV-based, edge, microcontroller-based flood monitoring
* TinyML relevance: Yes
* TinyML justification: The paper deploys a Random Forest model on an STM32F411RE microcontroller using NanoEdge AI and reports RAM and Flash usage.

### Model / Method

* Model: Random Forest; SVM; SEFR
* Architecture family: Classical ML
* Techniques: Lightweight model deployment, feature extraction, region growth, embedded model conversion to C header file
* Framework: NanoEdge AI; Arduino IDE
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: STM32F411RE Nucleo board with 5110 Nokia LCD
* Hardware type: MCU
* Processor / microcontroller: STM32F411RE, ARM Cortex-M-based microcontroller
* Clock frequency: Not reported
* SRAM / RAM: 31.5 KB RAM for Random Forest
* Flash / ROM / Storage: 87.3 KB Flash for Random Forest
* Power consumption: Low power consumption mentioned, but exact value not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, compute, resource-constrained deployment

### Dataset

* Name: UAV image dataset
* Type: Not reported
* Dataset size: 644 images; 544 training images and 100 testing images
* Number of classes: 2
* Input resolution: Not reported
* Data modality: UAV images

### Metrics

* Accuracy: 90.00% for Random Forest; 88.3% for SVM; 87.54% for SEFR
* mAP: Not reported
* Precision: Not reported
* Recall: Mentioned, but exact value not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: 31.5 KB for Random Forest; 54.5 KB for SVM; 40.7 KB for SEFR
* Flash usage: 87.3 KB for Random Forest; 54.5 KB for SVM; 40.7 KB for SEFR
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Conversion of trained model into lightweight C header file for microcontroller deployment
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Lightweight C header file generation using NanoEdge AI
* Hardware-specific optimization: Deployment configured for STM32F411RE microcontroller
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: 87.3 KB for Random Forest
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly deploys a machine learning model on an STM32F411RE ARM Cortex-M microcontroller and reports KB-scale RAM and Flash usage.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes, compared Random Forest, SVM, and SEFR
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The Random Forest model achieved the best reported performance with 90.00% accuracy on 100 UAV test images. The deployed Random Forest model used 31.5 KB RAM and 87.3 KB Flash on the STM32F411RE microcontroller.

### Limitations

* The model was trained on a relatively small dataset of 544 images, which may limit generalizability.
* Extreme weather conditions may affect UAV data collection and image quality.
* More advanced models such as CNNs may improve accuracy but could exceed resource constraints.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: No
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a microcontroller-based embedded AI flood detection system that classifies UAV image features as flooded or non-flooded using a Random Forest model deployed on an STM32F411RE board through NanoEdge AI.

| Paper            | Year | Task           | Model         | Technique                       | Device                   | Dataset        | Main Metric     | Latency | Model Size | SRAM/RAM | Flash   | Energy | Framework                | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---: | -------------- | ------------- | ------------------------------- | ------------------------ | -------------- | --------------- | ------- | ---------- | -------- | ------- | ------ | ------------------------ | -------- | ------------- | ------------- |
| Chaudhari et al. | 2025 | Classification | Random Forest | Lightweight C header deployment | STM32F411RE Nucleo board | 644 UAV images | Accuracy 90.00% | N/A     | N/A        | 31.5 KB  | 87.3 KB | N/A    | NanoEdge AI; Arduino IDE | N/A      | N/A           | Yes           |
