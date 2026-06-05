Paper ID: Revolutionize-dental-diagnostics-AI-powered-detection-and-localization-of-oral-lesions-using-edge-devices

TinyML classification: Near-TinyML — The deployment target is Raspberry Pi 4, an edge/Linux-based platform, with no explicit MCU-class deployment or microcontroller-level memory constraints.

Basic Info

Authors: Talal Bonny; Abd Alrhman Hammal; Wafaa Al Nassan; Mohamed Elhoseny

Year: 2025

Title: Revolutionize dental diagnostics: AI-powered detection and localization of oral lesions using edge devices 

Source: Network Modeling Analysis in Health Informatics and Bioinformatics, 14:108

Type: Experimental

Problem & Context

Task: Object Detection

Objective: Detect and localize oral lesions and dental conditions in bitewing dental images using an AI-based edge diagnostic system.

Application domain: Dental healthcare diagnostics

Scenario: Edge, embedded, clinical point-of-care

TinyML relevance: Partial

TinyML justification: The paper deploys YOLOv5/CNN inference on a Raspberry Pi 4 low-cost edge device, but does not report MCU-class deployment, TensorFlow Lite Micro, SRAM/Flash constraints, or microcontroller-level execution.

Model / Method

Model: CNN with YOLOv5; YOLOv5l reported

Architecture family: CNN

Techniques: Otsu thresholding preprocessing; YOLO-based object detection; Raspberry Pi edge deployment; GPU accelerator used for efficiency

Framework: TensorFlow; YOLOv5; Python environment; Google Colab for training

Training type: Fine-tuning

Inference type: On-device

Hardware

Device: Raspberry Pi 4 board with camera, display, and GPU accelerator

Hardware type: SoC + GPU accelerator

Processor / microcontroller: Raspberry Pi 4 board

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Low cost, limited computing power, real-time inference, privacy, latency, bandwidth, reduced reliance on external servers

Dataset

Name: Private bitewing dental X-ray dataset annotated at University of Sharjah

Type: Private

Dataset size: 200 images

Number of classes: 6

Input resolution: 1282×910

Data modality: Grayscale bitewing dental X-ray images

Metrics

Accuracy: Class-wise true positive/confusion matrix values: Tooth 0.88; Caries 0.82; Composite 0.66; Amalgam 0.86; Gic 0.01; Crown 0.78

mAP: Not reported

Precision: Precision-Recall values: Tooth 0.909; Caries 0.736; Composite 0.658; Amalgam 0.823; Gic 0.496; Crown 0.705

Recall: Recall-Confidence values: Tooth 0.95; Caries 0.93; Composite 0.82; Amalgam 0.90; Gic 0.50; Crown 0.94

F1-score: F1-Confidence values: Tooth 0.88; Caries 0.70; Composite 0.69; Amalgam 0.84; Gic 0.01; Crown 0.72; average all classes 0.68

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

Optimization

Techniques used: Otsu thresholding segmentation for preprocessing; GPU accelerator for increasing efficiency

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: GPU accelerator used with Raspberry Pi 4 to process more images per second

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

Communication required during inference: No cloud communication reported during inference

Candidate for Strict TinyML: No

Reason: The target device is Raspberry Pi 4, not an MCU-class platform, and the paper does not report SRAM/Flash constraints, TFLite Micro, OS-less execution, or MCU-level latency/energy metrics.

Benchmarking / Standardization

Benchmark used: Private bitewing dental X-ray dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Not reported

Comparison with previous works: Yes; related-work table compares prior dental X-ray deep learning studies

Reproducibility artifacts available: none

Results

Summary: The proposed YOLOv5/CNN system detects and localizes dental conditions in bitewing images and is demonstrated on Raspberry Pi 4 for real-time image and video inference. Reported class-wise precision-recall values range from 0.496 for Gic to 0.909 for Tooth, with average F1-confidence of 0.68.

Limitations: The dataset is private and small, with only 200 images; the authors state that limited samples affect class performance and that future work should increase dataset size, test external images for generalizability, and perform clinical trials.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an edge-based dental diagnostic system that combines CNN/YOLOv5 object detection with Raspberry Pi 4 deployment to detect and localize oral lesions in bitewing dental images.

| Paper        | Year | Task             | Model       | Technique                            | Device                           | Dataset                                           | Main Metric                                                                                         | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework                    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | ---------------- | ----------- | ------------------------------------ | -------------------------------- | ------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ------- | ---------- | -------- | ----- | ------ | ---------------------------- | -------- | ------------- | ------------- |
| Bonny et al. | 2025 | Object Detection | YOLOv5l/CNN | Otsu preprocessing + edge deployment | Raspberry Pi 4 + GPU accelerator | Private bitewing dental X-ray dataset, 200 images | Precision-Recall: Tooth 0.909; Caries 0.736; Composite 0.658; Amalgam 0.823; Gic 0.496; Crown 0.705 | N/A     | N/A        | N/A      | N/A   | N/A    | TensorFlow / YOLOv5 / Python | N/A      | None          | No            |
