Paper ID: A-locally-processed-light-weight-deep-neural-network-for-detecting-colorectal-polyps-in-wireless-capsule-endoscopes

TinyML classification: Strict TinyML — The paper explicitly evaluates deployment on Arduino Nano 33 BLE, an MCU-class Cortex-M4 platform, with reported embedded memory and latency constraints.

Basic Info

Authors: Yunlong Wang; Sunyoung Yoo; Jan-Matthias Braun; Esmaeil S. Nadimi

Year: 2021

Title: A locally-processed light-weight deep neural network for detecting colorectal polyps in wireless capsule endoscopes

Source: Journal of Real-Time Image Processing, 18:1183–1194 

Type: Experimental

Problem & Context

Task: Object Detection

Objective: Design a lightweight DNN with small parameter-storage size and sufficient inference accuracy for local colorectal polyp detection in wireless capsule endoscopes.

Application domain: Medical image processing; wireless capsule endoscopy; colorectal polyp detection.

Scenario: Embedded/on-capsule inference; wireless capsule endoscope; FPGA validation; future AI ASIC deployment.

TinyML relevance: Yes

TinyML justification: The paper targets local inference inside a wireless capsule endoscope with strong memory, latency, power, compute, and communication constraints, reporting 29.1 KB parameter storage and FPGA real-time validation.

Model / Method

Model: Custom lightweight DNN with 8 × 8 polyp confidence-map output.

Architecture family: CNN

Techniques: Lightweight fully convolutional design, SqueezeNet-inspired Fire layers, simplified YOLO-style output, fixed-point quantization, batch normalization, data augmentation, hyperparameter exploration.

Framework: TensorFlow; Xilinx Vitis AI

Training type: From scratch

Inference type: On-device

Hardware

Device: Xilinx ZCU102 FPGA board; target wireless capsule endoscope and future AI ASIC.

Hardware type: FPGA / SoC

Processor / microcontroller: XCZU9EG-2FFVB1156E MPSoC with 6 CPU cores and FPGA fabric; one CPU core used in tests; DNN implemented in FPGA fabric.

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory size, parameter storage, power consumption, computational capacity, heat generation, inference speed, physical size, product price, and wireless communication energy.

Dataset

Name: Not reported

Type: Private

Dataset size: 1528 total images; 764 images with at least one colorectal polyp and 764 without polyps; 1222 training images; 153 test images; augmented training set of 12,220 images.

Number of classes: 1 target class, colorectal polyp, plus no-polyp negative images.

Input resolution: 227 × 227 × 3

Data modality: RGB image

Metrics

Accuracy: Not reported

mAP: AP25 = 91.7%; AP50 = 88.3%; AP75 = 86.6%; AP95 = 79.3% for the best quantization setting reported.

Precision: Not reported as scalar value

Recall: Not reported as scalar value

F1-score: Not reported

Latency: Less than 6.28 ms on FPGA; tested range 5.48–6.28 ms.

FPS: 105 FPS on RTX 2070 comparison; supports operation above 150 Hz according to the paper.

Throughput: Not reported

Model size: 29.1 KB parameter storage

Parameters: 162.7 K parameters for the reported S11 = 30, E33 = 90, Fn = 2 setting.

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Lightweight architecture, low-bit fixed-point quantization, SqueezeNet-inspired Fire layers, simplified YOLO-style confidence map, batch normalization, data augmentation, and FPGA implementation using Vitis AI.

Quantization: Mixed precision; custom fixed-point bitW/bitA quantization explored.

Pruning: No

Knowledge distillation: No

Compression method: Low-bit quantization and lightweight architecture.

Hardware-specific optimization: FPGA implementation using Xilinx Vitis AI; architecture designed toward future AI ASIC deployment.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 29.1 KB parameter storage

Energy per inference reported: Not reported

Latency on target device reported: Less than 6.28 ms on FPGA

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No for the intended WCE use case; LAN communication is used only in the FPGA test setup for sending images and displaying results.

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets ultra-low-power embedded local inference inside a wireless capsule endoscope with kilobyte-scale parameter storage and real-time FPGA validation.

Benchmarking / Standardization

Benchmark used: Private WCE colorectal polyp image dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: SSD with ResNet101, YOLO V3 with Darknet-53, and Faster R-CNN with VGG16.

Comparison with previous works: Yes, comparison with popular object-detection DNNs; prior WCE work discussed but not directly benchmarked due to different datasets, loss functions, and evaluation criteria.

Reproducibility artifacts available: Not reported; recorded demonstration video only.

Results

Summary: The proposed DNN reached AP25 = 91.7% on the test set with 29.1 KB parameter storage. FPGA inference required less than 6.28 ms per image, below the 167 ms real-time requirement for 6 fps WCE operation.

Limitations

The method deliberately sacrifices precise polyp localization by using an 8 × 8 confidence map instead of exact bounding-box prediction. FPGA real-time testing was limited to float-type parameters because Vitis AI accepted only float-type models in their setup. The paper also identifies larger datasets, NAS-based design exploration, and sequential image processing as future work.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a lightweight locally processed DNN for colorectal polyp detection in wireless capsule endoscopes, optimized for very small parameter storage and real-time embedded inference.

| Wang et al. | 2021 | Object Detection | Custom lightweight DNN | Low-bit quantization + lightweight SqueezeNet/YOLO-like design | ZCU102 FPGA / target WCE ASIC | Private WCE images, 1528 images | AP25 = 91.7% | <6.28 ms | 29.1 KB | N/A | N/A | N/A | TensorFlow + Vitis AI | Mixed | None | Yes |
