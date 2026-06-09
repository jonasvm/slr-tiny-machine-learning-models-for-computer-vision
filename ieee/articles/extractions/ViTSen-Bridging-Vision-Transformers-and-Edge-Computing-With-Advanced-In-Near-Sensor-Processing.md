Paper ID: ViTSen-Bridging-Vision-Transformers-and-Edge-Computing-With-Advanced-In-Near-Sensor-Processing

TinyML classification: Near-TinyML — The paper targets resource-constrained IoT devices and evaluates image classification, object detection, and segmentation, but experiments are GPU-based and MCU-level deployment is not shown.

Basic Info

Authors: Sepehr Tabrizchi; Brendan C. Reidy; Deniz Najafi; Shaahin Angizi; Ramtin Zand; Arman Roohi

Year: 2024

Title: ViTSen: Bridging Vision Transformers and Edge Computing With Advanced In/Near-Sensor Processing

Source: IEEE Embedded Systems Letters, Vol. 16, No. 4, December 2024 

Type: Methodological

Problem & Context

Task: Classification

Objective: Optimize vision transformers for resource-constrained edge vision using in-sensor image compression and near-sensor analog convolution.

Application domain: IoT visual sensing and edge image processing

Scenario: Edge, embedded, IoT, in-sensor processing, near-sensor processing

TinyML relevance: Partial

TinyML justification: The paper targets low-power edge/IoT vision and resource-constrained image sensors, but does not report MCU-class deployment, SRAM/Flash constraints, TensorFlow Lite Micro, or fully on-device MCU inference.

Model / Method

Model: ViTSen with ViT, DeiT, and DINOv2 variants; performance evaluation focuses on DeiT-T16

Architecture family: ViT

Techniques: In-sensor RGB-to-grayscale compression; near-sensor analog convolution; ReRAM crossbar; quantization; color channel reduction; hardware/software co-design; analog positional encoding

Framework: PyTorch; Verilog-A; HSPICE; Python-based behavioral model

Training type: Pretrained/fine-tuned ViT models, DeiT trained on ImageNet-1k, and DINOv2 self-supervised pretraining with fine-tuning

Inference type: Hybrid

Hardware

Device: ViTSen integrated in/near-sensor processing engine

Hardware type: Other

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: On-chip storage for weights and positional encoding reported, but capacity not reported

Power consumption: 1370 mW

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: No

Constraints mentioned: Power, latency, data transmission, data movement, ADC overhead, memory bottlenecks, compute cost

Dataset

Name: ImageNet-1k

Type: Public

Dataset size: Not reported

Number of classes: 1k

Input resolution: 224 × 224

Data modality: RGB images and grayscale-converted images

Metrics

Accuracy: Top-1 ImageNet-1k accuracy; DeiT-T/16 RGB FP 68.6%, W8 67.1%, W6 57.0%, W4 17.1%; DeiT-T/16 grayscale FP 56.0%, W8 52.8%, W6 36.7%, W4 6.0%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: 5M parameters for DeiT-T16

MACs / FLOPs: Approximately 19.5M operations performed close to the sensor

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 1370 mW

Optimization

Techniques used: Post-training quantization; in-sensor RGB-to-grayscale compression; ReRAM-based near-sensor analog convolution; reduced ADC use; hardware-aware ViT embedding adaptation

Quantization: PTQ

Pruning: No

Knowledge distillation: No

Compression method: RGB-to-grayscale in-sensor compression and reduced ADC output bandwidth/storage

Hardware-specific optimization: ReRAM crossbar, integrated ADCs, optimized pixel read circuitry, analog positional encoding, near-sensor convolution

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: No; only 5M parameters are reported for DeiT-T16

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: No

Communication required during inference: Off-chip processing is used for transformer components; cloud communication is not reported

Candidate for Strict TinyML: No

Reason: The work targets edge/IoT in-sensor and near-sensor processing but does not provide MCU-class deployment, SRAM/Flash usage, TFLM/CMSIS-NN implementation, or fully on-device inference evidence.

Benchmarking / Standardization

Benchmark used: ImageNet-1k Top-1 accuracy

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet-1k

Comparison with baseline models: Yes; full-precision models are compared with quantized and grayscale variants

Comparison with previous works: Yes; Table II compares ViTSen with prior NSP/ISP units

Reproducibility artifacts available: Not reported

Results

Summary: ViTSen achieves comparable accuracy to full-precision baselines under selected quantization settings and reports approximately 3.1 TOp/s/W efficiency. For DeiT-T16, 8-bit RGB quantization gives 67.1% Top-1 accuracy versus 68.6% full precision.

Limitations

The paper reports that only the embedding layer is processed close to the sensor while other transformer components are processed off-chip. It also reports relatively high power consumption for ViTSen and substantial accuracy degradation under 4-bit quantization.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an in/near-sensor ViT hardware/software co-design that combines RGB-to-grayscale in-sensor compression, ReRAM-based analog convolution, quantized embedding computation, and analog positional encoding for resource-constrained edge vision.

| Paper            | Year | Task           | Model             | Technique                                                        | Device                                   | Dataset     | Main Metric                                   | Latency | Model Size    | SRAM/RAM | Flash | Energy | Framework                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---: | -------------- | ----------------- | ---------------------------------------------------------------- | ---------------------------------------- | ----------- | --------------------------------------------- | ------- | ------------- | -------- | ----- | ------ | ------------------------- | -------- | ------------- | ------------- |
| Tabrizchi et al. | 2024 | Classification | ViTSen / DeiT-T16 | In/near-sensor compression and ReRAM analog convolution with PTQ | ViTSen 45-nm ReRAM in/near-sensor engine | ImageNet-1k | 67.1% Top-1 for DeiT-T/16 RGB W8; 3.1 TOp/s/W | N/A     | 5M parameters | N/A      | N/A   | N/A    | PyTorch / HSPICE / Python | PTQ      | None          | No            |
