Paper ID: Efficient-memory-reuse-methodology-for-CNN-based-real-time-image-processing-in-mobile-embedded-systems 

TinyML classification: Near-TinyML — targets embedded/mobile edge CNN inference, but the reported platform is ARM Cortex-A72 with 1GB LPDDR RAM rather than MCU-class deployment.

Basic Info

Authors: Kairong Zhao; Yinghui Chang; Weikang Wu; Hongyin Luo; Zirun Li; Shan He; Donghui Guo

Year: 2023

Title: Efficient memory reuse methodology for CNN-based real-time image processing in mobile-embedded systems

Source: Journal of Real-Time Image Processing, 20:118

Type: Methodological

Problem & Context

Task: Classification, object detection, face recognition, pose recognition, and real-time image processing

Objective: Reduce CNN intermediate-result memory footprint for real-time CNN inference on mobile-embedded and edge devices.

Application domain: Intelligent security, traffic management, mobile-embedded image processing

Scenario: Edge, embedded, mobile-embedded

TinyML relevance: Partial

TinyML justification: The paper targets memory-constrained embedded/edge CNN inference, but reports deployment on ARM Cortex-A72 with 1GB LPDDR RAM rather than MCU-class hardware.

Model / Method

Model: Improved Offset Calculation Algorithm and Layerline memory reuse algorithm evaluated on SqueezeNet_v1.1, MobileNet_v1, MobileNet_v2, ShuffleNet_v2, BlazeFace, BlazePose, YOLOv5, MobileNetV2-SSD, and DenseNet

Architecture family: CNN

Techniques: Memory reuse, intermediate tensor memory optimization, memory management, FP16 data format, layer fusion in the YOLOv5s case study

Framework: MNN

Training type: Not reported

Inference type: On-device

Hardware

Device: Embedded deep learning platform; Raspberry Pi 4 Model B used as motivational example

Hardware type: CPU / SoC

Processor / microcontroller: ARM Cortex-A72 core

Clock frequency: Not reported

SRAM / RAM: 1GB LPDDR RAM

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, latency, real-time responsiveness, throughput, energy efficiency, limited embedded-device resources

Dataset

Name: ImageNet; COCO for YOLOv5s motivational example

Type: Public

Dataset size: Not reported

Number of classes: Not reported

Input resolution: Not reported

Data modality: Image

Metrics

Accuracy: Top-1 accuracy on ImageNet: SqueezeNet_v1.1 60.4% no reuse, 60.2% Algorithm 1, 60.3% Algorithm 2; MobileNet_v1 70.6%, 70.7%, 70.1%; MobileNet_v2 74.7%, 74.3%, 74.6%; ShuffleNet_v2 71.5%, 71.3%, 71.7%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 71 FPS stated as an application requirement, not as a measured result

Throughput: Not reported

Model size: YOLOv5s parameters reported as 13.1 MB with FP16 and layer fusion

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Intermediate-result memory lower bounds: SqueezeNet_v1.1 3.01 MB; MobileNet_v1 3.06 MB; MobileNet_v2 4.59 MB; ShuffleNet_v2 1.15 MB; BlazeFace 0.66 MB; BlazePose 4.5 MB; YOLOv5 8.75 MB; MobileNetV2-SSD 8.24 MB; DenseNet 4.02 MB

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: CNN intermediate-result memory reuse, Improved Offset Calculation Algorithm, Layerline algorithm

Quantization: FP16

Pruning: No

Knowledge distillation: Not reported

Compression method: Memory reuse of non-overlapping intermediate tensors

Hardware-specific optimization: Hardware-independent memory reuse integrated into MNN

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: YOLOv5s parameters reported as 13.1 MB

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets embedded edge inference but reports ARM Cortex-A72 with 1GB LPDDR RAM and does not provide MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, SRAM, Flash, or energy evidence.

Benchmarking / Standardization

Benchmark used: CNN workloads including SqueezeNet_v1.1, MobileNet_v1, MobileNet_v2, ShuffleNet_v2, BlazeFace, BlazePose, YOLOv5, MobileNetV2-SSD, and DenseNet

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet; COCO

Comparison with baseline models: Yes, compared with existing memory reuse algorithms and no-reuse accuracy

Comparison with previous works: Yes, compared with algorithms from prior memory reuse works

Reproducibility artifacts available: dataset on request; code and model not reported

Results

Summary: Algorithm 1 reduces intermediate-result memory by 7–25% compared with its original version. Algorithm 2 achieves the theoretical lower bound on all selected CNNs and reduces intermediate memory by an average of 20.3% and 9.4% compared with two existing algorithms.

Limitations: Algorithm 2 has the highest time and space complexity, and Algorithm 1 does not achieve the theoretical lower bound for BlazeFace and YOLOv5.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes CNN intermediate-result memory reuse algorithms for reducing memory footprint during real-time CNN inference on mobile-embedded edge devices.

| Paper       | Year | Task                                                 | Model                                                                                      | Technique    | Device                           | Dataset        | Main Metric                                                            | Latency | Model Size                  | SRAM/RAM                                       | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ---------------------------------------------------- | ------------------------------------------------------------------------------------------ | ------------ | -------------------------------- | -------------- | ---------------------------------------------------------------------- | ------- | --------------------------- | ---------------------------------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Zhao et al. | 2023 | Classification / Object Detection / Image Processing | SqueezeNet, MobileNet, ShuffleNet, BlazeFace, BlazePose, YOLOv5, MobileNetV2-SSD, DenseNet | Memory reuse | ARM Cortex-A72 embedded platform | ImageNet; COCO | Algorithm 2 reduces intermediate memory by 20.3% and 9.4% vs baselines | N/A     | YOLOv5s parameters: 13.1 MB | 1GB LPDDR; YOLOv5 intermediate memory: 8.75 MB | N/A   | N/A    | MNN       | FP16     | None          | No            |
