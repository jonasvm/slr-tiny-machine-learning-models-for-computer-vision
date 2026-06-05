Paper ID: TinyML-Induced-Portable-Food-Defect-Detection-for-Edge-Computing

TinyML classification: Strict TinyML — explicitly reports MCU-class deployment on STM32H743 with low-memory model compression and low-power inference constraints.

## Basic Info

Authors: Yanxia Liu

Year: 2025

Title: TinyML Induced Portable Food Defect Detection for Edge Computing

Source: Internet Technology Letters, 8:e70044. 

Type: Experimental

## Problem & Context

Task: Food defect detection

Objective: Develop a portable lightweight food defect detection scheme using TinyML and mobile edge computing.

Application domain: Food safety / fruit surface defect detection

Scenario: Edge, embedded, mobile edge computing, portable device

TinyML relevance: Yes

TinyML justification: The paper explicitly targets TinyML, low-power portable devices, MCU-class deployment, model compression, quantization, latency, power consumption, and model-size constraints.

## Model / Method

Model: MobiEdgeNet

Architecture family: Hybrid CNN

Techniques: Hardware-aware NAS, dynamic binarization, mixed-precision quantization, model compression, hardware-aware channel pruning, knowledge distillation, DRL-based task offloading

Framework: PyTorch; Triton inference server; TensorRT; Vulkan API; Zephyr RTOS

Training type: Not reported

Inference type: Hybrid

## Hardware

Device: STM32H743 + Kendryte K210 + Xilinx Artix-7; NVIDIA Jetson Nano edge node also reported

Hardware type: MCU / NPU / FPGA / GPU / Edge device

Processor / microcontroller: STM32H743; Kendryte K210 dual-core 64-bit RISC-V; Xilinx Artix-7; NVIDIA Jetson Nano

Clock frequency: 480 MHz main frequency reported for STM32H743

SRAM / RAM: STM32H743 with 1 MB memory; host RAM recommendation of 32 GB also reported

Flash / ROM / Storage: Not reported

Power consumption: 85 mW single-frame inference power consumption; overall power consumption reduced to 65% of traditional ARM architecture

Energy per inference: Not reported

Execution without full OS: Yes

Fully on-device inference: No

Constraints mentioned: Memory, power, latency, compute, communication, model size, task offloading

## Dataset

Name: Not reported

Type: Private / not reported

Dataset size: Training set no less than 5000 images and test set no less than 1000 images reported as dataset requirement

Number of classes: Not reported

Input resolution: Not reported

Data modality: RGB images and hyperspectral data

## Metrics

Accuracy: 95.2%; 93.8% in cold chain warehouse; 94.5% in mobile farmers’ market

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 35 ms overall inference delay; 45 ms laboratory delay; 52 ms cold chain warehouse delay; 48 ms mobile farmers’ market delay

FPS: Not reported

Throughput: Not reported

Model size: 0.6 MB reported after compression; 1.2 MB reported in comparative table

Parameters: Not reported

MACs / FLOPs: 480 MFLOPs

RAM usage: 1 MB memory target reported for STM32H743; peak RAM not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 85 mW

## Optimization

Techniques used: Hardware-aware NAS, dynamic binarization, mixed-precision quantization, hardware-aware channel pruning, knowledge distillation, DRL offloading, CUDA stream parallelism, TensorRT optimization

Quantization: Mixed precision

Pruning: Yes

Knowledge distillation: Yes

Compression method: Hardware-aware channel pruning, dynamic binarization, mixed-precision quantization, model compression

Hardware-specific optimization: STM32H743 MAC and memory-bandwidth constraints, ARM Neon instruction set, Vulkan API, TensorRT, CUDA streams, MCU + NPU + FPGA architecture

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 0.6 MB; 1.2 MB also reported in comparative table

Energy per inference reported: Not reported

Latency on target device reported: 35 ms; scenario delays of 45 ms, 52 ms, and 48 ms also reported

Runs without full operating system: Yes

Fully on-device inference: No

Communication required during inference: Yes, edge/cloud offloading is part of the proposed architecture

Candidate for Strict TinyML: Yes

Reason: The paper explicitly reports operation of a compressed deep learning model on an STM32H743 microcontroller with 1 MB memory, low-power inference, model compression, quantization, and RTOS-based scheduling.

## Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: MobileNetV3-Small, VGG-16, ResNet50, MobileNetV3, TinyML-CAM

Comparison with previous works: Yes

Reproducibility artifacts available: dataset upon request; code and model not reported

## Results

Summary: The proposed system reports 95.2% accuracy for fruit surface defect detection, 35 ms inference delay, 85 mW power consumption, and compressed model size of 0.6 MB. The paper also reports deployment-oriented hardware using STM32H743, Kendryte K210, Xilinx Artix-7, and edge collaboration.

Limitations: Not explicitly stated; future work includes lightweight Transformer architecture, hyperspectral imaging for internal food quality, and federated learning for edge nodes.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes a TinyML and mobile-edge-computing-based portable food defect detection scheme using MobiEdgeNet, hardware-aware optimization, mixed-precision compression, and heterogeneous MCU + NPU + FPGA acceleration.

| Liu et al. | 2025 | Food defect detection | MobiEdgeNet | HA-NAS + mixed-precision quantization | STM32H743 + Kendryte K210 + Xilinx Artix-7 | Private/not reported food defect images | Accuracy 95.2% | 35 ms | 0.6 MB / 1.2 MB | 1 MB memory target | N/A | N/A | PyTorch / Triton / TensorRT / Zephyr RTOS | Mixed | None | Yes |
