Paper ID: Lightweight-Deep-Learning-Based-Intelligent-Edge-Surveillance-Techniques

TinyML classification: Near-TinyML — Evaluated on Jetson TX2 edge hardware with lightweight MobileNetV2-SSD/Tiny-YOLO, without explicit MCU-class deployment or memory constraints.

Basic Info

Authors: Yu Zhao, Yue Yin, Guan Gui

Year: 2020

Title: Lightweight Deep Learning Based Intelligent Edge Surveillance Techniques

Source: IEEE Transactions on Cognitive Communications and Networking 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Propose a lightweight intelligent edge surveillance method for detecting construction-site safety events while reducing computation cost, network traffic, delay, and operating cost.

Application domain: Intelligent surveillance; smart construction site; Industrial Internet of Things

Scenario: Edge-cloud surveillance system

TinyML relevance: Partial

TinyML justification: The paper targets lightweight edge AI computer vision on an NVIDIA Jetson TX2, but does not report MCU-class deployment, bare-metal/RTOS execution, or kilobyte-scale memory constraints.

Model / Method

Model: MobileNetV2-SSD and Tiny-YOLO at the edge node; YOLOV3 at the server side

Architecture family: CNN

Techniques: Depthwise separable convolution, lightweight backbone replacement, multi-scale object detection, edge-cloud partitioning, video compression and UDP transmission

Framework: Not reported

Training type: From scratch

Inference type: Hybrid

Hardware

Device: NVIDIA Jetson TX2 edge node; NVIDIA GTX 1080Ti server side

Hardware type: SoC / GPU

Processor / microcontroller: Edge node CPU: HMP Dual Denver 2/2 MB L2 + Quad ARM A57/2 MB L2; GPU: NVIDIA Pascal, 256 CUDA cores

Clock frequency: Not reported

SRAM / RAM: Edge node: 8 GB LPDDR4; server side: 128 GB LPDDR3

Flash / ROM / Storage: Edge node: 32 GB storage; server side: 3 TB storage

Power consumption: Edge node: 7.5 W; server side: 680 W

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: No

Constraints mentioned: Computational cost, network traffic, system delay, communication cost, storage, privacy, operating cost

Dataset

Name: Not reported

Type: Private

Dataset size: 100,000 level; training/validation split 7:3

Number of classes: Not reported

Input resolution: MobileNetV2-SSD: 300 × 300 × 3; Tiny-YOLO: Not reported

Data modality: Surveillance video / RGB images

Metrics

Accuracy: Not reported

mAP: YOLOV3 on GTX 1080Ti: 0.89; MobileNetV2-SSD on GTX 1080Ti: 0.68; Tiny-YOLO on Jetson TX2: 0.73; MobileNetV2-SSD on Jetson TX2: 0.68

Precision: 89% detection precision after edge-cloud joint computing

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: YOLOV3 on GTX 1080Ti: 18 FPS; MobileNetV2-SSD on GTX 1080Ti: 83 FPS; Tiny-YOLO on Jetson TX2: 12 FPS; MobileNetV2-SSD on Jetson TX2: 16 FPS

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Edge node: 7.5 W; server side: 680 W

Optimization

Techniques used: Depthwise separable convolution, MobileNetV2-SSD lightweight backbone, Tiny-YOLO reduced network depth, edge-cloud joint computing, video compression

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Lightweight CNN architecture using depthwise separable convolution; video compression before transmission

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: No

Fully on-device inference: No

Communication required during inference: Yes

Candidate for Strict TinyML: No

Reason: The system uses Jetson TX2 with Ubuntu and hybrid edge-cloud inference, without MCU-class deployment or strict memory/energy evidence.

Benchmarking / Standardization

Benchmark used: Private construction-site surveillance dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: YOLOV3, MobileNetV2-SSD, and Tiny-YOLO are compared by mAP and FPS on GTX 1080Ti and Jetson TX2.

Comparison with previous works: Not reported

Reproducibility artifacts available: Not reported

Results

Summary: The proposed edge-cloud INES system reached 16 FPS on Jetson TX2 using MobileNetV2-SSD and 12 FPS using Tiny-YOLO. The highest reported detection result was 0.89 mAP / 89% precision using server-side YOLOV3 after edge-cloud joint computing. The paper reports that the edge-device operating cost is one-tenth of the centralized server method.

Limitations

The paper reports that detection accuracy still has room for improvement and mentions weak system robustness as a future target.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a lightweight deep learning-based intelligent edge surveillance system that combines edge-side MobileNetV2-SSD/Tiny-YOLO pre-detection with cloud-side YOLOV3 confirmation for smart construction-site object detection.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Zhao et al. | 2020 | Object detection | MobileNetV2-SSD / Tiny-YOLO / YOLOV3 | Depthwise separable convolution and edge-cloud inference | NVIDIA Jetson TX2 | Private construction-site surveillance dataset | mAP 0.73 Tiny-YOLO on Jetson TX2; mAP 0.68 MobileNetV2-SSD on Jetson TX2 | N/A | N/A | 8 GB LPDDR4 | 32 GB storage | N/A | N/A | N/A | None | No |
