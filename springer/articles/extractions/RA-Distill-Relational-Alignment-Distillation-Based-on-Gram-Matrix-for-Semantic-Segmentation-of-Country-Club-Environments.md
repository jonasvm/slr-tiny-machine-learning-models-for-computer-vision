Paper ID: RA-Distill-Relational-Alignment-Distillation-Based-on-Gram-Matrix-for-Semantic-Segmentation-of-Country-Club-Environments

TinyML classification: Near-TinyML — Evaluated on embedded/edge hardware, but there is no explicit MCU-class or Cortex-M-level deployment evidence.

Basic Info

Authors: Yunseok Yang; Sang Jun Lee

Year: 2025

Title: RA-Distill: Relational Alignment Distillation Based on Gram Matrix for Semantic Segmentation of Country Club Environments

Source: International Journal of Control, Automation, and Systems, 23(11), 3349-3358 

Type: Methodological

Problem & Context

Task: Semantic segmentation

Objective: Improve lightweight semantic segmentation accuracy for autonomous golf cart perception while maintaining computational efficiency on resource-limited hardware.

Application domain: Autonomous driving in country club environments

Scenario: Embedded autonomous vehicle / edge perception

TinyML relevance: Partial

TinyML justification: The paper targets lightweight semantic segmentation for resource-limited embedded hardware and reports Jetson Nano latency/FPS, but does not report MCU-class deployment, SRAM/Flash constraints, TensorFlow Lite Micro, or ultra-low-power operation.

Model / Method

Model: RA-Distill with DeepLabV3+ teacher and student networks

Architecture family: CNN

Techniques: Knowledge distillation, relational alignment, Gram matrix, CKA similarity alignment, channel attention

Framework: Not reported

Training type: Transfer learning / fine-tuning

Inference type: On-device

Hardware

Device: NVIDIA Jetson Nano embedded board; NVIDIA RTX 3090 GPU used for experiments

Hardware type: SoC / GPU

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Computational complexity, memory, real-time processing, latency, resource-limited hardware

Dataset

Name: CC-dataset; CamVid

Type: Private / public

Dataset size: CC-dataset: 451 images, 355 training and 96 test; CamVid: 701 images, 367 training, 101 validation, and 233 test

Number of classes: CC-dataset: 5 classes; CamVid: 11-class protocol

Input resolution: CC-dataset: 1280 x 720; CamVid: 960 x 720; 720 x 720 used for FLOPs evaluation and random cropping

Data modality: Image

Metrics

Accuracy: Not reported

mAP: Not reported

Precision: CC-dataset: 88.51%; CamVid: 88.41%

Recall: CC-dataset: 84.07%; CamVid: 82.61%

F1-score: CC-dataset: 85.96%; CamVid: 85.10%

Latency: CC-dataset: 143.80 ms; CamVid: 110.58 ms

FPS: CC-dataset: 6.95 FPS; CamVid: 9.04 FPS

Throughput: CC-dataset: 6.95 FPS; CamVid: 9.04 FPS

Model size: Not reported

Parameters: Student model: 16.60M; Teacher model: 59.34M

MACs / FLOPs: CC-dataset student: 81.72G FLOPs; CamVid student: 81.77G FLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Knowledge distillation using Gram matrices from channel attention maps and CKA-based relational alignment

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Yes

Compression method: Teacher-student knowledge distillation into a lightweight student model

Hardware-specific optimization: Not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes, 143.80 ms on CC-dataset and 110.58 ms on CamVid using NVIDIA Jetson Nano

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports embedded Jetson Nano inference timing but does not provide MCU-class deployment, Cortex-M/TFLM evidence, SRAM/Flash usage, or energy measurements.

Benchmarking / Standardization

Benchmark used: CC-dataset; CamVid

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CamVid

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: RA-Distill achieved 77.20% mIoU and 85.96% F1-score on the CC-dataset, outperforming the teacher model and previous KD methods. On CamVid, RA-Distill achieved 76.16% mIoU and 85.10% F1-score while maintaining Jetson Nano inference latency comparable to other student models.

Limitations

Not reported

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes RA-Distill, a relational knowledge distillation framework that transfers inter-channel structural information from a DeepLabV3+ teacher to a lightweight student using Gram matrices and CKA for semantic segmentation.

| Paper       | Year | Task                  | Model                                     | Technique                                                            | Device             | Dataset            | Main Metric              | Latency                                    | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | --------------------- | ----------------------------------------- | -------------------------------------------------------------------- | ------------------ | ------------------ | ------------------------ | ------------------------------------------ | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Yang et al. | 2025 | Semantic segmentation | RA-Distill / DeepLabV3+ ResNet-18 student | Knowledge distillation with Gram matrix and CKA relational alignment | NVIDIA Jetson Nano | CC-dataset; CamVid | mIoU 77.20% (CC-dataset) | 143.80 ms (CC-dataset); 110.58 ms (CamVid) | N/A        | N/A      | N/A   | N/A    | N/A       | N/A      | N/A           | No            |
