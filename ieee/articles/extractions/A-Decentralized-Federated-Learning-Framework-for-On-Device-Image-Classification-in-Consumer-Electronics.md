Paper ID: A-Decentralized-Federated-Learning-Framework-for-On-Device-Image-Classification-in-Consumer-Electronics

TinyML classification: Near-TinyML — Relevant edge/on-device vision work, but no explicit MCU-class deployment or MCU-level constraints are reported.

## Basic Info

Authors: Imandi Raju, Abhishek Hazra, V. Siddhartha, B. N. Pavan Kumar

Year: 2025

Title: A Decentralized Federated Learning Framework for On-Device Image Classification in Consumer Electronics 

Source: IEEE Transactions on Consumer Electronics, Vol. 71, No. 3, August 2025

Type: Methodological

## Problem & Context

Task: Classification

Objective: Enable efficient, privacy-preserving, real-time on-device image classification using decentralized federated learning and lightweight deep learning models.

Application domain: Consumer electronics, UAV-based disaster response, surveillance, environmental monitoring

Scenario: Edge, fog-enabled UAV-as-a-Service, consumer electronics, on-device learning

TinyML relevance: Partial

TinyML justification: The paper targets on-device image classification on resource-constrained consumer electronics and UAV/fog devices, but does not report MCU-class deployment, bare-metal execution, TensorFlow Lite Micro, or SRAM/Flash constraints.

## Model / Method

Model: DFLNet

Architecture family: CNN

Techniques: Depthwise separable convolutions, skip connections, residual blocks, sparse mesh decentralized federated learning, transfer learning for baseline models

Framework: Keras

Training type: From scratch for DFLNet; transfer learning for baseline CNN models

Inference type: On-device

## Hardware

Device: Heterogeneous UAVs and fog-enabled consumer electronics devices in FU-Serve platform

Hardware type: GPU for training/evaluation infrastructure; fog/edge consumer electronics for target scenario

Processor / microcontroller: Intel Core i9 CPU for training/evaluation; not reported for deployment device

Clock frequency: 5 GHz for Intel Core i9 CPU

SRAM / RAM: 64 GB RAM for training/evaluation infrastructure; deployment RAM not reported

Flash / ROM / Storage: 500 GB SSD and 4 TB HDD for training/evaluation infrastructure; deployment storage not reported

Power consumption: Energy consumption analyzed across network topologies; exact power value not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Limited processing power, memory constraints, energy constraints, latency, privacy, communication overhead, synchronization overhead

## Dataset

Name: AIDER; NDD

Type: Public

Dataset size: Not reported

Number of classes: 5

Input resolution: 224 × 224 × 3

Data modality: RGB image

## Metrics

Accuracy: DFLNet: 96.90% on NDD; 97.82% on AIDER

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Class-specific F1-score reported in Table II; aggregate F1-score not reported

Latency: DFLNet inference time: 0.0253 s on NDD; 0.0233 s on AIDER

FPS: DFLNet: 39.50 FPS on NDD; 42.95 FPS on AIDER

Throughput: Not reported

Model size: 0.67 MB

Parameters: 0.06M

MACs / FLOPs: Not reported

RAM usage: Memory usage reported as 0.67 MB for DFLNet

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Energy consumption analyzed using PowerJoular, PowerTOP, and Perf; exact power value not reported

## Optimization

Techniques used: Lightweight CNN design, depthwise separable convolutions, residual/skip connections, sparse mesh topology for decentralized aggregation

Quantization: Not reported

Pruning: No

Knowledge distillation: No

Compression method: Depthwise separable convolutions and lightweight architecture design

Hardware-specific optimization: Sparse mesh topology optimized for energy efficiency and communication overhead in heterogeneous UAV/fog devices

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 0.67 MB

Energy per inference reported: Not reported

Latency on target device reported: 0.0253 s on NDD; 0.0233 s on AIDER

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports lightweight on-device image classification for edge/fog UAV devices, but does not provide MCU-class deployment, SRAM/Flash limits, bare-metal execution, or TensorFlow Lite Micro evidence.

## Benchmarking / Standardization

Benchmark used: AIDER and NDD disaster image datasets

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet used for pretrained baseline CNN models

Comparison with baseline models: Yes, compared with ResNet, InceptionV3, VGG16, DenseNet121, EfficientNetB0, NASNetMobile, MobileNetV2, MobileNetV3, and Modified MobileNetV2

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

## Results

Summary: DFLNet achieves 97.82% accuracy on AIDER and 96.90% on NDD with 0.06M parameters and 0.67 MB memory. It reports 0.0233 s inference time and 42.95 FPS on AIDER, outperforming larger models in efficiency while maintaining competitive accuracy.

Limitations: Future work aims to expand DFLNet to ARM-based edge devices and enhance multi-modal data processing capabilities.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Partial

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Partial

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes a decentralized federated learning framework with a lightweight CNN model, DFLNet, for privacy-preserving and energy-efficient on-device image classification in fog-enabled consumer electronics and UAV environments.

| Paper       | Year | Task           | Model  | Technique                                                  | Device                           | Dataset    | Main Metric               | Latency           | Model Size | SRAM/RAM             | Flash | Energy                           | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | -------------- | ------ | ---------------------------------------------------------- | -------------------------------- | ---------- | ------------------------- | ----------------- | ---------- | -------------------- | ----- | -------------------------------- | --------- | -------- | ------------- | ------------- |
| Raju et al. | 2025 | Classification | DFLNet | Depthwise separable CNN + decentralized federated learning | Heterogeneous UAV/fog CE devices | AIDER; NDD | Accuracy: 97.82% on AIDER | 0.0233 s on AIDER | 0.67 MB    | 0.67 MB memory usage | N/A   | Energy analyzed, exact value N/A | Keras     | N/A      | None          | No            |
