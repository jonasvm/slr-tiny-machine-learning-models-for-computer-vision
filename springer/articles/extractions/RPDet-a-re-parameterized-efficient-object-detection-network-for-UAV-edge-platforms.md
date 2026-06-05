Paper ID: RPDet-a-re-parameterized-efficient-object-detection-network-for-UAV-edge-platforms

TinyML classification: Near-TinyML — evaluated on Orin Nano and RK3588-RT edge platforms, but no explicit MCU-class deployment or microcontroller-level memory constraints are reported.

## Basic Info

Authors: Buhong Zhang, Zhigang Wang, Meibo Lv, Xiaodong Liu, Lei Zhang

Year: 2025

Title: RPDet: a re-parameterized efficient object detection network for UAV edge platforms

Source: Journal of Real-Time Image Processing 

Type: Experimental

## Problem & Context

Task: Object detection

Objective: To propose an efficient aerial object detector for UAV edge platforms that balances accuracy, speed, and energy efficiency.

Application domain: UAV aerial object detection

Scenario: Edge, embedded, autonomous system

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained UAV edge platforms and reports embedded deployment, FPS, power consumption, and efficiency, but does not target MCU-class TinyML deployment.

## Model / Method

Model: RPDet

Architecture family: CNN

Techniques: Re-parameterization, depthwise separable convolution, channel shuffle, lightweight feature fusion, channel attention, global context module

Framework: PyTorch 1.8.0; TensorRT-based FP16 optimization

Training type: Not reported

Inference type: On-device

## Hardware

Device: NVIDIA Jetson Orin Nano; RockChip RK3588-RT

Hardware type: GPU / NPU / SoC

Processor / microcontroller: NVIDIA Orin architecture with 32 Tensor Cores; RK3588-RT with CPU and three built-in NPUs

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: 12.5 W on Orin Nano; 11.2 W on RK3588-RT

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Power, payload, onboard resource limitations, computational complexity, real-time processing, energy efficiency

## Dataset

Name: VisDrone; HC-UAV

Type: Public / Private

Dataset size: VisDrone: 288 video sequences, 10,209 still images, over 2.6 million bounding boxes; HC-UAV: 20,676 images

Number of classes: VisDrone: Not reported; HC-UAV: 2

Input resolution: 640 × 640

Data modality: Aerial images; grayscale images for HC-UAV

## Metrics

Accuracy: Not reported

mAP: VisDrone: mAP0.5 = 0.462, mAP0.5:0.95 = 0.248, mAPs = 0.216; HC-UAV: mAP0.5 = 0.841, mAP0.5:0.95 = 0.375, mAPs = 0.362

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 173 FPS in dataset evaluation; 56.3 FPS on Orin Nano; 31.5 FPS on RK3588-RT

Throughput: Not reported

Model size: Not reported

Parameters: 6.1 M

MACs / FLOPs: 24.5 GFLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 12.5 W on Orin Nano; 11.2 W on RK3588-RT

## Optimization

Techniques used: Structural re-parameterization, Rep-DCSA, RepDFE, Rep-GFPN, FFM, IFEA, GC module, TensorRT-based FP16 optimization, INT8 quantization

Quantization: INT8 / FP16

Pruning: No

Knowledge distillation: No

Compression method: Structural re-parameterization

Hardware-specific optimization: TensorRT-based FP16 optimization on Orin Nano; INT8 quantization on RK3588-RT

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper evaluates RPDet on Jetson Orin Nano and RK3588-RT edge AI platforms, but does not report MCU-class deployment, SRAM/Flash constraints, bare-metal/RTOS execution, CMSIS-NN, or TensorFlow Lite Micro.

## Benchmarking / Standardization

Benchmark used: VisDrone; HC-UAV

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: VisDrone

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

## Results

Summary: RPDet achieved mAP0.5 of 0.462 on VisDrone and 0.841 on HC-UAV, with 6.1 M parameters, 24.5 GFLOPs, and 173 FPS in dataset evaluation. On embedded platforms, it achieved 56.3 FPS and 12.5 W on Orin Nano, and 31.5 FPS and 11.2 W on RK3588-RT.

Limitations

No explicit limitations section reported. Future work mentions incorporating infrared information to improve adaptability and robustness.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes RPDet, a re-parameterized CNN-based aerial object detector for UAV edge platforms that improves small-object detection accuracy, real-time performance, and energy efficiency through lightweight feature extraction, multi-scale feature fusion, and global context enhancement.

| Paper        | Year | Task             | Model | Technique                      | Device                      | Dataset          | Main Metric    | Latency | Model Size | SRAM/RAM | Flash | Energy         | Framework         | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | ---------------- | ----- | ------------------------------ | --------------------------- | ---------------- | -------------- | ------- | ---------- | -------- | ----- | -------------- | ----------------- | -------- | ------------- | ------------- |
| Zhang et al. | 2025 | Object Detection | RPDet | Structural re-parameterization | Jetson Orin Nano; RK3588-RT | VisDrone; HC-UAV | mAP0.5 = 0.841 | N/A     | N/A        | N/A      | N/A   | 12.5 W; 11.2 W | PyTorch; TensorRT | INT8     | None          | No            |
