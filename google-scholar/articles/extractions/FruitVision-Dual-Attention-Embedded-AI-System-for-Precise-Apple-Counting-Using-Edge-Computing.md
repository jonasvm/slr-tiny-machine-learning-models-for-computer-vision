Paper ID: FruitVision-Dual-Attention-Embedded-AI-System-for-Precise-Apple-Counting-Using-Edge-Computing

TinyML classification: Near-TinyML — evaluated on Jetson Nano edge hardware, but no explicit MCU-class deployment or Cortex-M/TFLite Micro-level constraints are reported.

Basic Info

Authors: Divyansh Thakur; Vikram Kumar

Year: 2024

Title: FruitVision: Dual-Attention Embedded AI System for Precise Apple Counting Using Edge Computing

Source: IEEE Transactions on Agrifood Electronics, Vol. 2, No. 2, September/October 2024 

Type: Experimental

Problem & Context

Task: Object Detection

Objective: Precise apple fruit detection and counting using an embedded edge AI system.

Application domain: Precision agriculture / smart farming

Scenario: Edge, embedded, IoT, agricultural field deployment

TinyML relevance: Partial

TinyML justification: The paper deploys improved YOLOv7 on NVIDIA Jetson Nano with a DepthAI camera for on-device edge inference, but it does not target MCU-class hardware or report MCU-level memory/energy constraints.

Model / Method

Model: Improved YOLOv7 with Global-SE Unified Attention Mechanism (GSEAM) and GELU activation

Architecture family: CNN

Techniques: Dual attention mechanism, GELU activation, data augmentation, color-space preprocessing, TensorRT optimization, ONNX conversion, optional quantization

Framework: PyTorch, NVIDIA JetPack SDK, CUDA, cuDNN, TensorRT, OpenCV, Oak-D SDK

Training type: Not reported

Inference type: On-device

Hardware

Device: NVIDIA Jetson Nano + Oak-D Lite DepthAI camera

Hardware type: SoC / GPU / embedded AI camera

Processor / microcontroller: Quad-core ARM Cortex-A57 @ 1.43 GHz; 128-core NVIDIA Maxwell GPU; Oak-D Lite RVC2 core

Clock frequency: 1.43 GHz CPU; memory 1600 MHz

SRAM / RAM: 4 GB 64-bit LPDDR4

Flash / ROM / Storage: Not reported

Power consumption: Depends on workload and peripherals

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Latency, compute efficiency, memory footprint reduction through quantization, edge inference, real-time processing

Dataset

Name: Self-created apple fruit dataset

Type: Private

Dataset size: 9,000 images

Number of classes: 1

Input resolution: 416 × 416 pixels

Data modality: RGB images and derived color-space images including LAB, HSV, CMYK, grayscale, CB channel, and CR channel

Metrics

Accuracy: Not reported

mAP: Not reported; AP = 99.13%

Precision: 99.54%

Recall: 98.94%

F1-score: 99.71%

Latency: 0.0549 s reported; Table VI reports IT values from 0.0284 s to 0.0700 s

FPS: Average 130 FPS reported; Table VI reports 120.0 to 135.0 FPS

Throughput: 130 FPS

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported numerically

Optimization

Techniques used: GSEAM dual attention, GELU activation, TensorRT optimization, ONNX conversion, optional quantization, data augmentation, color-space preprocessing

Quantization: Not reported; quantized and nonquantized models are evaluated, but quantization type is not specified

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Quantization, type not specified

Hardware-specific optimization: TensorRT optimization for Jetson GPU inference

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is NVIDIA Jetson Nano running JetPack Linux with GPU acceleration, not an MCU-class or bare-metal/RTOS TinyML platform.

Benchmarking / Standardization

Benchmark used: Self-created apple fruit dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: None

Comparison with baseline models: SSD, Faster R-CNN, YOLOv5, YOLOv7, DETR, SAM, CBAM

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: The proposed improved YOLOv7 model achieved 99.54% precision, 98.94% recall, 99.71% F1-score, and 99.13% AP for apple detection/counting. The system was deployed on NVIDIA Jetson Nano with a DepthAI camera and reported real-time performance of approximately 130 FPS.

Limitations

The paper reports challenges with distinguishing apples from background objects in cluttered orchard scenes, lighting variation, occlusion, overlapping fruits, fruit deformities, color variation, immature fruits, partially obscured fruits, false positives, false negatives, and localization errors.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an embedded edge AI apple-counting system that integrates an improved YOLOv7 model with a Global-SE dual attention mechanism, NVIDIA Jetson Nano, and a DepthAI camera for real-time apple detection and counting.

| Paper         | Year | Task             | Model                      | Technique                                             | Device                                         | Dataset                                  | Main Metric | Latency  | Model Size | SRAM/RAM    | Flash | Energy | Framework                    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | ---------------- | -------------------------- | ----------------------------------------------------- | ---------------------------------------------- | ---------------------------------------- | ----------- | -------- | ---------- | ----------- | ----- | ------ | ---------------------------- | -------- | ------------- | ------------- |
| Thakur et al. | 2024 | Object Detection | Improved YOLOv7 with GSEAM | Dual attention + TensorRT optimization + quantization | NVIDIA Jetson Nano + Oak-D Lite DepthAI camera | Self-created apple dataset, 9,000 images | AP 99.13%   | 0.0549 s | N/A        | 4 GB LPDDR4 | N/A   | N/A    | PyTorch / TensorRT / JetPack | N/A      | None          | No            |
