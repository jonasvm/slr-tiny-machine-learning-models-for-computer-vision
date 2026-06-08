Paper ID: Efficient-Vision-Transformer-for-Human-Centric-AIoT-Applications-Through-Token-Tracking-Assignment

TinyML classification: Near-TinyML — Edge/AIoT vision optimization is relevant, but experiments use ViT/ImageNet with GPU-based evaluation rather than MCU-class constraints.

Basic Info

Authors: Chuang Li; Yujie Peng; Gang Liu; Yangfan Li; Xulei Yang; Cen Chen

Year: 2024

Title: Efficient Vision Transformer for Human-Centric AIoT Applications Through Token Tracking Assignment

Source: IEEE Transactions on Consumer Electronics, Vol. 70, No. 1, February 2024 

Type: Methodological

Problem & Context

Task: Classification

Objective: Reduce redundant computations in Vision Transformer models for AIoT edge-device deployment while preserving accuracy.

Application domain: Human-centric AIoT and consumer electronics

Scenario: Edge, AIoT, consumer electronics

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained AIoT edge devices, but experiments are performed on ImageNet-1k with V100 GPU throughput measurement and no MCU-class deployment is reported.

Model / Method

Model: TMTP applied to AugReg, MAE, and SWAG Vision Transformer models

Architecture family: ViT

Techniques: Token merging, token pruning, token tracking assignment, token chunk merging, warm-up pruning strategy

Framework: Not reported

Training type: Fine-tuning for MAE models; off-the-shelf evaluation for AugReg and SWAG models

Inference type: Not reported

Hardware

Device: V100 GPU for throughput measurement; target AIoT edge device not reported

Hardware type: GPU

Processor / microcontroller: V100 GPU

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Limited compute and storage capacity, redundant computation, response time, resource-constrained edge devices

Dataset

Name: ImageNet-1k

Type: Public

Dataset size: 1200k training images; 50k validation images; 100k test images

Number of classes: 1000

Input resolution: 224×224; SWAG variants also report 384, 512, and 518 input sizes

Data modality: Image

Metrics

Accuracy: Top-1 accuracy up to 86.7% for ViT-H MAE with TMTP trained; SWAG with 80% token reduction reports only 0.05%–0.18% accuracy reduction

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Measured on V100 GPU with optimal batch size and fp32, but numeric throughput is not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: SWAG with 80% token reduction reduces GFLOPs by 35%; TMTP compresses 80%–90% of tokens and reduces computational cost by 35%–39%

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Token merging, token pruning, token tracking assignment, token chunk merging, warm-up pruning

Quantization: None; fp32 throughput measurement reported

Pruning: Yes

Knowledge distillation: Not reported

Compression method: Token reduction through merging and pruning

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper does not report MCU-class deployment, SRAM/Flash constraints, bare-metal or RTOS execution, energy per inference, or latency on target embedded hardware.

Benchmarking / Standardization

Benchmark used: ImageNet-1k

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet-1k

Comparison with baseline models: Yes; AugReg, MAE, SWAG, ViT variants, ToMe, DynamicViT, A-ViT, SP-ViT, Swin, SwinV2, CSWin, MViTv2, EfficientNet, and LV-ViT

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: TMTP reduces 80%–90% of tokens and lowers computational cost by 35%–39% with small accuracy degradation. In SWAG, pruning 80% of input tokens reduces GFLOPs by 35% while ImageNet-1k accuracy decreases by only 0.05%–0.18%.

Limitations: Practical deployment in consumer electronic products is left for future work; target edge or MCU hardware evaluation is not reported.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes TMTP, a token merging and pruning method with token tracking assignment to reduce redundant computations in Vision Transformer models for AIoT edge-device scenarios.

| Paper     | Year | Task           | Model      | Technique               | Device   | Dataset     | Main Metric     | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---- | -------------- | ---------- | ----------------------- | -------- | ----------- | --------------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Li et al. | 2024 | Classification | TMTP + ViT | Token merging + pruning | V100 GPU | ImageNet-1k | Top-1 Acc 86.7% | N/A     | N/A        | N/A      | N/A   | N/A    | N/A       | FP32     | None          | No            |
