## Paper ID: Lightweight-Intelligent-Detection-System-for-Personal-Protective-Equipment-in-Laboratories-of-Higher-Education-Institutions

TinyML classification: Near-TinyML — The work is relevant to edge computer vision and constrained deployment, but reports GPU-less host deployment rather than explicit MCU-class deployment.

### Basic Info

* Authors: Han Liao, Xuting Hu, Feng Wang, Zhanzhan Liu, Maowang Wu
* Year: 2025
* Title: Lightweight Intelligent Detection System for Personal Protective Equipment in Laboratories of Higher Education Institutions
* Source: IEEE Access
* Type: Experimental

### Problem & Context

* Task: Object detection
* Objective: Detect personal protective equipment in higher education laboratory environments in real time.
* Application domain: Laboratory safety monitoring
* Scenario: Edge / resource-constrained deployment
* TinyML relevance: Partial
* TinyML justification: The paper proposes a lightweight object detection model with pruning, knowledge distillation, model-size reduction, and GPU-less deployment, but it does not report MCU-class deployment or MCU-level memory/energy constraints.

### Model / Method

* Model: LabPPE-DS; LabPPE-DS-tiny
* Architecture family: CNN
* Techniques: CSDF-Encoder, TFFM, EDF, DyESLoss, LAMP pruning, BCKD knowledge distillation, CWD knowledge distillation
* Framework: PyTorch 2.1.0; PyQt5 for deployment interface
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Non-GPU host computer / edge computing device with external camera
* Hardware type: CPU for deployment; CPU + GPU for training
* Processor / microcontroller: Deployment processor not reported; training server uses Intel Xeon Platinum 8457C and NVIDIA GeForce RTX 4090
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Computational resources, GPU-less deployment, inference efficiency, model size, parameters, GFLOPs

### Dataset

* Name: Safety Lab Dataset
* Type: Public
* Dataset size: 427 original images; 988 images after augmentation; more than 2100 labeled instances
* Number of classes: 4
* Input resolution: 640 × 640
* Data modality: Image

### Metrics

* Accuracy: Not reported
* mAP: LabPPE-DS-tiny distilled: 96.9% mAP50 and 82.0% mAP50-95; LabPPE-DS: 95.9% mAP50 and 79.2% mAP50-95
* Precision: 96.8% for LabPPE-DS with DyESLoss
* Recall: 91.2% for LabPPE-DS with DyESLoss
* F1-score: Not reported
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: 2.1 Mb for LabPPE-DS-tiny distilled; 5.5 Mb for LabPPE-DS
* Parameters: 0.95M for LabPPE-DS-tiny distilled; 2.7M for LabPPE-DS
* MACs / FLOPs: 3.3 GFLOPs for LabPPE-DS-tiny distilled; 8.4 GFLOPs for LabPPE-DS
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: LAMP pruning, fine-tuning, BCKD knowledge distillation, CWD knowledge distillation, lightweight feature fusion modules
* Quantization: Not reported
* Pruning: Yes
* Knowledge distillation: Yes
* Compression method: LAMP pruning combined with knowledge distillation
* Hardware-specific optimization: GPU-less constrained deployment only; no hardware-specific inference library reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 2.1 Mb for LabPPE-DS-tiny distilled
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper reports lightweight object detection and GPU-less deployment, but does not provide evidence of MCU-class deployment, TFLM/CMSIS-NN use, SRAM/Flash constraints, or energy measurements.

### Benchmarking / Standardization

* Benchmark used: Safety Lab Dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes; YOLOv3-tiny, YOLOv12n, YOLOX-tiny, Hyper-YOLO, DETR-R50, RT-DETR-R18, Fast R-CNN, RTMDet-tiny
* Comparison with previous works: Yes; through mainstream object detection baselines
* Reproducibility artifacts available: Dataset

### Results

* Summary: LabPPE-DS-tiny distilled achieves 96.9% mAP50 and 82.0% mAP50-95 with 0.95M parameters, 3.3 GFLOPs, and 2.1 Mb model size. The system is deployed on a non-GPU host computer with an external camera for laboratory PPE monitoring.

### Limitations

* The dataset has class imbalance, especially for the goggles class.
* Future work is needed to integrate multimodal video, image, and sensor data.
* Future work is needed to further optimize inference speed and deployment efficiency.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a lightweight real-time PPE object detection system for higher education laboratories using CSPDarknet-based feature fusion, LAMP pruning, and knowledge distillation for constrained GPU-less deployment.

| Paper       | Year | Task             | Model          | Technique                                      | Device                | Dataset            | Main Metric                 | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework             | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------- | -------------- | ---------------------------------------------- | --------------------- | ------------------ | --------------------------- | ------- | ---------- | -------- | ----- | ------ | --------------------- | -------- | ------------- | ------------- |
| Liao et al. | 2025 | Object Detection | LabPPE-DS-tiny | LAMP pruning + BCKD/CWD knowledge distillation | Non-GPU host computer | Safety Lab Dataset | mAP50 96.9%; mAP50-95 82.0% | N/A     | 2.1 Mb     | N/A      | N/A   | N/A    | PyTorch 2.1.0 + PyQt5 | N/A      | None          | No            |
