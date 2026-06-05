Paper ID: Edge-AI-driven-Multi-camera-System-for-Adaptive-Robot-Speed-Control-in-Safety-critical-Environments

TinyML classification: Near-TinyML — uses embedded edge hardware with Jetson Nano, but there is no explicit MCU-class or ultra-low-power microcontroller deployment evidence.

## Basic Info

Authors: Nak-Won Choi, Yeong-Bin Kim, Bum Yong Park

Year: 2025

Title: Edge AI-driven Multi-camera System for Adaptive Robot Speed Control in Safety-critical Environments

Source: International Journal of Control, Automation, and Systems, 23(2), 489–497 

Type: Experimental

## Problem & Context

Task: Instance segmentation / object detection

Objective: Detect human workers using multiple RGB-D cameras and edge AI to adaptively reduce collaborative robot speed for safety.

Application domain: Collaborative robotics / industrial safety

Scenario: Edge AI, embedded SBC, human-robot collaboration

TinyML relevance: Partial

TinyML justification: The paper deploys YOLOv5n-seg on an NVIDIA Jetson Nano edge device, but does not target MCU-class or bare-metal TinyML deployment.

## Model / Method

Model: YOLOv5n-seg

Architecture family: CNN

Techniques: Instance segmentation, RGB-D image alignment, TensorRT FP16 optimization, ONNX conversion

Framework: PyTorch, ONNX, TensorRT, OpenCV, ROS

Training type: Not reported

Inference type: On-device edge inference

## Hardware

Device: NVIDIA Jetson Nano Developer Kit, Intel RealSense D435 cameras, Universal Robots UR3, Robotiq 2F-140 gripper

Hardware type: SoC / GPU

Processor / microcontroller: 128-core NVIDIA Maxwell GPU and quad-core ARM Cortex-A57 processor

Clock frequency: Not reported

SRAM / RAM: 4 GB LPDDR4

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Real-time latency, limited field of view, occlusion, communication bottlenecks, memory usage reduction with TensorRT

## Dataset

Name: Not reported

Type: Not reported

Dataset size: Not reported

Number of classes: 1 detected class reported: person

Input resolution: Combined RGB image 1280×480; each RGB frame 640×480

Data modality: RGB-D image

## Metrics

Accuracy: Not reported

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Object detection 119.62 ms and 122.47 ms; motion planning stop 686.85 ms and 683.93 ms; total robot speed-control response approximately 0.806 s

FPS: YOLOv5n-seg average FPS 8.27; inference-time FPS 10.46

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: TensorRT optimization, FP16 conversion, ONNX-to-TensorRT deployment

Quantization: FP16

Pruning: No

Knowledge distillation: No

Compression method: FP16 TensorRT engine conversion

Hardware-specific optimization: TensorRT acceleration on NVIDIA Jetson Nano GPU

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: ROS communication is used for robot control; no cloud communication is reported

Candidate for Strict TinyML: No

Reason: The deployment uses Jetson Nano with Ubuntu, ROS, GPU acceleration, and 4 GB LPDDR4 RAM rather than MCU-class hardware.

## Benchmarking / Standardization

Benchmark used: Gazebo simulation and actual collaborative robot experiment

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ISO/TS 15066 safety regulation

Comparison with baseline models: Not reported

Comparison with previous works: Qualitative comparison with prior RGB-D, UWB, HOG, Haar-like, and YOLO-based safety systems

Reproducibility artifacts available: Not reported

## Results

Summary: The system detected workers using YOLOv5n-seg on Jetson Nano and reduced UR3 joint speed from approximately 0.6 rad/s to 0.09 rad/s when the operator entered the safety range. The reported response time was approximately 0.806 s, and RGB-D distance error at 3 m averaged approximately 3.55%.

Limitations: The conclusion states that distance estimation should be improved by expanding the segmentation range to cover the entire object for more accurate worker position estimation.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes an edge AI-driven multi-camera RGB-D safety system that uses YOLOv5n-seg on Jetson Nano to detect workers, estimate distance, and adaptively control collaborative robot speed.

| Choi et al. | 2025 | Instance segmentation / object detection | YOLOv5n-seg | TensorRT FP16 optimization | NVIDIA Jetson Nano | N/A | Response time 0.806 s | 0.806 s | N/A | N/A | N/A | N/A | PyTorch / ONNX / TensorRT / ROS | FP16 | None | No |
