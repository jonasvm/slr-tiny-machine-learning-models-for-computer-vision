Paper ID: A-Reconfigurable-Neural-Network-Processor-With-Tile-Grained-Multicore-Pipeline-for-Object-Detection-on-FPGA

TinyML classification: Near-TinyML — FPGA-based edge acceleration is relevant to embedded vision, but the paper does not report microcontroller-class deployment or MCU-level constraints.

Basic Info

Authors: Libo Chang, Shengbing Zhang, Huimin Du, Yue Chen, Shiyu Wang

Year: 2021

Title: A Reconfigurable Neural Network Processor With Tile-Grained Multicore Pipeline for Object Detection on FPGA

Source: IEEE Transactions on Very Large Scale Integration (VLSI) Systems, Vol. 29, No. 11 

Type: Methodological

Problem & Context

Task: Object detection

Objective: Improve computational efficiency, throughput, and on-chip memory utilization for CNN-based object detection on FPGA.

Application domain: Object detection for human behavior cognition, intelligent driving, and anomaly detection.

Scenario: Edge / embedded FPGA-based inference.

TinyML relevance: Partial

TinyML justification: The paper targets low-power edge FPGA acceleration, but not MCU-class or TensorFlow Lite Micro deployment.

Model / Method

Model: Reconfigurable CNN processor evaluated with RetinaNet-ResNet-50, MobileNetV2-SSDLite, and YOLOv3.

Architecture family: CNN

Techniques: Mixed-precision quantization, bit-adaptive computing, tile-grained multicore pipelining, elastic on-chip buffer, computing near memory, cross-layer feature map fusion, macroinstruction set architecture.

Framework: Xilinx Vivado 2019.2; custom FPGA processor.

Training type: Not reported

Inference type: On-device

Hardware

Device: Xilinx ZCU102

Hardware type: FPGA / SoC

Processor / microcontroller: UltraScale FPGA with quad ARM Cortex-A53 processor.

Clock frequency: 200 MHz

SRAM / RAM: 4 GB PS DDR4; BRAM utilization: ResNet-50 743 BRAMs, RetinaNet-ResNet-50 788 BRAMs, MobileNetV2-SSDLite 724 BRAMs, YOLOv3 680 BRAMs.

Flash / ROM / Storage: Not reported

Power consumption: 12.6 W for MobileNetV2-SSDLite; 15.3 W for YOLOv3.

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: On-chip memory, off-chip memory access, power consumption, compute resources, throughput, latency.

Dataset

Name: COCO

Type: Public

Dataset size: Not reported

Number of classes: Not reported

Input resolution: Not reported

Data modality: RGB image

Metrics

Accuracy: Not reported separately from mAP.

mAP: RetinaNet-ResNet-50 35.6; MobileNetV2-SSDLite 21.3; YOLOv3 49.7.

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 170 ms for ResNet-50; not reported for RetinaNet-ResNet-50, MobileNetV2-SSDLite, or YOLOv3.

FPS: MobileNetV2-SSDLite 515.4 FPS; YOLOv3 22.0 FPS.

Throughput: RetinaNet-ResNet-50 1503 GOPS; MobileNetV2-SSDLite 1066 GOPS; YOLOv3 809 GOPS.

Model size: RetinaNet-ResNet-50 13.67 MB; MobileNetV2-SSDLite 2.31 MB; YOLOv3 44.1 MB.

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: BRAM utilization: RetinaNet-ResNet-50 788 BRAMs, MobileNetV2-SSDLite 724 BRAMs, YOLOv3 680 BRAMs.

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 12.6 W for MobileNetV2-SSDLite; 15.3 W for YOLOv3.

Optimization

Techniques used: Mixed-precision quantization, bit-adaptive DSP reuse, tile-grained pipelining, elastic on-chip buffer, cross-layer feature map fusion, computing near memory.

Quantization: Mixed precision

Pruning: No

Knowledge distillation: No

Compression method: Mixed-precision quantization with compression ratios of 10.6, 4.2, and 5.3 for the three evaluated object detection networks.

Hardware-specific optimization: Reconfigurable FPGA compute engine, adaptive DSP-based MAC operations, elastic on-chip BRAM buffer, DMA-based data transfer, macroinstruction scheduling.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: RetinaNet-ResNet-50 13.67 MB; MobileNetV2-SSDLite 2.31 MB; YOLOv3 44.1 MB.

Energy per inference reported: Not reported

Latency on target device reported: 170 ms for ResNet-50.

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Off-chip DDR memory access is used; cloud communication is not reported.

Candidate for Strict TinyML: No

Reason: The target platform is an FPGA/SoC with 4 GB DDR4, not an MCU-class device with SRAM/Flash constraints.

Benchmarking / Standardization

Benchmark used: COCO

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO

Comparison with baseline models: Yes; compared against 8-bit DSP reuse baseline, layer-level temporal mapping, and fixed interconnection buffer baseline.

Comparison with previous works: Yes; compared with prior FPGA object detection accelerators.

Reproducibility artifacts available: Not reported

Results

Summary: The proposed processor achieved 1503 GOPS for RetinaNet-ResNet-50, 1066 GOPS for MobileNetV2-SSDLite, and 809 GOPS for YOLOv3. Mixed-precision quantization reduced model sizes while keeping accuracy loss within 2 mAP.

Limitations

The paper reports that limited on-chip BRAM on the smaller FPGA platform reduces efficiency for large-scale object detection CNNs because some intermediate feature maps must be cached in off-chip memory.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a reconfigurable FPGA-based CNN processor with tile-grained multicore pipelining, mixed-precision computing, and elastic on-chip buffering for efficient object detection inference.

| Paper        | Year | Task             | Model                                            | Technique                                                | Device        | Dataset | Main Metric     | Latency          | Model Size                 | SRAM/RAM                     | Flash | Energy | Framework            | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | ---------------- | ------------------------------------------------ | -------------------------------------------------------- | ------------- | ------- | --------------- | ---------------- | -------------------------- | ---------------------------- | ----- | ------ | -------------------- | -------- | ------------- | ------------- |
| Chang et al. | 2021 | Object detection | RetinaNet-ResNet-50; MobileNetV2-SSDLite; YOLOv3 | Mixed-precision quantization + FPGA multicore pipelining | Xilinx ZCU102 | COCO    | YOLOv3 49.7 mAP | ResNet-50 170 ms | 13.67 MB; 2.31 MB; 44.1 MB | 4 GB DDR4; 788/724/680 BRAMs | N/A   | N/A    | Xilinx Vivado 2019.2 | Mixed    | None          | No            |
