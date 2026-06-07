Paper ID: SiamOHOT-A-Lightweight-Dual-Siamese-Network-for-Onboard-Hyperspectral-Object-Tracking-via-Joint-Spatial-Spectral-Knowledge-Distillation

TinyML classification: Near-TinyML — It targets embedded edge vision deployment on Jetson Xavier NX, but does not report MCU-class deployment or constraints.

Basic Info

Authors: Chen Sun, Xinyu Wang, Zhenqi Liu, Yuting Wan, Liangpei Zhang, Yanfei Zhong

Year: 2023

Title: SiamOHOT: A Lightweight Dual Siamese Network for Onboard Hyperspectral Object Tracking via Joint Spatial–Spectral Knowledge Distillation

Source: IEEE Transactions on Geoscience and Remote Sensing, Vol. 61, 2023, DOI: 10.1109/TGRS.2023.3307052 

Type: Experimental

Problem & Context

Task: Object tracking

Objective: Enable real-time onboard hyperspectral object tracking using a lightweight dual Siamese network compressed by joint spatial–spectral knowledge distillation.

Application domain: Hyperspectral video object tracking / remote sensing

Scenario: Embedded edge / onboard processing

TinyML relevance: Partial

TinyML justification: The paper targets on-device embedded edge inference on NVIDIA Jetson Xavier NX, but does not target MCU-class deployment or kilobyte-scale memory constraints.

Model / Method

Model: SiamOHOT

Architecture family: CNN / Dual Siamese CNN

Techniques: Knowledge distillation, model compression, lightweight backbone replacement, TensorRT layer/tensor fusion, precision calibration

Framework: PyTorch 1.12.0; TensorRT; Python PyQT; xiAPI

Training type: Knowledge distillation with pretrained RGB Siamese tracker

Inference type: On-device

Hardware

Device: NVIDIA Jetson Xavier NX with snapshot hyperspectral imager

Hardware type: SoC / GPU edge device

Processor / microcontroller: NVIDIA Jetson Xavier NX

Clock frequency: Not reported

SRAM / RAM: 16 GB RAM

Flash / ROM / Storage: Not reported

Power consumption: 20 W platform power reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory burden, storage resources, computational cost, latency, limited edge-device resources, real-time processing

Dataset

Name: 2021 WHISPERS Hyperspectral Object Tracking Challenge dataset

Type: Not reported

Dataset size: Training set: 40 video sequences, about 12,800 frames; test set: 35 video sequences, about 16,500 frames 

Number of classes: Not reported

Input resolution: Not reported

Data modality: Hyperspectral video, synthetic three-band pseudo-color data, RGB video

Metrics

Accuracy: Not reported

mAP: Not reported

Precision: DP = 0.883

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 3.2 FPS optimized on NVIDIA Jetson Xavier NX; 2.4 FPS unoptimized on NVIDIA Jetson Xavier NX; 38 FPS on NVIDIA GeForce RTX 3090 GPU

Throughput: 3.2 frames/s on optimized prototype edge system

Model size: 101 MB for SiamOHOT hyperspectral branch; 225 MB for SiamHYPER hyperspectral branch

Parameters: 101 MB reported for SiamOHOT hyperspectral branch

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 20 W platform power reported

Optimization

Techniques used: Joint spatial–spectral knowledge distillation, ResNet50-to-ResNet18 backbone compression, TensorRT layer/tensor fusion, precision calibration

Quantization: Not reported

Pruning: No

Knowledge distillation: Yes

Compression method: Student SiamOHOT network learns from SiamHYPER teacher using joint spatial–spectral knowledge distillation

Hardware-specific optimization: TensorRT optimization for NVIDIA Jetson Xavier NX

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 101 MB for SiamOHOT hyperspectral branch

Energy per inference reported: Not reported

Latency on target device reported: 3.2 FPS optimized on NVIDIA Jetson Xavier NX

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is an NVIDIA Jetson Xavier NX edge device with 16 GB RAM and 20 W power, not an MCU-class platform.

Benchmarking / Standardization

Benchmark used: One-pass evaluation on 2021 WHISPERS Hyperspectral Object Tracking Challenge dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: WHISPERS Hyperspectral Object Tracking Challenge dataset

Comparison with baseline models: SiamHYPER, MHT, BAE-Net, CNHT, SiamRPN++, ATOM, KeepTrack, ToMP

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: SiamOHOT achieved AUC = 0.634 and DP = 0.883 on WHISPERS, with 38 FPS on RTX 3090 and 3.2 FPS after TensorRT optimization on Jetson Xavier NX. The hyperspectral branch size was reduced from 225 MB in SiamHYPER to 101 MB in SiamOHOT.

Limitations

The compression rate is limited by the Siamese architecture, TensorRT cannot optimize the whole tracking network, and the shallower model is less robust in fast-motion or low-resolution scenes.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a lightweight dual Siamese hyperspectral object tracker compressed with joint spatial–spectral knowledge distillation and optimized for onboard embedded edge deployment.

| Sun et al. | 2023 | Object Tracking | SiamOHOT | Joint spatial–spectral knowledge distillation + TensorRT optimization | NVIDIA Jetson Xavier NX | 2021 WHISPERS Hyperspectral Object Tracking Challenge | AUC 0.634 / DP 0.883 | N/A | 101 MB | N/A | N/A | N/A | PyTorch + TensorRT | N/A | None | No |
