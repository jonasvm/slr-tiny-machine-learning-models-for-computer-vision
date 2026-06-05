Paper ID: Real-time-strawberry-detection-using-deep-neural-networks-on-embedded-system-RTSD-Net-An-edge-AI-application 

TinyML classification: Near-TinyML — uses embedded Jetson Nano edge hardware, but no explicit MCU-class deployment or MCU-level memory constraints.

## Basic Info

Authors: Yanchao Zhang; Jiya Yu; Yang Chen; Won Suk Lee; Wen Yang; Wenbo Zhang; Yong He

Year: 2022

Title: Real-time strawberry detection using deep neural networks on embedded system (RTSD-Net): An edge AI application

Source: Computers and Electronics in Agriculture, 192, 106586

Type: Experimental

## Problem & Context

Task: Object detection

Objective: Improve real-time strawberry detection speed on embedded edge hardware while maintaining detection accuracy.

Application domain: Smart agriculture; strawberry harvesting machinery

Scenario: Edge; embedded; agricultural machinery; UAV-collected field imagery

TinyML relevance: Partial

TinyML justification: The paper targets lightweight edge AI deployment on Jetson Nano, but does not report MCU-class deployment, SRAM/Flash constraints, or TensorFlow Lite Micro/CMSIS-NN use.

## Model / Method

Model: RTSD-Net

Architecture family: CNN

Techniques: Lightweight YOLOv4-tiny redesign; CSPNet replacement with CSPNet_F and CSPNet_S; reduced layers; reduced FLOPs; TensorRT acceleration; FP16 inference support; mosaic data augmentation; label smoothing; cosine annealing learning rate

Framework: PyTorch; ONNX; TensorRT

Training type: Not reported

Inference type: On-device

## Hardware

Device: NVIDIA Jetson Nano

Hardware type: SoC / GPU

Processor / microcontroller: Quad-core ARM Cortex-A57 CPU; Maxwell architecture 128-core GPU

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Cost, product volume, low power device, embedded compute capacity, latency/speed, model parameters, model size

## Dataset

Name: Strawberry dataset

Type: Author-collected / originally shared

Dataset size: Not reported

Number of classes: 3

Input resolution: 480 × 380 pixels after positive image segmentation

Data modality: Image

## Metrics

Accuracy: Not reported

mAP: 82.25% for RTSD-Net / Model E

Precision: Not reported

Recall: Not reported

F1-score: 79.00 for RTSD-Net / Model E

Latency: Not reported

FPS: 170 FPS on PC PTH; 13.1 FPS on Jetson Nano PTH/ONNX; 25.2 FPS on Jetson Nano TensorRT

Throughput: 25.2 FPS on Jetson Nano TensorRT

Model size: Not reported

Parameters: RTSD-Net parameters reduced by 44.05% compared with YOLOv4-tiny

MACs / FLOPs: 14.35 × 10^8 FLOPs for RTSD-Net / Model E

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: YOLOv4-tiny backbone simplification; reduced CSPNet complexity; reduced convolutional layers; TensorRT layer/tensor fusion; FP32-to-FP16 precision reduction described for inference

Quantization: FP16

Pruning: No

Knowledge distillation: No

Compression method: Architecture simplification and TensorRT serialization/layer fusion

Hardware-specific optimization: TensorRT acceleration on Jetson Nano

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 25.2 FPS on Jetson Nano TensorRT

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is Jetson Nano edge hardware with GPU/TensorRT support, not an MCU-class or bare-metal/RTOS TinyML device.

## Benchmarking / Standardization

Benchmark used: Author-collected strawberry detection dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO mentioned for context, not used as the main experimental benchmark

Comparison with baseline models: YOLOv3; YOLOv3-tiny; YOLOv4; YOLOv4-tiny; modified networks B, C, D, and E

Comparison with previous works: Related agricultural edge AI works are discussed, but the main quantitative comparison is against YOLO baselines and modified internal variants.

Reproducibility artifacts available: Dataset / model originally linked; corrigendum reports the link is no longer available and source code is shared by request

## Results

Summary: RTSD-Net achieved 82.25% mAP and 79.00 F1 while reducing FLOPs to 14.35 × 10^8. On Jetson Nano, TensorRT inference reached 25.2 FPS, faster than YOLOv4-tiny TensorRT at 21.9 FPS.

Limitations: Jetson Nano inference was much slower than PC inference, and the PTH-format model on Jetson Nano did not meet the real-time requirement before TensorRT acceleration.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

## Contribution

This paper proposes RTSD-Net, a simplified YOLOv4-tiny-based strawberry detection network optimized with reduced CSPNet structures and TensorRT deployment for real-time edge inference on Jetson Nano.

| Paper        | Year | Task             | Model    | Technique                                                   | Device      | Dataset            | Main Metric | Latency  | Model Size | SRAM/RAM | Flash | Energy | Framework                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ---------------- | -------- | ----------------------------------------------------------- | ----------- | ------------------ | ----------- | -------- | ---------- | -------- | ----- | ------ | ------------------------- | -------- | ------------- | ------------- |
| Zhang et al. | 2022 | Object detection | RTSD-Net | YOLOv4-tiny backbone simplification + TensorRT acceleration | Jetson Nano | Strawberry dataset | mAP 82.25%  | 25.2 FPS | N/A        | N/A      | N/A   | N/A    | PyTorch / ONNX / TensorRT | Mixed    | None          | No            |
