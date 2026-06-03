## Paper ID: Human-computer-Interaction-Gesture-Control-Recognition-for-High-performance-Embedded-AI-Computing-Platform

TinyML classification: Near-TinyML — Uses embedded/edge AI hardware for gesture recognition, but lacks clear evidence of microcontroller-class deployment.

### Basic Info

* Authors: Dongwei Fu
* Year: 2023
* Title: Human-computer Interaction Gesture Control Recognition for High-performance Embedded AI Computing Platform
* Source: Advances in Computer and Communications, 4(3), 210-214.
* Type: Experimental

### Problem & Context

* Task: Gesture recognition and tracking
* Objective: To design and evaluate a gesture control recognition system based on infrared cameras, CNN-based recognition, and an embedded AI computing platform.
* Application domain: Human-computer interaction
* Scenario: Embedded AI computing platform
* TinyML relevance: Partial
* TinyML justification: The paper targets embedded AI and low-cost/low-power gesture recognition, but it does not report MCU-class deployment, TensorFlow Lite Micro, SRAM/Flash constraints, or ultra-low-power bare-metal execution.

### Model / Method

* Model: CNN-based gesture recognition model; KNN also described for hand pose recognition
* Architecture family: CNN
* Techniques: Image preprocessing, color-space conversion, skin-color feature extraction, dynamic time warping optimization, gesture detection and tracking
* Framework: OpenCV
* Training type: Not reported
* Inference type: On-device / hybrid

### Hardware

* Device: High-performance embedded AI computing platform with infrared camera / Kinect 2.0
* Hardware type: SoC / CPU / Other
* Processor / microcontroller: ARM Cortex-A8 processor; Samsung 32-bit ARM7TDMI-SOC
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Power, performance, hardware cost, real-time processing

### Dataset

* Name: Not reported
* Type: Not reported
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: 640 × 480 camera images
* Data modality: Infrared image and color image / gesture image

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Image preprocessing, CNN parameter optimization, improved dynamic time warping algorithm, improved particle filter algorithm
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: Use of embedded AI platform and AI processing unit
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: The paper states that gesture images are transmitted to the cloud through an edge computing unit in the platform description.
* Candidate for Strict TinyML: No
* Reason: The paper discusses embedded AI gesture recognition but does not provide MCU-class hardware, memory, model size, latency, or energy evidence.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Comparison with three other gesture detection methods is mentioned, but quantitative values are not reported.
* Comparison with previous works: Not reported
* Reproducibility artifacts available: Not reported

### Results

* Summary: The paper reports that the proposed gesture detection, tracking, and recognition method is effective on the embedded platform. However, no quantitative performance metrics such as accuracy, latency, FPS, memory, model size, or energy are reported.

### Limitations

* Quantitative evaluation metrics are not reported.
* MCU-class deployment evidence is not reported.
* Memory, latency, energy, and model-size constraints are not reported.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Partial
* Reports evaluation metric clearly: No
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an embedded AI gesture recognition and tracking platform using infrared cameras, OpenCV-based processing, and CNN-based recognition for human-computer interaction.

| Paper     | Year | Task                             | Model | Technique                                                 | Device                                                                 | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | -------------------------------- | ----- | --------------------------------------------------------- | ---------------------------------------------------------------------- | ------- | ----------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Fu et al. | 2023 | Gesture recognition and tracking | CNN   | Image preprocessing and dynamic time warping optimization | ARM Cortex-A8 / Samsung ARM7TDMI-SOC embedded platform with Kinect 2.0 | N/A     | N/A         | N/A     | N/A        | N/A      | N/A   | N/A    | OpenCV    | N/A      | N/A           | No            |
