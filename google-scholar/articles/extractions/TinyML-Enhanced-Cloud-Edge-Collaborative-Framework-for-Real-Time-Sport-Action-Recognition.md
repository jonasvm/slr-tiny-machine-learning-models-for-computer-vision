Paper ID: TinyML-Enhanced-Cloud-Edge-Collaborative-Framework-for-Real-Time-Sport-Action-Recognition

TinyML classification: Near-TinyML — The paper uses TinyML-oriented edge vision optimization but does not explicitly report MCU-class deployment or microcontroller-level constraints.

Basic Info

Authors: Chao Yan

Year: 2025

Title: TinyML-Enhanced Cloud-Edge Collaborative Framework for Real-Time Sport Action Recognition

Source: Internet Technology Letters, 8:e70100 

Type: Experimental

Problem & Context

Task: Classification / action recognition

Objective: Real-time sports action recognition with reduced latency and energy consumption using a TinyML-enhanced cloud-edge collaborative framework.

Application domain: Sports analytics, athletic performance monitoring, athlete biomechanical analysis, AI-powered virtual coaching.

Scenario: Cloud-edge, edge, wearable sensor networks, video analytics.

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained edge inference with lightweight MobileNet, pruning, quantization, latency, and energy evaluation, but does not report MCU-class deployment or microcontroller-level constraints.

Model / Method

Model: Pruned MobileNetV3-Sport with temporal motion encoding.

Architecture family: CNN

Techniques: Tensor decomposition, pruning, quantization, knowledge distillation, federated training, WebRTC-based streaming, differential model updates.

Framework: WebRTC; ML deployment framework not reported.

Training type: Not reported

Inference type: Hybrid

Hardware

Device: Edge devices / smart edge sensor devices.

Hardware type: Other

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: 0.30 J

Execution without full OS: Not reported

Fully on-device inference: No

Constraints mentioned: Latency, energy, computation, resource constraints, communication, network dynamics.

Dataset

Name: Sports-5K

Type: Private

Dataset size: 5,000 video clips

Number of classes: 10 sports actions in setup; abstract mentions 23 athletic disciplines.

Input resolution: Not reported

Data modality: Video

Metrics

Accuracy: 91.5%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 40 ms

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: 0.30 J

Power consumption: Not reported

Optimization

Techniques used: Tensor decomposition, pruning, quantization, knowledge distillation, differential model updates.

Quantization: INT8

Pruning: Yes

Knowledge distillation: Yes

Compression method: Tensor decomposition, pruning, quantization.

Hardware-specific optimization: Not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: 0.30 J

Latency on target device reported: 40 ms, but target device is not specified.

Runs without full operating system: Not reported

Fully on-device inference: No

Communication required during inference: Yes

Candidate for Strict TinyML: No

Reason: The paper does not report MCU-class hardware, SRAM/Flash constraints, TensorFlow Lite Micro, bare-metal/RTOS execution, or fully on-device inference.

Benchmarking / Standardization

Benchmark used: Sports-5K

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: VGG16, ViT, EfficientNet, ResNet-series models.

Comparison with previous works: Yes

Reproducibility artifacts available: dataset upon request

Results

Summary: The proposed TinyML method achieved 91.5% recognition accuracy, 40 ms latency, and 0.30 J per inference on Sports-5K. It reduced latency by around 30% compared with existing solutions and outperformed VGG16, ViT, and EfficientNet in the reported metrics.

Limitations

Not reported; future work mentions deeper WebRTC-based streaming, accelerated model updates, fairness, and bias mitigation.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

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

This paper proposes a TinyML-enhanced cloud-edge collaborative framework for real-time sports action recognition using pruned MobileNetV3-Sport with temporal motion encoding and edge-oriented optimization.

| Paper      | Year | Task                                | Model                    | Technique                                                           | Device       | Dataset   | Main Metric     | Latency | Model Size | SRAM/RAM | Flash | Energy           | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | ----------------------------------- | ------------------------ | ------------------------------------------------------------------- | ------------ | --------- | --------------- | ------- | ---------- | -------- | ----- | ---------------- | --------- | -------- | ------------- | ------------- |
| Yan et al. | 2025 | Classification / action recognition | Pruned MobileNetV3-Sport | Tensor decomposition, pruning, quantization, knowledge distillation | Edge devices | Sports-5K | Accuracy: 91.5% | 40 ms   | N/A        | N/A      | N/A   | 0.30 J/inference | WebRTC    | INT8     | N/A           | No            |
