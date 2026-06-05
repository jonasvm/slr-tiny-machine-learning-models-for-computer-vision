Paper ID: Efficient-solid-waste-inspection-through-drone-based-aerial-imagery-and-TinyML-vision-model

TinyML classification: Strict TinyML — Explicitly reports TinyML deployment on MCU-class/ultra-low-power boards with 240.4 K RAM, 61.9 K flash, and device-level latency/accuracy metrics.

Basic Info

Authors: Timothy Malche; Priti Maheshwary; Pradeep Kumar Tiwari; Ahmed Hussein Alkhayyat; Abhinav Bansal; Raghvendra Kumar

Year: 2024

Title: Efficient solid waste inspection through drone-based aerial imagery and TinyML vision model

Source: Transactions on Emerging Telecommunications Technologies, 35(4):e4878, DOI: 10.1002/ett.4878 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Detect and classify garbage objects from drone-captured imagery using a TinyML computer vision model on resource-constrained devices.

Application domain: Smart city solid waste management

Scenario: Drone-based edge/embedded IoT monitoring

TinyML relevance: Yes

TinyML justification: The paper targets resource-constrained devices, quantizes the model to INT8, and reports RAM, flash, latency, and accuracy on embedded hardware platforms. 

Model / Method

Model: Improved Faster R-CNN TinyML vision model

Architecture family: CNN

Techniques: Improved IoU loss, Soft-NMS, INT8 quantization, Edge Impulse EON Compiler optimization, data augmentation

Framework: Edge Impulse BYOM; EON Compiler; PyTorch/ONNX shown in Figure 10

Training type: Not reported

Inference type: On-device

Hardware

Device: Sony Spresense; Arduino Nicla Vision; Arduino Portenta H7; Espressif ESP-EYE; Himax WE-I

Hardware type: MCU-class / resource-constrained embedded vision boards

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: 240.4 K RAM usage

Flash / ROM / Storage: 61.9 K flash usage

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, processing power, latency, storage, edge inference, communication/data upload

Dataset

Name: Local Jaipur garbage dataset + Kaggle/open-source image datasets

Type: Private + public

Dataset size: Around 2500 images; 6929 labeled instances

Number of classes: 6

Input resolution: Not reported

Data modality: RGB image; drone/smartphone images; image or video mentioned

Metrics

Accuracy: 91% overall; 90.6% Sony Spresense; 90.1% Arduino Nicla Vision; 90.9% Arduino Portenta H7; 91.2% Espressif ESP-EYE; 91.1% Himax WE-I

mAP: 0.91 test; 0.90 validation

Precision: 0.91 test; 0.90 validation

Recall: 0.84 test; 0.79 validation

F1-score: 0.88 test; 0.79 validation

Latency: 365 ms Sony Spresense; 61 ms Arduino Nicla Vision; 44 ms Arduino Portenta H7; 1043 ms Espressif ESP-EYE; 1043 ms Himax WE-I

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: 240.4 K

Flash usage: 61.9 K

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: INT8 quantization, Edge Impulse BYOM, EON Compiler, weight and activation quantization, dynamic range adjustment, fine-tuning, Improved IoU, Soft-NMS

Quantization: INT8

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: INT8 quantization using Edge Impulse EON Compiler

Hardware-specific optimization: Edge Impulse EON Compiler optimization for edge/resource-constrained devices

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Yes, 61.9 K

Model size reported: Not reported

Energy per inference reported: No

Latency on target device reported: Yes, 44–1043 ms depending on device

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No; cloud/LoRa communication is described for data upload and access after edge inference

Candidate for Strict TinyML: Yes

Reason: The paper reports INT8 TinyML deployment metrics on resource-constrained embedded vision devices with 240.4 K RAM usage, 61.9 K flash usage, and device-level latency.

Benchmarking / Standardization

Benchmark used: Custom waste object detection dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Not reported

Comparison with previous works: Yes, Table 1 compares existing garbage detection and classification approaches

Reproducibility artifacts available: Not reported

Results

Summary: The improved Faster R-CNN TinyML model achieved 0.91 test mAP and 0.90 validation mAP. The quantized model reported 240.4 K RAM usage, 61.9 K flash usage, and best latency of 44 ms on Arduino Portenta H7.

Limitations

Not reported

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a drone-based solid waste inspection system using an INT8-quantized improved Faster R-CNN TinyML vision model for on-device garbage object detection on resource-constrained embedded platforms.

| Paper         | Year | Task             | Model                 | Technique         | Device                                                                         | Dataset                                                    | Main Metric                    | Latency                               | Model Size | SRAM/RAM | Flash  | Energy | Framework                       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | ---------------- | --------------------- | ----------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------- | ------------------------------ | ------------------------------------- | ---------- | -------- | ------ | ------ | ------------------------------- | -------- | ------------- | ------------- |
| Malche et al. | 2024 | Object detection | Improved Faster R-CNN | INT8 quantization | Arduino Portenta H7; Arduino Nicla Vision; Sony Spresense; ESP-EYE; Himax WE-I | Local Jaipur garbage dataset + Kaggle/open-source datasets | mAP 0.91 test; 0.90 validation | 44 ms best; 61–1043 ms across devices | N/A        | 240.4 K  | 61.9 K | N/A    | Edge Impulse BYOM; EON Compiler | INT8     | N/A           | Yes           |
