Paper ID: Improved-Lightweight-YOLOv8-With-DSConv-and-Reparameterization-for-Continuous-Casting-Slab-Detection-on-Embedded-Device 

TinyML classification: Near-TinyML — The deployment target is Jetson Orin NX embedded GPU hardware, with no explicit MCU-class deployment.

Basic Info

Authors: Hao Ju; Yiming Fang; Hongliang Yang; Fengfei Si; Kesong Kang.

Year: 2025.

Title: Improved Lightweight YOLOv8 With DSConv and Reparameterization for Continuous Casting Slab Detection on Embedded Device.

Source: IEEE Transactions on Instrumentation and Measurement, Vol. 74, 2025, Article 5003712.

Type: Experimental.

Problem & Context

Task: Object Detection.

Objective: Real-time detection of slabs transmitted on roller tables for embedded deployment.

Application domain: Steel industry; continuous casting and rolling processes.

Scenario: Embedded edge industrial monitoring.

TinyML relevance: Partial.

TinyML justification: The paper targets embedded edge object detection with lightweight design, pruning, INT8 quantization, TensorRT deployment, latency/FPS, parameters, FLOPs, and model size, but deployment is on Jetson Orin NX rather than MCU-class hardware.

Model / Method

Model: DSCLERC-YOLOv8.

Architecture family: CNN.

Techniques: DSConv, C2f_DSConv, Lightweight Efficient-RepGFPN, CARAFE, reparameterization, depth-wise separable convolution, reduced P4 network structure, pruning, INT8 quantization, TensorRT optimization.

Framework: PyTorch for training; TensorRT for deployment.

Training type: From scratch; fine-tuning after pruning.

Inference type: On-device.

Hardware

Device: Jetson Orin NX.

Hardware type: SoC / GPU.

Processor / microcontroller: 2 GHz 8-core ARM Cortex-A78AE v8.2 64-bit CPU and 1024-core NVIDIA Ampere GPU.

Clock frequency: 2 GHz CPU.

SRAM / RAM: 16 GB LPDDR5.

Flash / ROM / Storage: Not reported.

Power consumption: Not reported.

Energy per inference: Not reported.

Execution without full OS: Not reported.

Fully on-device inference: Yes.

Constraints mentioned: Memory, power, latency, compute, model size, network transmission delay, deployment cost, real-time speed.

Dataset

Name: Custom continuous casting slab dataset; VOC2012.

Type: Private for slab dataset; public for VOC2012.

Dataset size: Slab dataset: 75,144 images; labels: 122,642 slab, 23,837 crane, 29,874 craneandslab; optimized from 323.3 GB to 37.0 GB.

Number of classes: 3 for slab dataset: slab, crane, craneandslab.

Input resolution: Original images are 1920 × 1080; network input is 640 × 640.

Data modality: Industrial camera images and real-time slab video.

Metrics

Accuracy: Not reported separately; object detection performance is reported using mAP.

mAP: Slab dataset: mAP@50 = 98.66%, mAP@50:95 = 86.91%; VOC2012: mAP@50 = 64.03%, mAP@50:95 = 43.95%.

Precision: 97.45% average on six slab datasets.

Recall: 98.21% average on six slab datasets.

F1-score: 97.93% average on six slab datasets; 97.82% in algorithm comparison on slab dataset; 62.87% on VOC2012.

Latency: 7.53 ms average on six slab datasets; 6.87 ms in algorithm comparison; 5.30 ms after pruning on 3_2 slab dataset.

FPS: 128 FPS in algorithm comparison; 76 FPS on Jetson Orin NX after pruning, quantization, and TensorRT deployment.

Throughput: 128 FPS in algorithm comparison; 76 FPS on target embedded device.

Model size: 2.3 MB.

Parameters: 0.72M before pruning; 0.36M after pruning.

MACs / FLOPs: 3.0 GFLOPs before pruning; 1.5 GFLOPs after pruning; MACs reduced by 48.2% after pruning.

RAM usage: Not reported.

Flash usage: Not reported.

Energy per inference: Not reported.

Power consumption: Not reported.

Optimization

Techniques used: Lightweight YOLOv8 redesign with DSConv, C2f_DSConv, Lightweight Efficient-RepGFPN, CARAFE, reduced P4 structure, pruning, INT8 quantization, and TensorRT deployment.

Quantization: INT8.

Pruning: Yes.

Knowledge distillation: No.

Compression method: Model pruning, INT8 quantization, reduced network stages, lightweight convolutions.

Hardware-specific optimization: TensorRT engine for Jetson Orin NX.

Use of CMSIS-NN: No.

Use of TensorFlow Lite Micro: No.

Use of MLPerf Tiny: No.

Strict TinyML Evidence

SRAM peak reported: Not reported.

Flash usage reported: Not reported.

Model size reported: 2.3 MB before pruning; post-pruning model size not reported.

Energy per inference reported: Not reported.

Latency on target device reported: FPS reported on Jetson Orin NX; target-device latency in ms not reported.

Runs without full operating system: Not reported.

Fully on-device inference: Yes.

Communication required during inference: Not reported.

Candidate for Strict TinyML: No.

Reason: The deployment target is Jetson Orin NX with 16 GB LPDDR5 and embedded GPU acceleration, not MCU-class hardware, bare-metal/RTOS deployment, or TensorFlow Lite Micro.

Benchmarking / Standardization

Benchmark used: Custom slab dataset; VOC2012.

MLPerf Tiny mentioned: No.

Visual Wake Words mentioned: No.

Other standard benchmark: VOC2012.

Comparison with baseline models: YOLOv8n, SSD, YOLOv5n, YOLOv6n, YOLOv7-tiny, ShuffleNetv2-YOLOv8, GhostNetv2-YOLOv8, VAAB-YOLOv5.

Comparison with previous works: Yes.

Reproducibility artifacts available: Not reported.

Results

Summary: DSCLERC-YOLOv8 achieved 86.91% mAP@50:95 on the slab dataset with 0.72M parameters, 3.0 GFLOPs, 2.3 MB model size, 6.87 ms latency, and 128 FPS in comparison experiments. After pruning, INT8 quantization, and TensorRT deployment, it reached 76 FPS on Jetson Orin NX. 

Limitations: The experiments are mainly based on the slab dataset; the P4 network may be less effective for other small targets or specific environments; deployment validation was limited to Jetson Orin NX.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes.

Reports memory usage: No.

Reports latency: Yes.

Reports energy or power: No.

Reports model size: Yes.

Reports optimization method: Yes.

Reports deployment framework: Yes.

Reports dataset and preprocessing: Yes.

Reports evaluation metric clearly: Yes.

Reports reproducibility artifacts: No.

Contribution

This paper proposes DSCLERC-YOLOv8, a lightweight YOLOv8-based object detector using DSConv, reparameterized feature fusion, CARAFE, pruning, INT8 quantization, and TensorRT deployment for real-time slab detection on embedded edge hardware.

| Ju et al. | 2025 | Object Detection | DSCLERC-YOLOv8 | DSConv + reparameterization + pruning + INT8 TensorRT | Jetson Orin NX | Custom slab dataset; VOC2012 | mAP@50:95 = 86.91% | 6.87 ms; 76 FPS on target | 2.3 MB | 16 GB LPDDR5 device RAM; runtime RAM N/A | N/A | N/A | PyTorch; TensorRT | INT8 | None | No |
