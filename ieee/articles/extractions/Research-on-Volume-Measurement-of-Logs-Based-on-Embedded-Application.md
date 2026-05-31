## Paper ID: Research-on-Volume-Measurement-of-Logs-Based-on-Embedded-Application

TinyML classification: Near-TinyML — Edge vision deployment is demonstrated on Jetson NX with INT8 quantization, not on MCU-class TinyML hardware.

### Basic Info

* Authors: Jishi Zheng; Shaoyi Li; Shiwen Zhang; Linghua Kong; Ding Zhigang
* Year: 2023
* Title: Research on Volume Measurement of Logs Based on Embedded Application
* Source: IEEE Access
* Type: Experimental

### Problem & Context

* Task: Segmentation
* Objective: Automatically measure vehicle-mounted log volume using improved Mask R-CNN instance segmentation, ellipse fitting, depth-based stratification, and embedded deployment.
* Application domain: Forestry log volume measurement
* Scenario: Embedded, mobile, vehicle-mounted edge device
* TinyML relevance: Partial
* TinyML justification: The paper deploys an optimized computer vision model on NVIDIA Jetson NX/Xavier NX embedded hardware, but it does not target MCU-class or bare-metal TinyML deployment.

### Model / Method

* Model: Wood Mask R-CNN / improved Mask R-CNN with Res2Net101 and PAFPN
* Architecture family: CNN
* Techniques: TensorRT quantization, model compression, FP16 inference, INT8 inference, Res2Net backbone, PAFPN feature aggregation, LSM ellipse fitting, K-means depth-based stratification, expansion convolution compensation
* Framework: MMDetection; TensorRT
* Training type: Transfer learning / fine-tuning from ImageNet pretrained weights
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson NX / Xavier NX embedded development platform
* Hardware type: SoC / GPU
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: 8 GB
* Flash / ROM / Storage: Not reported
* Power consumption: 20 W on Jetson NX
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Power consumption, inference speed, model storage size, computational requirements, memory access consumption

### Dataset

* Name: Vehicle-mounted Dense Logs dataset
* Type: Private
* Dataset size: 150 images; augmented 16 times
* Number of classes: 1
* Input resolution: 1600 × 1216 for inference speed testing
* Data modality: RGB log images; depth images used for diameter estimation

### Metrics

* Accuracy: Not reported
* mAP: Improved model mAP0.5:0.95 = 81.8%; INT8 model mAP0.5:0.95 = 81.0%
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Jetson NX INT8 = 2.523 FPS; Jetson NX FP16 = 1.679 FPS; Jetson NX FP32 = 0.3 FPS
* Throughput: Not reported
* Model size: FP32 = 512 MB; FP16 = 145 MB; INT8 = 96 MB
* Parameters: 96.94 M for Res2Net101 + PAFPN improved model
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Jetson NX = 20 W; NVIDIA 3060 = 170 W

### Optimization

* Techniques used: TensorRT quantization, FP16 inference, INT8 inference, model compression, expansion convolution compensation for quantization-induced mask loss
* Quantization: INT8 / FP16
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: TensorRT quantization from FP32 to FP16 and INT8
* Hardware-specific optimization: TensorRT optimization for NVIDIA embedded GPU deployment
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: INT8 = 96 MB; FP16 = 145 MB; FP32 = 512 MB
* Energy per inference reported: Not reported
* Latency on target device reported: Jetson NX INT8 = 2.523 FPS
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The deployment target is an NVIDIA Jetson NX/Xavier NX Linux-based embedded edge platform with 8 GB RAM and GPU acceleration, not an MCU-class TinyML device.

### Benchmarking / Standardization

* Benchmark used: Private Vehicle-mounted Dense Logs dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: ImageNet pretrained weights used for initialization
* Comparison with baseline models: Yes, against Mask R-CNN variants using ResNet50 + FPN, ResNet50 + PAFPN, ResNet101 + FPN, and Res2Net101 + PAFPN
* Comparison with previous works: Yes
* Reproducibility artifacts available: None; dataset and developed algorithm are not publicly available

### Results

* Summary: The improved Res2Net101 + PAFPN Mask R-CNN achieved mAP0.5:0.95 of 81.8% and improved small, medium, and large log segmentation mAP by 2.0%, 1.2%, and 4.4%, respectively. INT8 TensorRT deployment reduced model size to 96 MB and achieved 2.523 FPS on Jetson NX, with final vehicle log volume average error of 0.646% after expansion convolution compensation.

### Limitations

* Dataset and developed algorithm are not publicly available.
* Partial occlusion can produce inaccurate diameter estimation, requiring logs to be loaded so that log ends are exposed as much as possible.
* Detection of partially occluded logs is left for future work.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an embedded vehicle-mounted log volume measurement method based on improved Mask R-CNN instance segmentation, TensorRT quantization, depth-based stratification, and post-processing compensation for quantized inference.

| Paper        | Year | Task         | Model                                      | Technique                  | Device                       | Dataset                    | Main Metric              | Latency   | Model Size | SRAM/RAM | Flash | Energy          | Framework              | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ------------ | ------------------------------------------ | -------------------------- | ---------------------------- | -------------------------- | ------------------------ | --------- | ---------- | -------- | ----- | --------------- | ---------------------- | -------- | ------------- | ------------- |
| Zheng et al. | 2023 | Segmentation | WM R-CNN / Mask R-CNN + Res2Net101 + PAFPN | TensorRT INT8 quantization | NVIDIA Jetson NX / Xavier NX | Vehicle-mounted Dense Logs | mAP0.5:0.95 = 81.0% INT8 | 2.523 FPS | 96 MB      | 8 GB RAM | N/A   | N/A; 20 W power | MMDetection / TensorRT | INT8     | None          | No            |
