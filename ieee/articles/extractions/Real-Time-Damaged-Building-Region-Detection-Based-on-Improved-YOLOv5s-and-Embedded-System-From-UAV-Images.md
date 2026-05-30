## Paper ID: Real-Time-Damaged-Building-Region-Detection-Based-on-Improved-YOLOv5s-and-Embedded-System-From-UAV-Images

TinyML classification: Near-TinyML — It is edge/embedded computer vision with lightweight YOLOv5s evaluation on Linux-based Raspberry Pi and Xavier NX, but it does not provide MCU-class deployment evidence.

### Basic Info

* Authors: Yunlong Wang, Wenqing Feng, Kun Jiang, Qianchun Li, Ruipeng Lv, Jihui Tu
* Year: 2023
* Title: Real-Time Damaged Building Region Detection Based on Improved YOLOv5s and Embedded System From UAV Images
* Source: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, Vol. 16
* Type: Experimental / Methodological

### Problem & Context

* Task: Object detection
* Objective: Detect damaged building regions in real time from UAV images using an improved lightweight YOLOv5s model deployed on embedded systems.
* Application domain: Disaster response, humanitarian assistance, UAV remote sensing, building damage assessment
* Scenario: Embedded UAV / edge inference
* TinyML relevance: Partial
* TinyML justification: The paper targets embedded real-time computer vision with limited computation and memory, but deployment is on Linux-based Raspberry Pi 4B and NVIDIA Xavier NX rather than MCU-class hardware.

### Model / Method

* Model: DB-YOLOv5s / DB-YOLOv5
* Architecture family: CNN
* Techniques: Residual dilated convolution module, attention-based feature fusion, double-head detection module, lightweight YOLOv5s architecture modification, Focus module removal, K-means anchor adjustment
* Framework: PyTorch
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Raspberry Pi 4B; NVIDIA Xavier NX
* Hardware type: SoC / CPU / GPU
* Processor / microcontroller: Raspberry Pi 4B ARMv7 1.5 GHz; NVIDIA Xavier NX 4-core ARM A57 @ 1.43 GHz with 128-core Maxwell GPU
* Clock frequency: 1.5 GHz on Raspberry Pi 4B; 1.43 GHz on NVIDIA Xavier NX
* SRAM / RAM: 8 GB on Raspberry Pi 4B; 4 GB on NVIDIA Xavier NX
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Limited computation resources, limited memory, power consumption, real-time latency, embedded deployment

### Dataset

* Name: Ludian and Beichuan postdisaster UAV image datasets
* Type: Private
* Dataset size: 3738 postdisaster UAV images; 500 image samples used for training; 1230 damaged building regions annotated
* Number of classes: 1
* Input resolution: 416 × 416 cropped subimages; original images were 6000 × 4000 and 5365 × 3936 pixels
* Data modality: RGB UAV images

### Metrics

* Accuracy: Not reported
* mAP: 99.50%
* Precision: 96.36%
* Recall: 94.38%
* F1-score: 95.34%
* Latency: Not reported
* FPS: 87.89 FPS on RTX 2080 Ti; 2.27 FPS on NVIDIA Xavier NX; 1.16 FPS on Raspberry Pi 4B
* Throughput: Not reported
* Model size: 13.775 MB
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight YOLOv5s redesign, residual dilated convolution, attention-based feature fusion, decoupled classification/regression head, Focus module removal, anchor optimization with K-means
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Lightweight architecture and reduced parameter/model size
* Hardware-specific optimization: Embedded-system-oriented model design and evaluation on Raspberry Pi 4B and NVIDIA Xavier NX
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 13.775 MB
* Energy per inference reported: Not reported
* Latency on target device reported: FPS reported, but latency in milliseconds not reported
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The model is evaluated on Linux-based Raspberry Pi 4B and NVIDIA Xavier NX with GB-scale RAM, without MCU-class hardware, SRAM/Flash constraints, RTOS/bare-metal execution, or TensorFlow Lite Micro/CMSIS-NN evidence.

### Benchmarking / Standardization

* Benchmark used: Custom Ludian and Beichuan UAV earthquake image datasets
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: YOLOv3, YOLOv4, YOLOv4-tiny, YOLOv5s
* Comparison with previous works: Semantic scene change method, adopted CNN classification method, improved CNN classification method
* Reproducibility artifacts available: Not reported

### Results

* Summary: DB-YOLOv5s achieved 96.36% precision, 94.38% recall, 95.34% F1-score, and 99.50% mAP for damaged building region detection. The model reached 2.27 FPS on NVIDIA Xavier NX and 1.16 FPS on Raspberry Pi 4B, with a reported model size of 13.775 MB.

### Limitations

* The paper reports false negatives for small, flat, or visually ambiguous damaged regions.
* The paper reports false positives caused by rubble, debris, or visually similar postdisaster objects.
* The method focuses on approximate damaged building regions rather than detailed individual building damage information.
* The authors state that future work should address different scales and data sources from multiple remote sensing platforms and sensors.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a real-time embedded UAV damaged building region detection method based on an improved lightweight YOLOv5s architecture with residual dilated convolution, attention-based feature fusion, and a decoupled detection head.

| Paper       | Year | Task             | Model      | Technique                                                                         | Device                            | Dataset                                   | Main Metric | Latency | Model Size | SRAM/RAM           | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------- | ---------- | --------------------------------------------------------------------------------- | --------------------------------- | ----------------------------------------- | ----------- | ------- | ---------- | ------------------ | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Wang et al. | 2023 | Object detection | DB-YOLOv5s | Lightweight YOLOv5s with Res-DConv, BDCAM attention, and decoupled detection head | Raspberry Pi 4B; NVIDIA Xavier NX | Ludian and Beichuan UAV earthquake images | mAP 99.50%  | N/A     | 13.775 MB  | 8 GB RAM; 4 GB RAM | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
