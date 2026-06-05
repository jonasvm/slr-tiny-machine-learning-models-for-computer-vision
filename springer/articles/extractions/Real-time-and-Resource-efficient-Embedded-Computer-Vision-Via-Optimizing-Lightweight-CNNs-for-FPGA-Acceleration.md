Paper ID: Real-time-and-Resource-efficient-Embedded-Computer-Vision-Via-Optimizing-Lightweight-CNNs-for-FPGA-Acceleration

TinyML classification: Near-TinyML — Uses FPGA/MPSoC edge hardware and Vitis AI deployment, but does not report MCU-class deployment or Cortex-M/TFLite Micro-level constraints.

Basic Info

Authors: Ahmad Mouri Zadeh Khaki; Ahyoung Choi

Year: 2025

Title: Real-time and Resource-efficient Embedded Computer Vision Via Optimizing Lightweight CNNs for FPGA Acceleration

Source: Journal of Signal Processing Systems, 97:185–195 

Type: Experimental

Problem & Context

Task: Classification

Objective: Optimize and deploy lightweight CNNs on FPGA for real-time, resource-efficient image classification.

Application domain: Embedded computer vision; Edge AI

Scenario: Edge, embedded, IoT, autonomous systems, mobile computing

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained edge FPGA deployment with latency and resource-utilization evaluation, but does not target MCU-class TinyML hardware.

Model / Method

Model: MobileNetV2; SqueezeNet; ResNet18

Architecture family: CNN

Techniques: Transfer learning, INT8 post-training quantization, model pruning, FPGA-specific optimization, hardware-aware optimization

Framework: PyTorch; Xilinx Vitis AI; PYNQ

Training type: Transfer learning / fine-tuning

Inference type: On-device

Hardware

Device: Avnet Ultra96-V2 evaluation board with Zynq UltraScale+MPSoC FPGA

Hardware type: FPGA / SoC

Processor / microcontroller: Zynq UltraScale+MPSoC with ARM-based processing system and programmable logic; DPUCZDX8G B1600

Clock frequency: 325 MHz

SRAM / RAM: 2 GB available; 162 MB used

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Resource constraints, memory footprint, latency, computational complexity, power and thermal constraints, quantization-induced accuracy degradation

Dataset

Name: CIFAR-10

Type: Public

Dataset size: 60,000 images; 50,000 training images; 10,000 test images; training set further split into 40,000 training and 10,000 validation images

Number of classes: 10

Input resolution: Original 32×32; resized to 224×224

Data modality: RGB image

Metrics

Accuracy: MobileNetV2 Top-1 91.05%, Top-5 99.86%; SqueezeNet Top-1 89.27%, Top-5 99.71%; ResNet18 Top-1 94.73%, Top-5 99.90%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: MobileNetV2 10.04 ms/frame; SqueezeNet 6.28 ms/frame; ResNet18 19.95 ms/frame on FPGA

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: 162 MB

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Transfer learning, INT8 post-training quantization, pruning, Vitis AI compilation, FPGA/DPU-specific optimization

Quantization: INT8 / PTQ

Pruning: Yes

Knowledge distillation: No

Compression method: INT8 fixed-point quantization and pruning

Hardware-specific optimization: Vitis AI compiler targeting Zynq UltraScale+MPSoC and DPUCZDX8G B1600

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: MobileNetV2 10.04 ms/frame; SqueezeNet 6.28 ms/frame; ResNet18 19.95 ms/frame

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is an FPGA/MPSoC edge platform rather than an MCU-class device, and the paper does not report Cortex-M, TFLite Micro, SRAM/Flash, or bare-metal TinyML constraints.

Benchmarking / Standardization

Benchmark used: CIFAR-10

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10

Comparison with baseline models: CPU and GPU implementations of the same CNN models

Comparison with previous works: Yes

Reproducibility artifacts available: dataset

Results

Summary: The optimized FPGA implementations achieved Top-1 accuracies of 91.05% for MobileNetV2, 89.27% for SqueezeNet, and 94.73% for ResNet18. FPGA latency was 10.04 ms/frame, 6.28 ms/frame, and 19.95 ms/frame, respectively, with reported FPGA resource utilization.

Limitations

The paper reports that results are based on a single hardware platform and a fixed DPUCZDX8G B1600 configuration, limiting generalizability. Power consumption was not directly measured.

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

This paper proposes a PyTorch and Xilinx Vitis AI workflow for optimizing and deploying MobileNetV2, SqueezeNet, and ResNet18 on FPGA for real-time, resource-efficient image classification.

| Khaki et al. | 2025 | Classification | MobileNetV2; SqueezeNet; ResNet18 | INT8 quantization, pruning, FPGA-specific optimization | Avnet Ultra96-V2 Zynq UltraScale+MPSoC FPGA | CIFAR-10 | Accuracy: ResNet18 Top-1 94.73% | 6.28–19.95 ms/frame | N/A | 162 MB RAM | N/A | N/A | PyTorch; Xilinx Vitis AI; PYNQ | INT8/PTQ | None | No |
