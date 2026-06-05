Paper ID: Context-Aware-TinyML-Model-for-Korean-Handwriting-Recognition-Under-Online-Assisted-Learning-Scenes

TinyML classification: Near-TinyML — Relevant edge/TinyML computer-vision OCR work, but no explicit MCU-class hardware, memory, latency, or energy results are reported.

## Basic Info

Authors: Shunji Cui

Year: 2025

Title: Context-Aware TinyML Model for Korean Handwriting Recognition Under Online Assisted Learning Scenes

Source: Internet Technology Letters, 8:e636 

Type: Experimental

## Problem & Context

Task: Optical character recognition / Korean handwriting recognition

Objective: To design a context-aware TinyML model for Korean handwriting recognition using Mamba-based contextual modeling and distillation-based compression.

Application domain: Online Korean language learning

Scenario: Mobile, wearable, AIoT, edge

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained mobile/wearable edge devices and model compression, but experiments are reported on an NVIDIA RTX 4090 GPU and no MCU-class deployment metrics are provided.

## Model / Method

Model: Context-aware CRNN-based student model with 4-layer CNN, Mamba layer, CTC, and multi-layer joint distillation from a teacher network.

Architecture family: Hybrid CNN / Other

Techniques: Knowledge distillation, model compression, Mamba-based linear-complexity contextual modeling, reduced convolutional layers

Framework: PyTorch

Training type: Not reported; teacher network uses pre-trained VGG-16

Inference type: Not reported

## Hardware

Device: NVIDIA GeForce RTX 4090 with 24G memory for training/testing; wearable devices are targeted but not specified

Hardware type: GPU

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: 24G GPU memory reported for experimental hardware; target-device SRAM/RAM not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Resource-constrained mobile devices, strict time constraints, power requirements, latency, bandwidth, privacy, model complexity

## Dataset

Name: AIHub; MLT-h

Type: Public

Dataset size: AIHub collected 100,000 Korean characters; 674,110 text regions were selected for evaluation; 10,000 images were selected for testing and the rest for training; MLT-h was constructed from Korean text regions in the MLT17 test set

Number of classes: Not reported

Input resolution: 32 × 128

Data modality: Image/text-region OCR data

## Metrics

Accuracy: Ours: 94.2% on AIHub and 86.8% on MLT-h; CRNN + Mamba: 96.2% on AIHub and 90.2% on MLT-h

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported for proposed model; VGG16 baseline is described as having more than 138M weights

MACs / FLOPs: Not reported for proposed model; VGG16 baseline is described as requiring 15.5B MACs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Multi-layer joint knowledge distillation, reduced CNN student network, Mamba layer for linear-complexity contextual modeling

Quantization: Not reported

Pruning: No

Knowledge distillation: Yes

Compression method: Multi-layer joint distillation from teacher network to smaller student network

Hardware-specific optimization: Not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets mobile/wearable TinyML-style deployment but does not report MCU-class hardware, SRAM/Flash usage, target-device latency, or energy measurements.

## Benchmarking / Standardization

Benchmark used: AIHub; MLT-h

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: MLT-h derived from ICDAR MLT17 Korean text regions

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: dataset

## Results

Summary: The proposed distilled model achieved 94.2% word-level accuracy on AIHub and 86.8% on MLT-h. CRNN + Mamba achieved the highest reported accuracy, but the distilled model was presented as more suitable for mobile deployment due to fewer convolutional layers.

Limitations: The paper states that future work could explore multimodal information and that effective multimodal fusion remains challenging.

## Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes a context-aware TinyML-oriented Korean handwriting recognition model that combines CRNN-style OCR, Mamba-based contextual modeling, and multi-layer joint knowledge distillation for compressed mobile/wearable deployment.

| Paper      | Year | Task                          | Model              | Technique              | Device                                                  | Dataset      | Main Metric                        | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | ----------------------------- | ------------------ | ---------------------- | ------------------------------------------------------- | ------------ | ---------------------------------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Cui et al. | 2025 | OCR / handwriting recognition | CRNN-Mamba student | Knowledge distillation | RTX 4090 for experiments; wearable target not specified | AIHub; MLT-h | Accuracy: 94.2% AIHub, 86.8% MLT-h | N/A     | N/A        | N/A      | N/A   | N/A    | PyTorch   | N/A      | N/A           | No            |
