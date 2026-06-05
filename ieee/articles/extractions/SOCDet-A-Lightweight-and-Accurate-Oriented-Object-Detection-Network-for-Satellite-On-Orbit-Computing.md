Paper ID: SOCDet-A-Lightweight-and-Accurate-Oriented-Object-Detection-Network-for-Satellite-On-Orbit-Computing

TinyML classification: Near-TinyML — The paper targets resource-constrained satellite edge computing and NVIDIA Jetson TX2 evaluation, but does not show MCU-class deployment.

Basic Info

Authors: Yanhua Pang; Yamin Zhang; Qinglei Kong; Yi Wang; Bo Chen; Xibin Cao

Year: 2023

Title: SOCDet: A Lightweight and Accurate Oriented Object Detection Network for Satellite On-Orbit Computing

Source: IEEE Transactions on Geoscience and Remote Sensing, Vol. 61, Article 5608115

Type: Experimental

Problem & Context

Task: Object detection

Objective: Lightweight and accurate oriented object detection for satellite on-orbit computing under constrained computing and storage resources. 

Application domain: Remote sensing / satellite imagery

Scenario: Satellite on-orbit computing; edge / embedded GPU

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained satellite on-orbit inference and evaluates on NVIDIA Jetson TX2, but does not report MCU-class deployment, SRAM/Flash constraints, or bare-metal/RTOS execution. 

Model / Method

Model: SOCDet

Architecture family: CNN

Techniques: Lightweight one-stage oriented object detection architecture; structural reparameterization block (SRB); guided attention module (GAM); Single-kernel Omni-dimensional Dynamic Convolution (SODC). 

Framework: PyTorch

Training type: Not reported

Inference type: On-device

Hardware

Device: NVIDIA Jetson TX2

Hardware type: GPU / SoC

Processor / microcontroller: NVIDIA Jetson TX2

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Computation, storage, power, heat dissipation, communication bandwidth, inference speed, parameters, FLOPs

Dataset

Name: DOTA; HRSC2016; FAIR1M

Type: Public

Dataset size: DOTA: 2806 images and 188,282 instances; HRSC2016: 1061 images and 2976 objects; FAIR1M: more than 40,000 images and more than 1 million instances

Number of classes: DOTA: 15; HRSC2016: Not reported; FAIR1M: 5 categories and 37 subcategories

Input resolution: DOTA: 1024 × 1024 cropped patches with 200 overlap; HRSC2016: resized to 800 × 800; FAIR1M: 1024 × 1024 cropped patches with stride 200

Data modality: Remote-sensing images

Metrics

Accuracy: Not reported

mAP: DOTA: 78.83; HRSC2016: 94.28; FAIR1M: 34.53

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 37.63 ms for SOCDet in ablation results; target-device latency not directly reported

FPS: DOTA on TX2: 9.66; HRSC2016 on TX2: 10.82; FAIR1M on TX2: 9.37

Throughput: Not reported beyond FPS

Model size: Not reported

Parameters: DOTA: 9.98M; HRSC2016: 10.01M; FAIR1M: 11.28M

MACs / FLOPs: DOTA: 16.06G FLOPs; HRSC2016: 16.72G FLOPs; FAIR1M: 17.23G FLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Lightweight architecture design; structural reparameterization; guided attention; dynamic convolution

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Architectural lightweighting and structural reparameterization

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported directly; FPS is reported on TX2

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: No cloud/offloading required for inference; communication is used for model update and result feedback

Candidate for Strict TinyML: No

Reason: The deployment target is an NVIDIA Jetson TX2 embedded GPU running Ubuntu, with no MCU-class SRAM, Flash, energy-per-inference, or bare-metal/RTOS evidence.

Benchmarking / Standardization

Benchmark used: DOTA; HRSC2016; FAIR1M

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: PASCAL VOC2012 metrics for HRSC2016

Comparison with baseline models: RetinaNet; SOCDet_A; SOCDet_AS; SOCDet_ASS

Comparison with previous works: YOLOv3tiny; YOLOv4tiny; YOLOv5s; YOLOXnano; NanoDet-M; NanoDet-plus-M; PP-PicoDet-S; YOLOv6nano; YOLOv7tiny; PP-YOLOEs; S2ANet; AOPG; LO-Det

Reproducibility artifacts available: Dataset

Results

Summary: SOCDet achieved 78.83 mAP on DOTA, 94.28 mAP on HRSC2016, and 34.53 mAP on FAIR1M. On TX2, it reported 9.66 FPS on DOTA, 10.82 FPS on HRSC2016, and 9.37 FPS on FAIR1M.

Limitations

SOCDet performance on FAIR1M is reported as not particularly excellent because FAIR1M has 37 fine-grained classifications, large images, very small objects, and complex backgrounds.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes SOCDet, a lightweight one-stage oriented object detection network using SRB, GAM, and SODC for satellite on-orbit remote-sensing object detection.

| Paper       | Year | Task             | Model  | Technique        | Device            | Dataset                | Main Metric    | Latency | Model Size       | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------- | ------ | ---------------- | ----------------- | ---------------------- | -------------- | ------- | ---------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Pang et al. | 2023 | Object Detection | SOCDet | SRB + GAM + SODC | NVIDIA Jetson TX2 | DOTA; HRSC2016; FAIR1M | DOTA mAP 78.83 | N/A     | 9.98M parameters | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
