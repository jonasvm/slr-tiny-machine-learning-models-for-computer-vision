Paper ID: SPViT-Accelerate-Vision-Transformer-Inference-on-Mobile-Devices-via-Adaptive-Splitting-and-Offloading

Basic Info

Authors: Sifan Zhao, Tongtong Liu, Hai Jin, Dezhong Yao

Year: 2025

Title: SPViT: Accelerate Vision Transformer Inference on Mobile Devices via Adaptive Splitting and Offloading

Source: IEEE Transactions on Mobile Computing, Vol. 24, No. 10, October 2025 

Type: Experimental / Methodological

Problem & Context

Task: Classification

Objective: Accelerate Vision Transformer inference on resource-constrained mobile devices using adaptive splitting and offloading.

Application domain: Mobile intelligent visual applications

Scenario: Mobile edge collaborative inference

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained mobile/edge inference, but deployment uses Jetson TX2-based Manifold 2-G and Raspberry Pi 4B devices with local communication, not MCU-class or bare-metal TinyML hardware.

Model / Method

Model: SPViT applied to DeiT, Swin, DaViT, and T2T-ViT small/base models

Architecture family: ViT

Techniques: Adaptive split and offloading, Head-Width splitting, Neuron-Width splitting, ARIMA-V adaptive partitioning, token routing, distributed asynchronous inference

Framework: Not reported

Training type: Not reported; models are trained before deployment and the router is trained offline

Inference type: Hybrid / offloaded across nearby edge devices

Hardware

Device: Three Manifold 2-G devices and one Raspberry Pi 4B

Hardware type: SoC / CPU / GPU / Mobile edge

Processor / microcontroller: Manifold 2-G uses Nvidia Jetson TX2 with Dual-core Nvidia Denver and Quad-core ARM Cortex-A57 CPU plus 256-core Pascal GPU; Raspberry Pi 4B uses 1.5GHz Quad-core Broadcom BCM2711 Cortex-A72 plus Broadcom VideoCore VI GPU

Clock frequency: Raspberry Pi 4B: 1.5GHz; Manifold 2-G: Not reported

SRAM / RAM: Manifold 2-G: 8GB 128-bit LPDDR4; Raspberry Pi 4B: 4GB LPDDR4

Flash / ROM / Storage: Not reported

Power consumption: Manifold 2-G: 3–25W; Raspberry Pi 4B: 6.4W

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: No

Constraints mentioned: Latency, compute, FLOPs, communication bandwidth, transmission overhead, resource constraints, power, dynamic device availability

Dataset

Name: ImageNet

Type: public

Dataset size: Single ImageNet image for inference workload; 10,000 randomly selected ImageNet images for router training experiment

Number of classes: Not reported

Input resolution: 224 × 224 × 3; patch size 16 × 16; batch size 128

Data modality: RGB image

Metrics

Accuracy: Top-1 accuracy reported for referenced ViT/CNN models; SPViT-specific final accuracy value not reported

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: SPViT reduces inference latency by 2.2× to 3.3× across four state-of-the-art models; reported speedups include SPViT/80 and SPViT/160 improvements of 2.6×/3.2× for ViT-Small and 2.7×/3.5× for ViT-Base cases

FPS: Not reported

Throughput: Throughput variation under bandwidth and device changes is evaluated; absolute throughput not reported

Model size: Not reported in MB

Parameters: Table I reports parameters for selected models, including DeiT-Small 22M, Swin-Small 50M, Swin-Base 88M, DaViT-Small 49.7M, and DaViT-Base 87.9M

MACs / FLOPs: Table I reports FLOPs for selected models, including DeiT-Small 4.6G, Swin-Small 8.7G, Swin-Base 15.4G, DaViT-Small 8.8G, and DaViT-Base 15.5G

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Manifold 2-G: 3–25W; Raspberry Pi 4B: 6.4W

Optimization

Techniques used: Fine-grained intra-layer splitting, adaptive ARIMA-V offloading, token routing, asynchronous inference, local edge collaborative inference

Quantization: None; FP32 primarily used in experiments

Pruning: No

Knowledge distillation: No

Compression method: Token routing reduces computation and communication overhead

Hardware-specific optimization: Adaptive partitioning based on device compute capacity and bandwidth

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: No MB model size; parameters and FLOPs reported for selected models

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: No

Communication required during inference: Yes

Candidate for Strict TinyML: No

Reason: The system uses GB-RAM Linux-capable edge/mobile devices and collaborative offloading over local communication, with no MCU-class deployment, TensorFlow Lite Micro, CMSIS-NN, or kilobyte-scale memory evidence.

Benchmarking / Standardization

Benchmark used: ImageNet classification workload; latency benchmark tools

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet

Comparison with baseline models: Local inference, cloud server offloading, edge server offloading, DeViT, ED-ViT

Comparison with previous works: DeViT and ED-ViT are compared as splitting/offloading baselines

Reproducibility artifacts available: code

Results

Summary: SPViT accelerates ViT inference on mobile edge devices through adaptive intra-layer splitting, ARIMA-V partitioning, token routing, and asynchronous inference. Prototype experiments on three Manifold 2-G devices and one Raspberry Pi 4B show latency reductions of 2.2× to 3.3× across four ViT model families. 

Limitations

SPViT lacks adaptability to head-optimized ViT types and has insufficient support for miniature devices such as sensors. Re-splitting and offloading can also introduce 1–2 minutes of cold-start overhead during bandwidth or device changes.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes SPViT, an adaptive splitting and offloading method that accelerates Vision Transformer inference on mobile edge devices through fine-grained intra-layer partitioning, ARIMA-V adaptive offloading, token routing, and asynchronous inference.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Zhao et al. | 2025 | Classification | SPViT with DeiT, Swin, DaViT, T2T-ViT | Adaptive splitting/offloading + ARIMA-V + token routing + DAIV | 3× Manifold 2-G + Raspberry Pi 4B | ImageNet | Latency speedup 2.2×–3.3× | 2.2×–3.3× reduction | N/A | 8GB LPDDR4 / 4GB LPDDR4 | N/A | 3–25W; 6.4W | N/A | FP32 | None | No |
