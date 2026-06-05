Paper ID: Complementary-spatial-transformer-network-for-real-time-3D-object-recognition-A-tiny-deep-learning-model-in-target-space 

TinyML classification: Near-TinyML — relevant lightweight edge-AI vision work, but no explicit MCU-class deployment or constraints are reported.

## Basic Info

Authors: K. P. Krishna Kumar; Varghese Paul

Year: 2023

Title: Complementary spatial transformer network for real-time 3D object recognition: A tiny deep learning model in target space

Source: Journal of Real-Time Image Processing, 20:88

Type: Experimental

## Problem & Context

Task: Classification; 3D object recognition; yaw angle regression

Objective: Propose a tiny deep learning model named Complementary Spatial Transformer Network for real-time 3D object recognition.

Application domain: 3D point cloud object recognition

Scenario: Edge AI; robotics; autonomous navigation; IoT applications

TinyML relevance: Partial

TinyML justification: The paper proposes a tiny model with reduced parameters and edge-AI deployability, but experiments are performed on desktop CPU/GPU hardware and no MCU-class deployment is reported.

## Model / Method

Model: Complementary Spatial Transformer Network

Architecture family: Hybrid CNN

Techniques: Tiny architecture; target-space representation; position encoder; sampler; Conv3D; MaxPool3D; fully connected layers; data augmentation

Framework: PyTorch

Training type: From scratch

Inference type: On-device

## Hardware

Device: Desktop machine with Intel Core i5-9505H, 16 GB RAM, NVIDIA GeForce GTX 1650 with 4 GB dedicated graphics memory, Ubuntu Linux 22.04

Hardware type: CPU / GPU

Processor / microcontroller: Intel Core i5-9505H; NVIDIA GeForce GTX 1650

Clock frequency: Not reported

SRAM / RAM: 16 GB main memory; 4 GB dedicated GPU memory

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Memory requirements; number of parameters; computational complexity; inference latency; throughput; edge AI deployability

## Dataset

Name: ModelNet10; ModelNet40; ShapeNetCore

Type: Public

Dataset size: ModelNet40: 12,311 shapes, 9,843 train and 2,468 test; ModelNet10: 4,899 shapes, 3,991 train and 908 test; ShapeNetCore: 51,127 samples, 35,708 train, 5,158 validation and 10,261 test

Number of classes: ModelNet10: 10; ModelNet40: 40; ShapeNetCore: 55

Input resolution: 2048 × 3 point cloud input; 32 × 32 × 32 tensor representation

Data modality: 3D point cloud

## Metrics

Accuracy: CSTN: 91% on ModelNet10; 86% on ModelNet40; 78% on ShapeNetCore; yaw angle regression accuracy: 97.7% for ω = 90° and 88.57% for ω = 180°

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: CSTN voxel grid to detection: 0.32 ms on NVIDIA GTX 1650 GPU; CSTN xyz to detection: 0.7 ms on Intel Core i5 CPU

FPS: Not reported

Throughput: CSTN voxel grid to detection: 3095 DPS on NVIDIA GTX 1650 GPU; CSTN xyz to detection: 1410 DPS on Intel Core i5 CPU

Model size: Not reported

Parameters: CSTN classifier: 66.196 K; CSTN regression model: 81,257 parameters; ModelNet10 CSTN: 14 K parameters

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Reduced-parameter architecture; algorithmic enhancements; position encoder and sampler; single Conv3D and MaxPool3D localization network; early stopping; rotation augmentation

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Not reported

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 0.32 ms on NVIDIA GTX 1650 GPU; 0.7 ms on Intel Core i5 CPU

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: No

Reason: The paper does not report MCU-class deployment, SRAM/Flash constraints, bare-metal or RTOS execution, TensorFlow Lite Micro, CMSIS-NN, or energy per inference.

## Benchmarking / Standardization

Benchmark used: ModelNet10; ModelNet40; ShapeNetCore

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ModelNet10; ModelNet40; ShapeNetCore

Comparison with baseline models: VoxNet; LightNet; UprightRL; Upright 3D Conv Nets

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset

## Results

Summary: CSTN achieved 86% accuracy on ModelNet40 with 66.196 K parameters and 3095 DPS on NVIDIA GTX 1650 GPU. The model required only 10–35% of the trainable parameters of compared state-of-the-art networks and achieved 1.65–2× higher GPU throughput.

Limitations: Not reported

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

## Contribution

This paper proposes a Complementary Spatial Transformer Network, a tiny deep learning architecture for real-time 3D point cloud object recognition using target-space representation and reduced trainable parameters.

| Paper        | Year | Task                                               | Model | Technique                                          | Device                                        | Dataset                                | Main Metric                | Latency                 | Model Size | SRAM/RAM                   | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | -------------------------------------------------- | ----- | -------------------------------------------------- | --------------------------------------------- | -------------------------------------- | -------------------------- | ----------------------- | ---------- | -------------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Kumar et al. | 2023 | 3D object recognition / point cloud classification | CSTN  | Tiny target-space spatial transformer architecture | Intel Core i5-9505H CPU / NVIDIA GTX 1650 GPU | ModelNet10 / ModelNet40 / ShapeNetCore | 86% Accuracy on ModelNet40 | 0.32 ms GPU; 0.7 ms CPU | N/A        | 16 GB RAM; 4 GB GPU memory | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
