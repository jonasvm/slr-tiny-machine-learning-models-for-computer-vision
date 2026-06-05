Paper ID: Tiny-deep-learning-models-for-real-time-and-efficient-embedded-driver-state-detection

TinyML classification: Strict TinyML — explicitly targets MCU-class platforms and reports RAM/model-size constraints compatible with Arduino, STM32, and ESP32-style deployment.

Basic Info

Authors: Siham Essahraui; Abdussalam Elhanashi; Qinghe Zheng; Nawal Almutairi; Sergio Saponara

Year: 2026

Title: Tiny deep learning models for real-time and efficient embedded driver state detection

Source: Journal of Real-Time Image Processing, 23:39 

Type: Benchmark

Problem & Context

Task: Classification

Objective: Benchmark seven lightweight deep learning architectures for real-time driver state detection under embedded hardware constraints.

Application domain: Driver monitoring / intelligent transportation systems

Scenario: Embedded, low-power, on-device intelligent vehicles

TinyML relevance: Yes

TinyML justification: The paper explicitly targets TinyML/TinyDL embedded deployment and reports model size, RAM usage, and FPS for compact computer-vision models intended for Arduino, STM32, ESP32, and Arduino Nano BLE Sense-class devices.

Model / Method

Model: Efficient-Tiny; ESPNetv2-Small; MCUNet; Micro-MobileNet; PhiNets; ShuffleNetLite; SqueezeNetv11

Architecture family: CNN

Techniques: Lightweight CNN design, depthwise separable convolutions, grouped convolutions, dilated convolutions, fire modules, compound scaling, NAS-based MCUNet design, mixed-kernel convolutions

Framework: Not reported

Training type: from scratch

Inference type: on-device target; actual on-device deployment not reported

Hardware

Device: Target platforms mentioned include Arduino, STM32, ESP32, Arduino Nano BLE Sense, STM32 Nucleo, and ESP32-CAM; actual benchmark device not reported

Hardware type: MCU target; actual hardware not reported

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Efficient-Tiny 0.08 MB; ESPNetv2-Small 0.22 MB; MCUNet 0.03 MB; Micro-MobileNet 0.15 MB; PhiNets 0.15 MB; ShuffleNetLite 1.75 MB; SqueezeNetv11 0.05 MB

Flash / ROM / Storage: Not reported separately; model size reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Memory, Flash, SRAM, model size, latency, compute, energy efficiency, embedded deployment feasibility

Dataset

Name: State Farm Distracted Driver Detection dataset (SFDDD)

Type: public

Dataset size: 22,424 labeled RGB images and 79,726 unlabeled RGB images

Number of classes: 10

Input resolution: Original 640 × 480; resized to 224 × 224

Data modality: RGB image

Metrics

Accuracy: Efficient-Tiny 91.64%; ESPNetv2-Small 99.50%; MCUNet 97.85%; Micro-MobileNet 98.99%; PhiNets 99.66%; ShuffleNetLite 86.06%; SqueezeNetv11 95.81%

mAP: Not reported

Precision: Efficient-Tiny 93.02%; ESPNetv2-Small 99.45%; MCUNet 97.69%; Micro-MobileNet 99.26%; PhiNets 99.50%; ShuffleNetLite 92.93%; SqueezeNetv11 95.85%

Recall: Efficient-Tiny 92.56%; ESPNetv2-Small 99.44%; MCUNet 97.48%; Micro-MobileNet 99.23%; PhiNets 99.49%; ShuffleNetLite 86.23%; SqueezeNetv11 95.76%

F1-score: Efficient-Tiny 92.01%; ESPNetv2-Small 99.44%; MCUNet 97.54%; Micro-MobileNet 99.24%; PhiNets 99.49%; ShuffleNetLite 87.21%; SqueezeNetv11 95.76%

Latency: Not reported

FPS: Efficient-Tiny 26.81 FPS; ESPNetv2-Small 40.49 FPS; MCUNet 52.72 FPS; Micro-MobileNet 37.71 FPS; PhiNets 36.14 FPS; ShuffleNetLite 22.27 FPS; SqueezeNetv11 28.60 FPS

Throughput: Same as FPS

Model size: Efficient-Tiny 0.43 MB; ESPNetv2-Small 0.74 MB; MCUNet 0.20 MB; Micro-MobileNet 0.60 MB; PhiNets 0.60 MB; ShuffleNetLite 5.46 MB; SqueezeNetv11 0.33 MB

Parameters: Efficient-Tiny 0.021M; ESPNetv2-Small 0.057M; MCUNet 0.009M; Micro-MobileNet 0.039M; PhiNets 0.038M; ShuffleNetLite 0.458M; SqueezeNetv11 0.012M

MACs / FLOPs: Not reported

RAM usage: Efficient-Tiny 0.08 MB; ESPNetv2-Small 0.22 MB; MCUNet 0.03 MB; Micro-MobileNet 0.15 MB; PhiNets 0.15 MB; ShuffleNetLite 1.75 MB; SqueezeNetv11 0.05 MB

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Architecture-level lightweight design using compact CNNs, depthwise separable convolutions, grouped/dilated convolutions, fire modules, mixed-kernel convolutions, and NAS-oriented architecture design

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Architecture-level model compactness; no post-training compression implemented

Hardware-specific optimization: Hardware-oriented metrics are reported, but hardware-specific deployment optimization is not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: RAM usage reported from 0.03 MB to 1.75 MB

Flash usage reported: Not reported separately

Model size reported: Yes; 0.20 MB to 5.46 MB depending on model

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets MCU-class embedded deployment and reports sub-megabyte model sizes and RAM usage for several models, although actual MCU deployment measurements are not reported.

Benchmarking / Standardization

Benchmark used: State Farm Distracted Driver Detection dataset (SFDDD)

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: State Farm Distracted Driver Detection dataset

Comparison with baseline models: Yes; seven lightweight models are compared under a unified framework

Comparison with previous works: Yes; comparison with lightweight driver distraction detection studies is provided

Reproducibility artifacts available: dataset

Results

Summary: PhiNets achieved the highest accuracy at 99.66%, followed by ESPNetv2-Small at 99.50%. MCUNet had the lowest RAM usage at 0.03 MB and the highest FPS at 52.72, while several models remained below 1 MB model size.

Limitations

Hardware constraints, activation memory bottlenecks, compression trade-offs, and lack of post-training deployment optimizations are identified. The paper does not report actual MCU deployment, energy per inference, power consumption, or target-device latency.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a unified benchmark of seven lightweight TinyDL CNN architectures for real-time embedded driver state detection, evaluating classification accuracy, model size, RAM usage, and inference speed.

| Essahraui et al. | 2026 | Classification | Seven TinyDL CNNs | Lightweight CNN benchmarking | Arduino/STM32/ESP32 target; actual device N/A | SFDDD | Accuracy 99.66% | N/A; 22.27–52.72 FPS | 0.20–5.46 MB | 0.03–1.75 MB | N/A | N/A | N/A | N/A | N/A | Yes |
