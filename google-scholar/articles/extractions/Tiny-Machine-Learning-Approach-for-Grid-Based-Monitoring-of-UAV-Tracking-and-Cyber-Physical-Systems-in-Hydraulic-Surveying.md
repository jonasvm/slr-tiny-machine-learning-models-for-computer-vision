Paper ID: Tiny-Machine-Learning-Approach-for-Grid-Based-Monitoring-of-UAV-Tracking-and-Cyber-Physical-Systems-in-Hydraulic-Surveying

TinyML classification: Near-TinyML — it explicitly uses TinyML for UAV vision tracking, but does not provide clear MCU-class deployment, memory, latency, or energy constraints.

## Basic Info

Authors: Ajmeera Kiran; Janjhyam Venkata Naga Ramesh; Aadam Quraishi; Jagdish Chandra Patni; Ismail Keshta; Haewon Byeon; Mohan Raparthi; Mukta Sandhu; Mukesh Soni

Year: 2025

Title: Tiny Machine Learning Approach for Grid-Based Monitoring of UAV Tracking and Cyber-Physical Systems in Hydraulic Surveying

Source: IEEE Transactions on Intelligent Transportation Systems, Vol. 26, No. 9, September 2025

Type: Experimental

## Problem & Context

Task: Object detection and tracking

Objective: Improve UAV identification, locking, and tracking for hydraulic surveying and mapping using grid mapping, PTZ camera control, radar information, and TinyML-based image recognition.

Application domain: Hydraulic engineering surveying and mapping with UAVs

Scenario: Cyber-physical UAV monitoring system with vehicle-mounted radar and PTZ camera

TinyML relevance: Partial

TinyML justification: The paper explicitly frames the method as TinyML-based and applies it to UAV image recognition and tracking, but it does not report MCU-class deployment or strict TinyML hardware constraints.

## Model / Method

Model: Improved RetinaNet with ResNet152, MobileNet-based depthwise separable convolution, image preprocessing, radar-image fusion, grid mapping, and UAV target tracking

Architecture family: CNN

Techniques: Improved RetinaNet, image interpolation, median filtering, MobileNet depthwise separable convolution, radar-image fusion, PTZ grid target locking, 3D spatial grid division

Framework: Python for UAV recognition testing; C# for grid-based water conservation system testing

Training type: Not reported

Inference type: Not reported

## Hardware

Device: Vehicle-mounted platform with low-altitude radar and PTZ camera

Hardware type: Other

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Radar scanning intervals, fuzzy collected images, unstable UAV tracking, power supply limitation of UAV flight endurance

## Dataset

Name: Not reported

Type: Not reported

Dataset size: Not reported

Number of classes: 3 image categories reported

Input resolution: Not reported

Data modality: Camera images/video and radar scanning information

## Metrics

Accuracy: Not reported

mAP: Not reported

Precision: 97.0% on original images; 96.0% on interference images for the proposed method

Recall: 97.3% on original images; 96.3% on interference images for the proposed method

F1-score: 97.15% on original images; 96.15% on interference images for the proposed method

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Improved RetinaNet, image preprocessing, ResNet152 feature extraction, MobileNet depthwise separable convolution, radar-image fusion, and grid-based PTZ target locking

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: MobileNet depthwise separable convolution is used to accelerate and compress ResNet152

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper uses TinyML terminology but does not report MCU-class deployment, TFLM/CMSIS-NN implementation, SRAM, flash, model size, energy, or target-device latency.

## Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: YOLO, SSD, and RetinaNet

Comparison with previous works: Image-only target recognition and tracking method; radar target tracking method

Reproducibility artifacts available: Not reported

## Results

Summary: The proposed method achieved higher precision, recall, and F1-score than YOLO, SSD, and RetinaNet for UAV recognition under both original and interference image conditions. The highest reported F1-score was 97.15% on original images and 96.15% on interference images.

Limitations: The paper states that UAV flight endurance is limited by battery power and that the method cannot measure physical properties such as temperature, humidity, wind speed, and direction.

## Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Partial

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes a grid-based TinyML-oriented UAV tracking method that combines radar scanning, PTZ camera locking, image recognition, image correction, and target monitoring for hydraulic surveying and mapping.

| Paper        | Year | Task                          | Model                                       | Technique                                                                    | Device                                  | Dataset                  | Main Metric                                                 | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ----------------------------- | ------------------------------------------- | ---------------------------------------------------------------------------- | --------------------------------------- | ------------------------ | ----------------------------------------------------------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Kiran et al. | 2025 | Object Detection and Tracking | Improved RetinaNet with ResNet152/MobileNet | Depthwise separable convolution, image preprocessing, and radar-image fusion | Vehicle-mounted radar/PTZ camera system | Custom UAV image dataset | F1-score 97.15% original images; 96.15% interference images | N/A     | N/A        | N/A      | N/A   | N/A    | Python/C# | N/A      | None          | No            |
