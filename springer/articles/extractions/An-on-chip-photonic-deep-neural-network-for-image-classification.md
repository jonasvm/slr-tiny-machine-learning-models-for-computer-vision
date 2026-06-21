Paper ID: An-on-chip-photonic-deep-neural-network-for-image-classification

Basic Info

Authors: Farshid Ashtiani; Alexander J. Geers; Firooz Aflatouni

Year: 2022

Title: An on-chip photonic deep neural network for image classification

Source: Nature 

Type: Experimental

Problem & Context

Task: Classification

Objective: Demonstrate an integrated end-to-end photonic deep neural network chip for sub-nanosecond image classification through direct optical processing.

Application domain: Handwritten letter image classification

Scenario: On-chip photonic integrated hardware / optical neural-network inference

TinyML relevance: Partial

TinyML justification: The paper reports on-chip, low-latency, energy-efficiency-oriented inference hardware, but it does not target MCU-class deployment, TensorFlow Lite Micro, SRAM/Flash-constrained execution, or bare-metal/RTOS TinyML systems.

Model / Method

Model: Photonic deep neural network (PDNN)

Architecture family: Other

Techniques: Optical weighted-sum computation, opto-electronic ReLU activation, direct clock-less optical processing, on-chip pixel array, photonic routing, supply-light distribution

Framework: Keras for off-chip training and weight optimization

Training type: From scratch

Inference type: On-device

Hardware

Device: Integrated PDNN chip fabricated in AMF 180-nm silicon-on-insulator process, packaged with off-chip integrated amplifiers

Hardware type: Other

Processor / microcontroller: ATmel ATSAM3X8E microcontroller used for control; inference processor not reported

Clock frequency: Not reported; processing is described as clock-less

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: 3.75 W in high-speed mode; about 2 W in low-speed mode; 990 mW for linear weighted-sum operations

Energy per inference: Not reported; 14 pJ/OP end-to-end efficiency and 345 fJ/OP per layer are reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Latency, power consumption, energy efficiency, memory access, analogue-to-digital conversion, data transfer, photonic loss, bandwidth, scalability, routing complexity

Dataset

Name: Printed handwritten letters

Type: Private

Dataset size: 216 letters per iteration for two-class classification; 432 letters per iteration for four-class classification

Number of classes: 2 and 4

Input resolution: 5 × 6 pixel on-chip array

Data modality: Optical image formed from printed handwritten letters

Metrics

Accuracy: 93.8% for two-class classification; 89.8% for four-class classification; Keras CNN baseline achieved about 96% on the same four-class dataset

mAP: Not reported

Precision: Two-class: 92.8% and 94.9%; four-class: 97.9%, 93.5%, 81.9%, and 81.4%

Recall: Two-class: 95.1% and 92.6%; four-class: 87.1%, 83.3%, 92.6%, and 96.3%

F1-score: Not reported

Latency: 570 ps end-to-end high-speed classification time; under 1 µs in low-speed mode; about 425 ps on-chip photonic circuit delay

FPS: Not reported

Throughput: 0.27 TOPS end-to-end; 2.07 TOPS linear weight-sum operations; 3.5 TOPS/mm² linear computation density

Model size: Not reported

Parameters: 66 weight-setting PIN attenuators

MACs / FLOPs: 153 equivalent operations per classification

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported; 14 pJ/OP end-to-end efficiency and 345 fJ/OP per layer are reported

Power consumption: 3.75 W high-speed mode; about 2 W low-speed mode

Optimization

Techniques used: Custom photonic integrated computation, optical weighted sums, opto-electronic ReLU, clock-less propagation-based inference, balanced optical routing, supply-light distribution

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Not reported

Hardware-specific optimization: Yes; the neural network is implemented as a custom photonic-electronic chip using PIN attenuators, SiGe photodiodes, micro-ring modulators, and nanophotonic waveguides

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: No

Flash usage reported: No

Model size reported: No

Energy per inference reported: No

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No data-transfer module is required for input processing; external measurement/control equipment is used in the experimental setup

Candidate for Strict TinyML: No

Reason: The work uses a custom photonic integrated chip with watt-level power and no MCU-class SRAM/Flash, TFLM, CMSIS-NN, or bare-metal/RTOS deployment evidence.

Benchmarking / Standardization

Benchmark used: Printed handwritten-letter classification dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: None; MNIST is mentioned only as a reference for the baseline CNN architecture

Comparison with baseline models: Yes; compared with a conventional Keras CNN classifier achieving about 96% accuracy on the same four-class dataset

Comparison with previous works: Yes; compared with optical and electronic implementations including smart cameras, Edge TPU-based systems, and photonic neural networks

Reproducibility artifacts available: Dataset; code available on reasonable request

Results

Summary: The PDNN chip achieved 93.8% accuracy for two-class and 89.8% accuracy for four-class handwritten-letter classification. It demonstrated 570 ps end-to-end classification time in high-speed mode, 0.27 TOPS end-to-end throughput, and 14 pJ/OP end-to-end efficiency.

Limitations

The demonstration uses a small 5 × 6 pixel input and printed handwritten-letter datasets with two or four classes. The classification speed is limited by the bandwidth of the micro-ring modulators, SiGe photodiodes, and transimpedance amplifiers, while scalability requires addressing photonic routing complexity and supply-light distribution.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes an integrated end-to-end photonic deep neural network chip that directly processes optical images on an on-chip pixel array for sub-nanosecond handwritten-letter classification.

| Paper           | Year | Task           | Model | Technique                                                                        | Device                                                                  | Dataset                     | Main Metric                                | Latency | Model Size | SRAM/RAM | Flash | Energy           | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---: | -------------- | ----- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------- | --------------------------- | ------------------------------------------ | ------- | ---------- | -------- | ----- | ---------------- | --------- | -------- | ------------- | ------------- |
| Ashtiani et al. | 2022 | Classification | PDNN  | On-chip photonic computation with optical weighted sums and opto-electronic ReLU | PDNN chip, AMF 180-nm SOI, packaged with off-chip integrated amplifiers | Printed handwritten letters | Accuracy 93.8% two-class; 89.8% four-class | 570 ps  | N/A        | N/A      | N/A   | 14 pJ/OP; 3.75 W | Keras     | N/A      | None          | No            |
