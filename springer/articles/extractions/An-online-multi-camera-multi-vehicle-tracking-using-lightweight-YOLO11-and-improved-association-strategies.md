## Paper ID: An-online-multi-camera-multi-vehicle-tracking-using-lightweight-YOLO11-and-improved-association-strategies

TinyML classification: Near-TinyML — The work is deployed on a Jetson AGX Orin edge device, with no explicit MCU-class deployment or MCU-level memory constraints.

### Basic Info

* Authors: Feijiang Huang; Jialong Yao; Chengyue Su; Sheng Xu
* Year: 2025
* Title: An online multi-camera multi-vehicle tracking using lightweight YOLO11 and improved association strategies
* Source: Journal of King Saud University Computer and Information Sciences, 37:180
* Type: Methodological

### Problem & Context

* Task: Object detection and multi-camera multi-vehicle tracking
* Objective: Develop an efficient online MCMVT method with improved tracking accuracy and real-time edge-device performance.
* Application domain: Intelligent transportation and urban security
* Scenario: Edge AI / embedded GPU edge device
* TinyML relevance: Partial
* TinyML justification: The paper targets real-time edge deployment using a lightweight YOLO11s model, but the reported deployment is on NVIDIA Jetson AGX Orin rather than MCU-class hardware.

### Model / Method

* Model: YOLO11s detector + ResNet101-IBN-A feature extractor + optimized SCMVT/MCMVT association framework
* Architecture family: CNN
* Techniques: Lightweight detection, cosine-distance matching, IoU matching, EMA feature update, small-target filtering, hierarchical clustering, Dunn index-based clustering threshold optimization
* Framework: PyTorch
* Training type: Fine-tuning / transfer learning
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson AGX Orin
* Hardware type: SoC / GPU
* Processor / microcontroller: NVIDIA Ampere GPU with 2,048 CUDA cores and 64 Tensor cores; eight-core ARM Cortex-A78AE CPU cluster
* Clock frequency: Not reported
* SRAM / RAM: 32 GB LPDDR5 ECC memory
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Compute constraints, latency, real-time performance, resource-limited edge deployment, high-resolution multi-camera processing

### Dataset

* Name: COCO-Vehicle; CityFlowV2; VeRi-776
* Type: Public
* Dataset size: COCO-Vehicle uses car, bus, and truck categories with 80% training and 20% testing; feature extraction uses over 66,000 bounding boxes from CityFlowV2 S01/S03/S04 and over 50,000 boxes from VeRi-776; tracking is evaluated on CityFlowV2 S02 with four cameras
* Number of classes: 3 vehicle classes for COCO-Vehicle
* Input resolution: 640×640 for detector training; 384×384 for feature extraction; CityFlowV2 videos are 1920×1080
* Data modality: RGB video / image frames

### Metrics

* Accuracy: Not reported
* mAP: 74.3% mAP50 for YOLO11s on COCO-Vehicle
* Precision: IDP 81.32
* Recall: IDR 81.97
* F1-score: IDF1 81.64
* Latency: 8 ms per frame tracking time; 42.6 ms inference time on Jetson AGX Orin
* FPS: 3 FPS on Jetson AGX Orin; 10 FPS in the reported YOLO11s tracking experiment
* Throughput: Not reported
* Model size: Not reported
* Parameters: 9.4M for YOLO11s
* MACs / FLOPs: 21.6G FLOPs for YOLO11s
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight YOLO11s detector, cosine-distance and IoU joint matching, EMA feature update, small bounding-box filtering, hierarchical clustering with Dunn index
* Quantization: None
* Pruning: No
* Knowledge distillation: No
* Compression method: Lightweight model selection
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 42.6 ms inference time and 3 FPS on NVIDIA Jetson AGX Orin
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper reports deployment on a Jetson AGX Orin edge device with GPU acceleration and 32 GB RAM, with no MCU-class deployment, SRAM/Flash constraints, or bare-metal/RTOS execution evidence.

### Benchmarking / Standardization

* Benchmark used: CityFlowV2 S02; COCO-Vehicle
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: COCO2017; VeRi-776
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed method achieved IDF1 81.64 on the CityFlowV2 S02 scenario with 8 ms average tracking time per frame. On NVIDIA Jetson AGX Orin, YOLO11s achieved 3 FPS with 42.6 ms inference time.

### Limitations

* Robustness under severe occlusion and more complex scenes requires further improvement.
* High-resolution and multi-camera inputs remain computationally intensive for edge devices.
* Experiments are primarily based on CityFlowV2, so broader dataset validation is needed.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an efficient online multi-camera multi-vehicle tracking framework using lightweight YOLO11s detection, improved single-camera association, and hierarchical cross-camera trajectory matching for real-time edge deployment.

| Paper        | Year | Task                                             | Model                     | Technique                                                        | Device                 | Dataset                                | Main Metric             | Latency                               | Model Size | SRAM/RAM                        | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ------------------------------------------------ | ------------------------- | ---------------------------------------------------------------- | ---------------------- | -------------------------------------- | ----------------------- | ------------------------------------- | ---------- | ------------------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Huang et al. | 2025 | Multi-camera vehicle tracking / object detection | YOLO11s + ResNet101-IBN-A | Lightweight detector + cosine/IoU association + EMA + clustering | NVIDIA Jetson AGX Orin | COCO-Vehicle; CityFlowV2 S02; VeRi-776 | IDF1 81.64; mAP50 74.3% | 42.6 ms on Jetson; 8 ms tracking time | N/A        | 32 GB RAM device; RAM usage N/A | N/A   | N/A    | PyTorch   | FP32     | None          | No            |
