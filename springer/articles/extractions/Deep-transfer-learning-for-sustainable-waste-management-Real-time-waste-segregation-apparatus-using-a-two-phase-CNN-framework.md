Paper ID: Deep-transfer-learning-for-sustainable-waste-management-Real-time-waste-segregation-apparatus-using-a-two-phase-CNN-framework

TinyML classification: Near-TinyML — It uses low-power edge GPU hardware rather than explicit MCU-class deployment or MCU-level memory constraints.

Basic Info

Authors: Natheer Almtireen; Abdelrazzaq A. Abuhejleh; Mutaz Ryalat; Hisham Elmoaqet; Ghaith Al-refai

Year: 2025

Title: Deep transfer learning for sustainable waste management: Real-time waste segregation apparatus using a two-phase CNN framework

Source: The Journal of Supercomputing, 81:1411 

Type: Experimental

Problem & Context

Task: Classification

Objective: Automate segregation of plastic, paper, and metal waste using an AI-powered waste sorting apparatus.

Application domain: Sustainable waste management and recycling

Scenario: Edge, embedded, IoT-like smart waste sorting apparatus

TinyML relevance: Partial

TinyML justification: The paper targets low-power edge AI inference on NVIDIA Jetson Nano with ≤5 W operation and sub-200 ms latency, but it does not target MCU-class deployment or report MCU-level memory constraints.

Model / Method

Model: NASNet-Mobile; EfficientNet-B0; MobileNetV3-Large

Architecture family: CNN

Techniques: Transfer learning, fine-tuning, data augmentation, early stopping, TensorRT inference optimization, Grad-CAM, majority voting

Framework: TensorFlow/Keras, TF-TRT, NVIDIA TensorRT, TensorFlow runtime, NVIDIA JetPack SDK

Training type: Transfer learning / fine-tuning

Inference type: On-device

Hardware

Device: NVIDIA Jetson Nano Developer Kit with Raspberry Pi Camera Module 2 inside the AI-WSA apparatus

Hardware type: GPU / SoC

Processor / microcontroller: Quad-core ARM Cortex-A57 CPU and 128 CUDA-core GPU

Clock frequency: ARM Cortex-A57 @ 1.43 GHz

SRAM / RAM: 4 GB LPDDR4

Flash / ROM / Storage: Not reported

Power consumption: ≤5 W reported for the AI-WSA / Jetson Nano deployment; under 10 W also reported in comparative deployment discussion

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Power, latency, throughput, compute, safety delays, electromechanical reliability, real-time operation

Dataset

Name: Custom recyclable waste dataset

Type: Public + private/manual

Dataset size: 36,669 images; 25,667 training; 5,499 validation; 5,503 testing

Number of classes: 3

Input resolution: 224 × 224 pixels

Data modality: Image

Metrics

Accuracy: EfficientNet-B0: 91.6%; MobileNetV3-Large: 90.93%; NASNet-Mobile: 88.75%

mAP: N/A

Precision: EfficientNet-B0 macro precision: 91.67%

Recall: EfficientNet-B0 macro recall: 91.62%

F1-score: EfficientNet-B0 macro F1-score: 91.59%

Latency: Under 200 ms; average latency also reported as 200 ms per image

FPS: About 5 FPS

Throughput: EfficientNet-B0: about 20–23 items/min; MobileNetV3-Large: 21–24 items/min; safety-capped maximum: 30 items/min

Model size: Not reported

Parameters: EfficientNet-B0: 5.3M; NASNet-Mobile: 5.3M; MobileNetV3-Large: 5.4M

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: ≤5 W; under 10 W also reported in deployment comparison

Optimization

Techniques used: Transfer learning, fine-tuning, online data augmentation, early stopping, TensorRT / TF-TRT inference optimization, FP32 deployment, Grad-CAM analysis

Quantization: FP32

Pruning: No

Knowledge distillation: No

Compression method: Not reported

Hardware-specific optimization: NVIDIA TensorRT / TF-TRT optimization for Jetson Nano

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Under 200 ms on NVIDIA Jetson Nano

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: No cloud/offloading reported

Candidate for Strict TinyML: No

Reason: The deployment uses an NVIDIA Jetson Nano edge GPU/SoC with 4 GB RAM, not an MCU-class or bare-metal/RTOS TinyML platform.

Benchmarking / Standardization

Benchmark used: Custom recyclable waste dataset with 70/15/15 split and 3-fold cross-validation

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet used for pretrained model initialization, not as the target benchmark

Comparison with baseline models: Yes; NASNet-Mobile, EfficientNet-B0, and MobileNetV3-Large are compared

Comparison with previous works: Yes

Reproducibility artifacts available: Supplementary video; code, dataset, and model not reported

Results

Summary: EfficientNet-B0 achieved the best classification performance with 91.6% accuracy, 91.67% precision, 91.62% recall, and 91.59% F1-score. The deployed system achieved real-time inference under 200 ms on Jetson Nano, with practical throughput around 20–23 items/min for EfficientNet-B0 and 21–24 items/min for MobileNetV3-Large.

Limitations: Plastic classification remained difficult, with recall ≤87.59% across models. Future work suggests multispectral imaging, attention mechanisms, additional waste categories such as glass and e-waste, hardware optimization, and possible ensemble models with added computational cost.

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

This paper proposes an AI-powered waste sorting apparatus that combines a two-phase transfer learning CNN framework with NVIDIA Jetson Nano edge deployment for real-time classification and segregation of plastic, paper, and metal waste.

| Paper            | Year | Task           | Model           | Technique                                      | Device             | Dataset                         | Main Metric    | Latency | Model Size | SRAM/RAM               | Flash | Energy | Framework                          | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---: | -------------- | --------------- | ---------------------------------------------- | ------------------ | ------------------------------- | -------------- | ------- | ---------- | ---------------------- | ----- | ------ | ---------------------------------- | -------- | ------------- | ------------- |
| Almtireen et al. | 2025 | Classification | EfficientNet-B0 | Transfer learning + TensorRT FP32 optimization | NVIDIA Jetson Nano | Custom recyclable waste dataset | Accuracy 91.6% | <200 ms | N/A        | 4 GB LPDDR4; usage N/A | N/A   | N/A    | TensorFlow/Keras + TF-TRT/TensorRT | FP32     | None          | No            |
