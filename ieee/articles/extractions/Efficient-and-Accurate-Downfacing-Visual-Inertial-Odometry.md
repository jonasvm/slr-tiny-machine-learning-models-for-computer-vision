Paper ID: Efficient-and-Accurate-Downfacing-Visual-Inertial-Odometry

TinyML classification: Strict TinyML — It explicitly targets microcontroller-class/resource-constrained ultralow-power embedded deployment with reported memory, latency, and power constraints.

Basic Info

Authors: Jonas Kühne; Christian Vogt; Michele Magno; Luca Benini

Year: 2025

Title: Efficient and Accurate Downfacing Visual–Inertial Odometry

Source: IEEE Internet of Things Journal, Vol. 12, No. 22 

Type: Experimental

Problem & Context

Task: Visual–inertial odometry / feature tracking

Objective: Improve downfacing VIO accuracy and efficiency for resource-constrained micro- and nano-UAV platforms.

Application domain: Micro- and nano-UAV navigation

Scenario: Embedded, ultralow-power SoC, resource-constrained UAV

TinyML relevance: Yes

TinyML justification: The pipeline is optimized, quantized, parallelized, and deployed on the GAP9 ultralow-power RISC-V SoC for microcontroller-class/resource-constrained VIO.

Model / Method

Model: Downfacing VIO pipeline with PX4FLOW, ORB, and SuperPoint feature trackers plus rigid-body motion estimation and extended Kalman filtering

Architecture family: Other

Techniques: Quantization, fixed-point arithmetic, integer representation, parallelization, hardware-aware optimization, outlier rejection

Framework: GreenWaves Technologies SDK NNTool for SuperPoint quantization/deployment

Training type: Not reported

Inference type: On-device

Hardware

Device: GAP9 low-power SoC

Hardware type: SoC

Processor / microcontroller: 10-core RISC-V GAP9 SoC with nine-core compute cluster and fabric controller

Clock frequency: Up to 370 MHz

SRAM / RAM: 128 kB L1 shared memory; 1.5 MB interleaved L2 memory

Flash / ROM / Storage: Off-chip L3 memory used for SuperPoint; Flash/ROM not reported

Power consumption: 64–68 mW at 370 MHz using the nine-core compute cluster; 35–45 mW estimated when using two cluster cores

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, compute load, real-time processing, low-power deployment

Dataset

Name: Custom indoor and outdoor VIO benchmarking dataset

Type: Private/custom recorded dataset

Dataset size: 7 indoor sequences and 5 outdoor sequences

Number of classes: N/A

Input resolution: QQVGA 160 × 120

Data modality: Camera + IMU + ToF sensor; Vicon MoCap and GPS-RTK ground truth

Metrics

Accuracy: RMSE and relative translation error; ORB pipeline reports up to 3.65× RMSE reduction over baseline

mAP: N/A

Precision: N/A

Recall: N/A

F1-score: N/A

Latency: PX4FLOW ≈0.82 ms; ORB ≈8.44 ms; SuperPoint ≈84.03 ms, derived from reported maximum FPS at 370 MHz

FPS: PX4FLOW 1216.3 FPS; ORB 118.5 FPS; SuperPoint 11.9 FPS

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: SuperPoint does not fit fully into L1/L2 and is partially stored in off-chip L3 memory; peak RAM not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 64–68 mW at 370 MHz; 35–45 mW estimated for two-core PX4FLOW operation

Optimization

Techniques used: Low-precision integer representation, INT8 quantization, fixed-point logic, multicore parallelization, rigid-body motion estimation, outlier rejection, Kalman filtering

Quantization: INT8 for SuperPoint activations and weights; low-precision integer/fixed-point representations for ORB and PX4FLOW

Pruning: No

Knowledge distillation: No

Compression method: Quantization and fixed-point/integer implementation

Hardware-specific optimization: Yes, optimized for GAP9 RISC-V ultralow-power multicore SoC

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No off-device/cloud communication reported

Candidate for Strict TinyML: Yes

Reason: The paper explicitly targets resource-constrained microcontrollers and ultralow-power SoCs, reports GAP9 memory/power/latency constraints, and deploys the full VIO pipeline on-device.

Benchmarking / Standardization

Benchmark used: Custom indoor/outdoor VIO benchmark with RMSE and relative translation error using RPG Trajectory Evaluation toolkit

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, compared against original and parallelized PX4FLOW baseline

Comparison with previous works: Yes

Reproducibility artifacts available: code

Results

Summary: The optimized GAP9 pipeline improves RMSE by up to 3.65× over the baseline when using ORB. PX4FLOW achieves very high FPS and remains effective for smaller movements, while ORB provides better scalability for larger feature displacements.

Limitations

The method is restricted to downfacing camera configurations and planar motion assumptions, making it mainly suitable for structured environments. SuperPoint is memory-bound on GAP9, and PX4FLOW scales poorly for large displacements due to quadratic runtime growth.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes an optimized and quantized downfacing visual–inertial odometry pipeline with PX4FLOW, ORB, and SuperPoint feature trackers deployed and benchmarked on the ultralow-power GAP9 RISC-V SoC.

| Paper        | Year | Task                                        | Model                                 | Technique                                             | Device                         | Dataset                           | Main Metric                            | Latency                                                | Model Size | SRAM/RAM                       | Flash | Energy                     | Framework             | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ------------------------------------------- | ------------------------------------- | ----------------------------------------------------- | ------------------------------ | --------------------------------- | -------------------------------------- | ------------------------------------------------------ | ---------- | ------------------------------ | ----- | -------------------------- | --------------------- | -------- | ------------- | ------------- |
| Kühne et al. | 2025 | Visual–inertial odometry / feature tracking | PX4FLOW, ORB, SuperPoint VIO pipeline | Quantization, fixed-point arithmetic, parallelization | GAP9 RISC-V ultralow-power SoC | Custom indoor/outdoor VIO dataset | RMSE reduction up to 3.65× vs baseline | PX4FLOW 1216.3 FPS; ORB 118.5 FPS; SuperPoint 11.9 FPS | N/A        | 128 kB L1; 1.5 MB L2; peak N/A | N/A   | 64–68 mW power; energy N/A | GreenWaves SDK NNTool | INT8     | None          | Yes           |
