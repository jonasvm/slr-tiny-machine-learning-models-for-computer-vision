## Paper ID: BlinkBud-Detecting-Hazards-from-Behind-via-Sampled-Monocular-3D-Detection-on-a-Single-Earbud

TinyML classification: Near-TinyML — the system uses an MCU-based earbud and reports ultra-low-power wearable operation, but the neural-network inference is deployed on paired smartphones rather than clearly on MCU-class hardware.

### Basic Info

* Authors: Yunzhe Li, Jiajun Yan, Yuzhou Wei, Kechen Liu, Yize Zhao, Chong Zhang, Hongzi Zhu, Li Lu, Shan Chang, Minyi Guo
* Year: 2025
* Title: BlinkBud: Detecting Hazards from Behind via Sampled Monocular 3D Detection on a Single Earbud
* Source: Proceedings of the ACM on Interactive, Mobile, Wearable and Ubiquitous Technologies, Vol. 9, No. 4, Article 191
* Type: Experimental

### Problem & Context

* Task: Object detection and 3D object tracking
* Objective: Detect and track hazardous rear-approaching objects using sampled monocular images from a camera-equipped earbud and a paired smartphone.
* Application domain: Pedestrian and cyclist road safety
* Scenario: Wearable, mobile, edge, on-device sensing
* TinyML relevance: Partial
* TinyML justification: The system uses a low-power MCU-based earbud and reports power constraints, but neural-network inference is performed on a paired smartphone rather than fully on MCU-class hardware.

### Model / Method

* Model: YOLOv5s-based lightweight 2D object detector, pinhole-camera depth estimation, Extended Kalman Filter tracking, SARSA-based adaptive frame sampling, IMU-based pitch/yaw correction
* Architecture family: CNN + Classical ML / Other
* Techniques: Lightweight object detection, grayscale input, adaptive image sampling, Kalman-filter-based tracking, reinforcement-learning-based sampling, IMU-based motion compensation
* Framework: NCNN inference library
* Training type: Pretrained model; fine-tuning not reported
* Inference type: Hybrid

### Hardware

* Device: Customized camera-equipped earbud paired with Redmi K70, Mi11, and Redmi K20 smartphones
* Hardware type: MCU + Mobile
* Processor / microcontroller: ESP32-S3 MCU on earbud; Snapdragon 8 Gen 2, Snapdragon 888, and Snapdragon 730 on smartphones
* Clock frequency: Not reported
* SRAM / RAM: Smartphone RAM of 12 GB, 8 GB, and 6 GB; earbud SRAM not reported
* Flash / ROM / Storage: Smartphone storage of 512 GB, 256 GB, and 128 GB; earbud flash not reported
* Power consumption: 29.8 mW on earbud and 702.6 mW on smartphone on average
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes, locally on paired smartphone without cloud upload; not MCU-only
* Constraints mentioned: Power, computation, communication overhead, latency, image transmission, resource-constrained wearable operation

### Dataset

* Name: Self-collected rear object approaching dataset
* Type: Private
* Dataset size: 262 one-minute video clips
* Number of classes: Not reported as a formal class count; current implementation focuses on cars and cycles
* Input resolution: 640 × 640 default; 320p, 640p, and 960p evaluated
* Data modality: Grayscale image, video, IMU sensor data, LiDAR-based ground truth

### Metrics

* Accuracy: 95.83% detection accuracy with grayscale input in a representative evaluation; RGB input reported as 94.45%
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 72 ms end-to-end latency; 30 ms image capture/transmission, 39 ms inference, less than 3 ms alert delivery
* FPS: 10 FPS during data collection
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Less than 1 GB average smartphone memory usage
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 29.8 mW on earbud and 702.6 mW on smartphone on average

### Optimization

* Techniques used: Grayscale input, lightweight YOLOv5s-based detection, compressed 2D object detection scheme, adaptive SARSA-based frame sampling, EKF tracking, IMU-based pitch/yaw correction
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Compressed 2D object detector mentioned, but compression method not specified
* Hardware-specific optimization: NCNN deployment on smartphones and adaptive sampling to reduce sensing, transmission, and computation
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 72 ms end-to-end on the earbud-smartphone system; 39 ms inference on smartphone
* Runs without full operating system: No
* Fully on-device inference: Yes, locally on paired smartphone without cloud upload; not MCU-only
* Communication required during inference: Yes, the earbud sends grayscale images and IMU data to the smartphone through WiFi/HTTP
* Candidate for Strict TinyML: No
* Reason: The system includes an MCU-based earbud, but the neural-network inference is deployed on smartphones and the paper does not report MCU-level memory, flash, model size, or inference execution.

### Benchmarking / Standardization

* Benchmark used: Self-collected rear object approaching dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: KITTI is used for the pretrained YOLOv5s model
* Comparison with baseline models: Yes, compared with naive EKF, interval frame sampling, random frame sampling, confidence-based frame sampling, and BlinkBud without IMU
* Comparison with previous works: Not reported as quantitative comparison
* Reproducibility artifacts available: Not reported

### Results

* Summary: BlinkBud achieved an average FPR of 4.90% and FNR of 1.47% across real-world scenarios. The system reported average power consumption of 29.8 mW on the earbud and 702.6 mW on the smartphone, with 72 ms end-to-end latency.

### Limitations

* The user study is formative, single-day, and based on self-reported questionnaires without task-based usability trials or standardized instruments.
* External validity is limited because evaluation involved ten participants on a single university campus under limited traffic and weather conditions.
* Vision-based tracking may degrade in very low-light conditions when the camera cannot capture clear images.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a wearable rear-hazard detection system that uses a camera-equipped earbud and paired smartphone to perform sampled monocular 3D object detection and tracking with adaptive low-power visual sensing.

| Paper     | Year | Task                                    | Model                                         | Technique                                                   | Device                       | Dataset                                        | Main Metric          | Latency          | Model Size | SRAM/RAM                           | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | --------------------------------------- | --------------------------------------------- | ----------------------------------------------------------- | ---------------------------- | ---------------------------------------------- | -------------------- | ---------------- | ---------- | ---------------------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Li et al. | 2025 | Object detection and 3D object tracking | YOLOv5s-based detector + EKF + SARSA sampling | Adaptive frame sampling and lightweight grayscale detection | ESP32-S3 earbud + smartphone | Self-collected rear object approaching dataset | FPR 4.90%, FNR 1.47% | 72 ms end-to-end | N/A        | <1 GB smartphone RAM; MCU SRAM N/A | N/A   | N/A    | NCNN      | N/A      | None          | No            |
