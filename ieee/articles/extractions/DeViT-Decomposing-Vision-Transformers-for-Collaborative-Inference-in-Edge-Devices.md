Paper ID: DeViT-Decomposing-Vision-Transformers-for-Collaborative-Inference-in-Edge-Devices

TinyML classification: Near-TinyML — evaluated on Jetson Nano/edge hardware with efficient on-device vision inference, but no explicit MCU-class constraints.

Basic Info

Authors: Guanyu Xu, Zhiwei Hao, Yong Luo, Han Hu, Jianping An, Shiwen Mao

Year: 2024

Title: DeViT: Decomposing Vision Transformers for Collaborative Inference in Edge Devices

Source: IEEE Transactions on Mobile Computing, Vol. 23, No. 5, May 2024 

Type: Methodological

Problem & Context

Task: Classification

Objective: Achieve fast and energy-efficient collaborative inference for large Vision Transformers on edge devices while maintaining comparable accuracy.

Application domain: General computer vision / AIoT image classification

Scenario: Collaborative inference across multiple edge devices

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained edge devices and reports latency, energy, power, parameters, and FLOPs on NVIDIA Jetson Nano, but does not target MCU-class TinyML deployment.

Model / Method

Model: DeViT, DeDeiT, DeCCT

Architecture family: ViT

Techniques: Vision Transformer decomposition, model shrinking, dataset partitioning, feature aggregation, knowledge distillation, feature matching, ensemble learning

Framework: PyTorch; timm used for compared approaches; communication module based on gPRC

Training type: Not reported

Inference type: Hybrid

Hardware

Device: 4 NVIDIA Jetson Nano devices and 1 TP-LINK TL-SG1008D switch

Hardware type: SoC / GPU

Processor / microcontroller: Quad-core ARM Cortex-A57 MPCore

Clock frequency: 1.6 GHz

SRAM / RAM: 4 GB RAM

Flash / ROM / Storage: Not reported

Power consumption: DeViTs: 6.46 ± 0.6 W; DeDeiTs: 6.86 ± 0.7 W; DeCCTs: 7.99 ± 0.6 W; Jetson Nano TDP: 10 W

Energy per inference: DeViTs: 204.29 ± 25.0 mJ; DeDeiTs: 221.08 ± 24.0 mJ; DeCCTs: 165.09 ± 17.5 mJ

Execution without full OS: Not reported

Fully on-device inference: No, inference is collaborative across multiple edge devices with inter-device communication.

Constraints mentioned: Memory, storage, compute, latency, energy, power, communication overhead, bandwidth

Dataset

Name: CIFAR-100; Oxford 102 Flower; Stanford Cars; ImageNet-1K

Type: Public

Dataset size: CIFAR-100: 60,000 images; Oxford 102 Flower: 40 to 258 images per class; Stanford Cars: 16,185 images; ImageNet-1K: 1.2 million training images and 50,000 testing images

Number of classes: CIFAR-100: 100; Oxford 102 Flower: 102; Stanford Cars: 196; ImageNet-1K: 1,000

Input resolution: 224 × 224

Data modality: RGB image

Metrics

Accuracy: On ImageNet-1K edge evaluation: DeViTs: 74.85%; DeDeiTs: 81.94%; DeCCTs: 79.12%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: On ImageNet-1K edge evaluation: DeViTs: 31.30 ± 2.3 ms; DeDeiTs: 32.22 ± 2.1 ms; DeCCTs: 20.66 ± 1.6 ms

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: DeViTs: 23.0 M; DeDeiTs: 23.9 M; DeCCTs: 18.3 M

MACs / FLOPs: DeViTs: 5.9 G; DeDeiTs: 5.9 G; DeCCTs: 5.1 G

RAM usage: Device RAM: 4 GB; runtime RAM usage not reported

Flash usage: Not reported

Energy per inference: DeViTs: 204.29 ± 25.0 mJ; DeDeiTs: 221.08 ± 24.0 mJ; DeCCTs: 165.09 ± 17.5 mJ

Power consumption: DeViTs: 6.46 ± 0.6 W; DeDeiTs: 6.86 ± 0.7 W; DeCCTs: 7.99 ± 0.6 W

Optimization

Techniques used: Model decomposition, encoder reduction, head reduction, embedding reduction, neuron reduction, model shrinking, knowledge distillation, feature matching, feature aggregation, ensemble learning

Quantization: None

Pruning: Yes, through removal of unimportant heads and neurons during model shrinking

Knowledge distillation: Yes

Compression method: Decomposition-and-ensemble knowledge distillation with structural shrinking

Hardware-specific optimization: Decomposition according to number of edge devices and hardware configuration

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Parameters and FLOPs reported; storage size for proposed models not reported

Energy per inference reported: Yes

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: No, inference requires collaborative execution and communication among edge devices.

Communication required during inference: Yes

Candidate for Strict TinyML: No

Reason: The deployment uses NVIDIA Jetson Nano edge devices with PyTorch and 4 GB RAM, not MCU-class hardware, TensorFlow Lite Micro, bare-metal/RTOS execution, or KB-scale SRAM/Flash constraints.

Benchmarking / Standardization

Benchmark used: CIFAR-100; Oxford 102 Flower; Stanford Cars; ImageNet-1K

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet-1K; CIFAR-100

Comparison with baseline models: Yes, compared with ViT-L/16, DeiT-B, CCT-14_7×2, T2T-ViTt-14, Twins-SVT-S, Twins-PCPVT-S, MobileViT-S, and MobileViT-S-Ens

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: DeCCTs achieved 79.12% Top-1 accuracy, 20.66 ± 1.6 ms latency, and 165.09 ± 17.5 mJ energy per inference on Jetson Nano using ImageNet-1K. DeDeiTs achieved the highest reported edge accuracy among proposed models, with 81.94% Top-1 accuracy, 32.22 ± 2.1 ms latency, and 221.08 ± 24.0 mJ energy per inference.

Limitations

The paper focuses on homogeneous edge devices and states that future work will analyze device heterogeneity and efficient collaborative inference on heterogeneous edge devices.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a collaborative edge inference framework that decomposes large Vision Transformers into multiple smaller models and uses decomposition-and-ensemble knowledge distillation to reduce latency and energy consumption while preserving classification accuracy.

| Paper     | Year | Task           | Model                  | Technique                                       | Device             | Dataset                                                  | Main Metric           | Latency  | Model Size | SRAM/RAM | Flash | Energy    | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---- | -------------- | ---------------------- | ----------------------------------------------- | ------------------ | -------------------------------------------------------- | --------------------- | -------- | ---------- | -------- | ----- | --------- | --------- | -------- | ------------- | ------------- |
| Xu et al. | 2024 | Classification | DeViT / DeDeiT / DeCCT | ViT decomposition + DEKD knowledge distillation | NVIDIA Jetson Nano | ImageNet-1K; CIFAR-100; Oxford 102 Flower; Stanford Cars | 81.94% Top-1 accuracy | 20.66 ms | N/A        | 4 GB RAM | N/A   | 165.09 mJ | PyTorch   | N/A      | None          | No            |
