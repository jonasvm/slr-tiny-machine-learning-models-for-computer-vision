Paper ID: MobiHisNet-A-Lightweight-CNN-in-Mobile-Edge-Computing-for-Histopathological-Image-Classification

TinyML classification: Near-TinyML — Edge/mobile deployment is reported, but there is no explicit MCU-class or Cortex-M-level deployment evidence.

Basic Info

Authors: Abhinav Kumar, Anshul Sharma, Vandana Bharti, Amit Kumar Singh, Sanjay Kumar Singh, Sonal Saxena

Year: 2021

Title: MobiHisNet: A Lightweight CNN in Mobile Edge Computing for Histopathological Image Classification

Source: IEEE Internet of Things Journal, Vol. 8, No. 24, DOI: 10.1109/JIOT.2021.3119520 

Type: Experimental

Problem & Context

Task: Classification

Objective: Develop and evaluate a lightweight CNN for breast cancer histopathological image classification on edge/mobile devices.

Application domain: Medical image analysis / breast cancer histopathology

Scenario: Mobile edge computing, IoT, Raspberry Pi, smartphones

TinyML relevance: Partial

TinyML justification: The paper targets on-device edge/mobile inference on Raspberry Pi and smartphones, but does not target MCU-class or bare-metal TinyML deployment.

Model / Method

Model: MobiHisNet

Architecture family: CNN

Techniques: Depthwise separable convolution, depth multiplier tuning, post-training quantization, model compression

Framework: TensorFlow Lite

Training type: Transfer learning / fine-tuning

Inference type: On-device

Hardware

Device: Raspberry Pi 3 B+ Rev 1.3; Redmi 4A; OPPO F11; Samsung A51

Hardware type: CPU / Mobile / SoC

Processor / microcontroller: Raspberry Pi 3 B+ with 1.4-GHz quad-core BCM2835 ARMv7 CPU; Redmi 4A Snapdragon 425; OPPO F11 Mediatek MT6771; Samsung A51 Exynos 9611

Clock frequency: Raspberry Pi: 1.4 GHz; smartphones: Not reported

SRAM / RAM: Raspberry Pi: 1 GB RAM; Redmi 4A: 2 GB RAM; OPPO F11: 6 GB RAM; Samsung A51: 6 GB RAM

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No for Android smartphones; Raspberry Pi OS details not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, computation, inference time, model size, bandwidth, edge-device resource constraints

Dataset

Name: BreakHis

Type: Not reported

Dataset size: 7,909 microscopic images

Number of classes: 8 histopathological classes shown in the dataset distribution; benign/malignant output illustrated

Input resolution: 224 × 224 × 3

Data modality: RGB histopathological image

Metrics

Accuracy: Proposed γ = 0.5 with FP16: 89.94% at 40X, 87.50% at 100X, 91.51% at 200X, 84.15% at 400X

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Raspberry Pi with FP16 and γ = 0.5: about 180 ms; Table VI reports 180.34 ms at 40X, 180.95 ms at 100X, 181.15 ms at 200X, 181.65 ms at 400X

FPS: Not reported

Throughput: Not reported

Model size: Proposed γ = 0.5: 15.44 MB before compression; FP16 on mobile devices: 3.77 MB; INT8 on mobile devices: 1.93 MB

Parameters: Proposed γ = 0.5: 1.88 million

MACs / FLOPs: Proposed γ = 0.5: 300.10 million FLOPs

RAM usage: Proposed γ = 0.5 FP16 peak memory on mobile devices: 18.63 MB on Redmi 4A, 17.75 MB on OPPO F11, 17.95 MB on Samsung A51

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Depthwise separable convolution, depth multiplier γ, post-training quantization with FP32, FP16, and INT8

Quantization: FP16 and INT8 PTQ

Pruning: No

Knowledge distillation: No

Compression method: Post-training quantization and depth multiplier reduction

Hardware-specific optimization: Thread selection evaluated; no hardware-specific kernel optimization reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: No; peak memory in MB is reported, but SRAM usage is not reported

Flash usage reported: No

Model size reported: Yes

Energy per inference reported: No

Latency on target device reported: Yes

Runs without full operating system: No for Android smartphones; Raspberry Pi OS details not reported

Fully on-device inference: Yes

Communication required during inference: No cloud or offloading reported

Candidate for Strict TinyML: No

Reason: The paper evaluates Raspberry Pi and smartphone deployment with GB-scale RAM, but does not report MCU, Cortex-M, TFLite Micro, bare-metal/RTOS execution, SRAM/Flash constraints, or energy per inference.

Benchmarking / Standardization

Benchmark used: BreakHis

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: VGG16, ResNet50, Xception, InceptionV3, MobileNetV1, EffNetB0

Comparison with previous works: Compared with state-of-the-art pretrained baseline models

Reproducibility artifacts available: Not reported

Results

Summary: MobiHisNet achieved high BreakHis classification accuracy with reduced parameters and FLOPs compared with larger pretrained CNNs. The γ = 0.5 and FP16 configuration was selected as the best balance between accuracy, inference time, and memory peak, with about 180 ms inference time on Raspberry Pi.

Limitations

Energy consumption was not reported and is mentioned as future work; future work also suggests component-wise computational-cost analysis and extension to a multiclass problem.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes MobiHisNet, a lightweight MobileNet-based CNN compressed with post-training quantization for on-device breast cancer histopathological image classification on Raspberry Pi and smartphones.

| Paper        | Year | Task           | Model      | Technique                     | Device                                             | Dataset  | Main Metric                                | Latency                              | Model Size                 | SRAM/RAM                                          | Flash | Energy | Framework       | INT8/QAT           | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | -------------- | ---------- | ----------------------------- | -------------------------------------------------- | -------- | ------------------------------------------ | ------------------------------------ | -------------------------- | ------------------------------------------------- | ----- | ------ | --------------- | ------------------ | ------------- | ------------- |
| Kumar et al. | 2021 | Classification | MobiHisNet | Depthwise separable CNN + PTQ | Raspberry Pi 3 B+; Redmi 4A; OPPO F11; Samsung A51 | BreakHis | Accuracy: 91.51% at 200X with γ = 0.5 FP16 | ~180 ms on Raspberry Pi γ = 0.5 FP16 | 3.77 MB FP16; 1.93 MB INT8 | Peak memory 17.75–18.63 MB FP16 on mobile devices | N/A   | N/A    | TensorFlow Lite | INT8/PTQ; FP16/PTQ | None          | No            |
