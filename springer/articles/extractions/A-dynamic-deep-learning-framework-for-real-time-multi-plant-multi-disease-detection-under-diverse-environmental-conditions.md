Paper ID: A-dynamic-deep-learning-framework-for-real-time-multi-plant-multi-disease-detection-under-diverse-environmental-conditions

TinyML classification: Near-TinyML — The work targets mobile on-device TFLite Android inference rather than microcontroller-class deployment.

## Basic Info

Authors: Sejal Rahul Trivedi; Neha Sharma

Year: 2025

Title: A dynamic deep learning framework for real-time multi-plant, multi-disease detection under diverse environmental conditions

Source: International Journal of Information Technology 

Type: Experimental

## Problem & Context

Task: Classification and segmentation

Objective: Detect plant type and plant leaf disease under diverse real-world field conditions.

Application domain: Agriculture / precision farming / plant disease diagnosis

Scenario: Mobile, on-device, offline field diagnosis

TinyML relevance: Partial

TinyML justification: The paper reports TensorFlow Lite Android deployment for real-time offline inference, but does not report MCU-class hardware, bare-metal/RTOS execution, SRAM/Flash constraints, energy, or MCU latency.

## Model / Method

Model: CropLeafNet

Architecture family: CNN

Techniques: SWMAD preprocessing, HSV segmentation, flood-fill segmentation, CNN-based segmentation, 6-channel raw + processed image stacking, dual-layer CNN classification, histogram balancing, data augmentation, dropout regularization, TensorFlow Lite conversion

Framework: TensorFlow Lite

Training type: From scratch

Inference type: On-device

## Hardware

Device: Android mobile application

Hardware type: Mobile

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Offline inference, real-time field use, computational efficiency, variable lighting/background conditions

## Dataset

Name: PlantVillage dataset + real-time cotton and castor leaf images from agricultural fields in Gujarat

Type: Public + private

Dataset size: Not reported

Number of classes: Not reported

Input resolution: 128 × 128

Data modality: RGB image

## Metrics

Accuracy: 98% classification accuracy reported in abstract; 97% average accuracy reported in results; 97.442% validation accuracy for large layer configuration

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: SWMAD preprocessing, histogram balancing, data augmentation, dropout regularization, 6-channel image stacking, TensorFlow Lite conversion

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: TensorFlow Lite conversion

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

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: No

Reason: The deployment is an Android TensorFlow Lite mobile application, with no evidence of MCU-class execution, bare-metal/RTOS operation, or reported SRAM/Flash/energy constraints.

## Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: PlantVillage dataset

Comparison with baseline models: Yes; compares optimizers, layer configurations, HSV segmentation, flood-fill segmentation, and CNN segmentation.

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset upon request

## Results

Summary: CropLeafNet achieved 98% classification accuracy in the abstract and approximately 97% average accuracy in results. The best reported validation accuracy was 97.442% for the large CNN layer configuration, and the model was deployed as an offline Android TensorFlow Lite application.

Limitations

HSV segmentation performed poorly on complex backgrounds. Flood-fill segmentation was computationally intensive and sensitive to parameter tuning. SWMAD initially caused unstable training due to overfitting and feature loss before raw + processed image stacking was introduced.

## Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

## Contribution

This paper proposes CropLeafNet, a dual-layer CNN framework with SWMAD preprocessing, CNN-based segmentation, and TensorFlow Lite Android deployment for real-time offline plant disease detection.

| Paper          | Year | Task                            | Model       | Technique                                                | Device                     | Dataset                                                | Main Metric  | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | ------------------------------- | ----------- | -------------------------------------------------------- | -------------------------- | ------------------------------------------------------ | ------------ | ------- | ---------- | -------- | ----- | ------ | --------------- | -------- | ------------- | ------------- |
| Trivedi et al. | 2025 | Classification and segmentation | CropLeafNet | SWMAD preprocessing + dual-layer CNN + TFLite conversion | Android mobile application | PlantVillage + real-time cotton and castor leaf images | 98% accuracy | N/A     | N/A        | N/A      | N/A   | N/A    | TensorFlow Lite | N/A      | N/A           | No            |
