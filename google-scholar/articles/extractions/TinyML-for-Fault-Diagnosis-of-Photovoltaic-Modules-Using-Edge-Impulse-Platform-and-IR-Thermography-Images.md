Paper ID: TinyML-for-Fault-Diagnosis-of-Photovoltaic-Modules-Using-Edge-Impulse-Platform-and-IR-Thermography-Images

TinyML classification: Strict TinyML — explicitly targets low-power MCU deployment using Edge Impulse on Arduino Nano 33 BLE Sense and Arduino Portenta H7 with reported memory and latency constraints.

## Basic Info

Authors: A. Mellit, N. Blasuttigh, S. Pastore, M. Zennaro, A. Massi Pavan 

Year: 2025

Title: TinyML for Fault Diagnosis of Photovoltaic Modules Using Edge Impulse Platform and IR Thermography Images 

Source: IEEE Transactions on Industry Applications, Vol. 61, No. 5, September/October 2025 

Type: Experimental

## Problem & Context

Task: Classification

Objective: Classify photovoltaic module faults from infrared thermography images using a TinyML model deployed on low-power MCU hardware.

Application domain: Photovoltaic module fault diagnosis

Scenario: Edge, embedded, MCU, low-power on-device inference

TinyML relevance: Yes

TinyML justification: The paper develops a TinyML model using Edge Impulse and evaluates feasibility on Arduino Nano 33 BLE Sense and Arduino Portenta H7 MCUs, reporting hardware resources, quantization, and inference latency. 

## Model / Method

Model: MobileNetV1 and MobileNetV2; selected model is MobileNetV2.

Architecture family: CNN

Techniques: Transfer learning, INT8 post-training quantization evaluation, width multiplier tuning, input resolution sensitivity analysis, Edge Impulse EON compiler deployment.

Framework: Edge Impulse

Training type: Transfer learning

Inference type: On-device

## Hardware

Device: Arduino Portenta H7 for selected best model; Arduino Nano 33 BLE Sense also evaluated.

Hardware type: MCU

Processor / microcontroller: Arduino Portenta H7: Arm Cortex M7-M4 dual core; Arduino Nano BLE Sense Rev2: nRF52840.

Clock frequency: Arduino Portenta H7: 480–240 MHz; Arduino Nano BLE Sense Rev2: 64 MHz.

SRAM / RAM: Arduino Portenta H7: 1 MB; Arduino Nano BLE Sense Rev2: 256 kB.

Flash / ROM / Storage: Arduino Portenta H7: 2 MB; Arduino Nano BLE Sense Rev2: 1 MB.

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, flash, latency, hardware resources, low power, bandwidth, communication, energy constraints, data privacy.

## Dataset

Name: Not reported

Type: Private

Dataset size: 2000 IR thermography images

Number of classes: 4

Input resolution: 256×192 collected images; selected model input resolution 96×96.

Data modality: Infrared thermography images

## Metrics

Accuracy: 98% average test accuracy for selected MobileNetV2 model; class accuracies: D1 99.1%, D2 96.1%, D3 96.9%, N 100%.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: D1 99%, D2 97%, D3 98%, N 100%.

Latency: 242 ms estimated on Arduino Portenta H7 for selected MobileNetV2 model; 331 ms co-simulation inference time reported on Arduino Portenta H7.

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: 894 kB for selected MobileNetV2 model.

Flash usage: 1.6 MB for selected MobileNetV2 model.

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Input resolution tuning, width multiplier tuning, INT8 post-training quantization evaluation, Edge Impulse EON compiler hardware-optimized C++ generation.

Quantization: PTQ INT8 evaluated; selected best model is non-quantized FP32.

Pruning: No

Knowledge distillation: No

Compression method: INT8 quantization evaluated; width multiplier reduction evaluated.

Hardware-specific optimization: Edge Impulse EON compiler used to generate hardware-optimized C++ source code and Arduino library.

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: 894 kB RAM usage for selected MobileNetV2 model.

Flash usage reported: 1.6 MB flash usage for selected MobileNetV2 model.

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 242 ms estimated on Arduino Portenta H7; 331 ms co-simulation inference time.

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets MCU-class deployment on Arduino Nano 33 BLE Sense and Arduino Portenta H7, with reported RAM, flash, latency, quantization, and fully local inference.

## Benchmarking / Standardization

Benchmark used: Custom PV infrared thermography dataset.

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: MobileNetV1 and MobileNetV2 compared across input sizes, width multipliers, and quantization settings.

Comparison with previous works: Yes, related PV fault diagnosis methods are compared in Table I.

Reproducibility artifacts available: Not reported

## Results

Summary: The selected non-quantized MobileNetV2 model achieved 98% average test accuracy using 96×96 input resolution and was deployed on Arduino Portenta H7. Quantized MobileNetV2 reached up to 88% accuracy, while MobileNetV1 reached up to 91.2% non-quantized and 87.5% quantized. The deployed prototype demonstrated real-time PV fault classification using a 3D-printed thermal camera.

Limitations: The model failed or underperformed for some emerging defects such as overheated wires and junction boxes, and the authors state that additional defect classes, multi-defect cases, broader datasets, quantitative temperature analysis, and power-loss estimation remain future work.

## Practical Reporting Checklist Evidence

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

## Contribution

This paper proposes a TinyML-based embedded PV fault diagnosis system that uses Edge Impulse and MobileNet models to classify infrared thermography images on low-power Arduino MCU hardware.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Mellit et al. | 2025 | Classification | MobileNetV2 | EON compilation; input-size/width-multiplier tuning; INT8 PTQ evaluated | Arduino Portenta H7 | Custom PV IR thermography dataset | 98% accuracy | 331 ms | N/A | 894 kB | 1.6 MB | N/A | Edge Impulse | FP32 | N/A | Yes |
