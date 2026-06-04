Paper ID: Accelerating-AI-and-Computer-Vision-for-Satellite-Pose-Estimation-on-the-Intel-Myriad-X-Embedded-SoC

TinyML classification: Near-TinyML — Evaluated on an embedded VPU/SoC rather than MCU-class hardware.

## Basic Info

Authors: Vasileios Leon; Panagiotis Minaidis; George Lentaris; Dimitrios Soudris 

Year: 2023

Title: Accelerating AI and Computer Vision for Satellite Pose Estimation on the Intel Myriad X Embedded SoC

Source: Microprocessors and Microsystems 103 (2023) 104947

Type: Experimental

## Problem & Context

Task: Satellite pose estimation and pose tracking

Objective: Accelerate hybrid AI/CV satellite pose estimation and tracking on a low-power embedded heterogeneous SoC.

Application domain: Space avionics; vision-based navigation

Scenario: Embedded edge/on-board processing

TinyML relevance: Partial

TinyML justification: The paper targets low-power embedded on-device AI/CV on Intel Myriad X VPU, but not MCU-class TinyML hardware.

## Model / Method

Model: UrsoNet DNN with ResNet-50 backbone + custom classical CV pipeline

Architecture family: Hybrid CNN / Classical CV

Techniques: Image resampling, SHAVE parallelization, SIMD, variable tuning, sliding buffer, CMX scratchpad use, cache optimization, loop merging, dynamic/static task scheduling, power management

Framework: TensorFlow; OpenVINO 2021.3; Myriad Development Kit R15.4; mvNCI API

Training type: Transfer learning / fine-tuning

Inference type: On-device

## Hardware

Device: Intel Movidius Myriad X VPU / Intel Neural Compute Stick 2

Hardware type: SoC / VPU / NPU / DSP

Processor / microcontroller: Neural Compute Engine, 16 programmable 128-bit VLIW SHAVE vector cores, 2 LEON4 processors

Clock frequency: 700 MHz; CIF at 50 MHz

SRAM / RAM: 512 MB LPDDR4 DRAM; 2.5 MB CMX scratchpad memory

Flash / ROM / Storage: Not reported

Power consumption: Around 2 W; 2.0 W for Bilinear/Bicubic AI pipeline; 2.2 W for Lanczos AI pipeline

Energy per inference: Not reported

Execution without full OS: Yes, RTEMS RTOS is configured for LEON

Fully on-device inference: Yes

Constraints mentioned: Power, latency, compute, on-board processing, SWaP, embedded memory hierarchy

## Dataset

Name: soyuz_hard; soyuz_easy also reported for additional results

Type: Not reported

Dataset size: 4000 training images, 500 validation images, 500 testing images

Number of classes: Not applicable

Input resolution: 1024 × 1024 × 3 input image; 512 × 512 × 3 DNN inference image; 1024 × 1024 × 1 CV tracking input

Data modality: RGB image; grayscale image for CV pipeline

## Metrics

Accuracy: LOCE 1.15–1.18 m and ORIE 14.57°–14.76° on soyuz_hard; LOCE 0.7 m and ORIE 8.7° on soyuz_easy

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: DNN inference 373 ms; AI pose estimation pipeline 374–392 ms; CV pose tracking 218–341 ms

FPS: AI pose estimation 2.6–2.7 FPS; CV pose tracking 3.1–5.1 FPS; overall up to 5 FPS

Throughput: 2.7–5.1 FPS for the targeted AI/CV embedded system

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Around 2 W; 2.0–2.2 W in Table 2

## Optimization

Techniques used: Low-level Myriad X optimization, NCE/SHAVE mapping, SIMD, sliding buffer, variable tuning, CMX scratchpad transfers, cache optimization, loop merging, dynamic scheduling, image resampling, power management

Quantization: FP16

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Image resampling/downscaling from 1024 × 1024 × 3 to 512 × 512 × 3

Hardware-specific optimization: Yes, optimized for Myriad X NCE, SHAVEs, CMX, DMA, LEON processors, and power islands

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes, 374–392 ms for AI pose estimation and 218–341 ms for CV pose tracking

Runs without full operating system: Yes, RTEMS RTOS is reported

Fully on-device inference: Yes

Communication required during inference: No cloud/off-device inference communication reported

Candidate for Strict TinyML: No

Reason: The target is an embedded VPU/SoC with 512 MB DRAM and OpenVINO deployment, not MCU-class hardware with KB/low-MB SRAM/Flash constraints.

## Benchmarking / Standardization

Benchmark used: Custom evaluation on satellite pose estimation/tracking workloads

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO used for pretrained weights, not as the evaluation benchmark

Comparison with baseline models: Original UrsoNet without resampling; straightforward SHAVE parallelization; LEON4 CPU

Comparison with previous works: Yes, compared with Myriad 2, LEON4, Jetson Nano CPU/GPU, Tegra K1, and Zynq-7000

Reproducibility artifacts available: Not reported

## Results

Summary: The AI pipeline achieves 2.6–2.7 FPS with 373 ms DNN inference latency and around 2 W power. The CV tracking pipeline achieves 218–341 ms latency and 3.1–5.1 FPS, while the system reaches up to 5 FPS for 1-MegaPixel images.

Limitations: The final high-level policy for coordinating AI and CV pipelines is not implemented and requires additional exploration with test campaigns and real satellite datasets.

## Practical Reporting Checklist Evidence

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

## Contribution

This paper proposes a single-chip hybrid AI/CV embedded system for satellite pose estimation and tracking on Intel Myriad X using UrsoNet, a classical CV pipeline, and low-level hardware-specific optimizations.

| Paper       | Year | Task                               | Model                                     | Technique                                                                | Device             | Dataset    | Main Metric                          | Latency                      | Model Size | SRAM/RAM                                      | Flash | Energy | Framework                   | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------------------------- | ----------------------------------------- | ------------------------------------------------------------------------ | ------------------ | ---------- | ------------------------------------ | ---------------------------- | ---------- | --------------------------------------------- | ----- | ------ | --------------------------- | -------- | ------------- | ------------- |
| Leon et al. | 2023 | Satellite pose estimation/tracking | UrsoNet ResNet-50 + classical CV pipeline | Myriad X low-level parallelization, SIMD, cache optimization, resampling | Intel Myriad X VPU | soyuz_hard | LOCE 1.15–1.18 m; ORIE 14.57°–14.76° | AI 374–392 ms; CV 218–341 ms | N/A        | 512 MB LPDDR4; 2.5 MB CMX capacity; usage N/A | N/A   | N/A    | TensorFlow + OpenVINO + MDK | FP16     | None          | No            |
