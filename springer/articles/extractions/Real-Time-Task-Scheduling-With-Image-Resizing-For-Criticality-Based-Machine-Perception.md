Paper ID: Real-Time-Task-Scheduling-With-Image-Resizing-For-Criticality-Based-Machine-Perception 

TinyML classification: Near-TinyML — The work targets embedded GPU/Jetson-class edge deployment, but does not report MCU-class deployment or Cortex-M/TFLite Micro-level constraints.

Basic Info

Authors: Yigong Hu; Shengzhong Liu; Tarek Abdelzaher; Maggie Wigness; Philip David

Year: 2022

Title: Real-time task scheduling with image resizing for criticality-based machine perception

Source: Real-Time Systems, 58:430–455

Type: Methodological

Problem & Context

Task: Object detection

Objective: Reduce computing demand and improve real-time perception by scheduling, resizing, and merging image segments according to criticality.

Application domain: Autonomous driving; autonomous drones and cars

Scenario: Embedded edge AI platform with camera and LiDAR sensor

TinyML relevance: Partial

TinyML justification: The paper targets embedded edge machine perception on an NVIDIA Jetson AGX Xavier SoC, but does not target MCU-class or ultra-low-power TinyML deployment.

Model / Method

Model: YOLOv5

Architecture family: CNN

Techniques: Image resizing, sub-frame scheduling, LiDAR-based segmentation, segment merging, batching, tracking-based task skipping

Framework: YOLOv5 implementation; deep learning framework not reported

Training type: Not reported

Inference type: On-device

Hardware

Device: NVIDIA Jetson AGX Xavier SoC

Hardware type: SoC / CPU / GPU

Processor / microcontroller: 8-core Carmel Arm v8.2 64-bit CPU; 512-core Volta GPU

Clock frequency: Constant GPU clock frequency used; value not reported

SRAM / RAM: 32 GB shared memory

Flash / ROM / Storage: Not reported

Power consumption: 30 W operating mode

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Real-time deadlines, latency, compute resources, batching constraints, GPU workload, LiDAR segmentation overhead

Dataset

Name: Waymo Open Dataset; COCO dataset for YOLO training

Type: Public

Dataset size: Waymo sequences are 20 seconds with synchronized camera and LiDAR at 10 Hz; total size not reported

Number of classes: 4 Waymo object types; 80 COCO classes for training

Input resolution: Segments padded to 32×32, 64×64, 128×128, and 256×256

Data modality: Camera frames + LiDAR measurements

Metrics

Accuracy: Average normalized accuracy reported; exact numeric values not reported

mAP: Used to define normalized accuracy as achieved mAP divided by full-frame detection mAP; absolute mAP not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Average inference latency evaluated across 40 ms to 160 ms frame intervals; exact numeric table not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 30 W operating mode

Optimization

Techniques used: Image resizing, resize-merge scheduling, segment merging, LiDAR cueing, batching, tracking-based reuse, greedy scheduling approximation

Quantization: None reported

Pruning: No

Knowledge distillation: No

Compression method: Input resizing; not model compression

Hardware-specific optimization: GPU batching of same-size segments and constant GPU clock frequency

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Average inference latency plotted; scheduling overhead below 12 ms for 70 objects

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is an embedded GPU/SoC with 32 GB shared memory, not an MCU-class platform with SRAM/Flash-constrained TinyML deployment.

Benchmarking / Standardization

Benchmark used: Waymo Open Dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO dataset used for YOLO training

Comparison with baseline models: Yes; Proposed, No-merge, RTCSA2021, RTSS2020, and Full

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: The proposed resize-merge scheduling framework improves normalized accuracy and reduces inference latency compared with prior scheduling baselines under real-time frame intervals. Scheduling overhead remains below 12 ms for 70 objects.

Limitations

LiDAR cueing covers only a limited portion of the camera scene, has a limited range of 75 meters in the Waymo setup, and is sensitive to multi-path effects, object surface type, and weather.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a real-time criticality-based machine perception framework that uses LiDAR-based segmentation, sub-frame image resizing, segment merging, and greedy scheduling to improve embedded edge object detection efficiency.

| Paper     | Year | Task             | Model  | Technique                                                               | Device                   | Dataset                  | Main Metric                     | Latency                                                                      | Model Size | SRAM/RAM         | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---- | ---------------- | ------ | ----------------------------------------------------------------------- | ------------------------ | ------------------------ | ------------------------------- | ---------------------------------------------------------------------------- | ---------- | ---------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Hu et al. | 2022 | Object Detection | YOLOv5 | Sub-frame image resizing + LiDAR segmentation + resize-merge scheduling | NVIDIA Jetson AGX Xavier | Waymo Open Dataset; COCO | Normalized accuracy / mAP ratio | Average inference latency plotted; scheduling overhead <12 ms for 70 objects | N/A        | 32 GB shared RAM | N/A   | N/A    | YOLOv5    | N/A      | None          | No            |
