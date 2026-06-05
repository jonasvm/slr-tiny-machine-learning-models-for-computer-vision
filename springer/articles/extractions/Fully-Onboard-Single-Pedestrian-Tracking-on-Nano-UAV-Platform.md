Paper ID: Fully-Onboard-Single-Pedestrian-Tracking-on-Nano-UAV-Platform

TinyML classification: Strict TinyML — explicitly targets MCU-class nano-UAV deployment with GAP8/AI-deck constraints and reports memory, fps, and mJ/frame metrics.

Basic Info

Authors: Haolin Chen; Ruidong Wu; Wenshuai Lu; Xinglong Ji; Tao Wang; Haolun Ding; Yuxiang Dai; Bing Liu

Year: 2023

Title: Fully Onboard Single Pedestrian Tracking on Nano-UAV Platform

Source: Journal of Intelligent & Robotic Systems, 109:50 

Type: Experimental

Problem & Context

Task: Object tracking; pedestrian detection

Objective: Develop a lightweight single pedestrian tracking algorithm for fully onboard nano-UAV deployment under strict memory, compute, power, and latency constraints.

Application domain: Nano-UAV pedestrian tracking

Scenario: Embedded, nano-UAV, ultra-low-power, fully onboard inference

TinyML relevance: Yes

TinyML justification: The paper targets fully onboard inference on a nano-UAV using an MCU-class ultra-low-power GAP8-based AI-deck, with explicit memory, latency, power, energy, quantization, and model-size constraints.

Model / Method

Model: Lightweight tracking algorithm with pruned YOLOv3-Tiny-based object detection frontend and motion-based tracking backend using Kalman filter, IoU distance, area distance, and Hungarian association.

Architecture family: CNN / Classical ML

Techniques: Channel pruning, INT8 quantization, layer fusion, hardware-aware tiling, small input resolution

Framework: TFLite per-channel 8-bit quantization; GAP8 AutoTiler deployment

Training type: Transfer learning and fine-tuning

Inference type: On-device

Hardware

Device: Crazyflie 2.1 nano-UAV with AI-deck and Flow deck

Hardware type: MCU / SoC

Processor / microcontroller: GreenWaves Technologies GAP8 SoC; STM32F405 Cortex-M4 MCU for flight control

Clock frequency: FC and CL tested up to 250 MHz; in-field experiment used CL = 125 MHz and FC = 150 MHz

SRAM / RAM: STM32F405 has 192 kB SRAM; GAP8 has 512 KB L2 memory and 64 kB L1 scratchpad; AI-deck has 64 Mbit HyperRAM

Flash / ROM / Storage: STM32F405 has 1 Mb flash; AI-deck includes 512 Mbit HyperFlash

Power consumption: 225.7 mW at maximum-performance configuration; 81.4 mW in most energy-saving configuration

Energy per inference: 5.3 mJ/frame at maximum-performance configuration; ∼7 mJ/frame in selected in-field configuration

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, compute, storage, payload, communication

Dataset

Name: Custom HM01B0 low-resolution grayscale dataset; COCO used for pretraining

Type: Private/custom and public

Dataset size: 4628 labeled low-resolution grayscale images for detection training/evaluation; 4165 train and 463 validation; tracking datasets contain 745, 523, and 311 frames; COCO pretraining used 117266 training images and 4952 validation images

Number of classes: 1 class for fine-tuning: person; COCO pretraining uses 80 classes

Input resolution: 128 × 160

Data modality: Grayscale image

Metrics

Accuracy: Not reported

mAP: Not reported

Precision: 0.977 precision score for tracking

Recall: Not reported

F1-score: Not reported

Latency: 24.63 ms/frame at FC = 250 MHz and CL = 250 MHz; object detection frontend about 20 ms/frame; tracking backend <7 ms/frame

FPS: Up to 43 fps; ∼18 fps in selected in-field configuration

Throughput: 43 frames/second

Model size: 326 kB

Parameters: 3.0 × 10^5

MACs / FLOPs: 23.7 MMACs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: 5.3 mJ/frame

Power consumption: 225.7 mW at maximum-performance configuration

Optimization

Techniques used: Channel pruning, TFLite per-channel 8-bit quantization, Conv-BN/MaxPool/ReLU layer fusion, GAP8 AutoTiler-based tiling, hardware-aware deployment on cluster and fabric-controller domains

Quantization: INT8

Pruning: Yes

Knowledge distillation: Not reported

Compression method: Channel pruning, INT8 quantization, and layer fusion

Hardware-specific optimization: GAP8 AutoTiler tiling, layer fusion, L1/L2/L3 memory scheduling, deployment of detection frontend on cluster and tracking backend on fabric controller

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 326 kB

Energy per inference reported: 5.3 mJ/frame

Latency on target device reported: 24.63 ms/frame at FC = 250 MHz and CL = 250 MHz

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No external communication/cloud required during inference

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets fully onboard nano-UAV inference on MCU-class ultra-low-power embedded hardware with reported model size, latency, FPS, power, energy, quantization, and memory-aware deployment.

Benchmarking / Standardization

Benchmark used: Custom tracking datasets with OTB-style precision score and success score metrics

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO used for pretraining; OTB-style precision and success plots used for tracking evaluation

Comparison with baseline models: Yes, compared against YOLOv3-Tiny, SiamRPN++, and SiamMask

Comparison with previous works: Yes, compared with PULP-Frontnet and PULP-Dronet V2 for onboard performance

Reproducibility artifacts available: none

Results

Summary: The proposed tracking algorithm achieves 0.977 precision score, 0.574 success score, 43 fps peak onboard performance, 5.2 MACs/cycle computing efficiency, and 5.3 mJ/frame energy efficiency. The frontend uses 326 kB memory, 3.0 × 10^5 parameters, and 23.7 MMACs.

Limitations

The tracking backend cannot handle fast target motion greater than 1.0 m/s. The algorithm is also limited for small targets when the straight-line distance between target and UAV is more than 3 m.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a lightweight fully onboard single pedestrian tracking algorithm for nano-UAVs using a pruned and INT8-quantized YOLOv3-Tiny-based detection frontend, a motion-based tracking backend, and GAP8-specific deployment optimizations.

| Paper       | Year | Task                                   | Model                                                        | Technique                                          | Device                                   | Dataset                                            | Main Metric           | Latency        | Model Size | SRAM/RAM                              | Flash               | Energy       | Framework                            | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | -------------------------------------- | ------------------------------------------------------------ | -------------------------------------------------- | ---------------------------------------- | -------------------------------------------------- | --------------------- | -------------- | ---------- | ------------------------------------- | ------------------- | ------------ | ------------------------------------ | -------- | ------------- | ------------- |
| Chen et al. | 2023 | Object tracking / pedestrian detection | Pruned YOLOv3-Tiny frontend + Kalman-filter tracking backend | Channel pruning + INT8 quantization + layer fusion | Crazyflie 2.1 nano-UAV with GAP8 AI-deck | Custom HM01B0 grayscale dataset + COCO pretraining | Precision score 0.977 | 24.63 ms/frame | 326 kB     | 512 KB L2; 64 kB L1; 64 Mbit HyperRAM | 512 Mbit HyperFlash | 5.3 mJ/frame | TFLite quantization + GAP8 AutoTiler | INT8     | None          | Yes           |
