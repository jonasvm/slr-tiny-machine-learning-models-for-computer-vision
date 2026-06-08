Paper ID: A-Real-Time-Road-Damage-Detection-System-for-IoT-Edge-Devices-Using-Lightweight-Deep-Learning-Models

TinyML classification: Near-TinyML — uses edge-device deployment on Jetson Xavier NX, but does not provide MCU-class deployment evidence.

## Basic Info

Authors: Youxiang Huang; Zhuo Wang; Yue Yin; Zhiyi Lu; Yingfeng Ding; Donglai Jiao; Guan Gui

Year: 2025

Title: A Real-Time Road Damage Detection System for IoT Edge Devices Using Lightweight Deep Learning Models

Source: IEEE Internet of Things Journal, Vol. 12, No. 20, 15 October 2025 

Type: Experimental

## Problem & Context

Task: Object detection

Objective: Real-time road damage detection for IoT edge deployment.

Application domain: Road damage detection; pavement monitoring; smart transportation.

Scenario: IoT edge device; vehicle-mounted camera; edge-cloud road monitoring system.

TinyML relevance: Partial

TinyML justification: The paper deploys a lightweight quantized YOLOv5s model on an NVIDIA Jetson Xavier NX edge device, but does not target MCU-class or bare-metal TinyML deployment.

## Model / Method

Model: YOLOv5s

Architecture family: CNN

Techniques: Quantization; ONNX conversion; TensorRT deployment; DeepStream acceleration; edge-cloud integration.

Framework: PyTorch; ONNX; TensorRT; DeepStream

Training type: Not reported

Inference type: On-device inference with cloud transmission of detection results.

## Hardware

Device: NVIDIA Jetson Xavier NX edge device

Hardware type: SoC / GPU edge device

Processor / microcontroller: NVIDIA Jetson Xavier NX

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Computational resources, cost, latency, model size, processing speed, edge-device deployment, cloud communication/storage.

## Dataset

Name: RoadCAVS

Type: Private / self-collected real-world dataset

Dataset size: 15,612 images with 18,709 annotations; abstract reports 13,528 annotated frames.

Number of classes: 9

Input resolution: 640×480 raw images; preprocessed to 640×640.

Data modality: Video frames / road images from vehicle-mounted camera.

## Metrics

Accuracy: Not reported

mAP: YOLOv5s mAP = 68.00% at IoU 0.5; YOLOv5s standard verification mean = 90.99%.

Precision: Not reported

Recall: Not reported

F1-score: Reported as highest for YOLOv5s, but numeric value not reported.

Latency: Approximately 20 ms per image; benchmark inference time for YOLOv5s = 8.9 ms.

FPS: Not reported

Throughput: Not reported

Model size: 14.1 MB

Parameters: 7.2 M

MACs / FLOPs: 16.0 GFLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Lightweight YOLOv5s model selection; quantization; ONNX conversion; TensorRT engine deployment; DeepStream acceleration.

Quantization: Not reported; paper states the model is quantized but does not specify precision.

Pruning: No

Knowledge distillation: No

Compression method: Quantization; TensorRT optimization.

Hardware-specific optimization: TensorRT engine generated for NVIDIA Jetson platform using DeepStream.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 14.1 MB

Energy per inference reported: Not reported

Latency on target device reported: Approximately 20 ms per image

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Detection is performed on the edge device; results are uploaded to cloud for storage and analysis.

Candidate for Strict TinyML: No

Reason: Deployment uses NVIDIA Jetson Xavier NX edge hardware and does not report MCU-class deployment, SRAM/Flash constraints, bare-metal execution, or energy per inference.

## Benchmarking / Standardization

Benchmark used: RoadCAVS custom dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Faster R-CNN; SSD; YOLOv5l; YOLOv5m; YOLOv5s.

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

## Results

Summary: YOLOv5s achieved the best balance between accuracy and efficiency among the evaluated models, with 68.00% mAP at IoU 0.5, 14.1 MB model size, 7.2 M parameters, and 16.0 GFLOPs. The deployed system achieved approximately 20 ms per image on NVIDIA Jetson Xavier NX for real-time road damage detection.

Limitations

The dataset lacks images captured under poor lighting conditions. The GPS positioning system may have deviations. Detection accuracy is limited for pit, lateral crack, and longitudinal crack categories due to insufficient samples and similarity with road background.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes an end-to-end IoT edge road damage detection system using a lightweight YOLOv5s model deployed on NVIDIA Jetson Xavier NX with cloud-based storage and visualization.

| Paper        | Year | Task             | Model   | Technique                          | Device                  | Dataset  | Main Metric           | Latency      | Model Size | SRAM/RAM | Flash | Energy | Framework                              | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ---------------- | ------- | ---------------------------------- | ----------------------- | -------- | --------------------- | ------------ | ---------- | -------- | ----- | ------ | -------------------------------------- | -------- | ------------- | ------------- |
| Huang et al. | 2025 | Object detection | YOLOv5s | Quantization + TensorRT deployment | NVIDIA Jetson Xavier NX | RoadCAVS | mAP 68.00% at IoU 0.5 | ~20 ms/image | 14.1 MB    | N/A      | N/A   | N/A    | PyTorch + ONNX + TensorRT + DeepStream | N/A      | None          | No            |
