Paper ID: DIR-BHRNet-A-Lightweight-Network-for-Real-Time-Vision-Based-Multiperson-Pose-Estimation-on-Smartphones

TinyML classification: Near-TinyML — Evaluated on smartphones with mobile CPUs, without explicit MCU-class deployment or kilobyte/low-megabyte memory constraints.

Basic Info

Authors: Gongjin Lan, Yu Wu, Qi Hao

Year: 2024

Title: DIR-BHRNet: A Lightweight Network for Real-Time Vision-Based Multiperson Pose Estimation on Smartphones

Source: IEEE Transactions on Industrial Informatics, Vol. 20, No. 11

Type: Experimental

Problem & Context

Task: Multiperson pose estimation / keypoint detection

Objective: Develop a lightweight network for real-time multiperson pose estimation on smartphones.

Application domain: Human pose estimation for human-machine systems, human-computer interaction, sports analysis, healthcare, robotics, and entertainment.

Scenario: Mobile, on-device, smartphone-based vision inference.

TinyML relevance: Partial

TinyML justification: The paper targets real-time on-device computer vision on Android smartphones, but does not target MCU-class or bare-metal TinyML deployment.

Model / Method

Model: DIR-BHRNet

Architecture family: CNN

Techniques: Dense inverted residual module, depthwise convolution, shortcut connection, balanced HRNet architecture, computational cost balancing.

Framework: PyTorch, ONNX, NCNN, Android Studio

Training type: Not reported

Inference type: On-device

Hardware

Device: Xiaomi 10, Xiaomi 12, Redmi K40 Android smartphones

Hardware type: Mobile / CPU / SoC

Processor / microcontroller: Snapdragon 865, Snapdragon 870, Snapdragon 8

Clock frequency: Not reported

SRAM / RAM: 8 GB and 12 GB smartphone memory; measured program memory usage ranges from 80 MB to 172 MB.

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Computational cost, latency, memory usage, real-time inference, low-performance mobile computing hardware.

Dataset

Name: COCO, CrowdPose

Type: Public

Dataset size: COCO has over 200k images and 250k annotated person instances; CrowdPose has over 20k images and 80k annotated person instances.

Number of classes: Not reported; COCO uses 17 keypoints per person.

Input resolution: 256 × 256, 384 × 384, 512 × 512

Data modality: RGB image / smartphone camera image

Metrics

Accuracy: Not reported

mAP: DIR-BHRNet-32 reports 50.5 mAP on COCO and 52.4 mAP on CrowdPose.

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: DIR-BHRNet-32 at 384 × 384 reports 95.2 ms on Redmi K40, 87.7 ms on Xiaomi 10, and 84.7 ms on Xiaomi 12.

FPS: DIR-BHRNet-32 at 384 × 384 reports 10.5 FPS on Redmi K40, 11.4 FPS on Xiaomi 10, and 11.8 FPS on Xiaomi 12.

Throughput: 10.5–11.8 FPS for DIR-BHRNet-32 at 384 × 384 on tested smartphones.

Model size: Not reported

Parameters: DIR-BHRNet-32 reports 6.03M parameters.

MACs / FLOPs: DIR-BHRNet-32 reports 6.32 GFLOPs.

RAM usage: DIR-BHRNet reports 90 MB at 256 × 256, 125 MB at 384 × 384, and 172 MB at 512 × 512.

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Lightweight CNN design using DIR modules, depthwise convolution, shortcut connection, balanced branch computation, and NCNN mobile deployment.

Quantization: Not reported

Pruning: No

Knowledge distillation: No

Compression method: Lightweight architecture design

Hardware-specific optimization: NCNN deployment optimized for mobile phone CPUs.

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

Communication required during inference: No

Candidate for Strict TinyML: No

Reason: The paper deploys on Android smartphones with 8 GB or 12 GB RAM and does not report MCU-class, bare-metal, RTOS, SRAM, Flash, or energy constraints.

Benchmarking / Standardization

Benchmark used: COCO, CrowdPose, OKS-based mAP

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO, CrowdPose

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Code, Android executable file, video

Results

Summary: DIR-BHRNet-32 achieves 50.5 mAP on COCO and 52.4 mAP on CrowdPose with 6.03M parameters and 6.32 GFLOPs. On Android smartphones, it runs above 10 FPS at 384 × 384 input resolution with 125 MB memory usage.

Limitations: Not reported; future work mentions attention mechanisms and real-time 3-D multiperson pose estimation on smartphones.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes DIR-BHRNet, a lightweight CNN architecture combining dense inverted residual modules and a balanced HRNet structure for real-time multiperson pose estimation on Android smartphones.

| Lan et al. | 2024 | Multiperson pose estimation | DIR-BHRNet | Lightweight architecture with depthwise convolution and balanced HRNet | Android smartphones | COCO, CrowdPose | 50.5 mAP COCO; 52.4 mAP CrowdPose | 84.7–95.2 ms | N/A | 125 MB | N/A | N/A | PyTorch/ONNX/NCNN | N/A | None | No |
