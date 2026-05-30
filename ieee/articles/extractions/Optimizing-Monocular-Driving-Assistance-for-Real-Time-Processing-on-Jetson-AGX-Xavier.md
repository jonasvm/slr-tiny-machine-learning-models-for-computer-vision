## Paper ID: Optimizing-Monocular-Driving-Assistance-for-Real-Time-Processing-on-Jetson-AGX-Xavier

TinyML classification: Near-TinyML — evaluated on Jetson AGX Xavier edge hardware with GPU/DLA acceleration rather than microcontroller-class constraints.

### Basic Info

* Authors: Huy-Hung Nguyen; Duong Nguyen-Ngoc Tran; Long Hoang Pham; Jae Wook Jeon
* Year: 2024
* Title: Optimizing Monocular Driving Assistance for Real-Time Processing on Jetson AGX Xavier
* Source: IEEE Access
* Type: Experimental

### Problem & Context

* Task: Object detection, lane detection, traffic object recognition, scene analysis for collision avoidance
* Objective: Develop and optimize a real-time monocular ADAS pipeline running on a single Jetson AGX Xavier embedded device.
* Application domain: Advanced driver assistance systems and autonomous driving
* Scenario: Edge, embedded, autonomous system
* TinyML relevance: Partial
* TinyML justification: The paper targets on-device edge inference on Jetson AGX Xavier with optimization for real-time embedded deployment, but it does not target MCU-class or bare-metal/RTOS TinyML constraints.

### Model / Method

* Model: UFLDv2 for lane detection; YOLOv8 for traffic object detection; LPRNet for speed-limit/character recognition; rule-based scene analysis
* Architecture family: CNN
* Techniques: Multithreaded processing, TensorRT optimization, post-training quantization, FP16 precision, INT8 precision, GPU/DLA task allocation
* Framework: PyTorch, TensorRT, NVIDIA JetPack
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson AGX Xavier DevKit; also evaluated on Jetson AGX Orin DevKit and GeForce Titan Xp workstation
* Hardware type: SoC with CPU, GPU, Tensor Cores, and DLA accelerators
* Processor / microcontroller: Jetson AGX Xavier with 8-core Carmel CPU, Volta GV10B GPU with 512 CUDA cores and 64 Tensor Cores, and 2× DLA v1 cores
* Clock frequency: CPU 2.26 GHz; GPU 1377 MHz; DLA 1.4 GHz
* SRAM / RAM: 32 GB shared memory
* Flash / ROM / Storage: Not reported
* Power consumption: Jetson AGX Xavier supports 10 W, 15 W, and 30 W profiles; experiments used 30 W
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Compute, latency, power, memory bandwidth, communication overhead, cross-device communication, edge-cloud latency

### Dataset

* Name: KATECH Korean dashcam traffic dataset
* Type: Not reported
* Dataset size: More than 160,000 traffic frames; 10,000 images with additional scene-analysis annotations
* Number of classes: 23 traffic object classes
* Input resolution: Dataset frames at 1280×720, 1280×672, or 1920×1080; model inputs include 640×640, 1280×1280, 320×1600, and 24×94 depending on module
* Data modality: Monocular RGB dashcam traffic images/video frames

### Metrics

* Accuracy: Scene analysis overall accuracy up to 97.8%
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Up to 43.67 FPS on Jetson AGX Xavier
* Throughput: Whole-system throughput up to 43.67 FPS on Jetson AGX Xavier; up to 131.36 FPS on Jetson AGX Orin at 60 W
* Model size: Not reported
* Parameters: UFLDv2-res18 206.30M; UFLDv2-res34 216.41M; YOLOv8s 11.16M; YOLOv8m 25.89M; YOLOv8l 43.67M; LPRNet 0.45M
* MACs / FLOPs: UFLDv2-res18 37.40G; UFLDv2-res34 75.16G; YOLOv8s-640 28.60G; YOLOv8m-640 78.90G; YOLOv8s-1280 114.40G; YOLOv8l-640 165.20G; YOLOv8m-1280 315.80G; LPRNet 0.29G
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 30 W power profile used for Jetson AGX Xavier experiments

### Optimization

* Techniques used: Multithreading, TensorRT inference optimization, post-training quantization, FP16 precision, INT8 precision, workload allocation across GPU and DLA cores
* Quantization: INT8 and FP16 PTQ
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Post-training quantization
* Hardware-specific optimization: TensorRT, NVIDIA DLA acceleration, GPU/DLA task mapping, Jetson power-profile configuration
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: FPS reported, but per-inference latency not reported
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: No
* Reason: The deployment target is a Linux-based Jetson AGX Xavier SoC with GPU/DLA acceleration and 32 GB shared memory, not an MCU-class device with kilobyte- or low-megabyte-scale memory constraints.

### Benchmarking / Standardization

* Benchmark used: COCO-style AP50 metric for traffic object detection; scene-analysis accuracy; whole-system FPS throughput
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: COCO detection evaluation metric
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The optimized INT8 configurations exceeded 30 FPS on Jetson AGX Xavier, with the best configuration reaching 43.67 FPS. The best reported traffic object detection AP50 was 91.6% for YOLOv8s-1280×1280, and scene-analysis accuracy reached 97.8%.

### Limitations

* YOLOv8m-640×640 and YOLOv8l-640×640 had lower traffic-light performance due to small object size and lower input resolution.
* Whole-system throughput was lower than individual module throughput because unsupported DLA layers fall back to the GPU and GPU/DLA cores share memory bandwidth.
* Jetson AGX Orin at 30 W underperformed Jetson AGX Xavier due to reduced GPU and DLA frequencies under that power profile.

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

* This paper proposes a modular real-time monocular ADAS implemented entirely on a single Jetson AGX Xavier using UFLDv2, YOLOv8, LPRNet, TensorRT, multithreading, and post-training quantization.

| Paper         | Year | Task                                                                  | Model                    | Technique                       | Device            | Dataset                               | Main Metric                      | Latency        | Model Size | SRAM/RAM                      | Flash | Energy | Framework          | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---: | --------------------------------------------------------------------- | ------------------------ | ------------------------------- | ----------------- | ------------------------------------- | -------------------------------- | -------------- | ---------- | ----------------------------- | ----- | ------ | ------------------ | -------- | ------------- | ------------- |
| Nguyen et al. | 2024 | Object detection, lane detection, traffic recognition, scene analysis | UFLDv2 + YOLOv8 + LPRNet | TensorRT + PTQ + multithreading | Jetson AGX Xavier | KATECH Korean dashcam traffic dataset | AP50 91.6%; scene accuracy 97.8% | N/A; 43.67 FPS | N/A        | 32 GB shared RAM; runtime N/A | N/A   | N/A    | PyTorch + TensorRT | INT8     | None          | No            |
