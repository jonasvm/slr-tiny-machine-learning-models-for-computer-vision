Paper ID: A-TinyML-model-for-sidewalk-obstacle-detection-aiding-the-blind-and-visually-impaired-people

TinyML classification: Near-TinyML — The work targets TinyML and resource-constrained IoT vision, but the reported deployment/evaluation is mainly on Raspberry Pi 4 and CPU rather than explicit MCU-class hardware.

Basic Info

Authors: Ahmed Boussihmed; Khalid El Makkaoui; Ibrahim Ouahbi; Yassine Maleh; Abdelaziz Chetouani

Year: 2025

Title: A TinyML model for sidewalk obstacle detection: aiding the blind and visually impaired people

Source: Multimedia Tools and Applications, 84:25837–25864, DOI: 10.1007/s11042-024-20070-9 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Detect common sidewalk obstacles to assist blind and visually impaired people.

Application domain: Assistive technology for blind and visually impaired people

Scenario: IoT, embedded, edge, assistive wearable/smart-glasses context

TinyML relevance: Yes

TinyML justification: The paper explicitly targets TinyML and resource-constrained IoT/embedded deployment, reporting lightweight object detection models, compression, model size, and latency on Raspberry Pi 4 and CPU.

Model / Method

Model: YOLOv5n, YOLOv5s, YOLOv8n, YOLOv8s

Architecture family: CNN

Techniques: Quantization, weight pruning, model compression, ONNX Runtime acceleration, OpenVINO acceleration, data augmentation

Framework: PyTorch; ONNX Runtime; OpenVINO; TensorFlow 2 Object Detection API used for comparison

Training type: Not reported

Inference type: On-device

Hardware

Device: Raspberry Pi 4; Intel Xeon CPU @ 2.20GHz; Tesla T4 GPU; Tesla NVIDIA V100 GPU server for training

Hardware type: SoC / CPU / GPU

Processor / microcontroller: Raspberry Pi 4 processor not specified; Intel Xeon @ 2.20GHz reported for CPU benchmarking

Clock frequency: 2.20GHz for Intel Xeon CPU; Raspberry Pi 4 clock frequency not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, processing power, latency, compute, communication/cloud dependency

Dataset

Name: Sidewalk Obstacle Detection (SOD), SOD-v2

Type: Public/custom

Dataset size: 10,000 images; 30,834 object instances; 7,000 train images, 2,000 validation images, 1,000 test images; training subset augmented to 21,000 images

Number of classes: 22

Input resolution: 640×640

Data modality: Image

Metrics

Accuracy: Not reported

mAP: YOLOv8s: 60.0% mAP_50 and 42.8% mAP_50:95; YOLOv8n: 57.7% mAP_50 and 39.6% mAP_50:95; YOLOv5s: 56.1% mAP_50 and 35.7% mAP_50:95; YOLOv5n: 51.7% mAP_50 and 31.2% mAP_50:95; quantized YOLOv5n: 50.0% mAP_50 and 28.8% mAP_50:95

Precision: YOLOv5n on SOD-v2 test: 58.5%; YOLOv5n on dark images: 55.2%

Recall: YOLOv5n on SOD-v2 test: 50.2%; YOLOv5n on dark images: 39.8%

F1-score: YOLOv8s: 0.61; YOLOv8n: 0.57; YOLOv5s: 0.59; YOLOv5n: 0.53

Latency: YOLOv5n base: 592.0 ms on Raspberry Pi 4 and 181.7 ms on CPU; quantized YOLOv5n: 394.1 ms on Raspberry Pi 4 and 178.1 ms on CPU; OpenVINO YOLOv5n: 96.2 ms on CPU

FPS: Not reported

Throughput: Not reported

Model size: YOLOv5n base: 3.78 MB; quantized YOLOv5n: 1.93 MB; YOLOv8n: 5.96 MB; YOLOv5s: 13.88 MB; YOLOv8s: 21.5 MB

Parameters: YOLOv5n: 1.78M; YOLOv8n: 3.0M; YOLOv5s: 7.07M; YOLOv8s: 11.13M

MACs / FLOPs: YOLOv5n: 4.2G FLOPs; YOLOv8n: 8.1G FLOPs; YOLOv5s: 16.1G FLOPs; YOLOv8s: 28.5G FLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Quantization, weight pruning, ONNX Runtime, OpenVINO

Quantization: INT8

Pruning: Yes

Knowledge distillation: No

Compression method: Quantization and weight pruning

Hardware-specific optimization: OpenVINO CPU acceleration; ONNX Runtime inference acceleration

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes, minimum reported model size is 1.93 MB for quantized YOLOv5n

Energy per inference reported: Not reported

Latency on target device reported: Yes, Raspberry Pi 4 and CPU latency reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets TinyML and embedded IoT vision, but the reported deployment metrics are on Raspberry Pi 4 and CPU rather than MCU-class hardware with SRAM, Flash, no-OS, or energy evidence.

Benchmarking / Standardization

Benchmark used: SOD-v2; ExDARK subset for low-light robustness testing

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: MS-COCO; PASCAL-VOC; ExDARK

Comparison with baseline models: Yes, YOLOv5n, YOLOv5s, YOLOv8n, YOLOv8s, SSD MobileNet V2 FPNLite, EfficientDet-D1, Faster R-CNN ResNet50 V1

Comparison with previous works: Yes

Reproducibility artifacts available: code / dataset

Results

Summary: YOLOv8s achieved the highest detection performance with 60.0% mAP_50 and 42.8% mAP_50:95. YOLOv5n was the most compact model, reaching 1.93 MB after quantization, 50.0% mAP_50, and 394.1 ms latency on Raspberry Pi 4. OpenVINO reduced YOLOv5n CPU latency to 96.2 ms.

Limitations

The object detection task does not fully understand crowded sidewalk scenes.

The proposed model cannot provide safe and autonomous navigation for visually impaired people.

The model requires further investigation for real-time application deployment.

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

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a TinyML-oriented YOLO-based sidewalk obstacle detection model and SOD-v2 dataset for assisting blind and visually impaired people using lightweight object detection on resource-constrained IoT/edge devices.

| Paper             | Year | Task             | Model             | Technique                                         | Device               | Dataset | Main Metric  | Latency                                    | Model Size | SRAM/RAM | Flash | Energy | Framework                       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------------- | ---- | ---------------- | ----------------- | ------------------------------------------------- | -------------------- | ------- | ------------ | ------------------------------------------ | ---------- | -------- | ----- | ------ | ------------------------------- | -------- | ------------- | ------------- |
| Boussihmed et al. | 2025 | Object Detection | YOLOv5n / YOLOv8s | Quantization, pruning, OpenVINO/ONNX acceleration | Raspberry Pi 4 / CPU | SOD-v2  | 60.0% mAP_50 | 394.1 ms on Raspberry Pi 4; 96.2 ms on CPU | 1.93 MB    | N/A      | N/A   | N/A    | PyTorch, ONNX Runtime, OpenVINO | INT8     | None          | No            |
