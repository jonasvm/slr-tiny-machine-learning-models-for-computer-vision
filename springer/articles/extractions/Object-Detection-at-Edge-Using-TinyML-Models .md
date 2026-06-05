Paper ID: Object-Detection-at-Edge-Using-TinyML-Models 

TinyML classification: Near-TinyML — relevant TinyML edge vision work, but the reported deployment evidence is mobile/Raspberry Pi-class rather than explicit MCU-class deployment.

## Basic Info

Authors: Andhe Dharani; S. Anupama Kumar; Peethi N. Patil

Year: 2024

Title: Object Detection at Edge Using TinyML Models

Source: SN Computer Science, 5:11

Type: Experimental

## Problem & Context

Task: Object detection

Objective: Analyze TinyML models for edge-based object detection and water-level identification using FOMO and MobileNet SSD.

Application domain: Industrial object/water-level identification; smart stores; edge IoT vision.

Scenario: Edge, IoT, mobile, Raspberry Pi-class deployment.

TinyML relevance: Partial

TinyML justification: The paper explicitly uses TinyML, Edge Impulse, TensorFlow Lite conversion, and low-memory FOMO models, but the reported deployment evidence is mobile/Raspberry Pi-class rather than confirmed MCU-class execution.

## Model / Method

Model: FOMO; MobileNet SSD

Architecture family: CNN

Techniques: TensorFlow Lite conversion; INT8 quantization; grayscale preprocessing.

Framework: Edge Impulse; TensorFlow Lite

Training type: Not reported

Inference type: On-device

## Hardware

Device: Mobile phone; Raspberry Pi; Arduino Nano 33 BLE Sense mentioned as recommended TinyML hardware.

Hardware type: Mobile; SoC; MCU mentioned in background.

Processor / microcontroller: Not reported for deployment; Arduino Nano 33 BLE Sense background example uses ARM Cortex-M4F.

Clock frequency: Not reported for deployment; 64 MHz for Arduino Nano 33 BLE Sense background example.

SRAM / RAM: 244.0K peak RAM reported for FOMO; 4 KB peak RAM shown for Raspberry Pi deployment screen.

Flash / ROM / Storage: 76.3K flash usage reported for FOMO.

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, compute, communication/cloud avoidance.

## Dataset

Name: Not reported

Type: Private

Dataset size: Not reported

Number of classes: 3 classes shown for FOMO; 2 classes shown for MobileNet SSD validation.

Input resolution: 32 × 32 features shown for FOMO; otherwise not reported.

Data modality: RGB images; grayscale images.

## Metrics

Accuracy: RGB testing accuracy approximately 43%; 42.86% shown in Fig. 2; MobileNet SSD grayscale validation accuracy 66.7%; grayscale feature extraction reported as improving accuracy up to 98%.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: 75.9% for FOMO.

Latency: 288 ms inferencing time for FOMO; 1 ms processing time shown for Raspberry Pi deployment screen.

FPS: FOMO stated as 60 fps compared with MobileNet SSD at 2 fps on Raspberry Pi.

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: 244.0K peak RAM for FOMO; 4 KB peak RAM shown for Raspberry Pi deployment screen.

Flash usage: 76.3K flash usage for FOMO.

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: TensorFlow Lite conversion; INT8 quantization; grayscale preprocessing.

Quantization: INT8

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: TensorFlow Lite conversion and INT8 quantization.

Hardware-specific optimization: Edge Impulse on-device deployment/performance profiling.

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: 244.0K peak RAM for FOMO; 4 KB peak RAM shown for Raspberry Pi deployment screen.

Flash usage reported: 76.3K flash usage for FOMO.

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 288 ms inferencing time for FOMO; 1 ms processing time shown for Raspberry Pi deployment screen.

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports TinyML/edge object detection with low RAM/flash estimates, but does not demonstrate deployment on an MCU-class target or execution without a full operating system.

## Benchmarking / Standardization

Benchmark used: Custom water-level/object image dataset.

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: FOMO compared with MobileNet SSD.

Comparison with previous works: Qualitative comparison with cited FOMO/MobileNet SSD performance.

Reproducibility artifacts available: Not reported

## Results

Summary: FOMO achieved the best reported result among the tested models, with 75.9% F1-score, 288 ms inferencing time, 244.0K peak RAM, and 76.3K flash usage. RGB processing produced low accuracy around 43%, while grayscale preprocessing improved water-level demarcation and MobileNet SSD validation accuracy reached 66.7%.

Limitations: Edge Impulse did not support isolating the green RGB channel, and RGB water-level identification was inaccurate due to water transparency.

## Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes an Edge Impulse TinyML case study for edge object detection and water-level identification using FOMO and MobileNet SSD converted to TensorFlow Lite.

| Paper          | Year | Task             | Model               | Technique                                                              | Device                     | Dataset                       | Main Metric         | Latency                                               | Model Size | SRAM/RAM                                        | Flash | Energy | Framework                     | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | ---------------- | ------------------- | ---------------------------------------------------------------------- | -------------------------- | ----------------------------- | ------------------- | ----------------------------------------------------- | ---------- | ----------------------------------------------- | ----- | ------ | ----------------------------- | -------- | ------------- | ------------- |
| Dharani et al. | 2024 | Object detection | FOMO; MobileNet SSD | INT8 quantization; TensorFlow Lite conversion; grayscale preprocessing | Mobile phone; Raspberry Pi | Custom water-level cup images | FOMO F1-score 75.9% | 288 ms; 1 ms processing shown for Raspberry Pi screen | N/A        | 244.0K peak; 4 KB shown for Raspberry Pi screen | 76.3K | N/A    | Edge Impulse; TensorFlow Lite | INT8     | None          | No            |
