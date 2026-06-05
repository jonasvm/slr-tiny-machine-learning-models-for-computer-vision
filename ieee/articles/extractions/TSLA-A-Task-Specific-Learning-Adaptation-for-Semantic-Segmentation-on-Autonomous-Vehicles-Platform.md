Paper ID: TSLA-A-Task-Specific-Learning-Adaptation-for-Semantic-Segmentation-on-Autonomous-Vehicles-Platform

TinyML classification: Near-TinyML — targets embedded autonomous-vehicle edge hardware, but deployment is on NVIDIA DRIVE PX 2 rather than explicit MCU-class hardware.

Basic Info

Authors: Jun Liu, Zhenglun Kong, Pu Zhao, Weihao Zeng, Hao Tang, Xuan Shen, Changdi Yang, Wenbin Zhang, Geng Yuan, Wei Niu, Xue Lin, Yanzhi Wang 

Year: 2025

Title: TSLA: A Task-Specific Learning Adaptation for Semantic Segmentation on Autonomous Vehicles Platform 

Source: IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems

Type: Methodological

Problem & Context

Task: Segmentation

Objective: Customize semantic segmentation networks according to autonomous-driving hardware resources, computational budgets, and task-specific scenarios.

Application domain: Autonomous driving

Scenario: Embedded autonomous vehicle platform / edge autonomous system

TinyML relevance: Partial

TinyML justification: The paper targets embedded edge deployment on NVIDIA DRIVE PX 2 under computational-budget constraints, but does not target MCU-class TinyML hardware.

Model / Method

Model: TSLA semantic segmentation network based on MobileNetV4 backbone

Architecture family: CNN

Techniques: Width multiplier, classifier depth adjustment, classifier kernel adjustment, Bayesian optimization, hardware-aware computational-budget search

Framework: NVIDIA DIGITS

Training type: Not reported

Inference type: On-device

Hardware

Device: NVIDIA DRIVE PX 2

Hardware type: SoC / GPU / embedded autonomous-vehicle platform

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Compute budget, FPS, accuracy, memory, energy efficiency, scalability, latency/real-time processing

Dataset

Name: CamVid; Cityscapes

Type: Public

Dataset size: Not reported

Number of classes: 7 classes for Parking and Urban scenarios; 2 classes for Rural scenario

Input resolution: Not reported

Data modality: Camera images / video frames

Metrics

Accuracy: Not reported

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: CamVid: 61.20–108.6 FPS for TSLA variants; Cityscapes: 60.56–118.23 FPS for TSLA variants

Throughput: DRIVE PX 2 target handles up to 12 cameras; scenario settings include 15 FPS or 30 FPS per camera

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: TSLA model range reported as approximately 0.52–2.17 GFLOPs; scenario configurations require 69.78, 117.74, and 299.64 GigaOps/s

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Three-tier model scaling using width multiplier, classifier depth, and classifier kernel; Bayesian optimization with surrogate modeling under computational budgets

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Architectural scaling and computational-budget-aware configuration search

Hardware-specific optimization: Yes, optimized for DRIVE PX 2 computational budgets and autonomous-driving scenarios

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets an embedded NVIDIA DRIVE PX 2 autonomous-driving platform, not MCU-class or bare-metal/RTOS TinyML deployment.

Benchmarking / Standardization

Benchmark used: CamVid; Cityscapes

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CamVid; Cityscapes

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: TSLA achieves real-time semantic segmentation with low GFLOPs on CamVid and Cityscapes. The best reported TSLA-Large result reaches 78.80 Test IOU on Cityscapes and 78.6 Test IOU on CamVid, while smaller variants trade accuracy for higher FPS.

Limitations

Memory constraints increase as the model scales; larger parameter counts may reduce energy efficiency and increase optimization cost. The authors identify pruning, quantization, low-precision computing, and dynamic voltage scaling as future directions.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a task-specific semantic segmentation adaptation method that scales MobileNetV4-based models using width multiplier, classifier depth, classifier kernel, and Bayesian optimization to satisfy autonomous-driving edge hardware computational budgets.

| Paper      | Year | Task         | Model              | Technique                                                    | Device            | Dataset            | Main Metric                                     | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework     | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | ------------ | ------------------ | ------------------------------------------------------------ | ----------------- | ------------------ | ----------------------------------------------- | ------- | ---------- | -------- | ----- | ------ | ------------- | -------- | ------------- | ------------- |
| Liu et al. | 2025 | Segmentation | TSLA / MobileNetV4 | Hardware-aware architectural scaling + Bayesian optimization | NVIDIA DRIVE PX 2 | CamVid; Cityscapes | Cityscapes Test IOU 78.80; CamVid Test IOU 78.6 | N/A     | N/A        | N/A      | N/A   | N/A    | NVIDIA DIGITS | N/A      | None          | No            |
