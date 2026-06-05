Paper ID: Hybrid-Fixed-Point-Binary-Deep-Neural-Network-Design-Methodology-for-Low-Power-Object-Detection

TinyML classification: Near-TinyML — targets low-power embedded object detection and hardware-friendly quantized inference, but does not explicitly report MCU-class deployment.

Basic Info

Authors: Jiun-In Guo, Chia-Chi Tsai, Jian-Lin Zeng, Shao-Wei Peng, En-Chih Chang

Year: 2020

Title: Hybrid Fixed-Point/Binary Deep Neural Network Design Methodology for Low-Power Object Detection

Source: IEEE Journal on Emerging and Selected Topics in Circuits and Systems 

Type: Methodological

Problem & Context

Task: Object detection

Objective: Reduce model size, memory bandwidth, and computational complexity for low-power object detection while preserving mAP.

Application domain: Low-power object detection; ADAS-related detection in IVS dataset

Scenario: Embedded system / hardware accelerator

TinyML relevance: Partial

TinyML justification: Targets low-power embedded object detection and compact fixed-point/binary inference, but does not report MCU-class deployment or MCU-level memory/energy constraints.

Model / Method

Model: MobileNet-SSD; also evaluated with VGG-SSD and Darknet-YOLO variants

Architecture family: CNN

Techniques: Dynamic fixed-point quantization, binarization, layer-wise binarized training, knowledge transfer, attention transfer, K-L divergence thresholding, retraining, model compression

Framework: Not reported

Training type: Layer-wise training with knowledge transfer from a well-trained FP32 teacher model and retraining

Inference type: Not reported

Hardware

Device: Fixed-point/binary CNN hardware accelerator target; specific device not reported

Hardware type: Other

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Model size, memory bandwidth, computational complexity, power, PPA, detection accuracy loss

Dataset

Name: In-house IVS dataset; Pascal VOC

Type: Private; public

Dataset size: Not reported

Number of classes: IVS: 3; Pascal VOC: 20

Input resolution: Not reported

Data modality: Images

Metrics

Accuracy: Not reported

mAP: MobileNet-SSD FP32: 70.4% IVS mAP; hybrid 8-bit/binary retrained with K-L: 71.1% IVS mAP; Pascal VOC: 61.8% mAP with 9.6% loss

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: MobileNet-SSD FP32: 192 Mbits; hybrid 8-bit/binary: 17.2 Mbits; 91% reduction

Parameters: Hybrid 8-bit/binary MobileNet-SSD: 1.6M non-binary parameters and 4.4M binary parameters

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Hybrid fixed-point/binary quantization, layer-wise binarization, knowledge transfer, attention transfer, K-L divergence-based threshold selection, retraining

Quantization: Mixed precision

Pruning: No

Knowledge distillation: Yes

Compression method: Dynamic fixed-point quantization plus binary neural network compression

Hardware-specific optimization: 0/1 binary convolution for simpler XNOR-based hardware operation and fixed-point/binary datapath allocation

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 17.2 Mbits for hybrid 8-bit/binary MobileNet-SSD

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets low-power embedded hardware-friendly object detection but does not explicitly report MCU deployment, SRAM/Flash usage, bare-metal/RTOS execution, latency, or energy on MCU-class hardware.

Benchmarking / Standardization

Benchmark used: In-house IVS dataset; Pascal VOC

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Pascal VOC

Comparison with baseline models: FP32 MobileNet-SSD; hybrid float32/binary models; 9-bit, 8-bit, and 7-bit non-binary layer variants

Comparison with previous works: Compared with existing hybrid/binary detection models including YOLO-based, VGG/AlexNet-based, Darknet-YOLO, MobileNet-YOLO, and FPGA-related designs

Reproducibility artifacts available: Not reported

Results

Summary: The proposed hybrid 8-bit/binary MobileNet-SSD achieved 17.2 Mbits model size, 91% model-size reduction, 75.8% feature-map reduction, and 76.6% bandwidth reduction. On IVS, the retrained K-L variant reached 71.1% mAP, outperforming the FP32 baseline by 0.7 percentage points; on Pascal VOC it suffered 9.6% mAP loss.

Limitations

The paper reports higher mAP loss on Pascal VOC because the binarized model performs worse on small objects, and future work is to support a larger variety of object detection models.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: Yes

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a hybrid fixed-point/binary deep neural network design methodology for low-power object detection that combines layer-wise binarization, knowledge transfer, dynamic fixed-point quantization, and retraining to reduce model size and memory bandwidth with limited mAP degradation.

| Guo et al. | 2020 | Object detection | MobileNet-SSD | Hybrid fixed-point/binary quantization | Fixed-point/binary CNN hardware accelerator target | IVS; Pascal VOC | 71.1% IVS mAP; 61.8% Pascal VOC mAP | N/A | 17.2 Mbits | N/A | N/A | N/A | N/A | Mixed | None | No |
