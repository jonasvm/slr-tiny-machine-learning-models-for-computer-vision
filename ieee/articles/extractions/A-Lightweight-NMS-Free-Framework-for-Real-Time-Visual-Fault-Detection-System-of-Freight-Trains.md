Paper ID: A-Lightweight-NMS-Free-Framework-for-Real-Time-Visual-Fault-Detection-System-of-Freight-Trains

TinyML classification: Near-TinyML — evaluated as lightweight edge-relevant vision detection, but experiments use a PC with GTX2080Ti rather than MCU-class hardware.

Basic Info

Authors: Guodong Sun, Yang Zhou, Huilin Pan, Bo Wu, Ye Hu, Yang Zhang

Year: 2022

Title: A Lightweight NMS-Free Framework for Real-Time Visual Fault Detection System of Freight Trains

Source: IEEE Transactions on Instrumentation and Measurement, Vol. 71, 2022 

Type: Experimental / Methodological

Problem & Context

Task: Object detection

Objective: Achieve real-time and high-accuracy visual fault detection for freight train braking system components with low computational cost.

Application domain: Railway freight train fault detection

Scenario: Resource-limited outdoor vision-based inspection system

TinyML relevance: Partial

TinyML justification: The paper targets lightweight, real-time visual detection under limited computing resources and reports latency, memory usage, and model size, but does not report MCU-class deployment or TinyML framework use.

Model / Method

Model: NR FTI-FDet

Architecture family: CNN

Techniques: Lightweight backbone, NMS-free detection, fault feature pyramid, attention mechanism, bottleneck module, dilated convolution, focal loss, L1 loss, GIoU loss

Framework: Not reported

Training type: Not reported

Inference type: Not reported

Hardware

Device: PC environment with Intel Core i9-9900K CPU, 64 GB RAM, and single GTX2080Ti GPU

Hardware type: CPU / GPU

Processor / microcontroller: Intel Core i9-9900K 3.60 GHz; GTX2080Ti GPU

Clock frequency: 3.60 GHz

SRAM / RAM: 64 GB RAM; testing memory usage 1011 MB

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Computing resources, computational cost, latency, memory usage, model size

Dataset

Name: Bogie Block Key; Dust Collector; Fastening Bolt on Brake Beam

Type: Private

Dataset size: Bogie Block Key: 5440 training and 2897 testing images; Dust Collector: 815 training and 850 testing images; Fastening Bolt on Brake Beam: 1724 training and 1902 testing images

Number of classes: Not reported

Input resolution: 700 × 512 pixels

Data modality: Freight train images

Metrics

Accuracy: mCDR 98.40%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 0.012 s/image

FPS: Over 83 FPS

Throughput: Over 83 images/s

Model size: 95.9 MB

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: 436 MB training memory; 1011 MB testing memory

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: MobileNetV3-Small lightweight backbone, fault feature pyramid, fault enhance attention, fault bottleneck module, dilated fault bottleneck, NMS-free detection head

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Lightweight architecture and bottleneck-based model size reduction

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 95.9 MB

Energy per inference reported: Not reported

Latency on target device reported: 0.012 s/image on PC with GTX2080Ti GPU

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports lightweight edge-relevant computer vision metrics, but experiments use a PC with GPU and no MCU-class deployment, SRAM/Flash constraints, or TinyML runtime.

Benchmarking / Standardization

Benchmark used: Three private freight-train fault datasets

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: NR FTI-FDet achieved 98.40% mCDR, 0.012 s/image testing latency, over 83 FPS, 95.9 MB model size, and 1011 MB testing memory usage on three freight-train fault datasets. The method outperformed compared NMS-free detectors in accuracy and achieved the fastest testing speed among compared methods.

Limitations

The paper states that future work should further improve accuracy while maintaining speed and model size, use different image processing methods to increase detection speed, and deploy the framework to edge computing equipment after further optimization.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a lightweight NMS-free CNN framework for real-time visual fault detection of freight train braking-system components using MobileNetV3-Small, a fault feature pyramid, and an NMS-free detection head.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Sun et al. | 2022 | Object Detection | NR FTI-FDet | NMS-free lightweight MobileNetV3-Small with fault feature pyramid | PC with Intel Core i9-9900K, 64 GB RAM, GTX2080Ti GPU | Three private freight-train fault datasets | mCDR 98.40% | 0.012 s/image (>83 FPS) | 95.9 MB | 1011 MB test memory; 436 MB train memory | N/A | N/A | Not reported | N/A | None | No |
