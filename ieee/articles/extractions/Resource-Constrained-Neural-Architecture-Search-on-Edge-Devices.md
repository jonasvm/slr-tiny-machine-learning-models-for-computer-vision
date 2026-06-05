Paper ID: Resource-Constrained-Neural-Architecture-Search-on-Edge-Devices 

TinyML classification: Near-TinyML — evaluated on Jetson Nano edge hardware without explicit MCU-class deployment evidence.

## Basic Info

Authors: Bo Lyu, Hang Yuan, Longfei Lu, Yunye Zhang

Year: 2022

Title: Resource-Constrained Neural Architecture Search on Edge Devices

Source: IEEE Transactions on Network Science and Engineering, Vol. 9, No. 1

Type: Methodological

## Problem & Context

Task: Classification

Objective: Search Pareto-optimal neural architectures for edge devices by jointly considering accuracy, parameters, memory consumption, and real-world latency.

Application domain: Computer vision / image recognition

Scenario: Edge computing, embedded edge device

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained edge-device inference on Jetson Nano, but does not report MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, SRAM/Flash-constrained deployment.

## Model / Method

Model: Multi-objective NAS-generated MobileNetV2-based architecture

Architecture family: CNN

Techniques: Neural Architecture Search, reinforcement learning, multi-objective optimization, hardware-aware latency feedback, Pareto optimization, binary-path selection

Framework: PyTorch 1.0; CUDA 9.0

Training type: From scratch

Inference type: On-device

## Hardware

Device: Jetson Nano

Hardware type: SoC / GPU / CPU

Processor / microcontroller: 128-core Maxwell GPU; 4-core ARM A57 CPU

Clock frequency: 1.43 GHz CPU

SRAM / RAM: 4 GB 64-bit LPDDR4

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, latency, parameters, compute, energy sensitivity, communication efficiency

## Dataset

Name: ImageNet ILSVRC-2012

Type: Public

Dataset size: 1.2 million training samples; 50k validation samples

Number of classes: 1000

Input resolution: Not reported

Data modality: Image

## Metrics

Accuracy: Top-1 73.7%; Top-5 91.6%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 28.2 ms on Jetson Nano edge GPU

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: 1.1M

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Multi-objective NAS, reinforcement learning controller, latency-aware reward, parameter-aware reward, Pareto-frontier selection, MobileNetV2 search space

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Resource-constrained neural architecture search

Hardware-specific optimization: Target-device latency is measured on the edge device and incorporated into the NAS reward.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 1.1M parameters

Energy per inference reported: Not reported

Latency on target device reported: 28.2 ms on Jetson Nano edge GPU

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is Jetson Nano with 4 GB RAM, not an MCU-class or bare-metal TinyML platform.

## Benchmarking / Standardization

Benchmark used: ImageNet ILSVRC-2012

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet

Comparison with baseline models: MobileNetV1, MobileNetV2, NASNet, MnasNet, ProxylessNAS-R

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

## Results

Summary: The proposed NAS framework generated Pareto-optimal architectures for edge deployment. The selected model achieved 73.7% Top-1 accuracy, 91.6% Top-5 accuracy, 1.1M parameters, and 28.2 ms inference latency on Jetson Nano edge GPU.

Limitations: Online latency sampling is inefficient; the server waits for latency feedback; the pipeline has large engineering overhead; multi-hardware search is time-consuming and complex.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes a multi-objective resource-constrained NAS framework that searches MobileNetV2-based neural architectures directly for edge devices using reinforcement learning and hardware latency feedback.

| Paper      | Year | Task           | Model                              | Technique           | Device      | Dataset              | Main Metric                                | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework   | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | -------------- | ---------------------------------- | ------------------- | ----------- | -------------------- | ------------------------------------------ | ------- | ---------- | -------- | ----- | ------ | ----------- | -------- | ------------- | ------------- |
| Lyu et al. | 2022 | Classification | MobileNetV2-based NAS architecture | Multi-objective NAS | Jetson Nano | ImageNet ILSVRC-2012 | Top-1 Accuracy 73.7%; Top-5 Accuracy 91.6% | 28.2 ms | N/A        | 4 GB RAM | N/A   | N/A    | PyTorch 1.0 | N/A      | None          | No            |
