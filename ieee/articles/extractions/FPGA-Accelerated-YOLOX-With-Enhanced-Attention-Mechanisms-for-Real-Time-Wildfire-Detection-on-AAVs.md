Paper ID: FPGA-Accelerated-YOLOX-With-Enhanced-Attention-Mechanisms-for-Real-Time-Wildfire-Detection-on-AAVs

TinyML classification: Near-TinyML — FPGA/Kria KV260 edge deployment is reported, but there is no clear MCU-class deployment.

Basic Info

Authors: Anubhav Elhence; Anubhav Panda; Vinay Chamola; Biplab Sikdar

Year: 2025

Title: FPGA-Accelerated YOLOX With Enhanced Attention Mechanisms for Real-Time Wildfire Detection on AAVs

Source: IEEE Transactions on Instrumentation and Measurement, Vol. 74, Article 5027814, DOI: 10.1109/TIM.2025.3556164 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Real-time wildfire detection on autonomous aerial vehicles using an FPGA-accelerated object detection model.

Application domain: Wildfire detection, aerial robotics, environmental monitoring

Scenario: Embedded edge inference on FPGA-based AAV platform

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained, low-power, on-device FPGA inference for AAVs, but it does not demonstrate MCU-class TinyML deployment.

Model / Method

Model: LCAM-YOLOX

Architecture family: CNN

Techniques: Layerwise channel attention module, hybrid channel-spatial attention, Soft-NMS, INT8 post-training quantization, pruning, FPGA/DPU acceleration

Framework: PyTorch, ONNX, Xilinx Vitis AI compiler, XIR, DPU .xmodel, Netron

Training type: Not reported

Inference type: On-device

Hardware

Device: Xilinx Kria KV260 System on Module; also evaluated on ZCU104 and ZCU102

Hardware type: FPGA / SoC

Processor / microcontroller: Xilinx XCK26 UltraScale+ on KV260; DPUCZDX8G DPU

Clock frequency: 300 MHz DPU frequency

SRAM / RAM: System RAM not reported; KV260 FPGA resource use reported as BRAM 19/144 and URAM 42/64 for 1-core, BRAM 57/144 and URAM 64/64 for 2-core

Flash / ROM / Storage: Not reported

Power consumption: 9.72 W single-core KV260; 10.45 W measured at maximum KV260 DPU utilization

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Computational capacity, power availability, battery limitations, real-time latency, communication constraints, FPGA resource limits

Dataset

Name: Foggia dataset; custom wildfire dataset

Type: Public benchmark plus custom AAV/internet-sourced dataset with augmentation

Dataset size: Foggia dataset has 31 videos, including 14 fire videos and 17 videos with red objects and smoke; custom dataset size not reported

Number of classes: Five fire severity classes; smoke used as an auxiliary parameter

Input resolution: Model input 640 × 640 × 3; Foggia videos range from 320 × 240 to 400 × 256 pixels

Data modality: RGB video/images, AAV aerial imagery, multispectral and RGB camera imagery

Metrics

Accuracy: FP32 accuracy/mAP 79.89%

mAP: FP32 mAP 0.7989; preprocessed mAP 0.8163; INT8 quantized and pruned mAP 0.7811

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 195 FPS on KV260 1-core; 387 FPS on KV260 2-core; 193/337 FPS on ZCU104; 185/319/481 FPS on ZCU102

Throughput: Up to 37.15 FPS/W on KV260 with two DPU cores

Model size: Not reported in MB

Parameters: 9.6 M parameters; 6.72 M weights after pruning

MACs / FLOPs: 8.45 GFLOPs before pruning; 6.31 GFLOPs after pruning

RAM usage: System RAM not reported; DPU RAM usage listed as low

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 9.72 W single-core KV260; 10.45 W maximum KV260 measurement; 13.20 W ZCU104; 22.13 W ZCU102

Optimization

Techniques used: LCAM attention, spatial attention, Soft-NMS, resizing and normalization preprocessing, INT8 post-training quantization, 30% pruning, Vitis AI FPGA compilation, DPU deployment

Quantization: INT8 PTQ

Pruning: Yes

Knowledge distillation: Not reported

Compression method: INT8 quantization and 30% pruning

Hardware-specific optimization: Xilinx Vitis AI compilation, XIR intermediate representation, operator fusion, subgraph partitioning, DPU instruction generation, .xmodel deployment

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Parameters/weights reported, but model size in memory not reported

Energy per inference reported: Not reported

Latency on target device reported: FPS reported, latency not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No offloading reported; AAV communication security is mentioned separately

Candidate for Strict TinyML: No

Reason: The deployment target is FPGA/SoC edge hardware rather than MCU-class hardware, and SRAM/Flash, bare-metal/RTOS, TFLM, or MCU-level memory evidence is not reported.

Benchmarking / Standardization

Benchmark used: Foggia fire and smoke detection dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Foggia dataset

Comparison with baseline models: YOLOv3, YOLOv5, YOLOX-m, MobileNetV2, EfficientDet, Faster R-CNN, RetinaNet

Comparison with previous works: Yes; related wildfire detection, UAV vision, FPGA acceleration, TinyML, and small-object detection works are discussed

Reproducibility artifacts available: Code

Results

Summary: LCAM-YOLOX achieved 78.11% INT8 quantized mAP, 195 FPS on a single KV260 DPU core, and 10.45 W maximum measured KV260 power consumption. The model outperformed YOLOv3, YOLOv5, YOLOX-m, MobileNetV2, EfficientDet, Faster R-CNN, and RetinaNet in the reported accuracy/FPS tradeoff. 

Limitations

The study is optimized for single-camera input at 640 × 640 resolution; future work includes native higher-resolution support, super-resolution, multicamera setups, more diverse wildfire scenarios, hybrid quantization, dynamic frequency scaling, transformer-based comparisons, small-target detection algorithms, alternative edge platforms, and low-power microcontrollers.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes, FPGA BRAM/URAM resource utilization is reported

Reports latency: No

Reports energy or power: Yes

Reports model size: Yes, parameters/weights are reported

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes an FPGA-accelerated LCAM-YOLOX object detection framework with INT8 quantization and pruning for real-time wildfire detection on AAVs.

| Elhence et al. | 2025 | Object Detection | LCAM-YOLOX | INT8 PTQ + pruning | Xilinx Kria KV260 FPGA | Foggia + custom wildfire dataset | Quantized mAP 78.11% | N/A | N/A | N/A | N/A | N/A | Vitis AI/XIR/DPU | INT8/PTQ | None | No |
