Paper ID: Flame-and-smoke-recognition-on-smart-edge-using-deep-learning

TinyML classification: Near-TinyML — Uses edge devices and accelerators, but does not report MCU-class deployment or MCU-level memory constraints.

Basic Info

Authors: Endah Kristiani; Yi-Chun Chen; Chao-Tung Yang; Chia-Hsin Li

Year: 2023

Title: Flame and smoke recognition on smart edge using deep learning

Source: The Journal of Supercomputing, 79, 5552–5575 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Develop real-time flame and smoke recognition on smart edge devices using transfer learning and deep learning.

Application domain: Flame and smoke detection; disaster safety; UAV/aerial monitoring.

Scenario: Edge, embedded, IoT, UAV, web-based monitoring.

TinyML relevance: Partial

TinyML justification: The paper deploys deep-learning object detection on Raspberry Pi 4 with Intel NCS2 and NVIDIA Jetson Xavier NX, but does not target MCU-class deployment or report MCU-level SRAM/Flash constraints.

Model / Method

Model: YOLOv3; Faster R-CNN; SSD MobileNetv1-FPN

Architecture family: CNN

Techniques: Transfer learning; data augmentation; OpenVINO model conversion; Intel NCS2 acceleration; NVIDIA DeepStream acceleration.

Framework: TensorFlow; Keras; OpenVINO; DeepStream.

Training type: Transfer learning

Inference type: On-device

Hardware

Device: Raspberry Pi 4 + Intel Neural Compute Stick 2; NVIDIA Jetson Xavier NX

Hardware type: CPU / NPU / GPU / SoC

Processor / microcontroller: Raspberry Pi 4 ARM CPU; Intel Neural Compute Stick 2; NVIDIA Jetson Xavier NX

Clock frequency: Not reported

SRAM / RAM: Raspberry Pi 4: 4 GB RAM; NVIDIA Xavier NX: 16 GB RAM

Flash / ROM / Storage: Raspberry Pi 4 + Intel NCS2: 32 GB; NVIDIA Xavier NX: 16 GB

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Latency, FPS, compute limitations, real-time operation, communication/streaming.

Dataset

Name: Flame and smoke dataset

Type: Private

Dataset size: 2305 flame images, 1056 smoke images, 8000 ordinary scene images; 11,361 original images expanded to approximately 40,000 images.

Number of classes: 2 target classes: flame/fire and smoke.

Input resolution: 1280 × 720 for edge inference tests; training input resolution not reported.

Data modality: RGB image and video from aerial camera and webcam.

Metrics

Accuracy: Not reported

mAP: YOLOv3 mAP 31 in model comparison table; flame/smoke dataset mAP not reported.

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not directly reported as a main table metric; Raspberry Pi 4 + NCS2 reached 2.5 FPS and Jetson Xavier NX + DeepStream reached 10 FPS.

FPS: Raspberry Pi 4 + Intel NCS2: 2.5 FPS; NVIDIA Jetson Xavier NX + DeepStream: 10 FPS at 1280 × 720.

Throughput: Raspberry Pi 4 + Intel NCS2: 2.5 FPS; NVIDIA Jetson Xavier NX + DeepStream: 10 FPS.

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: OpenVINO model conversion to IR format; Intel NCS2 inference acceleration; NVIDIA DeepStream acceleration; data augmentation.

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: OpenVINO for Raspberry Pi 4 + Intel NCS2; DeepStream for NVIDIA Jetson Xavier NX.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes, through FPS results.

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: Not required for local inference, but video streaming to a server/web page is used for monitoring.

Candidate for Strict TinyML: No

Reason: Deployment uses Linux-based Raspberry Pi 4 with Intel NCS2 and NVIDIA Jetson Xavier NX rather than MCU-class hardware, and no MCU-level SRAM, Flash, energy, or bare-metal/RTOS evidence is reported.

Benchmarking / Standardization

Benchmark used: Private flame and smoke dataset.

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO is mentioned as the pre-training dataset for YOLOv3 and in model descriptions.

Comparison with baseline models: Yes, YOLOv3, Faster R-CNN, and SSD MobileNetv1-FPN are compared.

Comparison with previous works: Yes, related works are discussed.

Reproducibility artifacts available: dataset

Results

Summary: YOLOv3 achieved the lowest loss among the tested models, with loss 0.8 compared to Faster R-CNN at 2.3 and SSD at 1.2. Edge deployment reached 2.5 FPS on Raspberry Pi 4 + Intel NCS2 and 10 FPS on NVIDIA Jetson Xavier NX + DeepStream at 1280 × 720.

Limitations

The paper reports that using only the ARM CPU for real-time flame and smoke detection causes severe detection delay. The number of aerial images collected was limited, requiring dataset augmentation.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes an edge-computing flame and smoke detection system that deploys YOLOv3-based object detection on Raspberry Pi 4 with Intel NCS2 and NVIDIA Jetson Xavier NX with DeepStream for real-time video monitoring.

| Paper            | Year | Task             | Model  | Technique                          | Device                                               | Dataset                     | Main Metric                          | Latency | Model Size | SRAM/RAM             | Flash                 | Energy | Framework                               | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---: | ---------------- | ------ | ---------------------------------- | ---------------------------------------------------- | --------------------------- | ------------------------------------ | ------- | ---------- | -------------------- | --------------------- | ------ | --------------------------------------- | -------- | ------------- | ------------- |
| Kristiani et al. | 2023 | Object Detection | YOLOv3 | OpenVINO / DeepStream acceleration | Raspberry Pi 4 + Intel NCS2; NVIDIA Jetson Xavier NX | Private flame/smoke dataset | Loss 0.8; FPS 10 on Jetson Xavier NX | N/A     | N/A        | 4 GB RAM / 16 GB RAM | 32 GB / 16 GB storage | N/A    | TensorFlow; Keras; OpenVINO; DeepStream | N/A      | None          | No            |
