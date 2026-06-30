Paper ID: On-Orbit-AI-Cloud-Detection-Technique-for-Resource-Limited-Nanosatellite

Basic Info

Authors: Jin-Hyung Kim; Yongwoo Kim; Dong-Hyun Cho; Seong-Min Kim

Year: 2025

Title: On-Orbit AI: Cloud Detection Technique for Resource-Limited Nanosatellite

Source: International Journal of Aeronautical and Space Sciences, 26:1975–1988 

Type: Experimental

Problem & Context

Task: Segmentation / cloud detection / image classification

Objective: Develop and validate an onboard cloud detection and image-prioritization method for resource-limited nanosatellites.

Application domain: Earth-observation nanosatellites

Scenario: Embedded onboard processing / nanosatellite / edge AI

TinyML relevance: Partial

TinyML justification: The paper targets resource-limited onboard inference with power, compute, memory, and communication constraints, but deployment is on a Xilinx Zynq-7000 SoC/FPGA OBC rather than an MCU-class TinyML platform.

Model / Method

Model: Multi-phase cloud detection pipeline with image uniformity check, TriCloudNet classifier, and pruned U-Net segmentation model

Architecture family: CNN

Techniques: Network pruning, quantization, model compression, multi-stage filtering, FPGA-based hardware acceleration, image downsampling

Framework: PyTorch, libtorch C++ interface, OpenCV, Xilinx HLS, Vivado, PetaLinux, SDK

Training type: Not reported

Inference type: On-device

Hardware

Device: Space-proven onboard computer based on Xilinx Zynq-7000 / Zynq-7020 SoC; Nvidia Jetson Nano used for comparison

Hardware type: SoC / FPGA

Processor / microcontroller: Dual-core ARM Cortex-A9 CPU with programmable logic area

Clock frequency: Up to 666 MHz; configured to 200 MHz for the mission

SRAM / RAM: 256 MB DDR SDRAM with EDAC on OBC; ZC702 comparison platform reports 1 GB DDR3

Flash / ROM / Storage: Not reported

Power consumption: HW accelerator idle 187 mW; accelerator FPGA on 196 mW; 6U CubeSat power budget stated as approximately 20–30 W 

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Limited onboard computational power, limited memory, limited power, FPGA resources, communication bandwidth, latency, real-time onboard processing

Dataset

Name: SPARCS validation dataset; Landsat 8 Cloud Cover Assessment validation dataset

Type: Public

Dataset size: 80 SPARCS image patches and 1,330 Landsat 8 CCA image patches; total 1,410 image patches

Number of classes: 2 for U-Net cloud/non-cloud segmentation; 3 for TriCloudNet clear/partial cloud/overcast classification

Input resolution: 96 × 96 pixels

Data modality: RGB satellite image patches

Metrics

Accuracy: Not reported

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: OBC hardware-accelerated total inference time 1025 ms per image; TriCloudNet 92 ms; U-Net 933 ms; OBC software-only total 6368 ms; Jetson Nano Mode 0 total 1180 ms; Jetson Nano Mode 1 total 1800 ms 

FPS: Not reported

Throughput: Not reported

Model size: Baseline 264.40 MB; pruned 12.29 MB; hardware-accelerated 3.61 MB 

Parameters: Baseline 29 M; pruned 6 K; hardware-accelerated 2 K 

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: HW accelerator idle 187 mW; accelerator FPGA on 196 mW; single-stage processing 510 mWh; multi-stage processing 263 mWh for 1,410 images 

Optimization

Techniques used: Network pruning, quantization, multi-stage filtering, custom FPGA hardware acceleration, model-size reduction, input downsampling

Quantization: Not reported

Pruning: Yes

Knowledge distillation: No

Compression method: U-Net pruning reduced model size from 264.40 MB to 12.29 MB; hardware-accelerated implementation reported 3.61 MB model size

Hardware-specific optimization: Custom FPGA-based accelerator synthesized with HLS and implemented with Vivado/PetaLinux; TriCloudNet and U-Net configured as separate hardware accelerators

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes

Energy per inference reported: No

Latency on target device reported: Yes

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: No

Reason: The paper reports onboard inference on a Xilinx Zynq SoC/FPGA platform with DDR memory and PetaLinux rather than an MCU-class, Cortex-M, bare-metal, RTOS, TensorFlow Lite Micro, or CMSIS-NN deployment.

Benchmarking / Standardization

Benchmark used: SPARCS validation dataset and Landsat 8 CCA validation dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: SPARCS; Landsat 8 CCA

Comparison with baseline models: Yes

Comparison with previous works: Not reported

Reproducibility artifacts available: Dataset

Results

Summary: The hardware-accelerated OBC implementation achieved 1025 ms total inference time per 96 × 96 image and a 6.21× speedup over OBC software-only inference. The multi-stage pipeline reduced processing time and power by 48.7%, and onboard cloud detection reduced downlink data volume by 40–50%. 

Limitations

The implementation is optimized for a specific Xilinx Zynq-based OBC platform; TriCloudNet misclassified 10 out of 80 SPARCS validation images; the hardware-accelerated model has lower cloud coverage accuracy than the pruned software model.

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

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a multi-phase onboard cloud detection and image-prioritization pipeline combining TriCloudNet, pruned U-Net, and FPGA acceleration for resource-limited nanosatellite Earth-observation missions.

| Paper      | Year | Task                           | Model                      | Technique                                  | Device                               | Dataset                | Main Metric | Latency | Model Size | SRAM/RAM         | Flash | Energy                             | Framework                               | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | ------------------------------ | -------------------------- | ------------------------------------------ | ------------------------------------ | ---------------------- | ----------- | ------- | ---------- | ---------------- | ----- | ---------------------------------- | --------------------------------------- | -------- | ------------- | ------------- |
| Kim et al. | 2025 | Cloud detection / segmentation | TriCloudNet + pruned U-Net | Pruning + quantization + FPGA acceleration | Xilinx Zynq-7000 / Zynq-7020 SoC OBC | SPARCS + Landsat 8 CCA | CRE 6.84%   | 1025 ms | 3.61 MB    | 256 MB DDR SDRAM | N/A   | 263 mWh multi-stage / 1,410 images | PyTorch/libtorch + HLS/Vivado/PetaLinux | N/A      | None          | No            |
