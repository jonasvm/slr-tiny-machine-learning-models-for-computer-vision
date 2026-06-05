Paper ID: Optimized-embedded-AI-efficient-implementation-of-CNNs-on-ESP32-CAM-for-real-time-image-classification

TinyML classification: Strict TinyML — The paper explicitly evaluates deployment on Arduino Nano 33 BLE, an MCU-class Cortex-M4 platform, with reported embedded memory and latency constraints.

Basic Info

Authors: Faten Ben Aicha

Year: 2025

Title: Optimized embedded AI: efficient implementation of CNNs on ESP32-CAM for real-time image classification

Source: Computing, 107:206 

Type: Experimental

Problem & Context

Task: Classification

Objective: Deploy an optimized lightweight CNN for real-time image classification on ESP32-CAM under severe hardware constraints.

Application domain: Embedded AI, robotics, IoT, educational/low-cost robotic systems

Scenario: Embedded, edge, IoT, robotics, MCU-based on-device inference

TinyML relevance: Yes

TinyML justification: The paper explicitly targets ESP32-CAM microcontroller deployment with 520 KB SRAM, no FPU, limited stack space, quantized inference, and real-time on-device execution.

Model / Method

Model: Compact CNN with 28×28 grayscale input, two convolutional layers, max-pooling, dense layer, and softmax output; filter count is reported inconsistently as 64 filters and 32 filters.

Architecture family: CNN

Techniques: Full-integer quantization, post-training quantization, pruning, model compression, lookup tables, memory management, hardware-aware scheduling

Framework: TensorFlow Lite / TensorFlow Lite Micro

Training type: From scratch

Inference type: On-device

Hardware

Device: AI-Thinker ESP32-CAM

Hardware type: MCU

Processor / microcontroller: ESP32-CAM / ESP32 microcontroller

Clock frequency: 160 MHz

SRAM / RAM: 520 KB SRAM

Flash / ROM / Storage: 4 MB flash memory

Power consumption: < 0.8 W

Energy per inference: Not reported

Execution without full OS: Yes

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, compute, stack space, tensor buffer overflow, quantized memory alignment, WiFi/camera/inference concurrency, task scheduling

Dataset

Name: Fashion-MNIST

Type: Public

Dataset size: 60,000 training samples and 10,000 test samples; 15% of training set used for validation

Number of classes: 10

Input resolution: 28×28

Data modality: Grayscale image

Metrics

Accuracy: 92.3% optimized quantized CNN; 93.0% float32 baseline; 92.7% post-training quantization

mAP: Not reported

Precision: 91.8%

Recall: 91.2%

F1-score: 91.5%

Latency: 120 ms optimized inference; 450 ms unoptimized inference

FPS: Approximately 8–9 FPS

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: 450 KB

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: < 0.8 W

Optimization

Techniques used: Full-integer quantization, post-training quantization evaluation, pruning, model compression, lookup tables, TensorFlow Lite model conversion to C header, memory alignment handling, task scheduling, stack overflow recovery

Quantization: INT8

Pruning: Yes

Knowledge distillation: Not reported

Compression method: Full-integer quantization, pruning, model compression

Hardware-specific optimization: ESP32-CAM memory management, task arbitration between AI, camera, and WiFi modules, bit-packed memory allocator, lookup tables

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: Yes

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: 450 KB RAM usage reported; peak not explicitly stated

Flash usage reported: 4 MB flash capacity reported; model flash usage not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 120 ms

Runs without full operating system: Yes

Fully on-device inference: Yes

Communication required during inference: No cloud/offloading required; WiFi/web interface used for interaction and streaming

Candidate for Strict TinyML: Yes

Reason: The system runs a fully on-device quantized CNN on ESP32-CAM MCU hardware with 520 KB SRAM, no FPU, 450 KB RAM usage, and reported target-device latency and power.

Benchmarking / Standardization

Benchmark used: Fashion-MNIST

MLPerf Tiny mentioned: Yes

Visual Wake Words mentioned: No

Other standard benchmark: Fashion-MNIST

Comparison with baseline models: Yes, optimized model compared with unoptimized baseline

Comparison with previous works: Yes, compared with STM32H7 CMSIS-NN, EdgeTPU MobileNetV1, and Raspberry Pi 4B TFLite implementations

Reproducibility artifacts available: Not reported

Results

Summary: The optimized INT8 CNN achieved 92.3% accuracy, 120 ms inference latency, 450 KB RAM usage, and < 0.8 W power consumption on ESP32-CAM. Quantization and memory optimization reduced latency by 4× and memory usage by 80% compared with the unoptimized model.

Limitations

The paper reports that Fashion-MNIST does not reflect real-world image variability such as occlusion, lighting changes, or multi-object scenes. The 120 ms inference latency is suitable for low-frame-rate tasks but insufficient for high-speed applications such as industrial inspection or gesture recognition.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an optimized ESP32-CAM-based embedded AI system that deploys a quantized CNN for real-time on-device image classification under MCU-level memory, latency, and power constraints.

| Ben Aicha et al. | 2025 | Classification | Quantized CNN | Full-integer quantization + pruning + hardware-aware memory/scheduling optimization | ESP32-CAM | Fashion-MNIST | Accuracy 92.3% | 120 ms | N/A | 450 KB | 4 MB capacity | N/A | TensorFlow Lite Micro | INT8 | TFLM | Yes |
