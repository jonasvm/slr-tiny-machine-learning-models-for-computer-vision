Paper ID: Embedded-Edge-Artificial-Intelligence-for-Longitudinal-Rip-Detection-in-Conveyor-Belt-Applied-at-the-Industrial-Mining-Environment

TinyML classification: Strict TinyML — The paper explicitly uses a constrained K210 RISC-V edge device with 0.008 GB RAM, KPU acceleration, MicroPython, and compiled .kmodel local inference.

## Basic Info

Authors: Emerson Klippel; Ricardo Augusto Rabelo Oliveira; Dmitry Maslov; Andrea Gomes Campos Bianchi; Saul Emanuel Delabrida; Charles Tim Batista Garrocho

Year: 2022

Title: Embedded Edge Artificial Intelligence for Longitudinal Rip Detection in Conveyor Belt Applied at the Industrial Mining Environment

Source: SN Computer Science 

Type: Experimental

## Problem & Context

Task: Classification

Objective: Detect longitudinal rips in conveyor belts using images captured in real time and a DNN model executed locally on an edge device.

Application domain: Industrial mining environment

Scenario: Edge, embedded, industrial IoT

TinyML relevance: Yes

TinyML justification: The paper deploys local image classification on a SiPEED MAiX BiT/Kendryte K210 edge device with 0.008 GB RAM, MicroPython/uPython, KPU acceleration, and no centralized processing during inference.

## Model / Method

Model: 0.75 MobileNet-224 classifier

Architecture family: CNN

Techniques: Transfer learning, model conversion to `.tflite`, nncase compilation/compression to `.kmodel`, hardware-accelerated inference on KPU

Framework: aXeleRate, Keras-TensorFlow, TensorFlow Lite, nncase, MaixPy/MicroPython

Training type: Transfer learning

Inference type: On-device

## Hardware

Device: SiPEED MAiX BiT

Hardware type: SoC

Processor / microcontroller: Kendryte K210 RISC-V SoC with KPU convolutional neural network accelerator

Clock frequency: 0.40 GHz

SRAM / RAM: 0.008 GB

Flash / ROM / Storage: SD card used to store images and execute the `.kmodel`; flash/ROM not reported

Power consumption: 5 W power rating

Energy per inference: Not reported

Execution without full OS: Yes

Fully on-device inference: Yes

Constraints mentioned: Connectivity restrictions, communication latency, processing capacity, memory, energy, real-time operation

## Dataset

Name: Conveyor belt tear image dataset

Type: Private

Dataset size: 792 photos total; 396 damaged belt images and 396 normal belt images

Number of classes: 2

Input resolution: 224 × 224

Data modality: Image/photos

## Metrics

Accuracy: 94.6% training accuracy

mAP: Not reported

Precision: 100% on Google Colab validation; 100% on SiPEED validation; 100% in field tests

Recall: 97% on Google Colab validation; 97% on SiPEED validation; 93% in field tests

F1-score: 99% on Google Colab validation; 99% on SiPEED validation; 96% in field tests

Latency: Not reported

FPS: 6 fps on SiPEED during field tests

Throughput: 6 fps

Model size: Not reported

Parameters: 3.3 million parameters for 0.75 MobileNet-224 as reported in the model comparison table

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 5 W power rating

## Optimization

Techniques used: MobileNet lightweight architecture, transfer learning, nncase model compression/compilation, KPU hardware acceleration

Quantization: Not reported

Pruning: No

Knowledge distillation: No

Compression method: nncase compilation/compression to `.kmodel`

Hardware-specific optimization: Compilation for Kendryte K210 KPU

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported; FPS reported as 6 fps

Runs without full operating system: Yes

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: Yes

Reason: The paper deploys a CNN classifier on a constrained K210-based SiPEED MAiX BiT device with 0.008 GB RAM, MicroPython/uPython execution, KPU acceleration, and fully local inference.

## Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet used for transfer learning; Stanford Dogs cited only in MobileNet model comparison

Comparison with baseline models: No experimental baseline models on the proposed dataset; compares validation results between Google Colab and SiPEED execution

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

## Results

Summary: The 0.75 MobileNet-224 model reached 94.6% training accuracy and achieved identical validation results on Google Colab and SiPEED, with precision 100%, recall 97%, and F1-score 99%. In 9 field-test campaigns with 180 exposures, the prototype achieved precision 100%, recall 93%, F1-score 96%, and 6 fps.

Limitations: The paper states that future improvements are needed for automatic verification of optical lens cleanliness, sensor positioning, and lighting conditions; at 6 fps and 5 m/s belt speed, the smallest detectable longitudinal rip would be 0.8 m.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes an embedded edge AI prototype using a MobileNet classifier deployed on a SiPEED MAiX BiT/Kendryte K210 device for real-time longitudinal rip detection in industrial conveyor belts.

| Paper          | Year | Task           | Model              | Technique                                   | Device                          | Dataset                           | Main Metric       | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework                                            | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | -------------- | ------------------ | ------------------------------------------- | ------------------------------- | --------------------------------- | ----------------- | ------- | ---------- | -------- | ----- | ------ | ---------------------------------------------------- | -------- | ------------- | ------------- |
| Klippel et al. | 2022 | Classification | 0.75 MobileNet-224 | nncase compilation/compression for K210 KPU | SiPEED MAiX BiT / Kendryte K210 | Private conveyor belt tear images | F1 96% field test | N/A     | N/A        | 0.008 GB | N/A   | N/A    | aXeleRate/Keras-TensorFlow + TFLite + nncase/.kmodel | N/A      | None          | Yes           |
