Paper ID: Enhancing-Drone-Based-Precision-Agriculture-Performance-Optimization-of-TinyML-Models-on-Edge-Devices-and-Adaptive-Path-Planning

TinyML classification: Strict TinyML — it explicitly deploys TinyML vision models on an ESP-EYE 32 MCU using Edge Impulse with kilobyte-to-megabyte memory constraints.

Basic Info

Authors: Yagna S. H. Annadata; Aiswariya Thazhathethil; Vishnuvaradhan Moganarengam; Tooraj Nikoubin

Year: 2025

Title: Enhancing Drone-Based Precision Agriculture: Performance Optimization of TinyML Models on Edge Devices and Adaptive Path Planning

Source: SN Computer Science, 6:132 

Type: Experimental

Problem & Context

Task: Classification

Objective: Deploy TinyML models on autonomous drones for low-power real-time plant disease detection and adaptive path planning.

Application domain: Precision agriculture

Scenario: Edge, embedded, UAV/drone, autonomous system

TinyML relevance: Yes

TinyML justification: The paper targets ESP-EYE 32 microcontroller deployment using Edge Impulse and reports RAM, flash, latency, and power-related constraints for plant disease image classification. 

Model / Method

Model: MobileNetV2

Architecture family: CNN

Techniques: Transfer learning, parameter tuning, image-size optimization, learning-rate tuning, training-cycle tuning, validation-set tuning, neuron-count tuning, data augmentation

Framework: Edge Impulse

Training type: Transfer learning

Inference type: On-device

Hardware

Device: ESP-EYE 32 module integrated with a drone

Hardware type: MCU

Processor / microcontroller: ESP-EYE 32 MCU

Clock frequency: Not reported

SRAM / RAM: Physical SRAM/RAM not reported; peak RAM usage reported between 235.6 K and 2.5 M depending on configuration

Flash / ROM / Storage: Physical flash not reported; flash usage reported between 64.0 K and 1.6 M depending on configuration

Power consumption: ESP-EYE 32: 0.3–0.8 W; total drone full-throttle power demand approximately 891 W 

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, flash, latency, power, compute, battery life, wind conditions, flight path, field coverage, recharging

Dataset

Name: Not reported

Type: Not reported

Dataset size: 55 images reported for image-size experiments; full dataset size not reported

Number of classes: 2 for binary healthy vs disease-infected classification; multi-class count not reported

Input resolution: 96×96 for single-labeled and bounding-box-labeled models; 120×120 for multi-class; 160×160, 240×240, and 320×320 also evaluated

Data modality: Plant leaf images

Metrics

Accuracy: Single-labeled binary testing accuracy: 91.67%; bounding-box binary testing accuracy: 80.0%; single-labeled multi-class testing accuracy: 80.0%; conclusion reports testing accuracy up to 90% 

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Single-labeled binary inferencing time: 2519 ms; bounding-box binary inferencing time: 782 ms; single-labeled multi-class inferencing time: 4284 ms

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Single-labeled binary: 334.6 K; bounding-box binary: 235.6 K; single-labeled multi-class: 457.3 K

Flash usage: Single-labeled binary: 585.0 K; bounding-box binary: 64.0 K; single-labeled multi-class: 585.3 K

Energy per inference: Not reported

Power consumption: ESP-EYE 32: 0.3–0.8 W; total drone full-throttle power demand approximately 891 W

Optimization

Techniques used: Edge Impulse deployment, MobileNetV2 transfer learning, data augmentation, image-size reduction, learning-rate tuning, training-cycle tuning, validation-set tuning, neuron-count tuning

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: Edge Impulse-generated flashable deployment for ESP-EYE 32 and resource-aware parameter tuning

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Yes; peak RAM usage reported as 235.6 K, 334.6 K, 457.3 K, and up to 2.5 M depending on configuration

Flash usage reported: Yes; flash usage reported as 64.0 K, 585.0 K, 585.3 K, and up to 1.6 M depending on configuration

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes; inferencing time reported from 782 ms to 4284 ms for main configurations

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets ESP-EYE 32 microcontroller deployment with on-device TinyML inference and reports MCU-relevant RAM, flash, latency, and power constraints.

Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes; compares single-labeled binary, bounding-box binary, and single-labeled multi-class configurations

Comparison with previous works: Limited; the work builds upon previous TinyML drone agriculture work but does not report a broad external benchmark comparison

Reproducibility artifacts available: Not reported

Results

Summary: Single-labeled models outperformed bounding-box-labeled models for plant disease classification, with single-labeled binary testing accuracy of 91.67%. The ESP-EYE 32 deployment reports peak RAM as low as 235.6 K and flash usage as low as 64.0 K. Rectangular drone paths were most energy-efficient, covering approximately 6000 m² in 6–7 minutes and capturing around 250 images. 

Limitations

Not reported as a dedicated limitations section; future work includes advanced obstacle avoidance, human-drone interaction, and predictive maintenance, while high wind conditions reduce coverage and require additional recharging.

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

This paper proposes a TinyML-based autonomous drone framework for plant disease image classification on ESP-EYE 32 microcontrollers combined with adaptive path-planning simulation for precision agriculture.

| Annadata et al. | 2025 | Classification | MobileNetV2 | Edge Impulse deployment + parameter tuning | ESP-EYE 32 MCU | Plant leaf images, not named | Accuracy: 91.67% | 2519 ms | N/A | 334.6 K | 585.0 K | N/A | Edge Impulse | N/A | N/A | Yes |
