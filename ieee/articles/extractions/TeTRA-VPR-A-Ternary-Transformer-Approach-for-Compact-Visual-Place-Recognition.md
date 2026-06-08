Paper ID: TeTRA-VPR-A-Ternary-Transformer-Approach-for-Compact-Visual-Place-Recognition

TinyML classification: Near-TinyML — The paper targets resource-constrained IoT devices and evaluates image classification, object detection, and segmentation, but experiments are GPU-based and MCU-level deployment is not shown.

Basic Info

Authors: Oliver Grainge; Michael J. Milford; Indu Bodala; Sarvapali D. Ramchurn; Shoaib Ehsan

Year: 2025

Title: TeTRA-VPR: A Ternary Transformer Approach for Compact Visual Place Recognition

Source: IEEE Robotics and Automation Letters, Vol. 10, No. 8, August 2025, pp. 8396–8403 

Type: Experimental

Problem & Context

Task: Visual place recognition / image retrieval-based localization

Objective: Reduce memory consumption and inference latency of ViT-based visual place recognition while preserving Recall@1 accuracy on resource-constrained robotic platforms.

Application domain: Robotics navigation, mapping, localization, and long-term autonomy

Scenario: Edge / embedded robotic platforms, drones, and mobile robots

TinyML relevance: Partial

TinyML justification: The paper targets memory- and compute-constrained robotic platforms and evaluates on Jetson Xavier NX, but does not report MCU-class deployment, SRAM/Flash constraints, TensorFlow Lite Micro, or bare-metal/RTOS execution.

Model / Method

Model: TeTRA-VPR

Architecture family: ViT

Techniques: 2-bit ternary quantization, 1-bit binary embeddings, 8-bit activation quantization, progressive quantization-aware training, knowledge distillation, supervised contrastive fine-tuning

Framework: Not reported

Training type: Pre-training with distillation and fine-tuning

Inference type: On-device

Hardware

Device: Jetson Xavier NX; training used 4 H100 GPUs

Hardware type: SoC / embedded GPU

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, compute, latency, storage, power-constrained deployment

Dataset

Name: San Francisco; GSV-Cities; MSLS; Pitts30k; Tokyo 24/7; SVOX-Night; SVOX-Rain; SVOX-Snow; SVOX-Sun

Type: Not reported

Dataset size: Not reported

Number of classes: Not reported

Input resolution: Not reported

Data modality: Image

Metrics

Accuracy: Recall@1 reported; TeTRA-BoQ achieved 86.6 on MSLS, 91.7 on Pitts30k, 88.6 on Tokyo247, 64.9 on SVOX-Night, 96.7 on SVOX-Rain, 98.0 on SVOX-Snow, and 93.9 on SVOX-Sun.

mAP: Not reported

Precision: Not reported

Recall: Recall@1 reported as the primary metric

F1-score: Not reported

Latency: 176 ms/image on Jetson Xavier NX; 35% lower latency relative to EigenPlaces

FPS: 5.7 FPS on Jetson Xavier NX

Throughput: Not reported

Model size: Not reported as standalone model file size

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported as SRAM/RAM; total memory consumption and memory efficiency are reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Ternary ViT backbone quantization, binary embedding layer, 8-bit activation quantization, progressive QAT, knowledge distillation, Hamming-distance matching with XOR and bitcount operations

Quantization: QAT; 2-bit ternary weights, 8-bit activations, and 1-bit binary embeddings

Pruning: No

Knowledge distillation: Yes

Compression method: Ultra-low-bit quantization of the ViT backbone and binarization of the final embedding layer

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported as standalone model file size

Energy per inference reported: Not reported

Latency on target device reported: 176 ms/image on Jetson Xavier NX

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper evaluates compact edge VPR on Jetson Xavier NX and reports memory/latency benefits, but provides no MCU-class deployment or SRAM/Flash/energy evidence.

Benchmarking / Standardization

Benchmark used: VPR benchmarks

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: MSLS, Pitts30k, Tokyo 24/7, SVOX

Comparison with baseline models: Yes; DinoV2-BoQ, DinoV2-SALAD, ResNet50-BoQ, EigenPlaces, CosPlace, FloppyNet, NetVLADSP, DinoV2-BoQ-INT8, ResNet50-BoQ-INT8, EigenPlaces-D2048-INT8, and CosPlace-D2048-INT8

Comparison with previous works: Yes

Reproducibility artifacts available: code / model

Results

Summary: TeTRA reduces memory consumption by up to 69% and latency by 35% compared with efficient convolutional baselines while maintaining or improving Recall@1. It runs at 5.7 FPS on Jetson Xavier NX and shows strong memory efficiency across VPR benchmarks.

Limitations

Two-stage retrieval is left for future work; MCU-class deployment, SRAM/Flash usage, power consumption, and energy per inference are not reported.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a ternary Vision Transformer framework for compact visual place recognition using progressive quantization-aware training, binary embeddings, and knowledge distillation to reduce memory and latency on resource-constrained robotic platforms.

| Paper          | Year | Task                     | Model     | Technique                                            | Device           | Dataset                          | Main Metric                | Latency      | Model Size | SRAM/RAM            | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---: | ------------------------ | --------- | ---------------------------------------------------- | ---------------- | -------------------------------- | -------------------------- | ------------ | ---------- | ------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Grainge et al. | 2025 | Visual Place Recognition | TeTRA-VPR | 2-bit ternary QAT + binary embeddings + distillation | Jetson Xavier NX | MSLS; Pitts30k; Tokyo 24/7; SVOX | Recall@1 88.6% on Tokyo247 | 176 ms/image | N/A        | 215 MB total memory | N/A   | N/A    | N/A       | QAT      | None          | No            |
