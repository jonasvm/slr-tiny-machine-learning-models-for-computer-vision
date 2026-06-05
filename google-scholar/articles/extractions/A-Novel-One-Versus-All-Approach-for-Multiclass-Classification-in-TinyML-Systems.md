Paper ID: A-Novel-One-Versus-All-Approach-for-Multiclass-Classification-in-TinyML-Systems

TinyML classification: Strict TinyML — evaluated on an STM32L476RG ARM Cortex-M4 microcontroller with 1-MB Flash and 128-kB SRAM constraints.

Basic Info

Authors: Tobiasz Puslecki; Krzysztof Walkowiak

Year: 2025

Title: A Novel One-Versus-All Approach for Multiclass Classification in TinyML Systems

Source: IEEE Embedded Systems Letters, Vol. 17, No. 2, April 2025 

Type: Methodological

Problem & Context

Task: Classification

Objective: Improve energy efficiency and inference latency in TinyML multiclass classification using a thresholded one-versus-all method.

Application domain: Handwritten digit image classification

Scenario: Embedded, MCU-class TinyML system

TinyML relevance: Yes

TinyML justification: The paper explicitly targets TinyML systems with computation, memory, and energy constraints and profiles inference on an STM32L476RG ARM Cortex-M4 microcontroller.

Model / Method

Model: Thresholded One-Versus-All (TOVA) with logistic regression binary classifiers

Architecture family: Classical ML

Techniques: Threshold-based early exit, one-versus-all decomposition, fuzzy logic threshold selection

Framework: Python, NumPy, Scikit-learn, custom C-language profiling library

Training type: From scratch

Inference type: On-device

Hardware

Device: NUCLEO-L476RG module

Hardware type: MCU

Processor / microcontroller: STM32L476RG, 32-bit ARM Cortex-M4

Clock frequency: 80 MHz

SRAM / RAM: 128-kB SRAM

Flash / ROM / Storage: 1-MB Flash memory

Power consumption: Not reported; current consumption reported as 10.7 mA in inference mode and 1.18 µA in sleep mode at 3 V

Energy per inference: MNIST TOVA 13.77–124.64 µJ; MNIST OVA 138.42 µJ; USPS TOVA 5.65–52.97 µJ; USPS OVA 58.97 µJ

Execution without full OS: Not reported

Fully on-device inference: Yes for model profiling; full system behavior was simulated

Constraints mentioned: Computation, memory, energy, latency, battery capacity

Dataset

Name: MNIST; USPS

Type: Public

Dataset size: Not reported

Number of classes: 10

Input resolution: Not reported

Data modality: Grayscale image

Metrics

Accuracy: MNIST OVA 0.9171; MNIST TOVA 0.8380–0.9172; USPS OVA 0.9408; USPS TOVA 0.8750–0.9407

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: MNIST TOVA 0.39–3.53 ms; MNIST OVA 3.92 ms; USPS TOVA 0.16–1.50 ms; USPS OVA 1.67 ms

FPS: Not reported

Throughput: Synchronous simulation inferences: MNIST OVA 7,392,665; MNIST TOVA 10,715,577; USPS OVA 14,621,117; USPS TOVA 19,496,453

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: MNIST TOVA 13.77–124.64 µJ; MNIST OVA 138.42 µJ; USPS TOVA 5.65–52.97 µJ; USPS OVA 58.97 µJ

Power consumption: Not reported; current consumption reported as 10.7 mA inference and 1.18 µA sleep

Optimization

Techniques used: Thresholded OVA early exit and fuzzy logic threshold selector

Quantization: None reported

Pruning: No

Knowledge distillation: No

Compression method: Not reported

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Yes

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes for model profiling; full system behavior was simulated

Communication required during inference: Not reported

Candidate for Strict TinyML: Yes

Reason: The paper targets MCU-class TinyML deployment and profiles models on an STM32L476RG Cortex-M4 microcontroller with 1-MB Flash and 128-kB SRAM.

Benchmarking / Standardization

Benchmark used: MNIST; USPS

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: MNIST; USPS

Comparison with baseline models: Yes, OVA and LeNet5

Comparison with previous works: Not reported

Reproducibility artifacts available: Not reported

Results

Summary: TOVA reduces latency and energy consumption compared with OVA while causing only a small accuracy loss in synchronous simulations. In asynchronous simulations, TOVA reduces dropped samples and improves weighted accuracy under short sample intervals.

Limitations

Model ordering is identified as a relevant limitation, and future work will investigate classifier ordering and fuzzy inference system calibration.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a thresholded one-versus-all method for TinyML multiclass image classification that stops classifier evaluation early to reduce latency and energy consumption with limited accuracy loss.

| Paper           | Year | Task           | Model                                         | Technique                  | Device                                | Dataset     | Main Metric                                               | Latency           | Model Size | SRAM/RAM           | Flash             | Energy              | Framework                             | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---: | -------------- | --------------------------------------------- | -------------------------- | ------------------------------------- | ----------- | --------------------------------------------------------- | ----------------- | ---------- | ------------------ | ----------------- | ------------------- | ------------------------------------- | -------- | ------------- | ------------- |
| Puslecki et al. | 2025 | Classification | TOVA with logistic regression OVA classifiers | Threshold-based early exit | NUCLEO-L476RG / STM32L476RG Cortex-M4 | MNIST; USPS | Accuracy: MNIST TOVA up to 0.9172; USPS TOVA up to 0.9407 | 0.16–3.53 ms TOVA | N/A        | 128-kB SRAM device | 1-MB Flash device | 5.65–124.64 µJ TOVA | Scikit-learn; NumPy; custom C library | N/A      | None          | Yes           |
