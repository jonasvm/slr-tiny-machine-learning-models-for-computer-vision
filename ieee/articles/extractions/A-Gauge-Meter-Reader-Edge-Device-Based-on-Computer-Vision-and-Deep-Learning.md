Paper ID: A-Gauge-Meter-Reader-Edge-Device-Based-on-Computer-Vision-and-Deep-Learning

TinyML classification: Near-TinyML — The deployment targets Raspberry Pi Zero edge hardware, with no explicit MCU-class or Cortex-M/TFLite Micro deployment evidence.

## Basic Info

Authors: Wei-Jie Wang and Paul D. Rosero-Montalvo

Year: 2025

Title: A Gauge Meter Reader Edge Device Based on Computer Vision and Deep Learning

Source: IEEE Embedded Systems Letters, Vol. 17, No. 4, August 2025 

Type: Experimental

## Problem & Context

Task: Object Detection

Objective: Develop an edge device with a small camera to digitize analog gauge readings using object detection and pointer angle estimation.

Application domain: Industrial and manufacturing analog gauge monitoring

Scenario: Edge device, embedded vision, industrial IoT

TinyML relevance: Partial

TinyML justification: The paper targets on-device edge inference on Raspberry Pi Zero with a small quantized model, but does not report MCU-class, Cortex-M, bare-metal, RTOS, or TensorFlow Lite Micro deployment.

## Model / Method

Model: YOLOv5 nano and YOLOv5 small evaluated; YOLOv5 small selected for further deployment steps.

Architecture family: CNN

Techniques: Object detection, data augmentation, dynamic range quantization, Float16 quantization, 16×8 quantization, pointer angle estimation

Framework: TensorFlow instructions for quantization; YOLOv5 framework not reported

Training type: From scratch and pretrained weights evaluated; model trained from scratch used in further sections

Inference type: On-device

## Hardware

Device: Raspberry Pi Zero HW

Hardware type: CPU / SoC edge device

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Low computational capability, low power consumption, model size, edge deployment

## Dataset

Name: Dataset provided by Howells et al. [13]

Type: Not reported

Dataset size: 900 images from high-resolution videos of two similar analog meters; split 70:20:10 for train, validation, and test

Number of classes: 5 annotated target objects: minimum value mark, maximum value mark, pointer, pointer center, and pointer tip

Input resolution: Not reported

Data modality: Image frames from video

## Metrics

Accuracy: Using pretrained weights, 99% accuracy on each object; training from scratch achieved 100% accuracy in two of five objects and 99% in the rest

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: 2 MB for DRQ and Q16×8; 3.7 MB for FQ16

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Dynamic range quantization, Float16 quantization, 16×8 quantization

Quantization: INT8 PTQ dynamic range quantization selected; FP16 and mixed 16×8 quantization also evaluated

Pruning: No

Knowledge distillation: No

Compression method: Post-training quantization

Hardware-specific optimization: Quantization for Raspberry Pi Zero edge deployment

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 2 MB

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported; readings are intended to be sent to a server for further analysis

Candidate for Strict TinyML: No

Reason: The target hardware is Raspberry Pi Zero edge hardware, with no explicit MCU-class deployment, SRAM/Flash usage, bare-metal or RTOS execution, or TensorFlow Lite Micro evidence.

## Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: YOLOv5 nano and YOLOv5 small compared; pointer detection and pointer-tip detection approaches compared; quantization techniques compared

Comparison with previous works: Compared with Howells et al. [13], which deployed an analog gauge reading model on cell phones

Reproducibility artifacts available: Not reported

## Results

Summary: The deployed quantized model achieved ±0.261 bar average deviation and ±0.584 bar maximum error on Meter A, and ±1.438 psi average deviation and ±3.091 psi maximum error on Meter B. The selected DRQ model size was 2 MB.

Limitations

Not explicitly stated; future work suggests comparing the ML model with other ML methods and using knowledge distillation to further shrink the model.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes an edge-device analog gauge reader that uses YOLOv5-based object detection, quantization, and pointer angle estimation to convert analog meter readings into digital values.

| Paper       | Year | Task             | Model        | Technique                  | Device            | Dataset                                         | Main Metric                         | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework                            | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ---------------- | ------------ | -------------------------- | ----------------- | ----------------------------------------------- | ----------------------------------- | ------- | ---------- | -------- | ----- | ------ | ------------------------------------ | -------- | ------------- | ------------- |
| Wang et al. | 2025 | Object Detection | YOLOv5 small | Dynamic range quantization | Raspberry Pi Zero | Howells et al. analog gauge dataset; 900 images | ±0.261 bar AADV and ±1.438 psi AADV | N/A     | 2 MB       | N/A      | N/A   | N/A    | TensorFlow quantization instructions | INT8/PTQ | None          | No            |
