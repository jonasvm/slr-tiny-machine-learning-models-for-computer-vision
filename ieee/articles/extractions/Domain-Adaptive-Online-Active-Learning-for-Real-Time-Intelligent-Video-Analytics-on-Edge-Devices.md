## Paper ID: Domain-Adaptive-Online-Active-Learning-for-Real-Time-Intelligent-Video-Analytics-on-Edge-Devices

TinyML classification: Near-TinyML — The work targets edge AI computer vision on a Jetson NX device, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Michele Boldo, Mirco De Marchi, Enrico Martini, Stefano Aldegheri, Nicola Bombieri
* Year: 2024
* Title: Domain-Adaptive Online Active Learning for Real-Time Intelligent Video Analytics on Edge Devices
* Source: IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems, Vol. 43, No. 11, November 2024
* Type: Methodological

### Problem & Context

* Task: Human pose estimation and object detection
* Objective: To enable domain-adaptive online active learning and fine-tuning for real-time intelligent video analytics on resource-constrained edge devices.
* Application domain: Intelligent video analytics, healthcare, Industry 4.0/5.0, automotive object detection
* Scenario: Edge AI, resource-constrained edge devices, real-time video analytics
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained edge deployment and reports latency and energy on NVIDIA Jetson NX/Xavier NX, but it does not target MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, or kilobyte-scale memory deployment.

### Model / Method

* Model: SVD-based auto quality assessment with online active learning and teacher-student knowledge distillation; TRTPose/OpenPose for human pose estimation and SSD/YOLOv7 for object detection
* Architecture family: CNN
* Techniques: Online active learning, online domain adaptation, knowledge distillation, SVD-based quality assessment, sampling query optimization, pruning, quantization
* Framework: TRTPose, OpenPose, YOLOv7, SSD
* Training type: Fine-tuning
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson NX / NVIDIA Jetson Xavier NX; Intel i7 desktop with NVIDIA GeForce RTX 2070 SUPER used for comparison
* Hardware type: SoC / GPU
* Processor / microcontroller: 384 CUDA-core GPU accelerator, 6-core processor
* Clock frequency: Not reported
* SRAM / RAM: 8 GB unified memory
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Limited computational resources, memory resources, real-time latency, energy consumption, privacy, bandwidth, communication/offloading constraints

### Dataset

* Name: COCO, Human3.6M, VOC, LaSOT, real-world Industry 4.0 dataset
* Type: Public and private
* Dataset size: Not reported
* Number of classes: COCO has 80 classes; VOC has 20 classes; object detection case study focuses on cars
* Input resolution: 2K resolution for the real-world Industry 4.0 dataset
* Data modality: RGB video, video frames, motion capture ground truth for Human3.6M

### Metrics

* Accuracy: Human pose estimation reported using MPJPE; object detection reported using MAE
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: On Jetson NX, proposed method reports 47.1 ms, 44.1 ms, and 32.8 ms for HPE scenarios; 32.8 ms for OD
* FPS: Proposed method reports 21.3 Hz, 22.7 Hz, and 30.5 Hz for HPE scenarios on Jetson NX; 30.5 Hz for OD on Jetson NX
* Throughput: Reported in Hz
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: SVD-based training scheduling, online active learning, teacher-student knowledge distillation, sampling query optimization, pruning, quantization
* Quantization: Not reported
* Pruning: Yes
* Knowledge distillation: Yes
* Compression method: Pruning and quantization are mentioned, but detailed compression settings are not reported
* Hardware-specific optimization: Edge-device scheduling to reduce teacher execution and training overhead on NVIDIA Jetson NX/Xavier NX
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Yes
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No cloud or offloading required during the proposed edge execution
* Candidate for Strict TinyML: No
* Reason: The deployment target is NVIDIA Jetson NX/Xavier NX with GPU acceleration and 8 GB unified memory, not an MCU-class or bare-metal/RTOS TinyML platform.

### Benchmarking / Standardization

* Benchmark used: Human3.6M, COCO, VOC, LaSOT
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Human3.6M, COCO, VOC, LaSOT
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed method achieves similar accuracy to accuracy-based online adaptation while reducing teacher execution and training frequency. For object detection, it reports MAE of 100.8 pixels with 9.2% teacher execution and 9.2% update rate, compared with 108.7 pixels and 100% teacher execution for the accuracy-based approach.

### Limitations

* The framework targets spatio-temporal models with specific spatial and temporal correlation properties.
* Parallel execution of student, teacher, and training tasks is reported as unfeasible on Jetson Xavier NX due to resource limits.
* Algorithm parameters may need dataset-specific tuning.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an SVD-based domain-adaptive online active learning framework that performs teacher-student knowledge-distillation fine-tuning directly on edge devices for real-time video analytics.

| Paper        | Year | Task                                    | Model                        | Technique                                                    | Device                  | Dataset                                           | Main Metric                     | Latency      | Model Size | SRAM/RAM            | Flash | Energy        | Framework                      | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | --------------------------------------- | ---------------------------- | ------------------------------------------------------------ | ----------------------- | ------------------------------------------------- | ------------------------------- | ------------ | ---------- | ------------------- | ----- | ------------- | ------------------------------ | -------- | ------------- | ------------- |
| Boldo et al. | 2024 | Human pose estimation; Object detection | TRTPose/OpenPose; SSD/YOLOv7 | SVD-based OAL, knowledge distillation, pruning, quantization | NVIDIA Jetson Xavier NX | Human3.6M; COCO; VOC; LaSOT; Industry 4.0 dataset | MPJPE 8.5–12.2 px; MAE 100.8 px | 32.8–47.1 ms | N/A        | 8 GB unified memory | N/A   | 19.3–27.5 mWh | TRTPose; OpenPose; YOLOv7; SSD | N/A      | None          | No            |
