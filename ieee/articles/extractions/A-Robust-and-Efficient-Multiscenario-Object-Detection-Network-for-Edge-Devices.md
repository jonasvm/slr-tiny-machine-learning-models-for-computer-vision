Paper ID: A-Robust-and-Efficient-Multiscenario-Object-Detection-Network-for-Edge-Devices

TinyML classification: Near-TinyML — uses edge GPU hardware rather than explicit MCU-class deployment.

Basic Info

Authors: Zhihuan Chen, Aiwen Luo, Lin Ding, Jialu Zheng, Zunkai Huang

Year: 2025

Title: A Robust and Efficient Multiscenario Object Detection Network for Edge Devices

Source: IEEE Geoscience and Remote Sensing Letters, Vol. 22, Article 6003205. 

Type: Methodological

Problem & Context

Task: Object detection

Objective: Improve the tradeoff between detection accuracy, model size, and inference speed for multiscenario object detection on edge devices.

Application domain: Remote sensing, UAV-based object detection, general object detection.

Scenario: Edge, embedded, UAV, remote sensing.

TinyML relevance: Partial

TinyML justification: The paper targets edge-device deployment on Jetson Xavier NX, but does not report MCU-class deployment or kilobyte-scale memory constraints.

Model / Method

Model: MCA-YOLO

Architecture family: CNN

Techniques: MSPP, Ghost-convolution-based G-ELAN, HAN, RepConv, lightweight YOLO architecture.

Framework: PyTorch 1.12.0, CUDA 11.6

Training type: From scratch; COCO pretraining also evaluated.

Inference type: On-device

Hardware

Device: Jetson Xavier NX embedded in Prometheus450 UAV

Hardware type: SoC / GPU

Processor / microcontroller: Six-core 64-bit ARMv8 CPU and 384-core Volta GPU

Clock frequency: Not reported

SRAM / RAM: 8 GB LPDDR4x

Flash / ROM / Storage: 32 GB eMMC 5.1

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Computation, latency, model parameters, FLOPs, limited hardware resources, battery.

Dataset

Name: VOC, COCO, SIMD, VisDrone

Type: Public

Dataset size: VOC: 16,551 trainval and 4,952 test images; COCO: 118,287 train and 5,000 minval images; SIMD: 5,000 images; VisDrone: 6,471 train and 548 val images.

Number of classes: VOC: 20; COCO: 80; SIMD: 15; VisDrone: Not reported.

Input resolution: 640 × 640 for model evaluation; 640 × 480 UAV camera.

Data modality: RGB images and UAV video stream.

Metrics

Accuracy: Not reported separately

mAP: VOC: 83.9 mAP50 and 61.8 mAP50:95 with pretraining; COCO: 39.2 AP50:95 and 58.3 AP50; SIMD: 82.5 mAP50 and 66.0 mAP50:95; VisDrone: 37.7 mAP50 and 19.8 mAP50:95.

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: VOC: 334.9 FPS; COCO: 69.6 FPS; SIMD: 36.4 FPS; VisDrone: 34.8 FPS.

Throughput: Reported as FPS.

Model size: Not reported

Parameters: 6.3M on VOC, SIMD, and VisDrone; 6.5M on COCO.

MACs / FLOPs: 12.4 GFLOPs on VOC; 12.3 GFLOPs on SIMD and VisDrone.

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: MSPP, GC-based G-ELAN, HAN, RepConv, lightweight architectural design.

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Ghost convolution for lower computational cost; no explicit compression method reported.

Hardware-specific optimization: Not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Parameters reported; storage size not reported.

Energy per inference reported: Not reported

Latency on target device reported: Not reported; FPS reported on Jetson Xavier NX.

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No offloading reported; detection results are transmitted wirelessly to a ground station.

Candidate for Strict TinyML: No

Reason: The deployment uses Jetson Xavier NX with 8 GB RAM and a Volta GPU, not MCU-class hardware.

Benchmarking / Standardization

Benchmark used: VOC, COCO, SIMD, VisDrone

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: VOC, COCO, VisDrone

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Code

Results

Summary: MCA-YOLO achieves real-time object detection on Jetson Xavier NX with 36.4 FPS on SIMD and 34.8 FPS on VisDrone. It reports 82.5 mAP50 / 66.0 mAP50:95 on SIMD and 37.7 mAP50 / 19.8 mAP50:95 on VisDrone.

Limitations

Accuracy improvement remains possible; future work will focus on advanced feature extraction and data augmentation without increasing computational complexity.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes MCA-YOLO, a lightweight YOLOv7-tiny-based object detection network using MSPP, G-ELAN, Ghost convolution, and HAN for efficient multiscenario edge-device detection.

| Chen et al. | 2025 | Object detection | MCA-YOLO | MSPP + G-ELAN + HAN with Ghost convolution | Jetson Xavier NX UAV | VOC; COCO; SIMD; VisDrone | SIMD: 82.5 mAP50 / 66.0 mAP50:95; VisDrone: 37.7 mAP50 / 19.8 mAP50:95 | N/A; 36.4 FPS SIMD, 34.8 FPS VisDrone | 6.3M parameters | 8 GB LPDDR4x | 32 GB eMMC 5.1 | N/A | PyTorch 1.12.0 / CUDA 11.6 | N/A | None | No |
