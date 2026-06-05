Paper ID: Vis-Assist-computer-vision-and-haptic-feedback-based-wearable-assistive-device-for-visually-impaired

TinyML classification: Near-TinyML — Uses edge/on-device vision on Jetson Nano, but does not provide MCU-class deployment evidence.

Basic Info

Authors: Ibrahim Dede; Abdurrahman Gumus

Year: 2025

Title: Vis-Assist: computer vision and haptic feedback-based wearable assistive device for visually impaired

Source: Journal on Multimodal User Interfaces

Type: Experimental

Problem & Context

Task: Object detection

Objective: Develop a wearable assistive device that detects and classifies objects, measures distance, and provides real-time haptic feedback for visually impaired users.

Application domain: Assistive technology for visually impaired people

Scenario: Wearable edge-AI assistive device

TinyML relevance: Partial

TinyML justification: The system performs fully on-device edge inference on a Jetson Nano without external servers, but it does not target MCU-class deployment or report MCU-level memory constraints. 

Model / Method

Model: YOLOv7-Tiny

Architecture family: CNN

Techniques: Lightweight YOLOv7-Tiny model; object-class filtering; region-of-interest detection; haptic feedback encoding

Framework: Not reported

Training type: Not reported

Inference type: On-device

Hardware

Device: Vis-Assist wearable device

Hardware type: SoC / GPU / Other

Processor / microcontroller: Nvidia Jetson Nano; Arduino UNO for haptic feedback control

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: 10 W total device power consumption

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Power consumption, cost, real-time operation, wearability, external-server independence

Dataset

Name: COCO

Type: Public

Dataset size: Not reported

Number of classes: 19 object classes used for haptic feedback; selected from COCO object categories

Input resolution: Not reported

Data modality: RGB image + 1D LiDAR distance sensor

Metrics

Accuracy: 92% haptic object-pattern recognition accuracy after four hours of participant training

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported for model inference; object haptic feedback pattern takes approximately 1.2 seconds per object

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 10 W total device power consumption

Optimization

Techniques used: YOLOv7-Tiny lightweight edge model; class filtering; disabling rectangle drawing; ROI-based object feedback

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: YOLOv7-Tiny selected for real-time applications on edge devices such as Jetson Nano; no detailed hardware-specific optimization reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No external server required

Candidate for Strict TinyML: No

Reason: The deployment target is Jetson Nano edge hardware, not an MCU-class or bare-metal TinyML platform.

Benchmarking / Standardization

Benchmark used: Custom user experiments for object finding and obstacle navigation

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO object categories used

Comparison with baseline models: Not reported

Comparison with previous works: Yes, qualitative comparison with wearable assistive systems in the literature review table

Reproducibility artifacts available: Code

Results

Summary: Participants achieved 92% haptic pattern recognition accuracy after four hours of training. In experiments, the device achieved 90% success for finding a chair without obstacles and 85% success for finding a person with obstacles, with average completion times of 94.4 s and 121.5 s, respectively. 

Limitations

The experiments used only four blindfolded sighted participants, not visually impaired users. The study is a proof of concept and requires validation with larger and more diverse visually impaired participant groups in more complex real-world environments.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: Yes

Reports model size: No

Reports optimization method: No

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a wearable edge-AI assistive device that combines YOLOv7-Tiny object detection, LiDAR distance measurement, and haptic feedback arrays to support object awareness and navigation for visually impaired users.

| Paper       | Year | Task             | Model       | Technique                                | Device                             | Dataset                | Main Metric                                                  | Latency | Model Size | SRAM/RAM | Flash | Energy           | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------- | ----------- | ---------------------------------------- | ---------------------------------- | ---------------------- | ------------------------------------------------------------ | ------- | ---------- | -------- | ----- | ---------------- | --------- | -------- | ------------- | ------------- |
| Dede et al. | 2025 | Object detection | YOLOv7-Tiny | Lightweight edge model + class filtering | Jetson Nano + Arduino UNO wearable | COCO object categories | 90% chair-finding success; 85% person-with-obstacles success | N/A     | N/A        | N/A      | N/A   | 10 W total power | N/A       | N/A      | None          | No            |
