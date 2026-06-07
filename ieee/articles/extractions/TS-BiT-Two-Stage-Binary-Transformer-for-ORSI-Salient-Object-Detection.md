Paper ID: TS-BiT-Two-Stage-Binary-Transformer-for-ORSI-Salient-Object-Detection

TinyML classification: Near-TinyML — Uses 1-bit binarization and model-size/operation reduction for edge-relevant vision, but no explicit MCU-class deployment or constraints.

## Basic Info

Authors: Jinfeng Zhang, Tianpeng Liu, Jiehua Zhang, Li Liu

Year: 2025

Title: TS-BiT: Two-Stage Binary Transformer for ORSI Salient Object Detection

Source: IEEE Geoscience and Remote Sensing Letters, Vol. 22, Article 6003905 

Type: Methodological

## Problem & Context

Task: Salient object detection

Objective: Improve binary vision transformer performance for optical remote sensing image salient object detection under 1-bit representation.

Application domain: Optical remote sensing images

Scenario: Resource-constrained devices such as UAVs are mentioned as motivation; experiments are conducted on GPU.

TinyML relevance: Partial

TinyML justification: The paper targets model binarization to reduce computational cost and storage requirements, but does not report MCU-class deployment or TinyML hardware constraints.

## Model / Method

Model: TS-BiT applied to GeleNet and HFANet-R

Architecture family: ViT / Transformer

Techniques: 1-bit binarization, two-stage central-aware softmax binarization, dynamic gradient approximation, scaling factors

Framework: PyTorch

Training type: Not reported

Inference type: Not reported

## Hardware

Device: NVIDIA RTX 4090 GPU

Hardware type: GPU

Processor / microcontroller: NVIDIA RTX 4090 GPU

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Model complexity, parameter size, computational cost, storage requirements, resource-constrained devices

## Dataset

Name: EORSSD, ORSSD, ORSI-4199

Type: Not reported

Dataset size: ORSSD has 600 training images; ORSI-4199 has 2000 training images; EORSSD size not reported

Number of classes: Not reported

Input resolution: GeleNet uses 3 × 352 × 352; HFANet-R uses 3 × 448 × 448

Data modality: Optical remote sensing images

## Metrics

Accuracy: Not reported

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported; maximum F-measure is reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: GeleNet Ours 10.93 MB; HFANet-R Ours 41.85 MB

Parameters: Not reported

MACs / FLOPs: GeleNet Ours 1.78G OPs; HFANet-R Ours 14.3G OPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Binary neural network quantization of transformer attention and linear layers

Quantization: 1-bit binarization

Pruning: No

Knowledge distillation: No

Compression method: Weights and activations constrained to 1-bit representations using two-stage central-aware softmax binarization

Hardware-specific optimization: Efficient XNOR and bit-count operations are mentioned, but no target hardware backend is reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: GeleNet Ours 10.93 MB; HFANet-R Ours 41.85 MB

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports binary model compression but does not provide MCU-class deployment, SRAM/Flash usage, energy, latency, or bare-metal/RTOS execution evidence.

## Benchmarking / Standardization

Benchmark used: EORSSD, ORSSD, ORSI-4199

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes; FP, BiT, BiBERT, and BiViT

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

## Results

Summary: TS-BiT improves binary ViT performance for ORSI salient object detection across EORSSD, ORSSD, and ORSI-4199. Binary GeleNet is reduced from 96.59 MB to 10.93 MB and from 28.13G OPs to 1.78G OPs, while binary HFANet-R is reduced from 1339.52 MB to 41.85 MB and from 238.94G OPs to 14.3G OPs.

Limitations: The paper notes that the method still introduces a degree of quantization error.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

## Contribution

This paper proposes TS-BiT, a two-stage binary transformer method using central-aware softmax binarization and dynamic gradient approximation for optical remote sensing image salient object detection.

| Paper        | Year | Task                     | Model                        | Technique                    | Device              | Dataset                  | Main Metric                                           | Latency | Model Size          | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | ------------------------ | ---------------------------- | ---------------------------- | ------------------- | ------------------------ | ----------------------------------------------------- | ------- | ------------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Zhang et al. | 2025 | Salient object detection | TS-BiT with GeleNet/HFANet-R | 1-bit binarization with TCSB | NVIDIA RTX 4090 GPU | EORSSD; ORSSD; ORSI-4199 | Sα 0.9291 and Fβmax 0.8920 on ORSSD GeleNet Ours 1/32 | N/A     | 10.93 MB / 41.85 MB | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
