Paper ID: IoT-based-real-time-object-detection-system-for-crop-protection-and-agriculture-field-security

TinyML classification: Near-TinyML — Uses embedded/IoT hardware including ESP32-CAM and Raspberry Pi, but object detection is processed on a Linux/cloud server rather than deployed as MCU-class inference.

Basic Info

Authors: Priya Singh; Rajalakshmi Krishnamurthi

Year: 2024

Title: IoT-based real-time object detection system for crop protection and agriculture field security

Source: Journal of Real-Time Image Processing, 21:106 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Detect and classify humans and animals in agricultural fields and notify farmers in near real time.

Application domain: Agriculture, crop protection, field security

Scenario: IoT, embedded, edge/server-assisted, mobile notification

TinyML relevance: Partial

TinyML justification: The system uses low-power IoT devices including ESP32-CAM, Raspberry Pi, ultrasonic sensors, and LoRa, but object detection inference is transmitted to and processed on a Linux/cloud server rather than fully on MCU-class hardware.

Model / Method

Model: Ad-YOLOv8; YOLOv8, YOLOv7, and YOLOv6 used as baselines

Architecture family: CNN

Techniques: YOLOv8 hyperparameter/model adaptation, reduced input resolution, reduced number of classes, adjusted filters, learning rate, batch size, and epochs

Framework: Not reported

Training type: Fine-tuning

Inference type: Offloaded

Hardware

Device: Raspberry Pi 3B/3B+ with Pi Camera; ESP32-CAM with LoRa; ultrasonic sensor HC-SR04; Linux server; Android application with Firebase Cloud Messaging

Hardware type: MCU / CPU / SoC / Other

Processor / microcontroller: Raspberry Pi 3B+ quad-core ARM Cortex-A53; ESP32; Linux server with Intel Core i5 8th Gen and Nvidia K80/P4/T4/P100 GPUs

Clock frequency: Raspberry Pi 1.4 GHz; ESP32 80–240 MHz; Linux server 1.60–1.80 GHz

SRAM / RAM: Raspberry Pi 1 GB LPDDR2 SDRAM; ESP32 520 KB SRAM

Flash / ROM / Storage: Raspberry Pi MicroSD card; ESP32 4 MB Flash memory

Power consumption: Environment 1 average current consumption 405.81 mA; Environment 2 average current consumption 42.37 mA

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: No

Constraints mentioned: Power, latency, communication, compute, real-time operation, limited ESP32 resources

Dataset

Name: Not reported

Type: Not reported

Dataset size: Not reported

Number of classes: 11

Input resolution: 416 × 416

Data modality: Sensor + image

Metrics

Accuracy: 96%

mAP: 96%

Precision: 97%

Recall: 96%

F1-score: Not reported

Latency: Ad-YOLOv8 object detection processing time 0.82 s for test case 1 and 0.81 s for test case 2; end-to-end processing time 10 s and 6 s in Raspberry Pi environment; 7 s and 5 s in ESP32/LoRa environment

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Environment 1 average current consumption 405.81 mA; Environment 2 average current consumption 42.37 mA

Optimization

Techniques used: Ad-YOLOv8 configuration optimization using 416 × 416 input size, batch size 64, learning rate 0.001, 11 classes, reduced filters, reduced epochs, and adjusted YOLOv8 architecture components

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes, but not MCU on-device inference latency

Runs without full operating system: No

Fully on-device inference: No

Communication required during inference: Yes

Candidate for Strict TinyML: No

Reason: The ESP32-CAM and Raspberry Pi capture and transmit images, while object detection inference is processed on a Linux/cloud server, so the system does not demonstrate MCU-class fully on-device inference.

Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: YOLOv6, YOLOv7, YOLOv8

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: Ad-YOLOv8 achieved 97% precision, 96% recall, 96% mAP, and 96% accuracy. The ESP32/LoRa environment showed lower average current consumption than the Raspberry Pi environment.

Limitations

Future work mentions opportunities for optimization under dense networks, node and link failures, dynamic network conditions, herds of animals, heavy image processing tasks, and heuristic, genetic, or nature-inspired optimization.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an IoT-based crop protection system that combines ultrasonic sensing, Raspberry Pi or ESP32-CAM image capture, LoRa communication, server-side Ad-YOLOv8 object detection, Firebase Cloud Messaging, and Android notifications for agricultural field security.

| Paper        | Year | Task             | Model     | Technique                                              | Device                                    | Dataset | Main Metric | Latency                                            | Model Size | SRAM/RAM                                    | Flash                                  | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ---------------- | --------- | ------------------------------------------------------ | ----------------------------------------- | ------- | ----------- | -------------------------------------------------- | ---------- | ------------------------------------------- | -------------------------------------- | ------ | --------- | -------- | ------------- | ------------- |
| Singh et al. | 2024 | Object Detection | Ad-YOLOv8 | YOLOv8 hyperparameter/model configuration optimization | Raspberry Pi 3B+/ESP32-CAM + Linux server | N/A     | mAP 96%     | 0.81–0.82 s detection; 5–7 s ESP32/LoRa end-to-end | N/A        | 520 KB SRAM ESP32; 1 GB LPDDR2 Raspberry Pi | 4 MB ESP32 Flash; Raspberry Pi MicroSD | N/A    | N/A       | N/A      | None          | No            |
