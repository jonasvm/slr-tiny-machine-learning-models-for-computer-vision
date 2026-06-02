## Paper ID: An-integrated-and-real-time-social-distancing-mask-detection-and-facial-temperature-video-measurement-system-for-pandemic-monitoring

TinyML classification: Near-TinyML — The deployment is on NVIDIA Jetson embedded GPU platforms, with no explicit MCU-class or TensorFlow Lite Micro deployment evidence.

### Basic Info

* Authors: Abdussalam Elhanashi; Sergio Saponara; Pierpaolo Dini; Qinghe Zheng; Daiki Morita; Bisser Raytchev
* Year: 2023
* Title: An integrated and real-time social distancing, mask detection, and facial temperature video measurement system for pandemic monitoring
* Source: Journal of Real-Time Image Processing, 20:95
* Type: Experimental

### Problem & Context

* Task: Object detection
* Objective: Develop an integrated real-time Edge-AI video system for social distancing monitoring, face mask detection, and facial temperature measurement.
* Application domain: Pandemic monitoring and public health surveillance
* Scenario: Edge, embedded, IoT surveillance
* TinyML relevance: Partial
* TinyML justification: The paper targets real-time embedded edge deployment on NVIDIA Jetson platforms, but not MCU-class or ultra-low-power bare-metal deployment.

### Model / Method

* Model: Three YOLOv4-tiny object detectors
* Architecture family: CNN
* Techniques: Lightweight YOLOv4-tiny detection, multi-model parallel execution, bird’s-eye-view transformation for social distancing, thermal/RGB camera fusion
* Framework: Python/OpenCV mentioned; specific deployment framework not reported
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson Nano; NVIDIA Jetson Xavier AGX
* Hardware type: GPU / SoC
* Processor / microcontroller: Jetson Nano with 128-core Maxwell GPU and quad-core ARM A57 CPU; Jetson Xavier with 512-core GPU and 8-core ARMv8.2 CPU
* Clock frequency: Not reported
* SRAM / RAM: Jetson Nano 4 GB LPDDR4; Jetson Xavier 16 GB LPDDR4x
* Flash / ROM / Storage: Jetson Nano MicroSD card slot; Jetson Xavier 16 GB eMMC flash
* Power consumption: Jetson Nano 4.2–6.7 W depending on scenario; Jetson Xavier AGX 13–22.6 W depending on scenario
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Real-time performance, power consumption, compute cost, model size, low-cost embedded execution, thermal behavior

### Dataset

* Name: Face mask images from internet sources; thermal people images; thermal facial images from TFW dataset
* Type: Public / private mixed sources
* Dataset size: 900 face mask images; 2000 thermal images for social distancing; 9982 thermal facial images
* Number of classes: Mask/No Mask for mask detection; other class counts not reported
* Input resolution: 416 × 416 camera output for deployment
* Data modality: RGB video, thermal video, thermal images

### Metrics

* Accuracy: 96.2% for social distancing; 95.1% for mask detection; 96% for facial temperature model
* mAP: Not reported
* Precision: Reported graphically, exact values not reported
* Recall: Reported graphically, exact values not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Jetson Nano: 5.5 FPS thermal and 21 FPS visible for SD+MD+FTM; Jetson Xavier AGX: 18 FPS thermal and 62 FPS visible for SD+MD+FTM
* Throughput: Not reported
* Model size: 22.9 MB for social distancing YOLOv4-tiny; 22.8 MB for facial temperature YOLOv4-tiny; 23 MB for mask detection YOLOv4-tiny
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 4.2–6.7 W on Jetson Nano; 13–22.6 W on Jetson Xavier AGX

### Optimization

* Techniques used: Lightweight YOLOv4-tiny architecture, parallel execution on Jetson platforms, model size reduction techniques mentioned
* Quantization: Not reported
* Pruning: Yes
* Knowledge distillation: Yes
* Compression method: Quantization, pruning, and knowledge distillation are mentioned, but exact configurations are not reported
* Hardware-specific optimization: Parallel execution across available Jetson processing resources
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 22.8–23 MB per YOLOv4-tiny model
* Energy per inference reported: Not reported
* Latency on target device reported: FPS reported, latency not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: No
* Reason: The system runs on NVIDIA Jetson embedded GPU/SoC platforms rather than MCU-class hardware, and no MCU-level SRAM, Flash, RTOS, bare-metal, or TensorFlow Lite Micro evidence is reported.

### Benchmarking / Standardization

* Benchmark used: Custom task-specific evaluation datasets
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: YOLO, YOLOv2, YOLOv3-tiny, Faster R-CNN
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The integrated system achieved 96.2% accuracy for social distancing, 95.1% for mask detection, and 96% for facial temperature measurement. On Jetson Xavier AGX, the full three-task system reached 18 FPS from the thermal camera and 62 FPS from the visible camera.

### Limitations

* Performance decreases when the three YOLOv4-tiny models run simultaneously because of increased computational cost.
* Jetson Nano shows higher temperature under the three-task workload, which can trigger over-temperature alarms and degrade performance.
* Jetson Xavier AGX provides higher real-time performance but consumes more power.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an integrated real-time Edge-AI video monitoring system using three YOLOv4-tiny detectors on NVIDIA Jetson platforms for simultaneous social distancing, face mask detection, and facial temperature measurement.

| Paper            | Year | Task             | Model       | Technique                                 | Device                         | Dataset                                         | Main Metric                           | Latency                                              | Model Size | SRAM/RAM                        | Flash                                 | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---- | ---------------- | ----------- | ----------------------------------------- | ------------------------------ | ----------------------------------------------- | ------------------------------------- | ---------------------------------------------------- | ---------- | ------------------------------- | ------------------------------------- | ------ | --------- | -------- | ------------- | ------------- |
| Elhanashi et al. | 2023 | Object detection | YOLOv4-tiny | Lightweight CNN + parallel edge execution | Jetson Nano; Jetson Xavier AGX | Custom mask/thermal datasets; TFW thermal faces | Accuracy: 96.2% SD; 95.1% MD; 96% FTM | N/A; 18 FPS thermal and 62 FPS visible on Xavier AGX | 22.8–23 MB | 4 GB RAM Nano; 16 GB RAM Xavier | 16 GB eMMC on Xavier; MicroSD on Nano | N/A    | N/A       | N/A      | None          | No            |
