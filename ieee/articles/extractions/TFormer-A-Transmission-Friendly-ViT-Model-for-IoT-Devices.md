Paper ID: TFormer-A-Transmission-Friendly-ViT-Model-for-IoT-Devices

TinyML classification: Near-TinyML — The paper targets resource-constrained IoT devices and evaluates image classification, object detection, and segmentation, but experiments are GPU-based and MCU-level deployment is not shown.

## Basic Info

Authors: Zhichao Lu; Chuntao Ding; Felix Juefei-Xu; Vishnu Naresh Boddeti; Shangguang Wang; Yun Yang

Year: 2022

Title: TFormer: A Transmission-Friendly ViT Model for IoT Devices 

Source: IEEE Transactions on Parallel and Distributed Systems

Type: Methodological

## Problem & Context

Task: Classification; object detection; semantic segmentation

Objective: Reduce ViT model parameters and FLOPs to facilitate cloud-assisted deployment and updating on resource-constrained IoT devices.

Application domain: IoT vision services

Scenario: IoT devices with cloud-assisted training and model transmission

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained IoT devices and model efficiency, but does not report MCU-class deployment, SRAM/Flash usage, energy, or latency on embedded target hardware.

## Model / Method

Model: TFormer-S; TFormer-M; TFormer-L

Architecture family: ViT

Techniques: Hybrid layer; nonlearnable max/average pooling; pointwise convolution; group convolution; channel shuffle; PCS-FFN; parameter and FLOP reduction

Framework: Python 3.8; PyTorch 1.8; CUDA 11.1

Training type: ImageNet-1K training; MS COCO and ADE20K use ImageNet-1K pretrained weights

Inference type: Proposed on-device deployment after cloud training; hardware-validated inference not reported

## Hardware

Device: NVIDIA 3090 GPUs for experiments; IoT devices are conceptual; Raspberry Pi 4B mentioned only as future work

Hardware type: GPU for experiments; IoT hardware not reported

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Model parameters, FLOPs, storage resources, memory resources, communication/model transmission, computing resources

## Dataset

Name: ImageNet-1K; MS COCO; ADE20K

Type: Public

Dataset size: ImageNet-1K: 1.28M train, 50K validation; MS COCO: 118K train, 5K validation; ADE20K: 20K train, 2K validation

Number of classes: ImageNet-1K: 1,000; MS COCO: 80; ADE20K: 150

Input resolution: ImageNet-1K: 224×224; MS COCO: 1280×800; ADE20K: 512×512

Data modality: RGB image

## Metrics

Accuracy: ImageNet-1K Top-1 / Top-5: TFormer-S 76.1% / 92.9%; TFormer-M 79.7% / 94.8%; TFormer-L 80.6% / 95.4%

mAP: MS COCO AP: TFormer-S 37.1; TFormer-M 39.7; TFormer-L 41.2

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported as storage size; parameter counts reported

Parameters: Classification backbone: TFormer-S 8.4M, TFormer-M 14M, TFormer-L 20M; object detection: 18M, 24M, 30M; semantic segmentation: 12M, 18M, 24M

MACs / FLOPs: TFormer-S 1.2G Multi-Adds; TFormer-M 2.2G Multi-Adds; TFormer-L 3.2G Multi-Adds

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Replacement of MHA with hybrid layer; nonlearnable max/average pooling; multiscale pooling; pointwise convolution; PCS-FFN with group convolution and channel shuffle

Quantization: Not reported

Pruning: No

Knowledge distillation: No

Compression method: Architectural parameter and FLOP reduction through hybrid layer and PCS-FFN

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Parameters reported; storage size not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper does not report MCU-class deployment, SRAM/Flash constraints, target-device latency, energy, or bare-metal/RTOS execution.

## Benchmarking / Standardization

Benchmark used: ImageNet-1K; MS COCO; ADE20K

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet-1K; MS COCO; ADE20K

Comparison with baseline models: Yes, including ResNet, PVT, DeiT, Swin-Mixer, ResMLP, and PoolFormer

Comparison with previous works: Yes

Reproducibility artifacts available: Code reported as planned to be made publicly available

## Results

Summary: TFormer-L reports 80.6% Top-1 accuracy on ImageNet-1K, 41.2 AP on MS COCO, and 41.8% mIoU on ADE20K. The model reduces parameters and FLOPs through hybrid layers and PCS-FFN, but experiments are performed on GPUs rather than IoT target hardware.

Limitations: Real IoT deployment is future work, with Raspberry Pi 4B mentioned as a planned target. The paper does not report embedded-device latency, memory usage, energy, or power.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes, experimental GPU only

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes, code promised

## Contribution

This paper proposes a transmission-friendly vision transformer for IoT devices using a hybrid nonlearnable pooling layer and a partially connected shuffled feed-forward network to reduce parameters and FLOPs while maintaining performance on classification, detection, and segmentation tasks.

| Lu et al. | 2022 | Classification; object detection; segmentation | TFormer | Hybrid layer + PCS-FFN | NVIDIA 3090 GPUs; IoT devices conceptual | ImageNet-1K; MS COCO; ADE20K | 80.6% Top-1; 41.2 AP; 41.8% mIoU | N/A | N/A | N/A | N/A | N/A | PyTorch | N/A | None | No |
