Paper ID: Effective-Model-Compression-via-Stage-wise-Pruning

TinyML classification: Near-TinyML — it is relevant to efficient edge vision but does not provide explicit MCU-class deployment or TinyML framework evidence.

Basic Info

Authors: Ming-Yang Zhang; Xin-Yi Yu; Lin-Lin Ou

Year: 2023

Title: Effective Model Compression via Stage-wise Pruning

Source: Machine Intelligence Research, vol. 20, no. 6, pp. 937–951

Type: Methodological

Problem & Context

Task: Classification

Objective: Reduce the computational complexity of deep CNNs through automated stage-wise channel pruning while improving the consistency between proxy subnet performance and actual retrained performance.

Application domain: Computer vision model compression

Scenario: Mobile / embedded-oriented model compression; GPU latency measurement

TinyML relevance: Partial

TinyML justification: The paper targets efficient CNNs for embedded/mobile settings, but does not report MCU deployment, SRAM/Flash usage, bare-metal execution, TensorFlow Lite Micro, CMSIS-NN, or energy per inference.

Model / Method

Model: Stage-wise Pruning applied to ResNet-56, MobileNet V1, MobileNet V2, and ResNet-50

Architecture family: CNN

Techniques: Channel pruning, stage-wise pruning, inplace distillation, weight sharing, distributed evolutionary search

Framework: Not reported

Training type: from scratch

Inference type: on-device GPU latency measurement; otherwise not reported

Hardware

Device: NVIDIA 2080Ti GPU

Hardware type: GPU

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: FLOPs, latency, computational complexity, mobile deployment, training/search memory

Dataset

Name: CIFAR-10; ImageNet 2012

Type: public

Dataset size: CIFAR-10 validation split uses 200 images per class from training images; ImageNet validation split uses 50 images per class from training images; full dataset size not reported

Number of classes: Not reported

Input resolution: Not reported

Data modality: RGB image

Metrics

Accuracy: ResNet-56 on CIFAR-10: 95.03% top-1 accuracy; MobileNet V1 on ImageNet: 70.9% at 285M FLOPs and 60.3% at 41M FLOPs; MobileNet V2 on ImageNet: 73.4% at 220M FLOPs and 60.7% at 43M FLOPs; ResNet-50 on ImageNet: 76.1% at 2.0G FLOPs and 75.6% at 1.0G FLOPs

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: MobileNet V1 pruned inference time on 2080Ti GPU: 0.51 ms, 0.35 ms, 0.20 ms; MobileNet V2 pruned inference time on 2080Ti GPU: 0.52 ms, 0.41 ms, 0.32 ms

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: MobileNet V1 SWP: 1.7M and 0.5M; MobileNet V2 SWP: 2.6M and 1.9M; ResNet-50 SWP: 14.9M and 6.4M

MACs / FLOPs: ResNet-56 SWP: 61.36M FLOPs; MobileNet V1 SWP: 285M and 41M FLOPs; MobileNet V2 SWP: 220M and 43M FLOPs; ResNet-50 SWP: 2.0G and 1.0G FLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Stage-wise channel pruning, inplace distillation, distributed evolutionary algorithm, fullnet/subnet/tinynet training

Quantization: None

Pruning: Yes

Knowledge distillation: Yes

Compression method: Channel pruning

Hardware-specific optimization: Latency-constrained search using latency estimated from the target device

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes, on NVIDIA 2080Ti GPU

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper does not report MCU-class deployment, SRAM/Flash constraints, bare-metal execution, TinyML framework usage, or energy per inference; experiments are mainly classification pruning benchmarks with GPU latency measurement.

Benchmarking / Standardization

Benchmark used: CIFAR-10; ImageNet 2012

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10; ImageNet 2012

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: not reported

Results

Summary: SWP achieved 95.03% top-1 accuracy on CIFAR-10 with ResNet-56 at 61.36M FLOPs. On ImageNet, SWP achieved 76.1% top-1 accuracy for ResNet-50 at 2.0G FLOPs and improved MobileNet V1/V2 results under comparable FLOPs and latency constraints.

Limitations: The paper reports that using more stages requires more memory because intermediate feature maps must be saved. The work is evaluated on classification and states future extension to other computer vision tasks such as object detection and super-resolution.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a stage-wise channel pruning method with inplace distillation and distributed evolutionary search to improve automated CNN compression under FLOPs and latency constraints.

| Zhang et al. | 2023 | Classification | ResNet-56 / MobileNet V1 / MobileNet V2 / ResNet-50 | Stage-wise pruning + inplace distillation | NVIDIA 2080Ti GPU | CIFAR-10; ImageNet 2012 | 76.1% top-1 accuracy | 0.20–0.52 ms | N/A | N/A | N/A | N/A | N/A | N/A | N/A | No |
