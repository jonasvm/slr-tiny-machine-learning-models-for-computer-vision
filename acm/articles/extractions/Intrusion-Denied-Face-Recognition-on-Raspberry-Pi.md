Paper ID: Intrusion-Denied-Face-Recognition-on-Raspberry-Pi

TinyML classification: Near-TinyML — uses Raspberry Pi 5 rather than explicit MCU-class deployment or MCU-level memory/energy constraints.

## Basic Info

Authors: Metrine Nyaboke Osiemo; Dave Rushit; Mansi Bhavsar

Year: 2025

Title: Intrusion Denied: Face Recognition on Raspberry Pi

Source: Consortium for Computing Sciences in Colleges

Type: Experimental

## Problem & Context

Task: Face recognition / face detection

Objective: Develop a low-cost, AI-powered intrusion detection system using Raspberry Pi 5 for offline real-time facial recognition.

Application domain: Home and small business surveillance / intrusion detection

Scenario: Edge, embedded, IoT, on-device surveillance

TinyML relevance: Partial

TinyML justification: The paper targets offline, on-device computer vision inference on Raspberry Pi 5 edge hardware, but does not report MCU-class deployment or MCU-level memory, latency, or energy constraints. 

## Model / Method

Model: Dlib and YOLOv4-Tiny

Architecture family: CNN / Other

Techniques: Lightweight model selection; face encoding; bounding-box face detection

Framework: Dlib, OpenCV, Python, Tkinter, YOLOv4-Tiny

Training type: Not reported

Inference type: On-device

## Hardware

Device: Raspberry Pi 5 with PiCamera2 module

Hardware type: SoC / CPU

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Local Raspberry Pi file system mentioned; capacity not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Limited computational resources, real-time processing, lighting, face orientation, camera angle, multiple-face detection, higher-frame-rate processing

## Dataset

Name: Local face database; extended dataset on Kaggle mentioned

Type: Private / public

Dataset size: Not reported

Number of classes: Not reported

Input resolution: Not reported

Data modality: Live video feed and face images

## Metrics

Accuracy: Not reported numerically

mAP: Not reported

Precision: Not reported numerically

Recall: Not reported numerically

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Lightweight YOLOv4-Tiny model; Dlib 128-dimensional face encoding

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: No

Reason: The system runs on Raspberry Pi 5 using Python-based software and does not report MCU-class deployment, bare-metal/RTOS execution, or MCU-level memory and energy constraints.

## Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: LFW mentioned in related work for Dlib, but not used as an experimental benchmark

Comparison with baseline models: Dlib compared with YOLOv4-Tiny

Comparison with previous works: Yes, related work discusses FaceNet, MobileNetV2/FaceNet on Raspberry Pi-400, and Raspberry Pi face detection studies

Reproducibility artifacts available: code / dataset

## Results

Summary: The system demonstrates offline real-time face recognition and detection on Raspberry Pi 5. Dlib is reported as more accurate in controlled environments, while YOLOv4-Tiny is reported as faster and more adaptable under varied conditions.

Limitations: Raspberry Pi 5 computational constraints limit scalability to larger models and high-resolution or higher-frame-rate processing; performance is sensitive to lighting, face orientation, and camera angle; the system uses a small static face database; real-time alerts and remote access were not implemented.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: No

Reports deployment framework: Yes

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

## Contribution

This paper proposes a low-cost offline AI-powered intrusion detection system using Raspberry Pi 5, Dlib, and YOLOv4-Tiny for real-time face detection and recognition.

| Paper         | Year | Task                              | Model             | Technique                   | Device         | Dataset                                       | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework                         | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | --------------------------------- | ----------------- | --------------------------- | -------------- | --------------------------------------------- | ----------- | ------- | ---------- | -------- | ----- | ------ | --------------------------------- | -------- | ------------- | ------------- |
| Osiemo et al. | 2025 | Face recognition / face detection | Dlib; YOLOv4-Tiny | Lightweight edge deployment | Raspberry Pi 5 | Local face database; Kaggle dataset mentioned | N/A         | N/A     | N/A        | N/A      | N/A   | N/A    | Dlib; OpenCV; Python; YOLOv4-Tiny | N/A      | None          | No            |
