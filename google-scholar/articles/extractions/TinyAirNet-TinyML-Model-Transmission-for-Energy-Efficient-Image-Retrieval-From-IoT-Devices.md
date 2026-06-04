Paper ID: TinyAirNet-TinyML-Model-Transmission-for-Energy-Efficient-Image-Retrieval-From-IoT-Devices

TinyML classification: Strict TinyML — Explicitly discusses MCU-class constraints, including limited SRAM/Flash, TinyML model transmission, quantization, and STM32F746-oriented image settings.

## Basic Info

Authors: Junya Shiraishi, Mathias Thorsager, Shashi Raj Pandey, and Petar Popovski
Year: 2024
Title: TinyAirNet: TinyML Model Transmission for Energy-Efficient Image Retrieval From IoT Devices
Source: IEEE Communications Letters, Vol. 28, No. 9, September 2024 
Type: Methodological

## Problem & Context

Task: Image retrieval
Objective: Reduce overall energy consumption for pull-based IoT image retrieval by transmitting a TinyML model to IoT devices for local semantic filtering.
Application domain: 6G IoT networks; wireless image retrieval; AI-empowered IoT data collection
Scenario: Edge/IoT single-device scenario with a mobile robot capturing and storing camera images
TinyML relevance: Yes
TinyML justification: The paper explicitly uses TinyML models on memory-constrained IoT devices, discusses MCU SRAM/Flash limits, considers computation/communication/memory costs, and evaluates quantized TinyML model transmission.

## Model / Method

Model: TinyAirNet using a TinyML feature extractor; EtinyNet1.0 parameters used for numerical evaluation
Architecture family: Not reported
Techniques: TinyML model transmission, semantic query filtering, fixed-point QNN energy modeling, quantization-level analysis, threshold-based similarity filtering
Framework: Not reported
Training type: Not reported
Inference type: Hybrid

## Hardware

Device: Single IoT device / mobile robot; STM32F746 MCUs considered for image-size setting
Hardware type: MCU / Other
Processor / microcontroller: STM32F746 MCU considered
Clock frequency: Not reported
SRAM / RAM: Typical MCU SRAM constraint mentioned as <512 KB; actual SRAM usage not reported
Flash / ROM / Storage: Typical MCU flash constraint mentioned as <2 MB; actual flash usage not reported
Power consumption: NB-IoT transmit power 170 mW; receive power 160 mW
Energy per inference: Not reported
Execution without full OS: Not reported
Fully on-device inference: No
Constraints mentioned: Memory, energy, computation, communication, model size, quantization, retrieval accuracy

## Dataset

Name: Not reported
Type: Synthetic / not reported
Dataset size: N stored images; N=10 used in one evaluation and N varied in other evaluations
Number of classes: Not reported
Input resolution: 3 × 256 × 256 with 8-bit pixels
Data modality: RGB image

## Metrics

Accuracy: Retrieval accuracy γ; target retrieval accuracy γth = 0.98 in evaluations
mAP: Not reported
Precision: Not reported
Recall: Not reported
F1-score: Not reported
Latency: Not reported
FPS: Not reported
Throughput: Not reported
Model size: Ns = 0.976 M weights and biases
Parameters: 0.976 M weights and biases
MACs / FLOPs: Nc = 117 M MUAC operations
RAM usage: Not reported
Flash usage: Not reported
Energy per inference: Not reported
Power consumption: NB-IoT transmit power 170 mW; receive power 160 mW

## Optimization

Techniques used: TinyML model transmission, fixed-point QNN modeling, quantization-level comparison, threshold optimization for energy/retrieval trade-off
Quantization: INT8 and 16-bit fixed-point modeled; QAT/PTQ not reported
Pruning: Not reported
Knowledge distillation: Not reported
Compression method: Compression from large model M to TinyML model M̂ is described conceptually; specific implemented compression method not reported
Hardware-specific optimization: Not reported
Use of CMSIS-NN: Not reported
Use of TensorFlow Lite Micro: Not reported
Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: No; typical MCU SRAM constraint <512 KB mentioned
Flash usage reported: No; typical MCU flash constraint <2 MB mentioned
Model size reported: Yes; Ns = 0.976 M weights and biases
Energy per inference reported: No
Latency on target device reported: No
Runs without full operating system: Not reported
Fully on-device inference: No
Communication required during inference: Yes
Candidate for Strict TinyML: Yes
Reason: The paper explicitly targets TinyML for memory-constrained IoT/MCU-class devices and considers MCU SRAM/Flash constraints, quantization, communication, and energy, although real-device deployment metrics are not reported.

## Benchmarking / Standardization

Benchmark used: Custom numerical simulation with baseline offloading scheme
MLPerf Tiny mentioned: No
Visual Wake Words mentioned: No
Other standard benchmark: ImageNet mentioned only as background; not used as an evaluation benchmark
Comparison with baseline models: Yes; compared against simple offloading where the IoT device transmits all observations without computation
Comparison with previous works: Not reported
Reproducibility artifacts available: Not reported

## Results

Summary: TinyAirNet achieved up to 67% energy reduction under an accuracy constraint when many images are stored. Theoretical and simulation results matched, and the method became more energy-efficient than the baseline as the number of stored images increased.
Limitations: Evaluation is theoretical/numerical rather than experimental; the main scenario is single-device; multi-device and experimental evaluation are left for future work.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes
Reports memory usage: No
Reports latency: No
Reports energy or power: Yes
Reports model size: Yes
Reports optimization method: Yes
Reports deployment framework: No
Reports dataset and preprocessing: No
Reports evaluation metric clearly: Yes
Reports reproducibility artifacts: No

## Contribution

This paper proposes TinyAirNet, an energy-efficient pull-based IoT image retrieval framework that transmits a TinyML model from an edge server to IoT devices for local semantic filtering before image transmission.

| Paper            | Year | Task            | Model                               | Technique                                                      | Device                                      | Dataset              | Main Metric                                          | Latency | Model Size             | SRAM/RAM                                  | Flash                                   | Energy                                  | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---- | --------------- | ----------------------------------- | -------------------------------------------------------------- | ------------------------------------------- | -------------------- | ---------------------------------------------------- | ------- | ---------------------- | ----------------------------------------- | --------------------------------------- | --------------------------------------- | --------- | -------- | ------------- | ------------- |
| Shiraishi et al. | 2024 | Image retrieval | TinyAirNet / EtinyNet1.0 parameters | TinyML model transmission + quantization-level energy modeling | STM32F746 MCU considered / IoT mobile robot | Synthetic simulation | Up to 67% energy reduction under accuracy constraint | N/A     | 0.976 M weights/biases | <512 KB typical MCU constraint; usage N/A | <2 MB typical MCU constraint; usage N/A | Tx 170 mW; Rx 160 mW; per-inference N/A | N/A       | INT8     | N/A           | Yes           |
