## Paper ID: A-power-aware-vision-based-virtual-sensor-for-real-time-edge-computing

TinyML classification: Near-TinyML — the system targets edge vision on NVIDIA Jetson Nano, but there is no explicit MCU-class deployment evidence.

### Basic Info

* Authors: Chiara Contoli; Lorenzo Calisti; Giacomo Di Fabrizio; Nicholas Kania; Alessandro Bogliolo; Emanuele Lattanzi.
* Year: 2024
* Title: A power-aware vision-based virtual sensor for real-time edge computing
* Source: Journal of Real-Time Image Processing, 21:103
* Type: Experimental

### Problem & Context

* Task: Object detection and multi-object tracking.
* Objective: Reduce energy consumption in real-time edge-based multi-object tracking while preserving tracking accuracy.
* Application domain: Edge video analytics, traffic monitoring, pedestrian monitoring, privacy-preserving virtual sensing.
* Scenario: Edge computing.
* TinyML relevance: Partial
* TinyML justification: The paper targets power-aware computer vision on an edge device, but deployment is on NVIDIA Jetson Nano rather than MCU-class TinyML hardware.

### Model / Method

* Model: SSD MobileNet, TAO TrafficCamNet, lightweight IOU tracker, and Dynamic Inference Power Manager.
* Architecture family: CNN + Classical ML / Other
* Techniques: Adaptive frame rate, frame skipping, power-aware dynamic inference management.
* Framework: NVIDIA Jetson Inference
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson Nano
* Hardware type: GPU / SoC
* Processor / microcontroller: NVIDIA Maxwell GPU and quad-core ARM Cortex-A57 MPCore CPU.
* Clock frequency: Not reported
* SRAM / RAM: 4 GB RAM
* Flash / ROM / Storage: 32 GB storage
* Power consumption: About 5 W during inference and tracking bursts; below 2 W during skipped frames.
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Power, energy, resource constraints, real-time processing, privacy, and edge-device limitations.

### Dataset

* Name: MOT17 benchmark; edited YouTube pedestrian and car video benchmarks.
* Type: Public
* Dataset size: 120-second pedestrian video at 30 FPS; 210-second car video at 30 FPS; MOT17 size not reported.
* Number of classes: Not reported
* Input resolution: TrafficCamNet uses 960 × 544 input; benchmark video resolution not reported.
* Data modality: RGB video

### Metrics

* Accuracy: Tracking accuracy decrease reported as less than 1.2%.
* mAP: Not reported
* Precision: Association precision reported in plots, but exact values are not tabulated.
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Source videos use 30 FPS; system FPS not reported.
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: About 5 W during inference/tracking and below 2 W during skipped frames; energy savings of about 36% for low-dynamicity videos and 21% for more dynamic videos.

### Optimization

* Techniques used: Dynamic Inference Power Manager with adaptive frame-rate control and frame skipping.
* Quantization: Not reported
* Pruning: No
* Knowledge distillation: No
* Compression method: Not reported
* Hardware-specific optimization: Deployment and evaluation on NVIDIA Jetson Nano using NVIDIA Jetson Inference.
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: No
* Reason: The system is deployed on NVIDIA Jetson Nano, a Linux-capable GPU-based edge platform, with no explicit MCU-class, RTOS, TensorFlow Lite Micro, SRAM, or Flash-constrained deployment evidence.

### Benchmarking / Standardization

* Benchmark used: MOT17; pedestrian and car video benchmarks.
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: MOTChallenge / MOT17
* Comparison with baseline models: Yes, compared against the same detection/tracking pipeline with DIPM disabled.
* Comparison with previous works: Related work is discussed, but no direct quantitative comparison with previous systems is reported.
* Reproducibility artifacts available: Dataset/public benchmarks; code and model not reported.

### Results

* Summary: The proposed DIPM reduced energy consumption by about 36% in low-dynamicity car videos and about 21% in more dynamic pedestrian videos. Tracking accuracy degradation remained below 1.2%, and MOT17 experiments showed limited impact when the DIPM parameters were properly calibrated.

### Limitations

* No dedicated limitations section is reported.
* The paper notes that residual power remains because the CPU continues decoding input frames during skipped frames.
* The paper does not implement operating-system-dependent webcam-driver shutdown strategies for additional energy savings.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a power-aware real-time vision-based virtual sensor with a Dynamic Inference Power Manager that adaptively skips frames to reduce edge-device energy consumption during multi-object tracking.

| Paper          | Year | Task                                       | Model                                           | Technique                         | Device             | Dataset                               | Main Metric                                            | Latency | Model Size | SRAM/RAM | Flash         | Energy               | Framework               | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | ------------------------------------------ | ----------------------------------------------- | --------------------------------- | ------------------ | ------------------------------------- | ------------------------------------------------------ | ------- | ---------- | -------- | ------------- | -------------------- | ----------------------- | -------- | ------------- | ------------- |
| Contoli et al. | 2024 | Object detection and multi-object tracking | SSD MobileNet / TAO TrafficCamNet + IOU tracker | Dynamic frame-rate frame skipping | NVIDIA Jetson Nano | MOT17 + YouTube pedestrian/car videos | 21–36% energy saving with <1.2% tracking accuracy loss | N/A     | N/A        | 4 GB RAM | 32 GB storage | 21–36% energy saving | NVIDIA Jetson Inference | N/A      | None          | No            |
