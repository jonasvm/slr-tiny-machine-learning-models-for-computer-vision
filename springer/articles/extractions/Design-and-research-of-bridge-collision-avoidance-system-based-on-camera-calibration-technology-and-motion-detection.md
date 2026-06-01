## Paper ID: Design-and-research-of-bridge-collision-avoidance-system-based-on-camera-calibration-technology-and-motion-detection

TinyML classification: Near-TinyML — relevant edge-AI computer vision, but deployment is on Jetson/FPGA edge hardware rather than explicit MCU-class platforms.

### Basic Info

* Authors: Xiaolei Wang, Shichao Wang, Zhihao Wei, Ruijiang Ren, Jingshan Huang
* Year: 2025
* Title: Design and research of bridge collision avoidance system based on camera calibration technology and motion detection
* Source: Scientific Reports, 15:35146
* Type: Experimental

### Problem & Context

* Task: Object detection, segmentation, object tracking, trajectory prediction, and collision-risk detection
* Objective: Detect and predict bridge-collision risks from moving vehicles or vessels using calibrated camera-based vision and real-time risk assessment.
* Application domain: Smart transportation and bridge infrastructure safety
* Scenario: Edge AI, smart infrastructure, edge-cloud, IoT-enabled alerting
* TinyML relevance: Partial
* TinyML justification: The system targets real-time edge deployment and reports latency/FPS/GPU memory on Jetson Xavier NX, but it does not target MCU-class devices or strict TinyML constraints.

### Model / Method

* Model: YOLOv11, ViT-B/16, background subtraction, optical flow, Kalman Filter, DeepSORT, rule-based/ML risk classification
* Architecture family: Hybrid CNN / Transformer / Classical CV
* Techniques: Camera calibration, motion detection, object segmentation, object tracking, trajectory estimation, entropy-calibrated risk scoring, TensorRT edge optimization
* Framework: Python, CUDA, TensorFlow 2.x, PyTorch, OpenCV, SciPy, TensorRT, Docker, MQTT
* Training type: Fine-tuning
* Inference type: Hybrid

### Hardware

* Device: NVIDIA Jetson Xavier NX, Xilinx Zynq UltraScale+ FPGA, NVIDIA Tesla T4 for cloud comparison
* Hardware type: SoC / GPU / FPGA / Edge device
* Processor / microcontroller: NVIDIA Jetson Xavier NX; Xilinx Zynq UltraScale+ FPGA
* Clock frequency: Not reported
* SRAM / RAM: GPU memory usage reported as 3.2 GB on Jetson Xavier NX at 720p and 3.6 GB at 1080p
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes, for the edge-only configuration
* Constraints mentioned: Latency, compute, communication overhead, scalability, robustness, storage capacity, and computational overhead in ultra-low-power environments

### Dataset

* Name: Proprietary bridge collision avoidance dataset
* Type: Private
* Dataset size: 6,000+ annotated frames
* Number of classes: Not reported
* Input resolution: 720p and 1080p reported for efficiency tests; 480p also tested under robustness evaluation
* Data modality: Video frames with sensor-assisted ground truth from CCTV, LIDAR, radar, IMU, and drone footage

### Metrics

* Accuracy: 95.7% detection accuracy for the proposed BCAS
* mAP: YOLOv11 mAP@0.5 of 93.1% in daylight, 89.2% at night, and 85.7% in rain/fog
* Precision: Risk classification precision of 0.94 low risk, 0.88 medium risk, and 0.92 high risk
* Recall: Risk classification recall of 0.93 low risk, 0.89 medium risk, and 0.93 high risk
* F1-score: Risk F1-score of 0.92 for the proposed BCAS; macro F1-score 0.91 and weighted F1-score 0.93
* Latency: 90 ± 6 ms edge-only total latency; 136 ± 8 ms edge-cloud total latency; 162 ms average response latency in comparative evaluation
* FPS: 27.8 FPS on Jetson Xavier NX at 720p; 21.3 FPS on Jetson Xavier NX at 1080p; 54.2 FPS on NVIDIA Tesla T4 at 1080p
* Throughput: 27.8 FPS on Jetson Xavier NX at 720p
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: 3.2 GB GPU memory on Jetson Xavier NX at 720p; 3.6 GB at 1080p; 5.1 GB on Tesla T4 at 1080p
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: TensorRT edge deployment optimization, CUDA acceleration, edge-only latency optimization, entropy-based confidence calibration
* Quantization: None
* Pruning: No
* Knowledge distillation: No
* Compression method: Not reported
* Hardware-specific optimization: TensorRT and CUDA optimization for edge deployment
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 36 ms per frame on Jetson Xavier NX at 720p; 47 ms per frame at 1080p
* Runs without full operating system: Not reported
* Fully on-device inference: Yes, for edge-only configuration
* Communication required during inference: Not required for edge-only inference; edge-cloud configuration uses MQTT, HTTP API, and 5G-V2X communication
* Candidate for Strict TinyML: No
* Reason: The system is evaluated on Jetson Xavier NX, FPGA, and cloud GPU hardware with TensorRT/Docker-based edge deployment, without MCU-class deployment, SRAM/Flash constraints, TFLM, or energy-per-inference reporting.

### Benchmarking / Standardization

* Benchmark used: Proprietary dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: MS COCO and BDD100K used for pre-training/fine-tuning context, not as the main benchmark
* Comparison with baseline models: Yes, background subtraction, rule-based system, Faster R-CNN, CenterNet, and YOLOv8
* Comparison with previous works: Yes, through comparison with recent state-of-the-art models
* Reproducibility artifacts available: Dataset available from corresponding author upon reasonable request

### Results

* Summary: The proposed BCAS achieved 95.7% detection accuracy, 3.2% false alarm rate, and 162 ms average response latency. On Jetson Xavier NX, it achieved 27.8 FPS and 36 ms per frame at 720p with 3.2 GB GPU memory usage.

### Limitations

* Dataset scale is limited and may not cover all vehicle types, bridge geometries, or environmental conditions.
* Deep learning modules may require retraining for different regions or sensor types.
* Computationally intensive models may challenge deployment in resource-constrained or ultra-low-power environments.
* Model interpretability remains a concern for safety-critical applications.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an intelligent vision-based Bridge Collision Avoidance System that combines calibrated camera geometry, YOLOv11/ViT-based motion detection, trajectory prediction, and real-time edge/edge-cloud alert generation for bridge safety.

| Paper       | Year | Task                                                   | Model                                         | Technique                                                        | Device                                         | Dataset                             | Main Metric              | Latency                                              | Model Size | SRAM/RAM                                      | Flash | Energy | Framework                                     | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ------------------------------------------------------ | --------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------- | ----------------------------------- | ------------------------ | ---------------------------------------------------- | ---------- | --------------------------------------------- | ----- | ------ | --------------------------------------------- | -------- | ------------- | ------------- |
| Wang et al. | 2025 | Object detection / tracking / collision-risk detection | YOLOv11 + ViT-B/16 + Kalman Filter + DeepSORT | Camera calibration, motion detection, TensorRT edge optimization | Jetson Xavier NX; Xilinx Zynq UltraScale+ FPGA | Proprietary 6,000+ annotated frames | Detection accuracy 95.7% | 90 ± 6 ms edge-only; 162 ms average response latency | N/A        | 3.2 GB GPU memory on Jetson Xavier NX at 720p | N/A   | N/A    | PyTorch, TensorFlow, OpenCV, TensorRT, Docker | N/A      | None          | No            |
