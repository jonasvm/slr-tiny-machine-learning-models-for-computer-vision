## Paper ID: An-Efficient-Wildfire-Detection-System-for-AI-Embedded-Applications-Using-Satellite-Imagery

TinyML classification: Strict TinyML — The paper explicitly evaluates deployment on Arduino Nano 33 BLE, an MCU-class Cortex-M4 platform, with reported embedded memory and latency constraints.

### Basic Info

* Authors: George L. James; Ryeim B. Ansaf; Sanaa S. Al Samahi; Rebecca D. Parker; Joshua M. Cutler; Rhode V. Gachette; Bahaa I. Ansaf
* Year: 2023
* Title: An Efficient Wildfire Detection System for AI-Embedded Applications Using Satellite Imagery
* Source: Fire, 6, 169
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Design an efficient CNN-based wildfire detection system using satellite imagery while reducing computational requirements for embedded AI deployment.
* Application domain: Wildfire detection and remote sensing
* Scenario: Embedded AI, mobile, spacecraft/weather balloon, on-device inference
* TinyML relevance: Yes
* TinyML justification: The paper evaluates deployment cost on Arduino Nano 33 BLE Sense, reporting simulated Flash usage, peak RAM usage, and inference time for a Cortex-M4 MCU platform.

### Model / Method

* Model: MobileNetV1 and MobileNetV2 variants; selected model is MobileNetV2 with 160 × 160 input resolution and 0.5 depth multiplier.
* Architecture family: CNN
* Techniques: Transfer learning, image augmentation, MobileNet depth multiplier reduction, input-resolution tuning, dense-layer tuning, dropout tuning
* Framework: Edge Impulse Development Studio
* Training type: Transfer learning
* Inference type: On-device simulated

### Hardware

* Device: Arduino Nano 33 BLE Sense
* Hardware type: MCU
* Processor / microcontroller: Cortex-M4 microcontroller
* Clock frequency: Not reported
* SRAM / RAM: Peak RAM usage estimated, exact selected-model value not reported
* Flash / ROM / Storage: Flash usage estimated, exact selected-model value not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, latency, compute, Flash usage, RAM usage, communication cost

### Dataset

* Name: Sentinel-2 satellite imagery from San Isabel National Park with artificial wildfire augmentation
* Type: Synthetic
* Dataset size: 614 images; 76% training and 24% testing
* Number of classes: 2
* Input resolution: 96 × 96 and 160 × 160
* Data modality: Satellite imagery

### Metrics

* Accuracy: 95% for MobileNetV2 160 × 160 with 0.5 depth multiplier
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Inference time estimated on Arduino Nano 33 BLE Sense, exact selected-model value not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Peak RAM usage estimated, exact selected-model value not reported
* Flash usage: Flash usage estimated, exact selected-model value not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Transfer learning, data augmentation, input-resolution selection, MobileNet depth multiplier reduction, dropout tuning, dense-layer tuning
* Quantization: Not reported
* Pruning: No
* Knowledge distillation: No
* Compression method: MobileNet depth multiplier reduction
* Hardware-specific optimization: Edge Impulse simulation for Arduino Nano 33 BLE Sense
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Yes, as simulated peak RAM usage
* Flash usage reported: Yes, as simulated Flash usage
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Yes, as simulated inference time
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly evaluates a CNN model for Arduino Nano 33 BLE Sense, an MCU-class Cortex-M4 platform, using Flash, peak RAM, and inference-time constraints.

### Benchmarking / Standardization

* Benchmark used: Custom Edge Impulse deployment simulation and custom overall performance indicator
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes, MobileNetV1 and MobileNetV2 variants with different image resolutions, depth multipliers, dropout rates, and dense-layer sizes
* Comparison with previous works: Not reported
* Reproducibility artifacts available: Not reported

### Results

* Summary: MobileNetV2 with 160 × 160 input resolution and 0.5 depth multiplier achieved 95% classification accuracy while being about 65–70% lighter and faster than the full-depth MobileNetV2 reference model.

### Limitations

* Limited real wildfire satellite images required artificial fire-image augmentation.
* Sentinel-2 revisit frequency was reported as approximately five days, which is unsuitable for operational real-time wildfire detection.
* Deployment results were based on simulation rather than measured physical-device deployment.

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

* This paper proposes an embedded-oriented MobileNet-based wildfire classification methodology that optimizes CNN hyperparameters and evaluates simulated MCU deployment cost for satellite-image wildfire detection.

| Paper        | Year | Task           | Model       | Technique                                      | Device                    | Dataset                                         | Main Metric  | Latency | Model Size | SRAM/RAM                            | Flash                            | Energy | Framework    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | -------------- | ----------- | ---------------------------------------------- | ------------------------- | ----------------------------------------------- | ------------ | ------- | ---------- | ----------------------------------- | -------------------------------- | ------ | ------------ | -------- | ------------- | ------------- |
| James et al. | 2023 | Classification | MobileNetV2 | Transfer learning + depth multiplier reduction | Arduino Nano 33 BLE Sense | Sentinel-2 San Isabel augmented wildfire images | Accuracy 95% | N/A     | N/A        | Peak RAM estimated; exact value N/A | Flash estimated; exact value N/A | N/A    | Edge Impulse | N/A      | N/A           | Yes           |
