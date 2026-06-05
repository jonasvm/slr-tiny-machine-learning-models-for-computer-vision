Paper ID: Real-time-rapid-visual-fish-disease-detection-system-based-on-tiny-machine-learning

TinyML classification: Strict TinyML — explicitly targets microcontroller-based TinyML deployment with on-device real-time inference and resource-constrained hardware metrics.

Basic Info

Authors: Jiayi Wang; Yihan Yin; Jinqi Yang; Feiyu Zhu; Daoliang Li; Yang Wang

Year: 2025

Title: Real-time rapid visual fish disease detection system based on tiny machine learning

Source: Aquaculture International, 33:584 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Develop a real-time, on-site fish disease detection system using TinyML and machine vision for resource-constrained aquaculture environments.

Application domain: Aquaculture fish disease detection

Scenario: Edge, embedded, microcontroller-based, off-grid aquaculture monitoring

TinyML relevance: Yes

TinyML justification: The paper deploys an optimized YOLO11n model on an SG2002 RISC-V microcontroller with fully local inference, reported flash usage, latency, and power consumption.

Model / Method

Model: YOLO11n fish disease detection model

Architecture family: CNN

Techniques: Depthwise separable convolutions, channel-wise attention, CIoU loss, FP16 mixed-precision quantization, quantization-aware training, pruning

Framework: Ultralytics YOLO11; embedded deployment framework not reported

Training type: Not reported

Inference type: On-device

Hardware

Device: Waterproof fish disease detection device based on SG2002 RISC-V platform

Hardware type: MCU / NPU / SoC

Processor / microcontroller: Sanechip SG2002 RISC-V C906 with integrated NPU

Clock frequency: 1× core up to 1 GHz; 1× RISC-V C906 core up to 700 MHz; low-power 8051 core at 25–300 MHz

SRAM / RAM: 256 MB DDR3 RAM

Flash / ROM / Storage: TF card for flash; YOLO11n flash usage 5332 KB

Power consumption: 1.82 W active inference; 0.67 W idle monitoring; 1.05 W mixed average

Energy per inference: Not reported

Execution without full OS: Yes; real-time operating system reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, compute, communication, off-grid deployment, resource-constrained edge vision

Dataset

Name: Custom largemouth bass fish disease dataset

Type: Private

Dataset size: 914 images; 640 training, 137 validation, 137 testing

Number of classes: 2

Input resolution: 640×640

Data modality: RGB/color fish images from camera/video acquisition

Metrics

Accuracy: Not reported

mAP: mAP50–95 = 0.736; fivefold cross-validation mean mAP50–95 = 0.734, SD = 0.012; FP32 baseline mAP50–95 = 0.742

Precision: 95% CI = 0.918–0.949; point estimate not reported

Recall: 95% CI = 0.902–0.934; point estimate not reported

F1-score: Not reported

Latency: 40.7 ms on SG2002 RISC-V device

FPS: 10–30 FPS frame acquisition rate; inference FPS not reported

Throughput: Not reported

Model size: Not separately reported; YOLO11n flash usage 5332 KB

Parameters: Absolute parameter count not reported; approximately 45% parameter reduction reported

MACs / FLOPs: Absolute MACs/FLOPs not reported; approximately 50% FLOPs reduction reported

RAM usage: 256 MB DDR3 device memory; runtime RAM usage not reported

Flash usage: 5332 KB for YOLO11n

Energy per inference: Not reported

Power consumption: 1.82 W active inference; 0.67 W idle monitoring; 1.05 W mixed average

Optimization

Techniques used: Depthwise separable convolutions, channel-wise attention, CIoU loss, FP16 mixed-precision quantization, QAT, pruning, DMA transfer, hardware-accelerated bilinear interpolation, DVFS

Quantization: FP16 / mixed precision / QAT

Pruning: Yes

Knowledge distillation: Not reported

Compression method: FP16 quantization, pruning, depthwise separable convolution

Hardware-specific optimization: SG2002 deployment, NPU use, DMA frame transfer, external flash to on-chip SRAM loading, hardware-accelerated bilinear interpolation, DVFS, RTOS-based processing

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: 5332 KB

Model size reported: 5332 KB flash usage; separate model size not reported

Energy per inference reported: Not reported

Latency on target device reported: 40.7 ms on SG2002 RISC-V device

Runs without full operating system: Yes; real-time operating system reported

Fully on-device inference: Yes

Communication required during inference: No; Wi-Fi/BLE are used for optional data transfer and monitoring

Candidate for Strict TinyML: Yes

Reason: The system explicitly targets microcontroller-based TinyML deployment with fully on-device inference and reports target-device flash, latency, RAM, and power constraints.

Benchmarking / Standardization

Benchmark used: Custom fish disease dataset; COCO small-object subset mentioned for empirical evaluation of separable-convolution design

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO small-object subset mentioned

Comparison with baseline models: YOLO11n compared with YOLO11s, YOLOv8n, and YOLOv5n; FP32 baseline compared with FP16 QAT model

Comparison with previous works: Narrative comparison with MobileNet, EfficientDet-Lite, NanoDet/PP-PicoDet, and PCR/histopathology; prior YOLO-based aquaculture and edge detection studies discussed

Reproducibility artifacts available: Dataset; code and model not reported

Results

Summary: YOLO11n achieved mAP50–95 of 0.736 with 40.7 ms inference time and 5332 KB flash usage on the SG2002 RISC-V device. The system consumed 1.82 W during active inference and supported fully on-device fish disease detection in a waterproof aquaculture deployment.

Limitations

Single-site, single-species dataset limited to Nocardia infections in largemouth bass.

Real-world lighting, water turbidity, and irregular fish movement may reduce detection accuracy.

Hardware constraints limit model complexity and inference accuracy.

The study is a proof-of-concept and requires validation across multiple farms, species, pathogens, and aquaculture environments.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a TinyML-based real-time fish disease detection system that deploys an optimized YOLO11n model on an SG2002 RISC-V microcontroller for fully on-device aquaculture monitoring.

| Paper       | Year | Task             | Model   | Technique                                             | Device                        | Dataset                                                 | Main Metric      | Latency | Model Size | SRAM/RAM    | Flash   | Energy | Framework                                             | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------- | ------- | ----------------------------------------------------- | ----------------------------- | ------------------------------------------------------- | ---------------- | ------- | ---------- | ----------- | ------- | ------ | ----------------------------------------------------- | -------- | ------------- | ------------- |
| Wang et al. | 2025 | Object detection | YOLO11n | FP16 QAT + pruning + depthwise separable convolutions | SG2002 RISC-V microcontroller | Custom largemouth bass fish disease dataset, 914 images | mAP50–95 = 0.736 | 40.7 ms | N/A        | 256 MB DDR3 | 5332 KB | N/A    | Ultralytics YOLO11; deployment framework not reported | QAT      | None          | Yes           |
