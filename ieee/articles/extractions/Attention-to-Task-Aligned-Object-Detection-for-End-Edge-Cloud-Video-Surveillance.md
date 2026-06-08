Paper ID: Attention-to-Task-Aligned-Object-Detection-for-End-Edge-Cloud-Video-Surveillance

TinyML classification: Near-TinyML — Edge CV deployment with lightweight/quantized models, but no explicit MCU-class deployment or MCU-level memory constraints.

Basic Info

Authors: Yuanyuan Liu, Zhiyuan Yu, Danlong Zong, Lu Zhu

Year: 2024

Title: Attention to Task-Aligned Object Detection for End–Edge–Cloud Video Surveillance

Source: IEEE Internet of Things Journal, Vol. 11, No. 8, 15 April 2024 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Develop a lightweight object detection and keyframe-based video surveillance system for resource-constrained edge devices.

Application domain: Smart video surveillance

Scenario: End–edge–cloud video surveillance with edge inference and cloud upload of detection results/keyframes.

TinyML relevance: Partial

TinyML justification: The paper targets edge AI computer vision on Raspberry Pi 4B, Redmi 4A, Jetson Nano, and Jetson Orin AGX, but does not target MCU-class deployment.

Model / Method

Model: AT-YOLO and Micro-CNN keyframe algorithm

Architecture family: CNN

Techniques: SCDB backbone, depthwise separable convolution, residual skip connections, SE attention, AGT-head, spatial attention, PANet, CSPLayer, RFB, anchor-free detection, keyframe filtering, quantization

Framework: TensorFlow Lite; Python

Training type: Not reported

Inference type: Hybrid

Hardware

Device: Raspberry Pi 4B; Redmi 4A; Jetson Nano; Jetson Orin AGX

Hardware type: CPU / GPU / SoC / Mobile

Processor / microcontroller: Raspberry Pi 4B: 1.5-GHz 4-core ARM Cortex-A72; Redmi 4A: 1.4-GHz 8-core Snapdragon 425; Jetson Nano: 1.4-GHz 4-core ARM; Jetson Orin AGX: 2.2-GHz 12-core ARM

Clock frequency: 1.5 GHz; 1.4 GHz; 1.4 GHz; 2.2 GHz

SRAM / RAM: Raspberry Pi 4B: 4 GB RAM; Redmi 4A: 2 GB RAM; Jetson Nano: 4 GB RAM; Jetson Orin AGX: 64 GB RAM

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Computation, storage, latency, bandwidth, memory, edge-device resource constraints

Dataset

Name: MS COCO train2017; KITTI 2-D object detection; customized Stanford Dogs; CIFAR-10

Type: Public

Dataset size: COCO: 115,000 training images, 5,000 validation images, 2.5 million labeled instances; KITTI: 7,481 training images; Stanford Dogs: 150,466 training images and 6,000 validation images

Number of classes: COCO: 80; KITTI: 8; Stanford Dogs: 120; CIFAR-10: 10

Input resolution: AT-YOLO: 320×320 and 416×416; KITTI images: 1242×375; Micro-CNN input: 192×160×3

Data modality: RGB image and video stream

Metrics

Accuracy: 79.59% on customized Stanford Dogs backbone evaluation; 93.18% on CIFAR-10 with SC-DenseNet-40

mAP: COCO AT-YOLO 416: 29.9 mAP, 46.5 mAP50, 32.0 mAP75; COCO AT-YOLO 320: 26.2 mAP, 39.8 mAP50, 26.8 mAP75; KITTI: 85.75 mAP

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Raspberry Pi 4B AT-YOLO: 401.70 ms FP32, 403.12 ms FP16, 299.26 ms INT8; Redmi 4A: 546.23 ms FP32, 539.68 ms FP16, 318.3 ms INT8; Jetson Nano: 102.55 ms FP32, 96.3 ms FP16; Jetson Orin AGX: 11.07 ms FP32, 9.24 ms FP16, 8.19 ms INT8

FPS: System with keyframe algorithm: 13.69 FPS average and 27.09 FPS maximum on Raspberry Pi 4B; Micro-CNN: 64 FPS after quantization on Raspberry Pi

Throughput: Not reported

Model size: AT-YOLO on KITTI: 12.9 MB

Parameters: AT-YOLO: 3.47M on COCO; AT-YOLO: 3.44M on KITTI; Micro-CNN: 0.32M

MACs / FLOPs: AT-YOLO 416: 3.43 GFLOPs; AT-YOLO 320: 2.02 GFLOPs; AT-YOLO on KITTI: 6.47 GFLOPs

RAM usage: Maximum system memory consumption no more than 260 MB on Raspberry Pi 4B

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Lightweight architecture design, SCDB, depthwise separable convolution, residual connection, attention-based AGT-head, keyframe filtering, TensorFlow Lite quantization

Quantization: INT8; FP16 and FP32 also evaluated

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: SCDB structural compression and INT8 quantization

Hardware-specific optimization: TensorFlow Lite quantization and deployment on edge devices

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 12.9 MB for AT-YOLO on KITTI; 3.47M parameters for AT-YOLO on COCO

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Yes, detection results and keyframes are uploaded to the cloud service during system operation

Candidate for Strict TinyML: No

Reason: Deployment is on Raspberry Pi, mobile, and Jetson-class edge devices with GB-scale RAM, not MCU-class hardware with SRAM/Flash constraints.

Benchmarking / Standardization

Benchmark used: COCO, KITTI, customized Stanford Dogs, CIFAR-10

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO; KITTI; CIFAR-10

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: AT-YOLO achieved 29.9 mAP on COCO with 3.47M parameters and 85.75 mAP on KITTI with 3.44M parameters. The deployed Raspberry Pi 4B surveillance system achieved 13.69 FPS average and reduced bandwidth to 467.29 kb/s using the keyframe algorithm.

Limitations

The conclusion states that future work should explore more robust object detection under diverse outdoor environments and variable weather conditions.

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

Reports reproducibility artifacts: No

Contribution

This paper proposes AT-YOLO and a Micro-CNN keyframe algorithm for an end–edge–cloud video surveillance system that performs lightweight object detection on edge devices while reducing bandwidth and improving real-time performance.

| Paper      | Year | Task             | Model   | Technique                                           | Device                                                  | Dataset                              | Main Metric                          | Latency                                                     | Model Size | SRAM/RAM                           | Flash | Energy | Framework       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | ---------------- | ------- | --------------------------------------------------- | ------------------------------------------------------- | ------------------------------------ | ------------------------------------ | ----------------------------------------------------------- | ---------- | ---------------------------------- | ----- | ------ | --------------- | -------- | ------------- | ------------- |
| Liu et al. | 2024 | Object detection | AT-YOLO | SCDB + AGT-head + keyframe filtering + quantization | Raspberry Pi 4B; Redmi 4A; Jetson Nano; Jetson Orin AGX | COCO; KITTI; Stanford Dogs; CIFAR-10 | 29.9 mAP on COCO; 85.75 mAP on KITTI | 299.26 ms INT8 on Raspberry Pi 4B; 13.69 FPS system average | 12.9 MB    | 260 MB system RAM; 4 GB device RAM | N/A   | N/A    | TensorFlow Lite | INT8     | N/A           | No            |
