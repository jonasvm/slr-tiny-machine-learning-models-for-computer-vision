Paper ID: DCGAN-Driven-Minority-Class-Augmentation-for-Lightweight-YOLO-Based-Photovoltaic-Defect-Localization-Suitable-for-Edge-Deployment

TinyML classification: Near-TinyML — Evaluated on Google Coral Dev Board/Edge TPU with TFLite and ∼2 W inference, which is edge hardware but not MCU-class.

Basic Info

Authors: Nakka Saampotth Maddileti; Rupesh Namburi; Rayappa David Amar Raj; Rama Muni Reddy Yanamala; Archana Pallakonda 

Year: 2025

Title: DCGAN-Driven Minority Class Augmentation for Lightweight YOLO-Based Photovoltaic Defect Localization Suitable for Edge Deployment

Source: IEEE Transactions on Device and Materials Reliability, Vol. 25, No. 3, September 2025

Type: Experimental

Problem & Context

Task: Object Detection

Objective: Real-time localization of photovoltaic faults in electroluminescence images using a lightweight YOLO-based detector suitable for edge deployment.

Application domain: Photovoltaic defect detection / solar inspection

Scenario: Edge, embedded, drone-based solar inspection, portable diagnostic devices

TinyML relevance: Partial

TinyML justification: The paper targets low-power edge deployment on Google Coral Edge TPU with TensorFlow Lite, but does not target MCU-class deployment or report MCU-level SRAM/Flash constraints. 

Model / Method

Model: YOLOv11n-GhostLite

Architecture family: CNN

Techniques: DCGAN-based synthetic augmentation, GhostConv, C3k2 residual blocks, GhostSPPF, C2PSA attention, anchor-free detection head, dynamic label assignment, TensorFlow Lite conversion, Edge TPU compilation

Framework: TensorFlow Lite; Edge TPU Compiler

Training type: Not reported

Inference type: on-device

Hardware

Device: Google Coral Dev Board with Edge TPU

Hardware type: NPU / SoC

Processor / microcontroller: NXP i.MX 8M Quad-core Cortex-A53; Google Edge TPU coprocessor

Clock frequency: Not reported

SRAM / RAM: 512 MB LPDDR4

Flash / ROM / Storage: 8 GB eMMC + microSD card support

Power consumption: Approximately 2 W during inference

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Power, latency, compute, parameters, GFLOPs, resource-limited deployment

Dataset

Name: PVEL-AD; PV Multi-Defect

Type: PVEL-AD: public; PV Multi-Defect: not reported; DCGAN synthetic augmentation used

Dataset size: PVEL-AD: 36,543 near-infrared images and 37,380 annotated bounding boxes; PV Multi-Defect: 1,108 grayscale images and 4,235 annotated defects

Number of classes: PVEL-AD: one defect-free class and ten defect types / eight annotated categories reported; PV Multi-Defect: five categories

Input resolution: PVEL-AD: 1024 × 1024; PV Multi-Defect: 600 × 600; training image size: 640 × 640

Data modality: Electroluminescence images; near-infrared images; grayscale images

Metrics

Accuracy: Not reported

mAP: PVEL-AD: 97.2% mAP@50 and 83.4% mAP@[50:95]; PV Multi-Defect: 96.4% mAP@50 and 76.5% mAP@[50:95] 

Precision: PVEL-AD: 93.7%; PV Multi-Defect: 93.9%

Recall: PVEL-AD: 96%; PV Multi-Defect: 93.5%

F1-score: Not reported

Latency: 2.2 ms reported in model comparison; 1904.33 ms per image on Edge TPU deployment

FPS: Over 30 FPS on embedded GPUs

Throughput: Not reported

Model size: Not reported as file size

Parameters: 2.34M

MACs / FLOPs: 6.2 GFLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Approximately 2 W during inference

Optimization

Techniques used: Lightweight YOLOv11n-GhostLite architecture, GhostConv, GhostSPPF, C2PSA attention, DCGAN augmentation, TensorFlow Lite quantized model conversion, Edge TPU compilation

Quantization: not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Lightweight architecture using GhostConv/GhostSPPF and quantized TensorFlow Lite deployment

Hardware-specific optimization: TensorFlow Lite conversion and Edge TPU Compiler for Google Coral Edge TPU

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 2.34M parameters; file size not reported

Energy per inference reported: Not reported

Latency on target device reported: 1904.33 ms per image on Edge TPU

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The target platform is a Linux-based Google Coral Dev Board with Edge TPU and 512 MB RAM, not an MCU-class device with reported SRAM/Flash constraints.

Benchmarking / Standardization

Benchmark used: PVEL-AD; PV Multi-Defect

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: not reported

Results

Summary: YOLOv11n-GhostLite with DCGAN augmentation achieved 97.2% mAP@50 on PVEL-AD and 96.4% mAP@50 on PV Multi-Defect with 2.34M parameters and 6.2 GFLOPs. Deployment on Google Coral Edge TPU reported approximately 1904.33 ms per image and ~2 W during inference.

Limitations

The paper reports weaker performance for subtle defects such as crack, finger, and scratch due to similar background textures, class imbalance, lightweight-model constraints, and possible annotation inconsistency. It also notes potential difficulty in real-world settings with variable lighting, occlusions, or subtle defects not represented in training data.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes YOLOv11n-GhostLite with DCGAN-based minority-class augmentation for lightweight photovoltaic defect localization and edge deployment on Google Coral Edge TPU.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Maddileti et al. | 2025 | Object Detection | YOLOv11n-GhostLite | DCGAN augmentation + lightweight YOLO/Ghost modules | Google Coral Dev Board Edge TPU | PVEL-AD; PV Multi-Defect | 97.2% mAP@50 / 96.4% mAP@50 | 1904.33 ms/image on Edge TPU | N/A | 512 MB RAM | 8 GB eMMC + microSD | N/A | TensorFlow Lite | N/A | None | No |
