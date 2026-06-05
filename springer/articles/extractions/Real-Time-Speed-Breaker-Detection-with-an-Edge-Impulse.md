Paper ID: Real-Time-Speed-Breaker-Detection-with-an-Edge-Impulse

TinyML classification: Strict TinyML — The paper explicitly uses Arduino Nano 33 BLE, TinyML/Edge Impulse, and an embedded camera-based real-time vision deployment.

## Basic Info

Authors: S. Manjula; M. Swarna Sudha; C. A. Yogaraja; C. Muthuaruna

Year: 2024

Title: Real-Time Speed Breaker Detection with an Edge Impulse

Source: SN Computer Science, 5:766 

Type: Experimental

## Problem & Context

Task: Classification / image-based speed breaker detection

Objective: Detect marked and unmarked speed breakers in real time and alert drivers.

Application domain: Road safety / driver-assistance systems

Scenario: Embedded, edge, vehicle-mounted system

TinyML relevance: Yes

TinyML justification: The paper explicitly uses Arduino Nano 33 BLE, TinyML, Edge Impulse, and ESP32 camera hardware for real-time speed breaker detection and alert generation.

## Model / Method

Model: MobileNetV2 96×96 0.35 model

Architecture family: CNN

Techniques: Transfer learning, data augmentation, grayscale conversion, DSP preprocessing, MobileNetV2 width multiplier 0.35

Framework: Edge Impulse

Training type: Transfer learning

Inference type: Hybrid

## Hardware

Device: Arduino Nano 33 BLE, ESP32 camera module, ultrasonic sensor, GPS receiver, piezo buzzer

Hardware type: MCU / Other

Processor / microcontroller: Arduino Nano 33 BLE; ESP32 camera module

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Real-time detection, timely driver alerts, low-cost portable deployment, challenging lighting and road conditions, embedded/mobile computational efficiency

## Dataset

Name: Not reported

Type: Private

Dataset size: Around 3200 images

Number of classes: 2

Input resolution: 96×96

Data modality: Road-surface images converted to grayscale

## Metrics

Accuracy: 92%

mAP: Not reported

Precision: 82%

Recall: 94%

F1-score: 89.2%

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

Techniques used: Transfer learning, data augmentation, grayscale preprocessing, DSP preprocessing, MobileNetV2 width multiplier 0.35

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: MobileNetV2 width multiplier 0.35

Hardware-specific optimization: Not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: The paper reports connection with Edge Impulse software for live classification, but does not clearly specify whether communication is required during final deployment.

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets Arduino Nano 33 BLE and TinyML-based embedded vision deployment, but does not report MCU memory, latency, model size, or energy measurements.

## Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: YOLOv4 architecture, RNN, KNN and Random Forest tree

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset available upon request

## Results

Summary: The MobileNetV2 96×96 0.35 model achieved 92% accuracy, 82% precision, 94% recall, and 89.2% F1-score for speed breaker detection. It outperformed the compared YOLOv4, RNN, and KNN + Random Forest methods in reported accuracy.

Limitations: Recall varies across epochs, the false negative rate is 17.89%, and memory, latency, model size, and energy results are not reported.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

## Contribution

This paper proposes a TinyML/Edge Impulse-based real-time speed breaker detection and driver alert system using MobileNetV2 96×96 0.35 with Arduino Nano 33 BLE and ESP32 camera hardware.

| Paper          | Year | Task           | Model                  | Technique                                           | Device                             | Dataset                                                     | Main Metric  | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | -------------- | ---------------------- | --------------------------------------------------- | ---------------------------------- | ----------------------------------------------------------- | ------------ | ------- | ---------- | -------- | ----- | ------ | ------------ | -------- | ------------- | ------------- |
| Manjula et al. | 2024 | Classification | MobileNetV2 96×96 0.35 | Transfer learning; data augmentation; width scaling | Arduino Nano 33 BLE + ESP32 camera | Private speed-breaker/plain-road images, around 3200 images | Accuracy 92% | N/A     | N/A        | N/A      | N/A   | N/A    | Edge Impulse | N/A      | None          | Yes           |
