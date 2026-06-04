Paper ID: HARP-UNET-A-Hardware-Accelerated-TinyML-Framework-for-Pothole-Segmentation-and-Road-Quality-Assessment-Using-UAVs

TinyML classification: Near-TinyML — it targets embedded edge vision hardware, but deployment is on Kria KV260 and Jetson Nano rather than explicit MCU-class platforms.

Basic Info

Authors: Anubhav Elhence, Harshil Jeswani, Vinay Chamola

Year: 2025

Title: HARP-UNET: A Hardware-Accelerated TinyML Framework for Pothole Segmentation and Road Quality Assessment Using UAVs

Source: IEEE Transactions on Intelligent Transportation Systems 

Type: Experimental

Problem & Context

Task: Segmentation

Objective: Real-time pothole segmentation from UAV imagery with road quality assessment and geotagging.

Application domain: Intelligent transportation systems and road infrastructure maintenance.

Scenario: UAV-based embedded edge deployment.

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained embedded UAV deployment using lightweight model design, INT8 quantization, pruning, and hardware acceleration, but does not report MCU-class deployment.

Model / Method

Model: HARP-UNET

Architecture family: Hybrid CNN

Techniques: Depthwise separable convolutions, residual connections, multi-scale channel attention gates, INT8 quantization, pruning, hardware acceleration.

Framework: PyTorch, Vitis AI, NVIDIA TensorRT

Training type: Not reported

Inference type: On-device

Hardware

Device: Kria KV260 and NVIDIA Jetson Nano

Hardware type: FPGA / SoC / GPU

Processor / microcontroller: Kria KV260 with Xilinx Zynq UltraScale+ MPSoC, quad-core ARM Cortex-A53, and 256k system logic cells; NVIDIA Jetson Nano with quad-core ARM Cortex-A57 CPU and 128-core NVIDIA Maxwell GPU.

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: KV260: 9.72 W single-core and 10.44 W dual-core in Table IV; Jetson Nano: 8.60 W.

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Compute, memory footprint, power, energy efficiency, real-time latency, communication, and storage.

Dataset

Name: Kaggle Pothole Detection Dataset and custom UAV pothole dataset

Type: Public + private

Dataset size: Kaggle dataset: 780 images; custom UAV dataset: 1,000 images.

Number of classes: 3 reported for custom dataset: road, pothole, and background.

Input resolution: 640 × 640 pixels for preprocessed Kaggle images.

Data modality: RGB image

Metrics

Accuracy: 99.40%

mAP: Not reported

Precision: 0.856

Recall: 0.881

F1-score: Not reported; Dice Similarity Coefficient: 0.850

Latency: Not reported

FPS: 64 FPS on Kria KV260 dual-core, 33 FPS on Kria KV260 single-core, and 21 FPS on NVIDIA Jetson Nano.

Throughput: Not reported

Model size: Not reported in MB

Parameters: 4.8 M

MACs / FLOPs: Not reported

RAM usage: KV260 BRAM/URAM utilization: 18/144 BRAM and 36/64 URAM for 1-core; 52/144 BRAM and 64/64 URAM for 2-core.

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: KV260: 9.72 W single-core and 10.44 W dual-core in Table IV; Jetson Nano: 8.60 W.

Optimization

Techniques used: Depthwise separable convolutions, multi-scale channel attention gates, residual connections, INT8 quantization, magnitude-based pruning, Vitis AI compilation, and TensorRT optimization.

Quantization: INT8

Pruning: Yes

Knowledge distillation: Not reported

Compression method: INT8 quantization and magnitude-based pruning.

Hardware-specific optimization: Vitis AI for Kria KV260 and NVIDIA TensorRT for Jetson Nano.

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: No

Model size reported: Parameters reported; model size in MB not reported.

Energy per inference reported: No

Latency on target device reported: FPS reported; latency in milliseconds not reported.

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment uses Kria KV260 and NVIDIA Jetson Nano embedded edge platforms, with no explicit MCU-class device, TensorFlow Lite Micro deployment, SRAM/Flash footprint, or bare-metal/RTOS evidence.

Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, compared with MobileNetV2-Seg, Res-UNet, UNet, EfficientNet-B0-Seg, DAU-FI Net, Attention U-Net, and Res-UNet++.

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: HARP-UNET reports mean IoU of 84.1% and accuracy of 99.40% for pothole segmentation. It achieves real-time embedded performance with up to 64 FPS on Kria KV260 and 21 FPS on NVIDIA Jetson Nano.

Limitations

The paper reports increased measurement errors at higher UAV altitudes and systematic underestimation of pothole areas due to irregular geometries. It also states that overlapping potholes and significant shadow effects are underrepresented in the dataset.

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

This paper proposes HARP-UNET, a hardware-accelerated lightweight U-Net-based framework for real-time UAV pothole segmentation and road quality assessment on embedded edge devices.

| Elhence et al. | 2025 | Segmentation | HARP-UNET | DSConv + MSCAG + INT8 quantization + pruning | Kria KV260; NVIDIA Jetson Nano | Kaggle Pothole Detection Dataset + custom UAV dataset | mIoU 84.1%; Accuracy 99.40% | N/A | 4.8M parameters | KV260 BRAM/URAM utilization reported | N/A | N/A | PyTorch; Vitis AI; TensorRT | INT8 | None | No |
