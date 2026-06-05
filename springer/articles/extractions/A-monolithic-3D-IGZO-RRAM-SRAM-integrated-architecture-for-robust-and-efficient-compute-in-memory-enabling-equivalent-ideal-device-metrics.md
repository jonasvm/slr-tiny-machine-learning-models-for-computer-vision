Paper ID: A-monolithic-3D-IGZO-RRAM-SRAM-integrated-architecture-for-robust-and-efficient-compute-in-memory-enabling-equivalent-ideal-device-metrics

TinyML classification: Near-TinyML — Relevant edge/efficient AI hardware for vision inference, but no explicit microcontroller-class platform or MCU-level constraints are reported.

Basic Info

Authors: Shengzhe Yan; Zhaori Cong; Zi Wang; Zhuoyu Dai; Zeyu Guo; Zhihang Qian; Xufan Li; Xu Zheng; Chuanke Chen; Nianduan Lu; Chunmeng Dou; Guanhua Yang; Xiaoxin Xu; Di Geng; Jinshan Yue; Lingfei Wang; Ling Li; Ming Liu

Year: 2025

Title: A monolithic 3D IGZO-RRAM-SRAM-integrated architecture for robust and efficient compute-in-memory enabling equivalent-ideal device metrics

Source: Science China Information Sciences, Vol. 68, Iss. 2, 122404 

Type: Methodological

Problem & Context

Task: Classification

Objective: Propose and evaluate a monolithic 3D IGZO-RRAM-SRAM compute-in-memory architecture for robust, high-density, energy-efficient neural network inference.

Application domain: Neural network hardware acceleration

Scenario: Edge AI / embedded AI hardware simulation

TinyML relevance: Partial

TinyML justification: The paper targets efficient on-chip neural network inference hardware and evaluates vision classification workloads, but does not report MCU-class deployment, TensorFlow Lite Micro, bare-metal execution, or kilobyte-scale memory constraints.

Model / Method

Model: Eq-CIM architecture evaluated with VGG-16, ResNet50, and ConvNeXt-T

Architecture family: CNN / Other

Techniques: Compute-in-memory, monolithic 3D integration, system-technology co-optimization, 8-bit activation / 4-bit weight quantization, device-to-algorithm variation transfer, functionality breakdown across IGZO/RRAM/SRAM

Framework: PyTorch-compatible accuracy analyzer

Training type: Not reported

Inference type: On-device architecture-level simulation

Hardware

Device: Proposed M3D IGZO-RRAM-SRAM Eq-CIM processor

Hardware type: SoC / Other

Processor / microcontroller: RISC-V CPU with M3D CIM tiles; no microcontroller reported

Clock frequency: CIM macro 400 MHz; IGZO/RRAM approximately 50 MHz; SRAM CIM 400 MHz @ 28 nm

SRAM / RAM: 192 KB SRAM CIM; maximum 1.5 MB activation storage reported

Flash / ROM / Storage: 32 MB RRAM weight storage; 1.5 MB IGZO activation storage; 192 KB SRAM CIM

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Area, energy efficiency, storage density, device variation, temperature robustness, frequency mismatch, activation/weight storage overhead

Dataset

Name: CIFAR-10; ImageNet

Type: Public

Dataset size: Not reported

Number of classes: Not reported

Input resolution: Not reported

Data modality: RGB image

Metrics

Accuracy: VGG-16 on CIFAR-10: 93.7%; ResNet50 on ImageNet: 80.0%; ConvNeXt-T on ImageNet: 80.8%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: VGG-16 on CIFAR-10: 0.769 ms; ResNet50 on ImageNet: 9.42 ms; ConvNeXt-T on ImageNet: 11.3 ms

FPS: Not reported

Throughput: Peak performance 9.83 TOPS

Model size: Maximum 32 MB weight reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Maximum 1.5 MB activation storage reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: M3D device integration, functionality breakdown, compute-in-memory, 8b/4b quantization, bandwidth multiplication, device-variation-aware simulation

Quantization: Mixed precision, 8-bit activation / 4-bit weight

Pruning: No

Knowledge distillation: No

Compression method: Quantization and hardware-level storage/function partitioning

Hardware-specific optimization: IGZO for activation storage, RRAM for weight storage, SRAM for digital CIM; N× bandwidth multiplication to reduce IGZO/RRAM and SRAM frequency mismatch

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: 192 KB SRAM CIM capacity reported; peak SRAM usage not reported

Flash usage reported: Not reported

Model size reported: Maximum 32 MB weight reported

Energy per inference reported: Not reported

Latency on target device reported: 0.769 ms, 9.42 ms, and 11.3 ms in architecture-level simulation

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper evaluates a simulated M3D compute-in-memory processor and does not report MCU-class deployment, bare-metal/RTOS execution, TensorFlow Lite Micro, or strict SRAM/Flash constraints.

Benchmarking / Standardization

Benchmark used: CIFAR-10 with VGG-16; ImageNet with ResNet50 and ConvNeXt-T

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10; ImageNet

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: Eq-CIM reports 93.7% TOP-1 accuracy on CIFAR-10 and 80.0% / 80.8% TOP-1 accuracy on ImageNet, with 0.769 ms to 11.3 ms simulated latency. It reports 19.8 Mb/mm² storage density, 723 GOPS/mm² system area efficiency, and up to 95.2 TOPS/W system energy efficiency. 

Limitations: The paper states that future fabrication requires addressing detailed 3D stacking processes, materials, yield, chip-level thermal management, and reliability.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a monolithic 3D IGZO-RRAM-SRAM compute-in-memory architecture that assigns IGZO to activation storage, RRAM to weight storage, and SRAM to digital CIM for robust and energy-efficient neural network inference.

| Paper      | Year | Task           | Model                          | Technique                    | Device                              | Dataset             | Main Metric                                      | Latency                      | Model Size          | SRAM/RAM                           | Flash | Energy | Framework                    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | -------------- | ------------------------------ | ---------------------------- | ----------------------------------- | ------------------- | ------------------------------------------------ | ---------------------------- | ------------------- | ---------------------------------- | ----- | ------ | ---------------------------- | -------- | ------------- | ------------- |
| Yan et al. | 2025 | Classification | VGG-16 / ResNet50 / ConvNeXt-T | M3D CIM + 8b/4b quantization | M3D IGZO-RRAM-SRAM Eq-CIM processor | CIFAR-10 / ImageNet | Accuracy: 93.7% CIFAR-10; 80.0% / 80.8% ImageNet | 0.769 ms / 9.42 ms / 11.3 ms | Up to 32 MB weights | 1.5 MB activation; 192 KB SRAM CIM | N/A   | N/A    | PyTorch-compatible simulator | Mixed    | None          | No            |
