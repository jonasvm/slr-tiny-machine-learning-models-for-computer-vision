Paper ID: Edge-Oriented-Social-Distance-Monitoring-System-Based-on-MTCNN

TinyML classification: Near-TinyML — edge deployment is on Jetson Nano, with no explicit MCU-class deployment.

Basic Info

Authors: Erick C. Valverde; Paul P. Oroceo; Angela C. Caliwag; Muhammad Adib Kamali; Wansu Lim; Martin Maier

Year: 2023

Title: Edge-Oriented Social Distance Monitoring System Based on MTCNN

Source: IEEE Transactions on Industrial Informatics, Vol. 19, No. 8, August 2023 

Type: Experimental

Problem & Context

Task: Face detection and facial landmark localization for social distance monitoring

Objective: Improve social distance estimation accuracy and reduce inference requirements for edge deployment.

Application domain: COVID-19 social distance monitoring

Scenario: Edge device, real-time monitoring, camera-based system

TinyML relevance: Partial

TinyML justification: The system targets edge deployment on NVIDIA Jetson Nano with memory, power, and inference-speed evaluation, but does not target MCU-class TinyML hardware.

Model / Method

Model: Optimized MTCNN

Architecture family: CNN

Techniques: Constrained network optimization, weight pruning, lower-precision weight representation, compression, inference optimization

Framework: Caffe, PyTorch, and TensorFlow are compared; proposed deployment framework not reported

Training type: Fine-tuning

Inference type: On-device

Hardware

Device: NVIDIA Jetson Nano

Hardware type: SoC / GPU

Processor / microcontroller: Quad-core Arm 1.43 GHz and 128-core NVIDIA Maxwell GPU

Clock frequency: 1.43 GHz

SRAM / RAM: Runtime memory usage reported as 2.6 GB CPU and 1.1 GB GPU for the proposed method

Flash / ROM / Storage: Not reported

Power consumption: 5100 mW

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, computational complexity, inference speed, data storage

Dataset

Name: WIDER FACE; CNN Face Point

Type: Public

Dataset size: WIDER FACE: 393,703 labeled faces from 32,203 images; CNN Face Point: 13,466 images

Number of classes: Not reported

Input resolution: Camera supports up to 1080p at 30 FPS; model input resolution not reported

Data modality: RGB image / video

Metrics

Accuracy: 99.7% detection accuracy for the proposed method

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 0.068 s for the proposed optimized MTCNN

FPS: 14.7 FPS; reported approximately 15 FPS

Throughput: 14.7 FPS

Model size: Not reported

Parameters: 98,821

MACs / FLOPs: Not reported

RAM usage: 2.6 GB CPU and 1.1 GB GPU

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 5100 mW

Optimization

Techniques used: Constrained weight pruning based on 0-1 knapsack, compression of P-Net/R-Net/O-Net, lower-precision weight conversion, inference optimization

Quantization: Not reported

Pruning: Yes

Knowledge distillation: No

Compression method: Constrained weight pruning with compression rates from 2× to 50×; proposed configuration uses P-Net 2×, R-Net 50×, and O-Net 50×

Hardware-specific optimization: Yes, network and inference optimizations targeting edge-device hardware/software performance

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 0.068 s; 14.7 FPS on NVIDIA Jetson Nano

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: Deployment is on NVIDIA Jetson Nano with embedded GPU resources, not on MCU-class hardware with SRAM/Flash-level constraints.

Benchmarking / Standardization

Benchmark used: WIDER FACE; CNN Face Point; real-time SDM experiment

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: WIDER FACE

Comparison with baseline models: Yes, compared with uncompressed MTCNN implementations using Caffe, PyTorch, and TensorFlow

Comparison with previous works: Yes, compared with CNN, Faster R-CNN, YOLOv3, YOLOv4, YOLOv5, YOLOv6, and YOLOv7 SDM systems

Reproducibility artifacts available: Not reported

Results

Summary: The optimized MTCNN achieved 99.7% detection accuracy, 14.7 FPS, 0.068 s inference latency, 98,821 parameters, and 5100 mW power consumption on NVIDIA Jetson Nano. The proposed facial-keypoint distance estimation reduced distance-estimation error compared with bounding-box-based SDM.

Limitations

The system is limited when humans do not face the camera completely or when people are too far from the camera and the face size falls below 8 × 8 pixels.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an edge-oriented social distance monitoring system that uses optimized MTCNN facial landmarks to improve distance estimation accuracy and enable efficient real-time deployment on NVIDIA Jetson Nano.

| Paper           | Year | Task                                        | Model           | Technique                                             | Device             | Dataset                    | Main Metric              | Latency            | Model Size | SRAM/RAM               | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---- | ------------------------------------------- | --------------- | ----------------------------------------------------- | ------------------ | -------------------------- | ------------------------ | ------------------ | ---------- | ---------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Valverde et al. | 2023 | Face detection / social distance monitoring | Optimized MTCNN | Constrained weight pruning and inference optimization | NVIDIA Jetson Nano | WIDER FACE; CNN Face Point | 99.7% detection accuracy | 0.068 s / 14.7 FPS | N/A        | 2.6 GB CPU; 1.1 GB GPU | N/A   | N/A    | N/A       | N/A      | None          | No            |
