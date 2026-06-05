Paper ID: Explainable-Knowledge-Distillation-for-On-Device-Chest-X-Ray-Classification

TinyML classification: Near-TinyML — evaluated for on-device/edge vision on constrained hardware such as Snapdragon 845, CPUs, and GPU, without explicit MCU-class deployment.

## Basic Info

Authors: Chakkrit Termritthikun, Ayaz Umer, Suwichaya Suwanwimolkul, Feng Xia, Ivan Lee

Year: 2024

Title: Explainable Knowledge Distillation for On-Device Chest X-Ray Classification

Source: IEEE/ACM Transactions on Computational Biology and Bioinformatics, Vol. 21, No. 4

Type: Experimental

## Problem & Context

Task: Classification

Objective: Create a compact deep learning model for real-time multi-label chest X-ray image classification using knowledge distillation and explainable AI.

Application domain: Medical imaging / chest X-ray diagnosis

Scenario: On-device, mobile, edge, constrained hardware platforms

TinyML relevance: Partial

TinyML justification: The paper targets on-device inference and constrained hardware platforms, but does not report MCU-class deployment, SRAM/Flash constraints, TensorFlow Lite Micro, CMSIS-NN, or bare-metal/RTOS execution.

## Model / Method

Model: EEEA-Net-C2 student model with OFA-595, DenseNet161, EEEA-Net-C2, Visformer-S, and AutoFormerV2-T teachers

Architecture family: CNN / Transformer

Techniques: Knowledge distillation, compact CNN student model, Grad-CAM explainability, Focal Binary Cross-Entropy loss, NAS-derived architectures

Framework: PyTorch

Training type: Transfer learning / fine-tuning with ImageNet-pretrained teacher networks and student training via knowledge distillation

Inference type: On-device

## Hardware

Device: Qualcomm Snapdragon 845, Intel Core i7-6700HQ CPU, Apple M1 Pro CPU, NVIDIA GTX 980 Ti GPU

Hardware type: SoC / CPU / GPU / Mobile

Processor / microcontroller: Qualcomm Snapdragon 845; Intel Core i7-6700HQ; Apple M1 Pro; NVIDIA GTX 980 Ti

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Computational complexity, latency, model size, limited hardware platforms, real-time inference

## Dataset

Name: ChestX-ray14; CheXpert; PadChest

Type: Public

Dataset size: ChestX-ray14: 112,120 frontal CXR images from 30,805 individuals; CheXpert: 224,316 CXR images from 65,240 patients; PadChest: 158,626 CXR images from 67,000 patients

Number of classes: ChestX-ray14: 14 disease labels; CheXpert: 12 abnormalities plus no-findings and support devices; PadChest: 19 differential diagnoses

Input resolution: 224 × 224

Data modality: Grayscale chest X-ray images converted to RGB format

## Metrics

Accuracy: ChestX-ray14: 93.9%; CheXpert: 86.8%; PadChest: 97.0% for EEEA-Net-C2 student with DenseNet161 teacher

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: ChestX-ray14: 93.4%; CheXpert: 84.9%; PadChest: 96.6% for EEEA-Net-C2 student with DenseNet161 teacher

Latency: EEEA-Net-C2: 107 ms on Snapdragon 845; 88.4 ms on Intel Core i7-6700HQ; 97.0 ms on Apple M1 Pro; 5.2 ms on NVIDIA GTX 980 Ti

FPS: Not reported

Throughput: Not reported

Model size: 18.3 MB for EEEA-Net-C2

Parameters: 4.7 million for EEEA-Net-C2

MACs / FLOPs: 0.3 billion FLOPs for EEEA-Net-C2

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Knowledge distillation from CNN- and Transformer-based teachers to compact EEEA-Net-C2 student; Grad-CAM explainability; Focal Binary Cross-Entropy and MSE distillation loss

Quantization: Not reported

Pruning: No

Knowledge distillation: Yes

Compression method: Teacher-student knowledge distillation into compact EEEA-Net-C2 model

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 18.3 MB

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper evaluates on-device chest X-ray classification on mobile/edge-class hardware, but does not provide MCU-class deployment evidence or SRAM/Flash/energy constraints.

## Benchmarking / Standardization

Benchmark used: ChestX-ray14, CheXpert, PadChest

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes

Comparison with previous works: Not reported

Reproducibility artifacts available: Not reported

## Results

Summary: Knowledge distillation improved the compact EEEA-Net-C2 student model across three CXR datasets. With DenseNet161 as teacher, EEEA-Net-C2 achieved AUC values of 83.7%, 87.1%, and 88.7% on ChestX-ray14, CheXpert, and PadChest, respectively, with 4.7M parameters and 0.3G FLOPs.

Limitations: Ground-truth localization bounding boxes are not readily available, and manual annotation by expert radiologists is expensive and time-consuming.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes an explainable knowledge distillation approach that transfers knowledge from CNN- and Transformer-based teachers to a compact EEEA-Net-C2 student model for on-device multi-label chest X-ray classification.

| Paper                | Year | Task           | Model       | Technique              | Device                                                                | Dataset                          | Main Metric              | Latency                                                                                                         | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------------- | ---: | -------------- | ----------- | ---------------------- | --------------------------------------------------------------------- | -------------------------------- | ------------------------ | --------------------------------------------------------------------------------------------------------------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Termritthikun et al. | 2024 | Classification | EEEA-Net-C2 | Knowledge distillation | Snapdragon 845; Intel Core i7-6700HQ; Apple M1 Pro; NVIDIA GTX 980 Ti | ChestX-ray14; CheXpert; PadChest | AUC: 83.7%, 87.1%, 88.7% | 107 ms on Snapdragon 845; 88.4 ms on Intel Core i7-6700HQ; 97.0 ms on Apple M1 Pro; 5.2 ms on NVIDIA GTX 980 Ti | 18.3 MB    | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
