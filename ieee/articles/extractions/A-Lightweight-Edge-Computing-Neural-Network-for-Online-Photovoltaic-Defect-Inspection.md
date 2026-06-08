Paper ID: A-Lightweight-Edge-Computing-Neural-Network-for-Online-Photovoltaic-Defect-Inspection

TinyML classification: Near-TinyML — relevant edge computer vision work, but no explicit MCU-class deployment or MCU-level memory constraints are reported.

Basic Info

Authors: Jinlin Ye, Yuhan Liu, Liang Yang, Haiyong Chen, Changjun Wang, Yidong Zhou, Wei Zhang

Year: 2025

Title: A Lightweight Edge Computing Neural Network for Online Photovoltaic Defect Inspection

Source: IEEE Transactions on Instrumentation and Measurement, Vol. 74, Article 2510014 

Type: Experimental / Methodological

Problem & Context

Task: Object detection

Objective: Develop a lightweight detector for real-time photovoltaic defect inspection under edge computing environments.

Application domain: Photovoltaic plant inspection

Scenario: Autonomous aerial vehicle edge inspection; photovoltaic production-line defect inspection

TinyML relevance: Partial

TinyML justification: The paper targets edge computing and resource-constrained real-time inspection, but does not report MCU-class deployment, SRAM/Flash constraints, bare-metal execution, TensorFlow Lite Micro, or MCU-level energy/latency.

Model / Method

Model: GSDet; GSDet-Tiny

Architecture family: CNN

Techniques: Structural reparameterization, NDGraph pruning, group-level sparse training, channel feature knowledge distillation, model lightweighting

Framework: Not reported

Training type: Not reported

Inference type: Not reported

Hardware

Device: Intended AAV edge device not specified; NVIDIA GeForce RTX 3090 Ti GPU reported for experiments/training

Hardware type: GPU for experiments; edge device unspecified

Processor / microcontroller: NVIDIA GeForce RTX 3090 Ti; microcontroller not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Limited cloud access, communication constraints, limited edge computing resources, real-time inference, model parameters, computational complexity

Dataset

Name: AAVPV; PVEL2019; PVEL2021

Type: AAVPV private; PVEL public

Dataset size: AAVPV: 1021 training images and 92 test images; PVEL2019: 3706 images; PVEL2021: 21044 images

Number of classes: AAVPV: 3; PVEL: 8

Input resolution: Not reported

Data modality: Infrared drone images for AAVPV; photovoltaic electroluminescence images for PVEL

Metrics

Accuracy: Not reported

mAP: AAVPV GSDet: 0.378 mAP, 0.723 mAP50; AAVPV GSDet-Tiny: 0.341 mAP, 0.669 mAP50; PVEL2019 GSDet: 0.399 mAP, 0.633 mAP50; PVEL2019 GSDet-Tiny: 0.407 mAP, 0.657 mAP50

Precision: AAVPV GSDet-n: 0.778; AAVPV GSDet-n-Tiny-2x: 0.746

Recall: AAVPV GSDet-n: 0.692; AAVPV GSDet-n-Tiny-2x: 0.656

F1-score: Not reported

Latency: Not reported

FPS: AAVPV GSDet: 1087 FPS; AAVPV GSDet-Tiny: 1404.5 FPS; PVEL2019 GSDet: 1227.7 FPS; PVEL2019 GSDet-Tiny: 1434.4 FPS

Throughput: Reported as FPS

Model size: Not reported in MB

Parameters: AAVPV GSDet: 2.09 M; AAVPV GSDet-Tiny: 0.96 M; PVEL2019 GSDet: 2.09 M; PVEL2019 GSDet-Tiny: 0.77 M

MACs / FLOPs: GSDet: 5.9 GFLOPs; GSDet-Tiny: 2.9 GFLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Structural reparameterization module, NDGraph structured pruning, group-level sparse training, channel feature knowledge distillation

Quantization: Not reported

Pruning: Yes

Knowledge distillation: Yes

Compression method: NDGraph neuron-dependency pruning with 2x, 3x, 4x, and 5x compression rates

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Parameters and GFLOPs reported; model size in MB not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Edge computing is proposed to reduce cloud dependence, but inference communication requirements are not explicitly reported

Candidate for Strict TinyML: No

Reason: The paper targets edge computing but does not report MCU-class hardware, SRAM/Flash usage, energy per inference, bare-metal/RTOS execution, CMSIS-NN, or TensorFlow Lite Micro.

Benchmarking / Standardization

Benchmark used: AAVPV; PVEL2019; PVEL2021; VOC and COCO evaluation metrics

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, YOLOv8 baseline models

Comparison with previous works: Yes, Cascade-RCNN, MS-RCNN, YOLOX-l, PPYOLOE-s, RTMDet-s, DINO, RT-DETR, Faster RPAN-CNN, and BAF-Detector

Reproducibility artifacts available: Not reported

Results

Summary: GSDet and GSDet-Tiny reduce parameters and GFLOPs while maintaining competitive photovoltaic defect detection performance. GSDet-Tiny achieves 0.96 M parameters, 2.9 GFLOPs, 0.669 mAP50, and 1404.5 FPS on AAVPV.

Limitations: The paper states that the method mainly focuses on algorithmic lightweighting and that edge-device hardware constraints are not fully addressed.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: Yes, FPS only

Reports energy or power: No

Reports model size: Yes, parameters and GFLOPs only

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a lightweight edge computing photovoltaic defect detector, GSDet/GSDet-Tiny, using structural reparameterization, NDGraph pruning, and channel feature knowledge distillation to improve real-time detection efficiency.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Ye et al. | 2025 | Object Detection | GSDet-Tiny | Structural reparameterization + NDGraph pruning + CFKD | AAV edge device not specified; RTX 3090 Ti for experiments | AAVPV; PVEL2019; PVEL2021 | AAVPV mAP50 0.669; PVEL2019 mAP50 0.657 | N/A; 1404.5 FPS on AAVPV | N/A; 0.96 M parameters | N/A | N/A | N/A | N/A | N/A | None | No |
