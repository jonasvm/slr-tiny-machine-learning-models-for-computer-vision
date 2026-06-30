Paper ID: Resource-Aware-Scene-Text-Recognition-Using-Learned-Features-Quantization-and-Contour-Based-Character-Extraction

## Basic Info

Authors: Olutosin Ajibola Ademola; Eduard Petlenkov; Mairo Leier

Year: 2023

Title: Resource-Aware Scene Text Recognition Using Learned Features, Quantization, and Contour-Based Character Extraction

Source: IEEE Access, vol. 11, pp. 56865–56874 

Type: Experimental

## Problem & Context

Task: Scene text detection and recognition

Objective: Develop a resource-aware scene text detection and recognition approach for integer-only embedded hardware.

Application domain: Shipping container number detection and recognition

Scenario: Embedded / edge / resource-constrained hardware

TinyML relevance: Partial

TinyML justification: The paper targets embedded integer-only hardware and reports model size, RAM usage, inference time, computational cost, and INT8 quantization, but the deployment target is a Google Coral Development Board rather than a clearly MCU-class TinyML platform.

## Model / Method

Model: End-to-end scene text detection and recognition pipeline using modified EAST for text detection and a lightweight CNN for character recognition.

Architecture family: CNN

Techniques: 8-bit signed integer quantization, quantization offset/bias, contour-based character extraction, lightweight CNN design

Framework: Not reported

Training type: Not reported

Inference type: On-device

## Hardware

Device: Google Coral Development Board

Hardware type: SoC / NPU

Processor / microcontroller: Quad Cortex-A53, Cortex-M4F, Edge TPU coprocessor

Clock frequency: Not reported

SRAM / RAM: 1 GB RAM

Flash / ROM / Storage: 8 GB flash memory

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Storage, memory, computational power, inference time, integer-only operations, energy

## Dataset

Name: Proprietary shipping container image dataset

Type: Private

Dataset size: 2,000 images for text detection; 8,750 extracted character images for text recognition

Number of classes: 35 character classes

Input resolution: 320 × 320 for text detection; 64 × 64 for character recognition

Data modality: Natural scene container images and extracted character images

## Metrics

Accuracy: Text recognition: 99.73% original; 99.62% quantized

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Text detection: 2356.00 ms original; 1450.77 ms quantized. Text recognition: 3.59 ms original; 2.18 ms quantized

FPS: Not reported

Throughput: Not reported

Model size: Text detection: 96.21 MB original; 24.83 MB quantized. Text recognition: 0.88 MB original; 0.23 MB quantized

Parameters: Text recognition model: 1,107,712 parameters

MACs / FLOPs: Text detection computational cost: 15072.50 MFLOP original; 0 MFLOP quantized. Text recognition computational cost: 20.20 MFLOP original; 0 MFLOP quantized

RAM usage: Text detection: 286.23 MB original; 40.63 MB quantized. Text recognition: 5.04 MB original; 3.29 MB quantized. End-to-end pipeline: 291.27 MB original; 43.92 MB quantized

Flash usage: Reported as model size

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: 8-bit signed integer quantization, quantization offset for ground-truth labels, contour-based character extraction

Quantization: INT8

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: 8-bit symmetric signed integer quantization

Hardware-specific optimization: Models optimized for integer-only embedded hardware

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: No

Flash usage reported: Yes

Model size reported: Yes

Energy per inference reported: No

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets a Google Coral Development Board with 1 GB RAM, 8 GB flash, Cortex-A53/Cortex-M4F processors, and Edge TPU, which relaxes MCU-class TinyML constraints.

## Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes; original models are compared with quantized models

Comparison with previous works: Not reported

Reproducibility artifacts available: Not reported

## Results

Summary: Quantization reduced model size by about 3.8×, improved inference speed by about 1.6×, and reduced maximum RAM usage by about 6.6×. The quantized recognition model achieved 99.62% accuracy, while the quantized detection model reported 26.23% mean loss.

Limitations: The method is limited to less-clustered scene text images and may not be suitable for all types of scene text because of the quantization bias introduced during ground-truth label preparation.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes a resource-aware scene text detection and recognition pipeline that combines learned CNN features, 8-bit signed integer quantization, quantization offset, and contour-based character extraction for integer-only embedded hardware.

| Paper          | Year | Task                                 | Model                                                             | Technique         | Device                         | Dataset                            | Main Metric                                             | Latency                                   | Model Size                            | SRAM/RAM                                              | Flash                                 | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---: | ------------------------------------ | ----------------------------------------------------------------- | ----------------- | ------------------------------ | ---------------------------------- | ------------------------------------------------------- | ----------------------------------------- | ------------------------------------- | ----------------------------------------------------- | ------------------------------------- | ------ | --------- | -------- | ------------- | ------------- |
| Ademola et al. | 2023 | Scene text detection and recognition | Modified EAST with ResNet-50 detector; lightweight CNN recognizer | INT8 quantization | Google Coral Development Board | Private shipping container dataset | 99.62% recognition accuracy; 26.23% detection mean loss | 1450.77 ms detection; 2.18 ms recognition | 24.83 MB detector; 0.23 MB recognizer | 40.63 MB detector; 3.29 MB recognizer; 43.92 MB total | 24.83 MB detector; 0.23 MB recognizer | N/A    | N/A       | INT8     | None          | No            |
