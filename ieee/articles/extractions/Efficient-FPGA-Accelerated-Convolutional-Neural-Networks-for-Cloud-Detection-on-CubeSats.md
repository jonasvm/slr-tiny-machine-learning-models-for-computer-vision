Paper ID: Efficient-FPGA-Accelerated-Convolutional-Neural-Networks-for-Cloud-Detection-on-CubeSats

TinyML classification: Near-TinyML — Uses FPGA/Zynq UltraScale+ MPSoC edge hardware for low-power onboard vision, but not MCU-class deployment.

Basic Info

Authors: Angela Cratere; M. Salim Farissi; Andrea Carbone; Marcello Asciolla; Maria Rizzi; Francesco Dell’Olio; Augusto Nascetti; Dario Spiller

Year: 2025

Title: Efficient FPGA-Accelerated Convolutional Neural Networks for Cloud Detection on CubeSats

Source: IEEE Journal on Miniaturization for Air and Space Systems 

Type: Experimental

Problem & Context

Task: Classification and segmentation

Objective: Implement and evaluate four FPGA-accelerated CNN models for onboard CubeSat cloud detection, comparing accuracy, latency, model complexity, and power consumption.

Application domain: Earth observation cloud detection on CubeSats

Scenario: Onboard embedded edge inference for resource-constrained CubeSat missions

TinyML relevance: Yes

TinyML justification: The paper targets low-power, resource-constrained, fully onboard inference using FPGA/DPU acceleration, pruning, INT8 quantization, latency, and power evaluation, but not MCU-class deployment.

Model / Method

Model: Pixel-Net; Kernel-Net; U-Net; Patch-Net

Architecture family: CNN

Techniques: Channel pruning; INT8 quantization; quantization-aware training; FPGA/DPU deployment; data augmentation for Patch-Net

Framework: TensorFlow; Xilinx Vitis AI; PYNQ

Training type: From scratch

Inference type: On-device

Hardware

Device: Avnet Ultra96-V2 board with Xilinx Zynq UltraScale+ MPSoC and DPUCZDX8G DPU B1600 architecture

Hardware type: FPGA / SoC

Processor / microcontroller: Xilinx Zynq UltraScale+ MPSoC with DPUCZDX8G IP core

Clock frequency: Not reported

SRAM / RAM: 2 GB RAM on Ultra96-V2 board

Flash / ROM / Storage: Not reported

Power consumption: Pixel-Net 2.4 W; Kernel-Net 2.5 W; U-Net 2.4 W; Patch-Net 2.5 W after pruning

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: DPU buffer memory, 2 GB RAM limit, model complexity, latency, power consumption, compute, onboard storage, downlink bandwidth

Dataset

Name: Sentinel-2 Level-2A products

Type: Not reported

Dataset size: 16 Sentinel-2 scenes; 10 scenes for training/validation; 6 scenes for test; Pixel-Net test set of 240,000 pixels; Patch-Net and U-Net test subset of 500 tiles; training/validation tile dataset of 4,231 tiles

Number of classes: 2

Input resolution: Pixel-Net 1 × 1 × 12; Kernel-Net 5 × 5 × 12; Patch-Net and U-Net 256 × 256 × 12

Data modality: Multispectral satellite imagery with 12 spectral bands

Metrics

Accuracy: Pixel-Net 95.71%; Kernel-Net 97.42%; U-Net 98.04%; Patch-Net 98.4% after pruning and INT8 FPGA deployment

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Pixel-Net 0.30 ms/px; Kernel-Net 0.31 ms/px; U-Net 26.7 ms/tile; Patch-Net 17.5 ms/tile after pruning

FPS: Pixel-Net 0.051; Kernel-Net 0.049; U-Net 37.45; Patch-Net 57.14 after pruning

Throughput: Patch-Net 57.14 FPS; U-Net 37.45 FPS after pruning

Model size: Not reported

Parameters: Pixel-Net 17.43K; Kernel-Net 13.00K; U-Net 26.62K; Patch-Net 3.32M after pruning

MACs / FLOPs: Pixel-Net 84.67K; Kernel-Net 380.94K; U-Net 579.60M; Patch-Net 338.76M after pruning

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Pixel-Net 2.4 W; Kernel-Net 2.5 W; U-Net 2.4 W; Patch-Net 2.5 W after pruning

Optimization

Techniques used: Channel pruning; quantization-aware INT8 quantization; Vitis AI compilation; DPU deployment

Quantization: INT8 / QAT

Pruning: Yes

Knowledge distillation: Not reported

Compression method: Structured channel pruning and INT8 quantization

Hardware-specific optimization: Yes, models were adapted and compiled for Xilinx Vitis AI DPU deployment on FPGA/SoC hardware

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Parameters and FLOPs reported; storage model size not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: No

Reason: The paper uses FPGA/Zynq UltraScale+ MPSoC edge hardware with DPU acceleration, not MCU-class or bare-metal/RTOS TinyML deployment.

Benchmarking / Standardization

Benchmark used: Custom Sentinel-2 onboard cloud detection evaluation

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, baseline float32 models were compared against pruned INT8 FPGA-deployed versions

Comparison with previous works: Yes, compared with CloudScout, UNet-CloudScout, FPGA-CloudScout, and CloudSatNet-1

Reproducibility artifacts available: Not reported

Results

Summary: The pruned INT8 FPGA-deployed models retained high accuracy, with Patch-Net reaching 98.4% accuracy at 57.14 FPS and U-Net reaching 98.04% accuracy at 37.45 FPS. Channel pruning reduced parameters by up to 98.6% and FLOPs by up to 90.7%, while power consumption remained around 2.4–2.5 W after pruning.

Limitations

Pixel-wise models had impractically high latency for full-image segmentation. The tested SoC board supported only a single DPU core and did not allow concurrent processing of multiple patches. Image-level models require substantial training datasets.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes FPGA-accelerated DPU deployment of four CNN architectures for real-time onboard CubeSat cloud detection using channel pruning and INT8 quantization.

| Paper          | Year | Task                                            | Model                                   | Technique                  | Device                                                  | Dataset                                   | Main Metric    | Latency | Model Size       | SRAM/RAM | Flash | Energy | Framework                    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | ----------------------------------------------- | --------------------------------------- | -------------------------- | ------------------------------------------------------- | ----------------------------------------- | -------------- | ------- | ---------------- | -------- | ----- | ------ | ---------------------------- | -------- | ------------- | ------------- |
| Cratere et al. | 2025 | Cloud detection classification and segmentation | Pixel-Net; Kernel-Net; U-Net; Patch-Net | Channel pruning + INT8 QAT | Avnet Ultra96-V2 with Xilinx Zynq UltraScale+ MPSoC DPU | Sentinel-2 Level-2A multispectral imagery | 98.4% accuracy | 17.5 ms | 3.32M parameters | 2 GB RAM | N/A   | N/A    | TensorFlow + Vitis AI + PYNQ | QAT      | None          | No            |
