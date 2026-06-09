Paper ID: EQ-ViT-Algorithm-Hardware-Co-Design-for-End-to-End-Acceleration-of-Real-Time-Vision-Transformer-Inference-on-Versal-ACAP-Architecture

TinyML classification: Near-TinyML — targets ACAP/FPGA-class edge acceleration rather than explicit MCU-class deployment.

Basic Info

Authors: Peiyan Dong; Jinming Zhuang; Zhuoping Yang; Shixin Ji; Yanyu Li; Dongkuan Xu; Heng Huang; Jingtong Hu; Alex K. Jones; Yiyu Shi; Yanzhi Wang; Peipei Zhou

Year: 2024

Title: EQ-ViT: Algorithm-Hardware Co-Design for End-to-End Acceleration of Real-Time Vision Transformer Inference on Versal ACAP Architecture

Source: IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems, Vol. 43, No. 11, November 2024 

Type: Methodological

Problem & Context

Task: Classification

Objective: Enable deterministic real-time ViT inference with sub-1 ms latency using algorithm-hardware co-design on AMD Versal ACAP.

Application domain: Real-time computer vision inference

Scenario: Edge, embedded, SoC, FPGA/ACAP acceleration

TinyML relevance: Partial

TinyML justification: The paper targets low-latency and energy-efficient on-device ViT inference on ACAP/FPGA-class edge hardware, but does not target MCU-class deployment.

Model / Method

Model: EQ-ViT applied to DeiT-T, DeiT-160, DeiT-256, and LV-ViT-T

Architecture family: ViT

Techniques: INT8 quantization, QAT, activation-aware quantization, nonlinear-function quantization, Log2Q, outlier-predictable QAT, algorithm-hardware co-design, on-chip forwarding, fine-grained pipelining, design-space exploration

Framework: PyTorch 3.8; EQ-ViT automation framework; AIE intrinsic C/C++; FPGA high-level synthesis code; ARM CPU host code

Training type: Not reported

Inference type: On-device

Hardware

Device: AMD Versal ACAP VCK190 board

Hardware type: SoC / FPGA / Other

Processor / microcontroller: AMD Versal ACAP with ARM CPUs, FPGA programmable logic, and AIE vector cores

Clock frequency: Not reported

SRAM / RAM: 33 MB on-chip memory; 8 GB off-chip memory

Flash / ROM / Storage: Not reported

Power consumption: VCK190 TDP <180 W

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Deterministic latency, energy efficiency, on-chip memory, off-chip bandwidth, compute utilization, communication, quantization accuracy

Dataset

Name: ImageNet-1k; CIFAR-100; CIFAR-10

Type: Public

Dataset size: Not reported

Number of classes: Not reported

Input resolution: 224×224 for DeiT-T

Data modality: Image

Metrics

Accuracy: ImageNet Top-1: 74.5% DeiT-T, 70.5% DeiT-160, 78.2% DeiT-256, 80.5% LV-ViT-T; CIFAR-100 Top-1: 86.6%, 84.4%, 88.3%, 89.5%; CIFAR-10 Top-1: 98.3%, 96.9%, 98.9%, 99.4%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: VCK190: 0.56 ms DeiT-T, 0.46 ms DeiT-160, 0.89 ms DeiT-256, 0.61 ms LV-ViT-T

FPS: VCK190: 10695 image/s DeiT-T, 13187 image/s DeiT-160, 6726 image/s DeiT-256, 9836 image/s LV-ViT-T

Throughput: VCK190: 10695 image/s, 13187 image/s, 6726 image/s, 9836 image/s

Model size: DeiT-T 5.6 MB; DeiT-160 4 MB; DeiT-256 7.4 MB; LV-ViT-T 6.75 MB

Parameters: Not reported

MACs / FLOPs: DeiT-T 1.3G MACs; DeiT-160 0.9G MACs; DeiT-256 2.1G MACs; LV-ViT-T 1.6G MACs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: VCK190 TDP <180 W

Optimization

Techniques used: Activation-aware QAT, INT8 quantization, Log2Q attention-map quantization, outlier-predictable QAT, INT-Softmax2n, I-GeLUImp, heterogeneous spatial accelerators, on-chip data forwarding, fine-grained pipelining, MIP-based design-space exploration

Quantization: INT8 QAT

Pruning: No

Knowledge distillation: Yes

Compression method: INT8 quantization of weights, activations, and nonlinear functions

Hardware-specific optimization: ACAP-specific mapping across AIEs and FPGA programmable logic with on-chip forwarding and fine-grained pipelining

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: No

Flash usage reported: No

Model size reported: Yes

Energy per inference reported: No

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is AMD Versal ACAP/FPGA-class hardware rather than MCU-class or bare-metal TinyML hardware.

Benchmarking / Standardization

Benchmark used: ImageNet-1k; CIFAR-100; CIFAR-10

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet-1k; CIFAR-100; CIFAR-10

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: EQ-ViT achieves 0.46–0.89 ms latency on AMD Versal ACAP VCK190 across four ViT models. It reports up to 2.4% Top-1 accuracy improvement over FP32 baselines and average speedups over CPU, GPU, FPGA, and ACAP baselines.

Limitations

Model partitioning across multiple devices for models that do not fit on one board is left as future work. The paper does not evaluate MCU-class deployment.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an INT8 algorithm-hardware co-design framework for accelerating real-time ViT inference on AMD Versal ACAP using activation-aware QAT, nonlinear-function quantization, and heterogeneous AIE/FPGA spatial acceleration.

| Paper       | Year | Task           | Model         | Technique                               | Device                 | Dataset                          | Main Metric                                                           | Latency      | Model Size | SRAM/RAM                     | Flash | Energy          | Framework        | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | -------------- | ------------- | --------------------------------------- | ---------------------- | -------------------------------- | --------------------------------------------------------------------- | ------------ | ---------- | ---------------------------- | ----- | --------------- | ---------------- | -------- | ------------- | ------------- |
| Dong et al. | 2024 | Classification | DeiT / LV-ViT | INT8 QAT + algorithm-hardware co-design | AMD Versal ACAP VCK190 | ImageNet-1k; CIFAR-100; CIFAR-10 | Top-1 accuracy: up to 80.5% ImageNet, 89.5% CIFAR-100, 99.4% CIFAR-10 | 0.46–0.89 ms | 4–7.4 MB   | 33 MB on-chip; 8 GB off-chip | N/A   | 142.8–280 FPS/W | PyTorch / EQ-ViT | INT8 QAT | None          | No            |
