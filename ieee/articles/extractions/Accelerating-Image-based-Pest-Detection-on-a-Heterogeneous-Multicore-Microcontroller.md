Paper ID: Accelerating-Image-based-Pest-Detection-on-a-Heterogeneous-Multicore-Microcontroller

TinyML classification: Strict TinyML — it explicitly deploys image-based detection on a microcontroller-class GAP9 SoC with MCU-level latency, energy, memory, and power constraints.

## Basic Info

Authors: Luca Bompani; Luca Crupi; Daniele Palossi; Olmo Baldoni; Davide Brunelli; Francesco Conti; Manuele Rusci; Luca Benini

Year: 2024

Title: Accelerating Image-based Pest Detection on a Heterogeneous Multicore Microcontroller

Source: IEEE Transactions on AgriFood Electronics, Vol. 2, No. 2, September/October 2024 

Type: Experimental

## Problem & Context

Task: Object detection

Objective: Compare and deploy Viola-Jones and MobileNetV3-SSDLite for on-device codling moth pest detection on a heterogeneous multicore MCU.

Application domain: Smart agriculture / pest monitoring

Scenario: Embedded battery-powered camera sensor node with near-sensor processing and LoRa communication

TinyML relevance: Yes

TinyML justification: The paper explicitly targets MCU-based, ultra-low-power, fully on-device image-based detection on GAP9 with reported memory, latency, energy, power, and battery-lifetime constraints.

## Model / Method

Model: Viola-Jones detector; MobileNetV3-SSDLite

Architecture family: CNN / Classical ML

Techniques: INT8 post-training quantization, hardware acceleration, memory tiling, L1/L2 buffering, duty-cycled power management

Framework: GAPflow toolset; ONNX model description

Training type: Transfer learning for MobileNetV3 backbone; SSDLite heads trained from scratch; AdaBoost variant for Viola-Jones

Inference type: On-device

## Hardware

Device: GreenWaves Technologies GAP9 SoC carrier board with Himax HM01B0 camera sensor and HTCC-AB01 LoRa module

Hardware type: MCU / SoC / hardware accelerator

Processor / microcontroller: GAP9 with host RISC-V core, 9 RISC-V cluster cores, and NE16 convolution accelerator

Clock frequency: 240 MHz at 0.65 V for GAP9; GAP8 comparison at 175 MHz and 1.2 V

SRAM / RAM: 1.5 MB L2 memory; 128 kB L1 scratch memory; 32 MB external RAM

Flash / ROM / Storage: 64 MB external FLASH

Power consumption: 33 mW for CNN processing on GAP9; 20.5 mW for Viola-Jones on GAP9; 79 mW reported for GAP8 comparison

Energy per inference: 4.85 mJ for MobileNetV3-SSDLite on GAP9; 4.61 mJ for Viola-Jones on GAP9

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, compute, energy, communication cost, battery lifetime

## Dataset

Name: Custom codling moth dataset; near-ds; far-ds

Type: Not reported

Dataset size: 158 images with 1275 labeled target insects; 127 training images and 31 validation images; near-ds has 11 images with 196 target objects; far-ds has 7 images with 158 target objects

Number of classes: 1 target class, Cydia pomonella, versus background

Input resolution: 2048 × 1536 original images resized to 320 × 240 for evaluation and deployment

Data modality: RGB images transformed to grayscale with additive Gaussian noise to mimic the Himax camera sensor

## Metrics

Accuracy: Viola-Jones: 81.7% near-ds and 45.0% far-ds; MobileNetV3-SSDLite float: 88.0% near-ds and 84.0% far-ds; MobileNetV3-SSDLite INT8: 83.0% near-ds and 72.0% far-ds

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: MobileNetV3-SSDLite on GAP9 NE16: 147 ms; Viola-Jones on GAP9: 221 ms

FPS: Not reported

Throughput: 10.9 MAC/cycle for MobileNetV3-SSDLite on GAP9 NE16

Model size: 3.44 MB INT8 parameters in external FLASH for MobileNetV3-SSDLite; 3.56 kB cascade classifier parameters for Viola-Jones

Parameters: 3.44 M parameters for MobileNetV3-SSDLite

MACs / FLOPs: 584 M MAC operations for MobileNetV3-SSDLite on 320 × 240 image

RAM usage: MobileNetV3-SSDLite on GAP9 uses 115.6 kB L1, 1.2 MB L2, and 1.3 MB external RAM; Viola-Jones on GAP9 uses 99.6 kB L1 and 384 kB L2

Flash usage: 3.44 MB external FLASH for MobileNetV3-SSDLite parameters; no external FLASH required for Viola-Jones

Energy per inference: 4.85 mJ for MobileNetV3-SSDLite on GAP9; 4.61 mJ for Viola-Jones on GAP9

Power consumption: 33 mW for MobileNetV3-SSDLite on GAP9; 20.5 mW for Viola-Jones on GAP9

## Optimization

Techniques used: INT8 post-training quantization, NE16 accelerator execution, GAPflow C code generation, L1/L2 memory buffering, external memory scheduling, Viola-Jones image tiling, duty-cycled power management

Quantization: INT8 PTQ

Pruning: No

Knowledge distillation: No

Compression method: INT8 post-training quantization and MobileNetV3-SSDLite depthwise-separable CNN design

Hardware-specific optimization: NE16 convolution accelerator, RISC-V cluster execution, L1/L2 tiling and buffering, external memory scheduling, 0.65 V / 240 MHz energy-efficient operating point

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: 115.6 kB L1 and 1.2 MB L2 for MobileNetV3-SSDLite on GAP9; 99.6 kB L1 and 384 kB L2 for Viola-Jones on GAP9

Flash usage reported: 3.44 MB external FLASH for MobileNetV3-SSDLite parameters

Model size reported: 3.44 M parameters / 3.44 MB for MobileNetV3-SSDLite; 3.56 kB classifier parameters for Viola-Jones

Energy per inference reported: 4.85 mJ for MobileNetV3-SSDLite; 4.61 mJ for Viola-Jones

Latency on target device reported: 147 ms for MobileNetV3-SSDLite on GAP9 NE16; 221 ms for Viola-Jones on GAP9

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No; communication is used after detection to transmit pest counts through LoRa

Candidate for Strict TinyML: Yes

Reason: The work explicitly deploys computer vision inference on an MCU-class GAP9 SoC and reports MCU-level memory, latency, power, energy, and battery-lifetime constraints.

## Benchmarking / Standardization

Benchmark used: Custom near-ds and far-ds pest detection test sets

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO used for MobileNetV3 backbone pretraining, not as the evaluation benchmark

Comparison with baseline models: Yes; Viola-Jones versus MobileNetV3-SSDLite and float versus INT8 CNN

Comparison with previous works: Yes; comparison against prior camera-based pest detection systems using STM32H7, GAP8, GSM, and LoRa/LoRaWAN

Reproducibility artifacts available: code

## Results

Summary: MobileNetV3-SSDLite INT8 achieved 83.0% accuracy on near-ds and 72.0% on far-ds, outperforming Viola-Jones especially on far-ds. On GAP9 NE16, CNN inference took 147 ms and consumed 4.85 mJ, with an estimated battery lifetime of 199 days in the high-frequency scenario.

Limitations: Post-training quantization reduced MobileNetV3-SSDLite accuracy, especially on far-ds, and the evaluation used small custom pest datasets.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

## Contribution

This paper proposes an MCU-based on-device pest detection system that compares Viola-Jones and MobileNetV3-SSDLite on GAP9 and demonstrates low-latency, low-energy image-based inference for battery-powered smart agriculture.

| Bompani et al. | 2024 | Object Detection | MobileNetV3-SSDLite; Viola-Jones | INT8 PTQ + NE16 hardware acceleration | GAP9 SoC | Custom codling moth dataset | Accuracy: 83.0% near-ds, 72.0% far-ds | 147 ms | 3.44 MB | 115.6 kB L1 + 1.2 MB L2 + 1.3 MB extRAM | 3.44 MB extFLASH | 4.85 mJ | GAPflow | INT8/PTQ | None | Yes |
