## Paper ID: Visual-LiDAR-Based-3D-Object-Detection-and-Tracking-for-Embedded-Systems

TinyML classification: Near-TinyML — the implementation targets an embedded Jetson AGX Xavier/Linux/CUDA platform rather than explicit MCU-class or TensorFlow Lite Micro deployment.

### Basic Info

* Authors: Muhammad Sualeh; Gon-Woo Kim
* Year: 2020
* Title: Visual-LiDAR Based 3D Object Detection and Tracking for Embedded Systems
* Source: IEEE Access
* Type: Experimental

### Problem & Context

* Task: 3D object detection and multi-object tracking
* Objective: Develop an embedded visual-LiDAR framework for joint 3D object detection and tracking in autonomous vehicle environments.
* Application domain: Autonomous vehicles
* Scenario: Embedded autonomous system
* TinyML relevance: Partial
* TinyML justification: The paper targets embedded real-time perception using limited computational resources, but the implementation uses NVIDIA Jetson AGX Xavier with Ubuntu, ROS, and CUDA rather than MCU-class TinyML hardware.

### Model / Method

* Model: Visual-LiDAR 3D MODT framework with YOLOv3 visual object detection, LiDAR ground segmentation, clustering, box fitting, and IMM-UKF-JPDAF tracking.
* Architecture family: Hybrid CNN + Classical tracking
* Techniques: Late sensor fusion, lightweight visual detection, cylindrical-grid LiDAR processing, L-shape box fitting, IMM-UKF-JPDAF tracking, track pruning, input-resolution tuning.
* Framework: ROS Melodic Morenia, Ubuntu Linux 18.04.1, CUDA 10.0, YOLOv3 ROS package
* Training type: Pretrained YOLOv3 on Microsoft COCO; LiDAR point-cloud classification does not involve direct point-cloud training.
* Inference type: On-device

### Hardware

* Device: Hyundai i30 platform with OS1-64 Ouster LiDAR, ZED camera, and NVIDIA Jetson AGX Xavier
* Hardware type: SoC / CPU / GPU
* Processor / microcontroller: NVIDIA Carmel ARM CPU processors; NVIDIA Jetson AGX Xavier GPU
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Limited computational resources, real-time performance, inference time, computational demand, embedded computing constraints, LiDAR sampling time.

### Dataset

* Name: KITTI Dataset; Microsoft COCO for pretrained YOLOv3
* Type: Public
* Dataset size: 10 KITTI dataset sequences with 2195 frames and 147 trackable objects for MODT evaluation
* Number of classes: Car, pedestrian, and cyclist reported for 3D MOT evaluation; YOLOv3 uses Microsoft COCO pretrained classes limited to trackable dynamic objects.
* Input resolution: 416 × 416 pixels for YOLOv3 visual detection
* Data modality: Camera image + 3D LiDAR point cloud

### Metrics

* Accuracy: MOTA 86.7% average for MODT evaluation
* mAP: YOLOv3 pretrained detector reported as 57.9 mAP AP50 on Microsoft COCO at 608 × 608 input resolution
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Maximum reported Jetson cycle time of 93.7 ms
* FPS: 236 FPS for the proposed tracker on KITTI car validation
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Optimized ground classification, 3D cylindrical-grid clustering, reduced neighbor search, track management pruning, input image resolution tuning, GPU use for visual detection, ARM CPU use for LiDAR preprocessing and tracking.
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: CUDA acceleration on Jetson AGX Xavier GPU for visual detection; LiDAR preprocessing and tracking on NVIDIA Carmel ARM CPU processors.
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Maximum Jetson cycle time of 93.7 ms
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: No for the single-vehicle MODT framework
* Candidate for Strict TinyML: No
* Reason: The paper targets embedded edge deployment on NVIDIA Jetson AGX Xavier with Ubuntu, ROS, and CUDA, without MCU-class hardware, bare-metal/RTOS execution, or SRAM/Flash/energy evidence.

### Benchmarking / Standardization

* Benchmark used: KITTI Dataset, MOT16 metrics, extended KITTI 3D MOT evaluation
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Microsoft COCO for pretrained YOLOv3
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed MODT framework achieved 86.7% average MOTA and 73.5% average MOTP on selected KITTI sequences. The embedded Jetson implementation remained within LiDAR sampling time, with maximum cycle time reported as 93.7 ms, while the tracker achieved 236 FPS on KITTI car validation.

### Limitations

* Performance degrades as range increases due to false positives, false negatives, and LiDAR sparsity.
* Objects entering the detection region at relative speeds above 80 km/h may fail to establish mature tracks.
* Correct dimensions and centroids cannot be reliably estimated for objects that remain partially occluded throughout their track life.
* Pedestrian tracking performance is lower in crowded scenes with nearby pedestrians.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an embedded visual-LiDAR late-fusion framework for joint 3D object detection and tracking using optimized LiDAR point-cloud processing, YOLOv3 visual classification, and IMM-UKF-JPDAF tracking.

| Paper         | Year | Task                             | Model                                              | Technique                                         | Device                   | Dataset | Main Metric | Latency                | Model Size | SRAM/RAM | Flash | Energy | Framework           | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | -------------------------------- | -------------------------------------------------- | ------------------------------------------------- | ------------------------ | ------- | ----------- | ---------------------- | ---------- | -------- | ----- | ------ | ------------------- | -------- | ------------- | ------------- |
| Sualeh et al. | 2020 | 3D object detection and tracking | Visual-LiDAR 3D MODT with YOLOv3 and IMM-UKF-JPDAF | Late sensor fusion and optimized LiDAR processing | NVIDIA Jetson AGX Xavier | KITTI   | MOTA 86.7%  | 93.7 ms max cycle time | N/A        | N/A      | N/A   | N/A    | ROS / Ubuntu / CUDA | N/A      | None          | No            |
