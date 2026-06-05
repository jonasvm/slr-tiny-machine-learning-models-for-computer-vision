Paper ID: Real-time-lightweight-strawberry-ripeness-detection-framework-based-on-YOLO11-deployed-on-edge-computing-platform

TinyML classification: Near-TinyML — Uses embedded edge deployment on Jetson AGX Orin, but does not report MCU-class deployment or microcontroller-level constraints.

Basic Info

Authors: Yang Gan; Xuefeng Ren; Huan Liu; Yongming Chen; Ping Lin

Year: 2025

Title: Real-time lightweight strawberry ripeness detection framework based on YOLO11 deployed on edge computing platform

Source: Journal of Food Measurement and Characterization, 19:8469–8491 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Real-time lightweight strawberry ripeness detection under complex agricultural environments for strawberry-picking robots.

Application domain: Smart agriculture / autonomous strawberry harvesting

Scenario: Edge / embedded agricultural robotics

TinyML relevance: Partial

TinyML justification: The paper targets embedded edge deployment on Jetson AGX Orin with FP16 quantization, model-size reduction, FPS, and power reporting, but does not target MCU-class or bare-metal TinyML deployment.

Model / Method

Model: SR-YOLO

Architecture family: CNN

Techniques: PConv-based Pela block, ELA attention, LAFPN, DySample, ASFF, Focaler-PIoU loss, FP16 quantization, TensorRT deployment

Framework: PyTorch, ONNX, TensorRT

Training type: Not reported

Inference type: On-device

Hardware

Device: NVIDIA Jetson AGX Orin

Hardware type: SoC / GPU

Processor / microcontroller: 12-core Arm Cortex-A78AE v8.2 64-bit CPU; NVIDIA Ampere GPU with 2048 CUDA cores and 64 Tensor Cores

Clock frequency: Not reported

SRAM / RAM: 64 GB 256-bit LPDDR5

Flash / ROM / Storage: 64 GB eMMC 5.1 storage

Power consumption: Approximately 22 W during continuous operation; 30 W power configuration used for inference

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, computing capability, latency, model size, power, real-time performance, complex backgrounds, occlusion, overlapping fruits

Dataset

Name: LSDS strawberry dataset; StrawDI_Db1; Straw_Rf; Straw_Sc

Type: Mixed public and private/in-house

Dataset size: LSDS has 5,500 original images; 14,300 images after augmentation; 66,913 annotated instances after augmentation

Number of classes: 3

Input resolution: 640×640

Data modality: RGB image

Metrics

Accuracy: Not reported

mAP: mAP50 92.1%; mAP95 75.0%; Jetson AGX Orin mAP50 84.3%

Precision: 91.3%

Recall: 85.3%

F1-score: Not reported

Latency: Not reported

FPS: 90.1 FPS on Jetson AGX Orin; 102.4 FPS reported in LSDS dataset comparison

Throughput: 90.1 FPS on Jetson AGX Orin

Model size: 5.1 MB on Jetson AGX Orin comparison

Parameters: 2.3 M

MACs / FLOPs: 5.8 G FLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Approximately 22 W; 4.1 FPS/W

Optimization

Techniques used: PConv-based Pela block, ELA attention, LAFPN, DySample, ASFF, Focaler-PIoU loss, ONNX export, TensorRT inference engine, FP16 quantization

Quantization: FP16

Pruning: No

Knowledge distillation: No

Compression method: Lightweight architectural redesign and FP16 quantization

Hardware-specific optimization: ONNX-to-TensorRT conversion and FP16 quantization on Jetson AGX Orin

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 5.1 MB

Energy per inference reported: Not reported

Latency on target device reported: 90.1 FPS reported; latency in milliseconds not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is Jetson AGX Orin with 64 GB LPDDR5 memory and TensorRT/FP16 inference, with no MCU-class, TFLM, SRAM/Flash, or bare-metal evidence.

Benchmarking / Standardization

Benchmark used: LSDS strawberry dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, YOLO11n baseline, feature-fusion variants, loss-function variants, and multiple YOLO-related models

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset available upon reasonable request; code and model not reported

Results

Summary: SR-YOLO achieved 91.3% precision, 85.3% recall, 92.1% mAP50, and 75.0% mAP95 with 2.3 M parameters and 5.8 G FLOPs. On Jetson AGX Orin, it achieved 90.1 FPS, 5.1 MB model size, approximately 22 W power consumption, and 4.1 FPS/W.

Limitations: The three-stage ripeness classification simplifies the continuous maturation process; generalization may be limited under heavy rain, dense fog, strong backlighting, or non-standard cultivation environments.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes SR-YOLO, a lightweight YOLO11-based strawberry ripeness detection framework using a PConv-based Pela block, LAFPN, Focaler-PIoU loss, and FP16 TensorRT deployment on Jetson AGX Orin.

| Paper      | Year | Task             | Model   | Technique                                         | Device          | Dataset                 | Main Metric | Latency  | Model Size | SRAM/RAM     | Flash      | Energy           | Framework             | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | ---------------- | ------- | ------------------------------------------------- | --------------- | ----------------------- | ----------- | -------- | ---------- | ------------ | ---------- | ---------------- | --------------------- | -------- | ------------- | ------------- |
| Gan et al. | 2025 | Object Detection | SR-YOLO | PConv/Pela + LAFPN + Focaler-PIoU + FP16 TensorRT | Jetson AGX Orin | LSDS strawberry dataset | mAP50 92.1% | 90.1 FPS | 5.1 MB     | 64 GB LPDDR5 | 64 GB eMMC | ~22 W; 4.1 FPS/W | PyTorch/ONNX/TensorRT | FP16     | None          | No            |
