Paper ID: Real-time-fire-detection-algorithm-on-low-power-endpoint-device

TinyML classification: Near-TinyML — Evaluated on a low-power endpoint chip with NPU rather than explicit MCU-class deployment.

Basic Info

Authors: Ruoyu Peng; Chaoyuan Cui; Yun Wu

Year: 2025

Title: Real-time fire detection algorithm on low-power endpoint device

Source: Journal of Real-Time Image Processing, 22:29 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Real-time flame and smoke detection on low-power endpoint hardware.

Application domain: Fire detection / video surveillance safety.

Scenario: Edge / embedded endpoint device / IoT camera system.

TinyML relevance: Yes

TinyML justification: The paper targets fully local inference on a low-power endpoint chip with NPU acceleration, INT8 quantization, latency evaluation, power reporting, and hardware-aware optimization. 

Model / Method

Model: YOLOv8-derived fire detection model with QARep module and LeakyReLU activation.

Architecture family: CNN

Techniques: Quantization-friendly activation function, QARep reparameterization, INT8 post-training quantization, transfer learning, hardware-aware channel alignment, input-resolution optimization.

Framework: PyTorch, ONNX, Ingenic Magik, C/C++.

Training type: Transfer learning / fine-tuning.

Inference type: On-device.

Hardware

Device: Ingenic T41 endpoint chip.

Hardware type: NPU / SoC.

Processor / microcontroller: XBurst2 CPU; MIPS architecture; integrated NPU.

Clock frequency: Not reported.

SRAM / RAM: 48 MB RAM.

Flash / ROM / Storage: Not reported.

Power consumption: 0.68–1.5 W.

Energy per inference: Not reported.

Execution without full OS: Not reported.

Fully on-device inference: Yes.

Constraints mentioned: Compute, latency, power, quantization, memory operations, endpoint-device characteristics, communication avoidance, channel alignment, input resolution.

Dataset

Name: D-Fire.

Type: Not reported.

Dataset size: 21,527 images; 26,557 bounding boxes; 17,221 training images; 4306 validation images. 

Number of classes: 2.

Input resolution: 640 × 640 and 672 × 416.

Data modality: Image.

Metrics

Accuracy: Not reported.

mAP: INT8 O(s): mAP@0.5 0.784, mAP 0.465; INT8 O(n): mAP@0.5 0.768, mAP 0.448.

Precision: INT8 O(s): 0.807; INT8 O(n): 0.797.

Recall: INT8 O(s): 0.710; INT8 O(n): 0.687.

F1-score: Not reported.

Latency: 46.70 ms for O(s) and 21.25 ms for O(n) at 672 × 416.

FPS: Not reported.

Throughput: Not reported.

Model size: Not reported.

Parameters: Not reported.

MACs / FLOPs: O(n): 11.8 GFLOPs; O(s): 44.1 GFLOPs.

RAM usage: Not reported.

Flash usage: Not reported.

Energy per inference: Not reported.

Power consumption: 0.68–1.5 W.

Optimization

Techniques used: QARep reparameterization, LeakyReLU activation, INT8 post-training quantization, 32-channel alignment, rectangular input resolution, transfer learning.

Quantization: INT8 / PTQ.

Pruning: Not reported.

Knowledge distillation: Not reported.

Compression method: Reparameterization and INT8 post-training quantization.

Hardware-specific optimization: Uses quantization-friendly LeakyReLU, channels as multiples of 32, 3 × 3 convolution preference, reduced Slice/Concat operations, and 672 × 416 input resolution aligned with sensor images.

Use of CMSIS-NN: No.

Use of TensorFlow Lite Micro: No.

Use of MLPerf Tiny: No.

Strict TinyML Evidence

SRAM peak reported: Not reported.

Flash usage reported: Not reported.

Model size reported: Not reported.

Energy per inference reported: Not reported.

Latency on target device reported: Yes.

Runs without full operating system: Not reported.

Fully on-device inference: Yes.

Communication required during inference: No.

Candidate for Strict TinyML: No.

Reason: The paper evaluates a low-power endpoint NPU device, but it does not report MCU-class deployment, bare-metal/RTOS execution, TensorFlow Lite Micro, or SRAM/Flash-level deployment constraints.

Benchmarking / Standardization

Benchmark used: D-Fire.

MLPerf Tiny mentioned: No.

Visual Wake Words mentioned: No.

Other standard benchmark: COCO2017 used for pretraining.

Comparison with baseline models: Yes, compared with YOLOv5-v10 and YOLOv8 variants.

Comparison with previous works: Yes.

Reproducibility artifacts available: Dataset.

Results

Summary: The proposed O(s) and O(n) models achieve low endpoint latency of 46.70 ms and 21.25 ms at 672 × 416 with competitive fire/smoke detection performance. INT8 quantization causes acceptable accuracy degradation compared with FP32 results. 

Limitations

The reported latency excludes preprocessing and post-processing time; NMS requires additional time; the method does not show a significant advantage under occlusion.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes.

Reports memory usage: No.

Reports latency: Yes.

Reports energy or power: Yes.

Reports model size: No.

Reports optimization method: Yes.

Reports deployment framework: Yes.

Reports dataset and preprocessing: Yes.

Reports evaluation metric clearly: Yes.

Reports reproducibility artifacts: No.

Contribution

This paper proposes a YOLOv8-derived, hardware-aware fire and smoke detection algorithm optimized with QARep, quantization-friendly LeakyReLU, INT8 deployment, and input-resolution adaptation for real-time inference on a low-power endpoint NPU.

| Paper       | Year | Task             | Model                | Technique                                                    | Device      | Dataset | Main Metric             | Latency                      | Model Size | SRAM/RAM                      | Flash | Energy | Framework                  | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ---------------- | -------------------- | ------------------------------------------------------------ | ----------- | ------- | ----------------------- | ---------------------------- | ---------- | ----------------------------- | ----- | ------ | -------------------------- | -------- | ------------- | ------------- |
| Peng et al. | 2025 | Object Detection | YOLOv8-derived QARep | QARep + LeakyReLU + INT8 PTQ + input-resolution optimization | Ingenic T41 | D-Fire  | mAP@0.5 0.784 INT8 O(s) | 46.70 ms O(s); 21.25 ms O(n) | N/A        | 48 MB RAM device; runtime N/A | N/A   | N/A    | PyTorch/ONNX/Ingenic Magik | INT8 PTQ | None          | No            |
