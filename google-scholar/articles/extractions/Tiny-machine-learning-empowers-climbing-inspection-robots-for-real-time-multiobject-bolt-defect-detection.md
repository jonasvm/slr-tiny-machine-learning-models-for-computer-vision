Paper ID: Tiny-machine-learning-empowers-climbing-inspection-robots-for-real-time-multiobject-bolt-defect-detection

TinyML classification: Strict TinyML — explicitly deploys FOMO on an Arduino Nicla Vision STM32H747 Arm Cortex-M microcontroller with reported Flash/RAM usage and Int8 inference latency.

Basic Info

Authors: Tzu-Hsuan Lin; Chien-Ta Chang; Alan Putranto

Year: 2024

Title: Tiny machine learning empowers climbing inspection robots for real-time multiobject bolt-defect detection 

Source: Engineering Applications of Artificial Intelligence, 133, 108618

Type: Experimental

Problem & Context

Task: Object detection

Objective: Real-time detection of normal, loose, and missing bolts using TinyML integrated with a magnetic climbing inspection robot.

Application domain: Steel structure inspection / bolt-defect detection

Scenario: Embedded, edge, robotic inspection, MCU-based on-device inference

TinyML relevance: Yes

TinyML justification: The paper explicitly targets TinyML object detection on a microcontroller-based climbing robot with reported Flash, RAM, quantization, latency, and power-related constraints.

Model / Method

Model: FOMO

Architecture family: CNN

Techniques: INT8 quantization, depthwise separable convolution, width multiplier, inverted bottleneck residual modules, lightweight FOMO object detection

Framework: Edge Impulse

Training type: Not reported

Inference type: On-device

Hardware

Device: Arduino Nicla Vision integrated into a magnetic climbing inspection robot

Hardware type: MCU

Processor / microcontroller: STM32H747AII6 dual Arm Cortex-M7/M4

Clock frequency: Cortex-M7 up to 480 MHz; Cortex-M4 up to 240 MHz

SRAM / RAM: 1 MB RAM

Flash / ROM / Storage: 2 MB Flash; 16 MB QSPI Flash

Power consumption: 374 μA in deep sleep mode; 105 mA during active image capture

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Processing power, memory, power consumption, battery operation, latency, bandwidth, communication, model size

Dataset

Name: Not reported

Type: Private

Dataset size: 914 images; 575 training images; 144 validation images; 195 testing images

Number of classes: 3

Input resolution: 240 × 240 image capture; resized to 96 × 96 for FOMO inference

Data modality: RGB image

Metrics

Accuracy: 82% average system accuracy

mAP: Not reported

Precision: 0.57–0.89; average 0.77

Recall: 0.67–0.87; average 0.76

F1-score: Average 0.75 across field scenarios; FOMO Int8 75.6%; FOMO Float32 76.2%

Latency: FOMO Int8 86 ms; FOMO Float32 142 ms

FPS: Not reported

Throughput: Not reported

Model size: FOMO Int8 0.072 MB Flash usage; FOMO Float32 0.096 MB Flash usage

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: FOMO Int8 239.1 KB; FOMO Float32 893.8 KB

Flash usage: FOMO Int8 0.072 MB; FOMO Float32 0.096 MB

Energy per inference: Not reported

Power consumption: 374 μA in deep sleep mode; 105 mA during active image capture

Optimization

Techniques used: INT8 quantization, FOMO lightweight architecture, depthwise separable convolution, width multiplier, inverted bottleneck residual modules

Quantization: INT8

Pruning: No

Knowledge distillation: No

Compression method: INT8 quantization and reduced-width lightweight CNN architecture

Hardware-specific optimization: FOMO optimized for edge computing on microcontrollers

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: 239.1 KB RAM usage for FOMO Int8; 893.8 KB RAM usage for FOMO Float32

Flash usage reported: 0.072 MB for FOMO Int8; 0.096 MB for FOMO Float32

Model size reported: Yes, through Flash usage

Energy per inference reported: Not reported

Latency on target device reported: 86 ms for FOMO Int8; 142 ms for FOMO Float32

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No offloaded inference reported; RTSP is used to stream annotated output images to the user

Candidate for Strict TinyML: Yes

Reason: The system deploys an INT8 FOMO object detection model fully on an Arduino Nicla Vision STM32H747 Cortex-M microcontroller with reported RAM, Flash, latency, and power-related constraints.

Benchmarking / Standardization

Benchmark used: Private bolt-defect dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: MobileNetV2 SSD FPN-Lite and YOLOv5-S

Comparison with previous works: Yes, visual-based loose bolt detection methods from 2015 to 2023

Reproducibility artifacts available: Dataset on request

Results

Summary: The FOMO Int8 model achieved 75.6% F1-score with 0.072 MB Flash usage, 239.1 KB RAM usage, and 86 ms inference time on the target MCU. Across 10 field scenarios, the system achieved average precision of 0.77, recall of 0.76, F1-score of 0.75, and accuracy of 0.82.

Limitations

The paper reports limitations related to microcontroller performance and image resolution, misclassification of loose and normal bolts, limited defect categories, and recognition challenges when object features are unclear or partially visible.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a TinyML-based real-time multiobject bolt-defect detection system using Edge Impulse FOMO deployed on an Arduino Nicla Vision microcontroller integrated into a magnetic climbing inspection robot.

| Paper      | Year | Task             | Model | Technique         | Device               | Dataset                     | Main Metric    | Latency | Model Size | SRAM/RAM | Flash    | Energy | Framework    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | ---------------- | ----- | ----------------- | -------------------- | --------------------------- | -------------- | ------- | ---------- | -------- | -------- | ------ | ------------ | -------- | ------------- | ------------- |
| Lin et al. | 2024 | Object Detection | FOMO  | INT8 quantization | Arduino Nicla Vision | Private bolt-defect dataset | F1-score 75.6% | 86 ms   | 0.072 MB   | 239.1 KB | 0.072 MB | N/A    | Edge Impulse | PTQ      | N/A           | Yes           |
