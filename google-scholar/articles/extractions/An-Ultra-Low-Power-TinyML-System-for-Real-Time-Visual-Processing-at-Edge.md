Paper ID: An-Ultra-Low-Power-TinyML-System-for-Real-Time-Visual-Processing-at-Edge

TinyML classification: Strict TinyML — explicitly targets MCU-based TinyML deployment with STM32L4R9 + NCP, 477KB model weights, on-chip SRAM, 160mW power, and 30FPS visual inference.

Basic Info

Authors: Kunran Xu, Huawei Zhang, Yishi Li, Yuhao Zhang, Rui Lai, Yi Liu

Year: 2023

Title: An Ultra-Low Power TinyML System for Real-Time Visual Processing at Edge

Source: IEEE Transactions on Circuits and Systems II: Express Briefs

Type: Experimental

Problem & Context

Task: Classification and object detection

Objective: Develop an ultra-low-power TinyML system for real-time visual processing at the edge.

Application domain: AIoT / IoT visual processing

Scenario: Edge, embedded, MCU-based TinyML

TinyML relevance: Yes

TinyML justification: The paper explicitly targets resource- and power-constrained TinyML systems using an MCU interconnected with a neural co-processor, on-chip memory, and ultra-low-power visual inference. 

Model / Method

Model: EtinyNet + neural co-processor system

Architecture family: CNN

Techniques: Parameter-efficient CNN backbone, Linear Depthwise Block, Dense Linear Depthwise Block, ASIC-based neural co-processor, application-specific instruction set, on-chip memory execution, tensor layout conversion

Framework: Custom application-specific instruction set for NCP

Training type: Not reported

Inference type: On-device

Hardware

Device: STM32L4R9 MCU + proposed neural co-processor

Hardware type: MCU + NPU / ASIC neural co-processor

Processor / microcontroller: STM32L4R9 MCU; proposed NCP implemented in TSMC 65 nm low-power technology

Clock frequency: STM32L4R9 at 120 MHz; NCP maximum frequency 250 MHz

SRAM / RAM: 992 KB on-chip SRAM in NCP; maximum feature map size 128 KB

Flash / ROM / Storage: Not reported

Power consumption: 160 mW for full system; 73.6 mW for NCP

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, compute, off-chip memory access, data transfer

Dataset

Name: ImageNet-1000; Pascal VOC

Type: Public

Dataset size: Not reported

Number of classes: 1000 for ImageNet-1000; not reported for Pascal VOC

Input resolution: 256 × 256 RGB image

Data modality: RGB image

Metrics

Accuracy: 66.5% ImageNet Top-1; 86.8% ImageNet Top-5

mAP: 56.4% on Pascal VOC object detection

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 5.5 ms on NCP

FPS: 30 FPS full system; up to 180 FPS on NCP

Throughput: 264 GOP/s peak performance; 449.1 Frames/s/mJ processing efficiency

Model size: 477 KB model weights

Parameters: 477K backbone parameters; 989K total parameters

MACs / FLOPs: Not reported

RAM usage: 992 KB on-chip SRAM; maximum feature map size 128 KB

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 160 mW full system; 73.6 mW NCP

Optimization

Techniques used: EtinyNet parameter-efficient architecture, neural co-processor acceleration, application-specific instruction set, on-chip SRAM storage, tensor layout conversion, int8 convolution hardware

Quantization: INT8 convolution / depthwise convolution with float32 batch normalization

Pruning: No

Knowledge distillation: No

Compression method: Parameter-efficient CNN architecture

Hardware-specific optimization: Yes; ASIC NCP, neural operation units, tensor memory layout, layout conversion circuit, SDIO/SPI MCU interface

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: 992 KB on-chip SRAM; maximum feature map size 128 KB

Flash usage reported: Not reported

Model size reported: 477 KB model weights

Energy per inference reported: Not reported

Latency on target device reported: 5.5 ms on NCP; 30 FPS full system

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Only MCU-NCP communication via SDIO/SPI; no cloud or off-device communication reported

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets MCU-based TinyML deployment with STM32L4R9 + NCP, on-chip memory, 477 KB model weights, 160 mW power consumption, and real-time visual inference.

Benchmarking / Standardization

Benchmark used: ImageNet-1000 classification; Pascal VOC object detection

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet-1000; Pascal VOC

Comparison with baseline models: Yes; MobileNetV2, MobileNeXt, ShuffleNetV2, MCUNet, MCUNetV2

Comparison with previous works: Yes; NullHop, ConvAix, YodaNN, Vega, CMSIS-NN, MCUNet

Reproducibility artifacts available: Not reported

Results

Summary: EtinyNet achieves 66.5% ImageNet Top-1 accuracy with 477 KB weights. The full STM32L4R9 + NCP system achieves 30 FPS visual processing at 160 mW, while the NCP reaches 5.5 ms latency and 73.6 mW power.

Limitations

Not reported

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

This paper proposes an ultra-low-power TinyML visual processing system combining the EtinyNet CNN backbone, an ASIC-based neural co-processor, and an application-specific instruction set for real-time MCU-class edge inference.

| Paper     | Year | Task                             | Model    | Technique                                                   | Device          | Dataset                   | Main Metric            | Latency | Model Size | SRAM/RAM            | Flash | Energy | Framework                  | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | -------------------------------- | -------- | ----------------------------------------------------------- | --------------- | ------------------------- | ---------------------- | ------- | ---------- | ------------------- | ----- | ------ | -------------------------- | -------- | ------------- | ------------- |
| Xu et al. | 2023 | Classification; Object Detection | EtinyNet | Parameter-efficient CNN + ASIC NCP + custom instruction set | STM32L4R9 + NCP | ImageNet-1000; Pascal VOC | 66.5% Top-1; 56.4% mAP | 5.5 ms  | 477 KB     | 992 KB on-chip SRAM | N/A   | N/A    | Custom NCP instruction set | INT8     | None          | Yes           |
