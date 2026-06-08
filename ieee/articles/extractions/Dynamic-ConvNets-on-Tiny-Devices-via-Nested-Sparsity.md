Paper ID: Dynamic-ConvNets-on-Tiny-Devices-via-Nested-Sparsity

TinyML classification: Strict TinyML — explicit MCU-class deployment with ARM Cortex-M7, constrained Flash/RAM, quantization, latency, storage, and vision benchmarks.

## Basic Info

Authors: Matteo Grimaldi, Luca Mocerino, Antonio Cipolletta, Andrea Calimera

Year: 2023

Title: Dynamic ConvNets on Tiny Devices via Nested Sparsity

Source: IEEE Internet of Things Journal, Vol. 10, No. 6, 15 March 2023, pp. 5073–5082. DOI: 10.1109/JIOT.2022.3222014 

Type: Methodological

## Problem & Context

Task: Image classification and object detection

Objective: Build dynamic sparse ConvNets that trade accuracy for latency at runtime while reducing storage footprint for tiny edge devices.

Application domain: IoT visual computing

Scenario: Edge, embedded, MCU-class IoT device

TinyML relevance: Yes

TinyML justification: The paper deploys image classification and object detection ConvNets on an ARM Cortex-M7 MCU with 512 kB SRAM and 2 MB Flash. 

## Model / Method

Model: Nested Sparse ConvNets using ResNet9, MobileNetV1, and SSD-MobileNetV2

Architecture family: CNN

Techniques: Nested sparsity, block pruning, gradient masking, in-place distillation, NestedCSR compression, custom sparse compute kernels, INT8 quantization

Framework: PyTorch v1.5.1 for training; CMSIS-NN v5.6.0 extension for MCU deployment; GNU Arm Embedded Toolchain 6.3.1 for cross-compilation

Training type: From scratch

Inference type: On-device

## Hardware

Device: NUCLEO-F767ZI board

Hardware type: MCU

Processor / microcontroller: ARM Cortex-M7 MCU

Clock frequency: 216 MHz

SRAM / RAM: 512 kB on-chip SRAM

Flash / ROM / Storage: 2 MB Flash

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, Flash storage, latency, compute workload, MCU resource constraints

## Dataset

Name: CIFAR-10, CIFAR-100, PASCAL VOC

Type: Public

Dataset size: CIFAR-10/100: 60k images each; PASCAL VOC: 15,870 RGB images and 37,813 annotated objects

Number of classes: CIFAR-10: 10; CIFAR-100: 100; PASCAL VOC: reduced to top-10 labels

Input resolution: CIFAR-10/100: 32 × 32; PASCAL VOC: 160 × 160

Data modality: RGB image

## Metrics

Accuracy: MobileNetV1 on CIFAR-10: up to 89.90% Top-1 for Nested Sparse at w=1.00, s=70%; ResNet9 on CIFAR-100: up to 73.56% Top-1 for Nested Sparse at w=1.00, s=70%

mAP: SSD-MobileNetV2 on PASCAL VOC: up to 68.30% mAP for Nested Sparse at w=0.50, s=70%

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: MobileNetV1 NestedCSR s=70%: 204 ms, 126 ms, 65 ms, and 24 ms for w=1.00, 0.75, 0.50, and 0.25; ResNet9 NestedCSR s=70%: 1093 ms, 630 ms, 292 ms, and 84 ms for w=1.00, 0.75, 0.50, and 0.25; SSD-MobileNetV2 Nested Sparse: 1225/1103/951 ms at w=0.50 and 883/807/712 ms at w=0.35 for s=70/80/90%

FPS: Not reported

Throughput: Not reported

Model size: MobileNetV1 NestedCSR: 1464/839/387/108 kB for w=1.00/0.75/0.50/0.25; ResNet9 NestedCSR: 1016/576/260/68 kB for w=1.00/0.75/0.50/0.25; SSD-MobileNetV2 Nested Sparse: 514 kB at w=0.50 and 334 kB at w=0.35

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Model storage reported as 68–1464 kB depending on model and width

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Nested sparse training, gradient masking, magnitude-based block pruning, NestedCSR sparse compression, custom sparse matrix multiplication kernels, INT8 quantization

Quantization: INT8

Pruning: Yes

Knowledge distillation: Yes

Compression method: NestedCSR block sparse storage format

Hardware-specific optimization: Custom sparse kernels integrated into CMSIS-NN with 1 × 2 block shape to exploit ARM Cortex-M7 SIMD media accelerator

Use of CMSIS-NN: Yes

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Yes

Model size reported: Yes

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets and evaluates MCU-class deployment on an ARM Cortex-M7 with 512 kB SRAM, 2 MB Flash, INT8 quantization, storage footprints, and latency on target hardware.

## Benchmarking / Standardization

Benchmark used: CIFAR-10, CIFAR-100, PASCAL VOC

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10, CIFAR-100, PASCAL VOC

Comparison with baseline models: Yes; compared with dense models, single sparse models, DSNN, and Slimmable ConvNets

Comparison with previous works: Yes; compared against dynamic pruning and layer width scaling approaches

Reproducibility artifacts available: Not reported

## Results

Summary: Nested Sparse ConvNets achieved comparable accuracy to individually trained sparse models while reducing storage footprint and enabling runtime latency-accuracy scaling. On MCU deployment, the method was evaluated for image classification and object detection, with reported storage, latency, and accuracy/mAP results.

Limitations: Sparsity levels are manually fixed before training, and layer-wise sparsity effects on accuracy and latency are not automatically optimized.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes Nested Sparse ConvNets, a dynamic sparse CNN training, compression, and deployment pipeline for runtime latency-accuracy scaling on MCU-class tiny devices.

| Paper           | Year | Task                             | Model                                                         | Technique                               | Device                        | Dataset                         | Main Metric                            | Latency    | Model Size | SRAM/RAM | Flash | Energy | Framework         | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---- | -------------------------------- | ------------------------------------------------------------- | --------------------------------------- | ----------------------------- | ------------------------------- | -------------------------------------- | ---------- | ---------- | -------- | ----- | ------ | ----------------- | -------- | ------------- | ------------- |
| Grimaldi et al. | 2023 | Classification; Object detection | Nested Sparse ConvNets; ResNet9; MobileNetV1; SSD-MobileNetV2 | Nested sparsity + NestedCSR compression | NUCLEO-F767ZI / ARM Cortex-M7 | CIFAR-10; CIFAR-100; PASCAL VOC | 89.90% Top-1; 73.56% Top-1; 68.30% mAP | 24–1225 ms | 68–1464 kB | 512 kB   | 2 MB  | N/A    | PyTorch; CMSIS-NN | INT8     | CMSIS-NN      | Yes           |
