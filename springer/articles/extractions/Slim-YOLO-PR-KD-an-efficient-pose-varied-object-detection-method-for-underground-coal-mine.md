Paper ID: Slim-YOLO-PR-KD-an-efficient-pose-varied-object-detection-method-for-underground-coal-mine

TinyML classification: Near-TinyML — Evaluated for edge/embedded mine vision with lightweight optimization, but no explicit MCU-class deployment is reported.

## Basic Info

Authors: Huaxing Mu; Jueting Liu; Yanyun Guan; Wei Chen; Tingting Xu; Zehua Wang

Year: 2024

Title: Slim-YOLO-PR_KD: an efficient pose-varied object detection method for underground coal mine

Source: Journal of Real-Time Image Processing, 21:160 

Type: Methodological

## Problem & Context

Task: Object detection

Objective: Improve real-time pose-varied object detection in underground coal mines under limited computing and storage resources.

Application domain: Underground coal mine monitoring

Scenario: Edge / embedded visual equipment for underground mining supervision

TinyML relevance: Partial

TinyML justification: The paper targets lightweight real-time object detection for visual equipment with limited computing and storage resources, but does not report MCU-class deployment or TinyML frameworks.

## Model / Method

Model: Slim-YOLO-PR_KD

Architecture family: CNN

Techniques: Lightweight YOLO design, knowledge distillation, efficient pose-varied attention, receptive field block variants, Ghost convolution, ScConv, shared-parameter detection head

Framework: Not reported

Training type: Not reported

Inference type: On-device edge inference implied; exact deployment setup not reported

## Hardware

Device: GTX 1650; Jetson Series referenced as comparable edge AI equipment

Hardware type: GPU / edge GPU

Processor / microcontroller: NVIDIA GTX 1650; specific Jetson model not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Limited computing resources, limited storage resources, limited energy supply, real-time performance, weak underground visual equipment, complex low-quality visual environment

## Dataset

Name: DsLMF+; DsLMF_1; DsLMF_2

Type: Public / available dataset

Dataset size: Not reported

Number of classes: DsLMF_1 has 8 behavior categories; DsLMF_2 includes 9 underground object categories and 8 guard-plate support status types

Input resolution: Not reported

Data modality: Underground visual images; video stream used for visualization comparison

## Metrics

Accuracy: Not reported

mAP: Slim-YOLO-PR_KD: DsLMF_1 mAP50 = 92.4, mAP50-95 = 76.7; DsLMF_2 mAP50 = 98.0, mAP50-95 = 82.9

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 67 FPS

Throughput: 67 FPS

Model size: Not reported

Parameters: 6.5M

MACs / FLOPs: 15.6B FLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: EPA module, RFB/RFB_SK module, C2f_GSG module, FS-Head shared-parameter detection head, Ghost convolution, ScConv, PIoU v2 loss, attention-guided knowledge distillation

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Yes

Compression method: Architectural slimming and attention-guided knowledge distillation; parameters reduced by 42% and computational complexity reduced by 46% compared with YOLOv8s baseline

Hardware-specific optimization: Not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 6.5M parameters; model size in MB not reported

Energy per inference reported: Not reported

Latency on target device reported: 67 FPS on GTX 1650; latency in ms not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets edge/embedded visual equipment but evaluates GPU-class hardware and does not report MCU-class memory, flash, energy, OS-free execution, or TensorFlow Lite Micro/CMSIS-NN deployment.

## Benchmarking / Standardization

Benchmark used: DsLMF+ underground comprehensive mining face image dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, YOLOv8s baseline

Comparison with previous works: Yes, compared with ViT Adapter-L, DETA, YOLOv5s, YOLOv5m, YOLOv7, CM-YOLO, YOLOv10s, YOLO-PR, and Slim-YOLO-PR

Reproducibility artifacts available: Dataset; code and model not reported

## Results

Summary: Slim-YOLO-PR_KD achieved 92.4 mAP50 and 76.7 mAP50-95 on DsLMF_1, and 98.0 mAP50 and 82.9 mAP50-95 on DsLMF_2. It reached 67 FPS with 6.5M parameters and 15.6B FLOPs, reducing parameters by 42% and computational complexity by 46% compared with YOLOv8s.

Limitations: Not reported

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

## Contribution

This paper proposes Slim-YOLO-PR_KD, a lightweight YOLO-based pose-varied object detection method using architectural slimming and attention-guided knowledge distillation for real-time underground coal mine monitoring.

## Comparative Table Output

| Paper     | Year | Task             | Model           | Technique                                 | Device                             | Dataset | Main Metric                               | Latency | Model Size      | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | ---------------- | --------------- | ----------------------------------------- | ---------------------------------- | ------- | ----------------------------------------- | ------- | --------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Mu et al. | 2024 | Object detection | Slim-YOLO-PR_KD | Lightweight YOLO + knowledge distillation | GTX 1650; Jetson Series referenced | DsLMF+  | mAP50-95 76.7 on DsLMF_1; 82.9 on DsLMF_2 | 67 FPS  | 6.5M parameters | N/A      | N/A   | N/A    | N/A       | N/A      | N/A           | No            |
