Paper ID: A-Multicore-and-Edge-TPU-Accelerated-Multimodal-TinyML-System-for-Livestock-Behavior-Recognition

TinyML classification: Strict TinyML — explicitly deploys TinyML models on microcontroller-class platforms using FreeRTOS/TFLM, Google Coral Dev Board Micro, Raspberry Pi Pico, and MCU-level latency/resource constraints.

Basic Info

Authors: Qianxue Zhang and Eiman Kanjo

Year: 2026

Title: A Multicore and Edge TPU-Accelerated Multimodal TinyML System for Livestock Behavior Recognition

Source: IEEE Internet of Things Journal, Vol. 13, No. 1, pp. 666–677, 1 January 2026, DOI: 10.1109/JIOT.2025.3624811 

Type: Experimental

Problem & Context

Task: Image classification; object detection; behavior recognition

Objective: Develop a low-budget, wireless-enabled, automated TinyML livestock monitoring and tracking system using multimodal sensor and vision inputs.

Application domain: Smart agriculture; livestock monitoring

Scenario: Embedded IoT; MCU-based edge deployment; wireless rural farm monitoring

TinyML relevance: Yes

TinyML justification: The paper explicitly targets commercial microcontrollers, on-device inference, TFLite/TFLM deployment, FreeRTOS-based embedded applications, latency constraints, model-size reduction, and resource-constrained livestock monitoring.

Model / Method

Model: MCUNet; MCUNet-YOLO; hybrid CNN-LSTM; late-fusion multimodal model

Architecture family: Hybrid CNN / RNN

Techniques: NAS; TinyNAS; evolutionary search; pruning; INT8 quantization; TFLite conversion; custom TFLite operators; late fusion; Edge TPU acceleration

Framework: PyTorch; TensorFlow; TensorFlow Lite; TensorFlow Lite Micro; coralmicro APIs; FreeRTOS; C++

Training type: Transfer learning / fine-tuning for MCUNet-YOLO; not fully reported for all models

Inference type: On-device

Hardware

Device: Google Coral Dev Board Micro; Raspberry Pi Pico; Arducam Mini 2MP Plus camera; ADXL345 accelerometer; Bluetooth module

Hardware type: MCU / NPU

Processor / microcontroller: Google Coral Dev Board Micro with M7 core, M4 core, and Edge TPU; Raspberry Pi Pico

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Coral board has more than 1 GB flash memory; on-board database uses <10 KB flash memory

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Yes

Fully on-device inference: Yes

Constraints mentioned: Memory, SRAM peak activations, flash, latency, compute, power, communication, cloud independence, model size

Dataset

Name: ImageNet(1k); mini-ImageNet; custom animal/grass/fence dataset; Pascal VOC 2007/2012; Japanese Cow behavior dataset

Type: Public and custom

Dataset size: mini-ImageNet has 60,000 images; custom dataset has 640 samples; Japanese Cow dataset uses six cows over one day; Pascal VOC size not reported

Number of classes: ImageNet(1k): 1000; mini-ImageNet: 100; custom dataset: 3; Pascal VOC reduced to 4; Japanese Cow dataset: 13 annotated behaviors, with 5 actions used; fused output: 8 classes

Input resolution: 176 × 176 for image classification; 224 × 224 for object detection; 10-s sliding windows for accelerometer behavior recognition

Data modality: RGB image; accelerometer time-series; sensor + image

Metrics

Accuracy: MCUNet ImageNet(1k): 68.2% / 67.8% fp32/int8; MCUNet mini-ImageNet: 86.8% / 86.2%; MCUNet custom dataset: 97.7% / 97.6%; CNN-LSTM: 98.95% / 98.94%; fused model: 97.56% / 96.87%

mAP: MCUNet-YOLO: 0.49; ResNet-YOLO baseline: 0.49; Darknet-YOLO baseline: 0.63

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: MCUNet: 16316 ms on M4, 2645 ms on M7, 60 ms on TPU; MCUNet-YOLO: 20 s+ on M4, 3871 ms on M7, 77 ms on TPU; CNN-LSTM: 2500 ms on M4, 495 ms on M7, 16 ms on TPU; fused model: 19 s on M4, 2970 ms on M7, 75 ms on TPU

FPS: Not reported

Throughput: Not reported

Model size: Up to 270× model size reduction; byte-level model size not reported

Parameters: MCUNet ImageNet(1k): 0.7421M; MCUNet mini-ImageNet: 0.5925M; MCUNet custom dataset: 0.5769M; MCUNet-YOLO: 0.73M; CNN-LSTM: 0.1858M; fused model: 0.6825M

MACs / FLOPs: MCUNet: 81.64M FLOPs; MCUNet-YOLO: 152.4M FLOPs; CNN-LSTM: 12.52M FLOPs; fused model: 107.3M FLOPs

RAM usage: Peak activations: MCUNet: 341K; MCUNet-YOLO: 0.55M; CNN-LSTM: 31.7K; fused model: 341K

Flash usage: On-board database uses <10 KB flash memory; model flash usage not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: TinyNAS; one-shot NAS; evolutionary search; width and resolution search; iterative pruning; full integer INT8 quantization; TFLite conversion; custom C++ kernels; Edge TPU acceleration; late fusion

Quantization: INT8

Pruning: Yes

Knowledge distillation: No

Compression method: NAS, pruning, and INT8 quantization

Hardware-specific optimization: Edge TPU acceleration; MCU-targeted NAS; TFLite Micro deployment; FreeRTOS/coralmicro embedded implementation; custom TFLite operators

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: Yes

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Peak activations reported: MCUNet 341K; MCUNet-YOLO 0.55M; CNN-LSTM 31.7K; fused model 341K

Flash usage reported: On-board database <10 KB; model flash usage not reported

Model size reported: Parameters, FLOPs, peak activations, and up to 270× model-size reduction reported; byte-level model size not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Yes

Fully on-device inference: Yes

Communication required during inference: No cloud communication required; BLE is used for alerts and device communication

Candidate for Strict TinyML: Yes

Reason: The system explicitly deploys TinyML models on commercial microcontroller-class hardware using FreeRTOS, TFLite Micro, on-device inference, and reported MCU/TPU latency and memory-profile metrics.

Benchmarking / Standardization

Benchmark used: ImageNet(1k); mini-ImageNet; Pascal VOC 2007/2012; Japanese Cow behavior dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet(1k); mini-ImageNet; Pascal VOC

Comparison with baseline models: MobileNetV2; ResNet-YOLO; Darknet-YOLO; original CNN; pruned CNN; original CNN-LSTM; pruned CNN-LSTM

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset / not reported for code or model

Results

Summary: The proposed MCUNet-YOLO achieved 0.49 mAP with 0.73M parameters and 77 ms TPU latency. The fused multimodal model achieved 97.56% / 96.87% fp32/int8 accuracy with 0.6825M parameters and 75 ms TPU latency. The system demonstrated up to 270× model-size reduction and on-device MCU deployment.

Limitations

The system was evaluated under controlled conditions rather than real farming settings. Performance may be affected by sensor placement and unpredictable animal behaviors. The custom dataset and sensor data are limited and may not cover real-world edge cases.

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

This paper proposes a multicore and Edge TPU-accelerated multimodal TinyML livestock monitoring system that performs image classification, object detection, and behavior recognition fully on commercial microcontroller-based edge devices.

| Paper        | Year | Task                                                         | Model                                      | Technique                                                 | Device                                          | Dataset                                                                                | Main Metric                              | Latency                                     | Model Size                                                           | SRAM/RAM                                     | Flash                            | Energy | Framework                                            | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ------------------------------------------------------------ | ------------------------------------------ | --------------------------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------- | ---------------------------------------- | ------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------- | -------------------------------- | ------ | ---------------------------------------------------- | -------- | ------------- | ------------- |
| Zhang et al. | 2026 | Image classification; object detection; behavior recognition | MCUNet; MCUNet-YOLO; CNN-LSTM; fused model | NAS + pruning + INT8 quantization + Edge TPU acceleration | Google Coral Dev Board Micro; Raspberry Pi Pico | ImageNet(1k); mini-ImageNet; Pascal VOC; custom dataset; Japanese Cow behavior dataset | mAP 0.49; fused accuracy 97.56% / 96.87% | 77 ms object detection TPU; 75 ms fused TPU | MCUNet-YOLO 0.73M params; fused 0.6825M params; up to 270× reduction | Peak acts 0.55M object detection; 341K fused | Database <10 KB; model flash N/A | N/A    | TensorFlow Lite; TFLM; PyTorch; TensorFlow; FreeRTOS | INT8     | TFLM          | Yes           |
