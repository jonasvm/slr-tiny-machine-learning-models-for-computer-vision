Paper ID: IoT-based-real-time-object-detection-system-for-crop-protection-and-agriculture-field-security 

TinyML classification: Near-TinyML — Uses embedded/IoT hardware, but object detection is processed on Linux/cloud/server infrastructure rather than MCU-class on-device inference.

Basic Info

Authors: Priya Singh; Rajalakshmi Krishnamurthi

Year: 2024

Title: IoT-based real-time object detection system for crop protection and agriculture field security

Source: Journal of Real-Time Image Processing, 21:106

Type: Experimental

Problem & Context

Task: Object detection

Objective: Detect and classify humans or animals roaming around agricultural fields and notify farmers in real time.

Application domain: Agriculture field security and crop protection

Scenario: IoT, embedded, edge/cloud-assisted, mobile notification

TinyML relevance: Partial

TinyML justification: The system uses ESP32-CAM, Raspberry Pi, LoRa, low-power IoT devices, latency, and power analysis, but object detection inference is transmitted to a Linux/cloud server rather than executed fully on MCU-class hardware.

Model / Method

Model: Ad-YOLOv8; compared with YOLOv8, YOLOv7, and YOLOv6

Architecture family: CNN

Techniques: Hyperparameter optimization, reduced input resolution, reduced number of classes, reduced filters/epochs, CSP/C2f modules, SPP, attention-based pyramid network, CIoU/DFL losses, non-maximum suppression

Framework: Not reported

Training type: Transfer learning / fine-tuning

Inference type: Offloaded / hybrid

Hardware

Device: Environment 1: HC-SR04, Raspberry Pi 3B/3B+, Pi-Cam/SJ Cam, Linux server, FCM, Android 9.0; Environment 2: HC-SR04, ESP32-CAM, LoRa, Linux/cloud server, FCM, Android 9.0

Hardware type: MCU / SoC / CPU / GPU / Other

Processor / microcontroller: Raspberry Pi 3B+ with 1.4 GHz quad-core ARM Cortex-A53; ESP32; Linux server with Intel Core i5 8th Gen and Nvidia K80/P4/T4/P100 GPUs

Clock frequency: Raspberry Pi: 1.4 GHz; ESP32: 80–240 MHz; Linux server CPU: 1.60–1.80 GHz

SRAM / RAM: Raspberry Pi: 1 GB LPDDR2 SDRAM; ESP32: 520 KB SRAM; Linux server: 8 GB primary storage reported

Flash / ROM / Storage: Raspberry Pi: MicroSD card; ESP32: 4 MB flash memory

Power consumption: Environment 1 average current: 405.81 mA; Environment 2 average current: 42.37 mA; Environment 1 modes: idle 268 mA, data collection 665 mA, transmission 488 mA; Environment 2 modes: idle 24 mA, data collection 46 mA, transmission 208 mA

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: No

Constraints mentioned: Power consumption, latency, communication, compute, real-time performance, limited ESP32 resources, false positives, battery depletion

Dataset

Name: Custom 11-class dataset

Type: Not reported

Dataset size: Not reported

Number of classes: 11

Input resolution: 416 × 416

Data modality: RGB image/frame with ultrasonic sensor trigger

Metrics

Accuracy: 96%; Ad-YOLOv8 test cases: 99% for one object and 98%, 76% for two objects

mAP: 96%

Precision: 97%

Recall: 96%

F1-score: Not reported

Latency: Ad-YOLOv8 model processing: 0.82 s for one object and 0.81 s for two objects; Environment 1 total processing: 10 s and 6 s; Environment 2 total processing: 7 s and 5 s

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Environment 1 average current: 405.81 mA; Environment 2 average current: 42.37 mA

Optimization

Techniques used: Hyperparameter optimization, input resizing to 416 × 416, reduced class count to 11, filter reduction, epoch selection, CSP/C2f modules, SPP, attention-based pyramid network, NMS

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: System-level use of LoRa and low-power IoT devices; no model-level hardware-specific optimization reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Ad-YOLOv8 processing time reported as 0.82 s and 0.81 s; end-to-end environment processing time reported as 10/6 s for Raspberry Pi environment and 7/5 s for ESP32/LoRa environment

Runs without full operating system: No

Fully on-device inference: No

Communication required during inference: Yes

Candidate for Strict TinyML: No

Reason: The ESP32/Raspberry Pi nodes capture and transmit images, but object detection inference is performed on a Linux/cloud server, with no MCU-class on-device inference or model memory footprint reported.

Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes; YOLOv8, YOLOv7, and YOLOv6

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset available if required; code/model not reported

Results

Summary: Ad-YOLOv8 achieved 97% precision, 96% recall, 96% mAP, and 96% accuracy. The ESP32/LoRa environment had lower average current consumption than the Raspberry Pi environment and lower total processing times in the reported embedded-system comparison.

Limitations

False alarms may occur due to wind or small animals. The system requires communication with Linux/cloud infrastructure for inference, and future work mentions optimization for dense networks, node/link failures, dynamic network conditions, herds of animals, and heavy image-processing tasks.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an IoT-based crop-protection system that combines ultrasonic sensing, ESP32-CAM/Raspberry Pi image capture, LoRa communication, server-side Ad-YOLOv8 object detection, Firebase Cloud Messaging, and an Android application for real-time farmer alerts.

| Singh et al. | 2024 | Object Detection | Ad-YOLOv8 | Hyperparameter and architecture optimization | ESP32-CAM / Raspberry Pi + Linux server | Custom 11-class dataset | mAP 96% | 0.81–0.82 s model; 5–7 s ESP32/LoRa pipeline | N/A | ESP32 520 KB SRAM; Raspberry Pi 1 GB RAM | ESP32 4 MB Flash; Raspberry Pi MicroSD | N/A | Arduino IDE / FCM / Web server API | N/A | None | No |
