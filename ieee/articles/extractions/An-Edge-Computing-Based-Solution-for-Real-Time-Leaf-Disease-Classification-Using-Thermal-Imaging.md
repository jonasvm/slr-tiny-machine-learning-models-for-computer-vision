Paper ID: An-Edge-Computing-Based-Solution-for-Real-Time-Leaf-Disease-Classification-Using-Thermal-Imaging 

TinyML classification: Near-TinyML — evaluated on Raspberry Pi 4B with Edge TPU/Intel NCS2 rather than MCU-class hardware.

Basic Info

Authors: Públio Elon Correa da Silva; Jurandy Almeida

Year: 2025

Title: An Edge Computing-Based Solution for Real-Time Leaf Disease Classification Using Thermal Imaging

Source: IEEE Geoscience and Remote Sensing Letters, Vol. 22, 2025, Article 7000105

Type: Experimental

Problem & Context

Task: Classification

Objective: Real-time leaf disease classification using thermal imaging on edge computing hardware.

Application domain: Agriculture; plant disease monitoring; crop health.

Scenario: Edge computing; embedded/IoT agricultural monitoring; Raspberry Pi 4B with hardware accelerators.

TinyML relevance: Partial

TinyML justification: The paper targets edge inference on Raspberry Pi 4B with Edge TPU and Intel NCS2 using compression, but does not target MCU-class TinyML hardware.

Model / Method

Model: MobileNetV1, MobileNetV2, VGG-16, InceptionV3

Architecture family: CNN

Techniques: Transfer learning, pruning, quantization-aware training, INT8 quantization, FP16 precision reduction, model compression, data augmentation.

Framework: TensorFlow, TensorFlow Lite, Edge TPU, OpenVINO

Training type: Transfer learning and fine-tuning

Inference type: On-device edge inference

Hardware

Device: Raspberry Pi 4B with 8-GB RAM; Coral USB Edge TPU; Intel NCS2; mobile phone with Infiray T3C thermal camera; RTX 3090 used for training.

Hardware type: CPU + NPU/VPU accelerator

Processor / microcontroller: Raspberry Pi 4B processor not reported; training used Intel Core i5 11400.

Clock frequency: Edge TPU standard and maximum frequency evaluated; exact clock frequency not reported.

SRAM / RAM: 8-GB RAM on Raspberry Pi 4B

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Latency, compute constraints, communication latency with cloud, model size, inference speed, resource-constrained edge deployment.

Dataset

Name: Self-collected thermal leaf disease dataset

Type: Public

Dataset size: 15,144 images reported in related-work discussion; 15,444 images reported in dataset section; 3340 test samples used for inference evaluation.

Number of classes: 7

Input resolution: Thermal camera resolution 384 × 288 pixels; model input resize value not reported.

Data modality: Grayscale thermal images

Metrics

Accuracy: Exact numerical table not reported; Fig. 5 reports approximately 92%–98% accuracy across models and platforms.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: TensorFlow Lite: MobileNetV1 107.67 ms, VGG16 152.22 ms, MobileNetV2 89.99 ms, InceptionV3 834 ms; Intel NCS2: MobileNetV1 24.10 ms, VGG16 52.90 ms, MobileNetV2 30.45 ms, InceptionV3 66.64 ms; Edge TPU Standard: MobileNetV1 47.36 ms, VGG16 47.65 ms, MobileNetV2 6.85 ms, InceptionV3 61.29 ms; Edge TPU Max: MobileNetV1 50.68 ms, VGG16 45.64 ms, MobileNetV2 5.39 ms, InceptionV3 59.71 ms.

FPS: TensorFlow Lite: MobileNetV1 8.67 FPS, VGG16 0.18 FPS, MobileNetV2 5.50 FPS, InceptionV3 1.18 FPS; Intel NCS2: MobileNetV1 22.51 FPS, VGG16 21.80 FPS, MobileNetV2 22.72 FPS, InceptionV3 17.32 FPS; Edge TPU Standard: MobileNetV1 26.20 FPS, VGG16 20.20 FPS, MobileNetV2 18.30 FPS, InceptionV3 14.36 FPS; Edge TPU Max: MobileNetV1 27.71 FPS, VGG16 17.18 FPS, MobileNetV2 21.49 FPS, InceptionV3 14.71 FPS.

Throughput: Not reported beyond FPS

Model size: Reported graphically in Fig. 5; approximately low-MB to 260 MB depending on model and platform; exact tabular values not reported.

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: 8-GB RAM device reported; runtime RAM usage not reported.

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Pruning, quantization-aware training, INT8 conversion for Edge TPU, FP16 precision reduction for OpenVINO/Intel NCS2, TensorFlow Lite conversion.

Quantization: INT8 / FP16 / QAT

Pruning: Yes

Knowledge distillation: No

Compression method: Pruning–quantization-aware training and precision reduction.

Hardware-specific optimization: Edge TPU-compatible TensorFlow Lite models and OpenVINO XML/bin files for Intel NCS2.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Local streaming from mobile phone thermal camera to Raspberry Pi via UDP; no cloud communication reported for inference.

Candidate for Strict TinyML: No

Reason: The deployment uses Raspberry Pi 4B with Edge TPU/Intel NCS2 accelerators and 8-GB RAM rather than MCU-class hardware or TensorFlow Lite Micro.

Benchmarking / Standardization

Benchmark used: Self-collected thermal leaf disease dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet pretrained weights used for transfer learning; not used as evaluation benchmark.

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: code / dataset

Results

Summary: The paper shows that pruning and quantization-aware training improve deployment feasibility for CNN-based thermal leaf disease classification on Raspberry Pi 4B with Edge TPU and Intel NCS2. MobileNetV1 achieved the highest reported FPS on Edge TPU Max, and MobileNetV2 achieved the lowest reported latency on Edge TPU Max.

Limitations

Thermal cameras are sensitive to daylight heat, which may affect accuracy. The method is currently limited to detecting a single disease per leaf.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes an edge computing-based real-time thermal leaf disease classification solution using compressed CNN models deployed on Raspberry Pi 4B with Edge TPU and Intel NCS2 acceleration.

| Correa da Silva et al. | 2025 | Classification | MobileNetV1, MobileNetV2, VGG-16, InceptionV3 | Pruning + QAT + precision reduction | Raspberry Pi 4B + Edge TPU/Intel NCS2 | Self-collected thermal leaf disease dataset | Accuracy approx. 92%–98% | 5.39 ms best reported | Approx. low-MB to 260 MB | 8 GB RAM device; runtime N/A | N/A | N/A | TensorFlow Lite / Edge TPU / OpenVINO | Mixed | None | No |
