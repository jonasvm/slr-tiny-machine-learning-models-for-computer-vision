Paper ID: Designing-a-Performance-Centric-MAC-Unit-with-Pipelined-Architecture-for-DNN-Accelerators

TinyML classification: Near-TinyML — evaluated on FPGA/ASIC-oriented DNN accelerator hardware, not explicitly on microcontroller-class or TFLite Micro deployment.

Basic Info

Authors: Gopal Raut; Jogesh Mukala; Vishal Sharma; Santosh Kumar Vishvakarma

Year: 2023

Title: Designing a Performance-Centric MAC Unit with Pipelined Architecture for DNN Accelerators

Source: Circuits, Systems, and Signal Processing, 42:6089–6115 

Type: Methodological / Experimental

Problem & Context

Task: Classification

Objective: To design and evaluate a performance-centric pipelined CORDIC-based MAC unit for DNN accelerators with improved throughput and area/power trade-offs.

Application domain: DNN accelerators for image classification and edge-AI applications.

Scenario: Edge AI, mobile, FPGA, ASIC.

TinyML relevance: Partial

TinyML justification: The paper targets low-power and area-efficient DNN acceleration for edge-AI hardware, but does not report MCU-class deployment, SRAM/Flash constraints, or TensorFlow Lite Micro execution.

Model / Method

Model: CORDIC-based pipelined MAC unit; fully connected NN 196:64:32:32:10; LeNet/Tensor CNN used for accuracy evaluation.

Architecture family: Other

Techniques: Fixed-point Q3.5 arithmetic, CORDIC-based MAC computation, pipelining, Pareto analysis, approximate computing, hardware-aware optimization.

Framework: HDL; Vivado-Xilinx; Synopsys Design Vision; TensorFlow DNN models for accuracy analysis. 

Training type: Not reported

Inference type: On-device

Hardware

Device: Virtex-7 FPGA VC707 Evaluation Kit; 45 nm ASIC post-synthesis evaluation.

Hardware type: FPGA / ASIC

Processor / microcontroller: Not reported

Clock frequency: 66 MHz for implemented fully connected CORDIC MAC-based NN; 460 MHz for standalone MAC unit; Table 6 throughput analysis also reports 50 MHz operation.  

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: 1.13 W on-chip power for proposed pipeline CORDIC fully connected NN; 322.7 µW dynamic power and 10.5 µW static power for proposed MAC at 45 nm; Monte Carlo mean dynamic power 319.7 µW.  

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Area, power, critical delay, throughput, hardware resources, bit precision, memory bandwidth.

Dataset

Name: MNIST; CIFAR-10

Type: Not reported

Dataset size: CIFAR-10 validation used a sample set of 1000 images; MNIST size not reported.

Number of classes: 10

Input resolution: Not reported

Data modality: Image

Metrics

Accuracy: PipeMAC LeNet accuracy: MNIST 97.9% at 8-bit and 98.7% at 32-bit; CIFAR-10 78.4% at 8-bit and 81.2% at 32-bit; fully connected NN accuracy 95.06%.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 360 clock cycles for first fully connected NN inference; 205 clock cycles after first inference; 1.86 ns MAC critical path delay on FPGA; 2.83 ns MAC delay at 45 nm ASIC synthesis.  

FPS: Not reported

Throughput: 4.450 GOPS for proposed pipeline CORDIC fully connected NN; 3.94 GOPS/W; 1.89× better performance throughput per watt than conventional MAC-based fully parallel neural network. 

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: 15,963 multiplication operations, 15,963 addition operations, and 138 activation-function operations reported for the DNN design. 

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 1.13 W on-chip power for proposed pipeline CORDIC fully connected NN; 322.7 µW dynamic power for proposed MAC at 45 nm.

Optimization

Techniques used: Five-stage pipelined CORDIC MAC, fixed-point Q3.5 arithmetic, Pareto-driven pipeline-stage selection, approximate computation, n-bit shift register, removal of feedback registers/multiplexers/barrel shifter.

Quantization: Fixed-point Q3.5; 4-bit, 8-bit, 12-bit, 16-bit, and 32-bit precision evaluated.

Pruning: No

Knowledge distillation: No

Compression method: Fixed-point arithmetic and approximate CORDIC-based MAC computation.

Hardware-specific optimization: Yes; FPGA and ASIC-oriented MAC architecture optimized for area, power, delay, and throughput.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 360 clock cycles for fully connected NN inference; 1.86 ns FPGA MAC critical path; 2.83 ns ASIC MAC delay.

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper evaluates FPGA/ASIC DNN accelerator hardware and does not provide MCU-class deployment, SRAM/Flash usage, TFLite Micro execution, or bare-metal/RTOS evidence.

Benchmarking / Standardization

Benchmark used: MNIST; CIFAR-10

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: MNIST; CIFAR-10

Comparison with baseline models: Yes; Xilinx IP MAC, iterative CORDIC, Vedic, Wallace, Booth, shift-add, and other MAC implementations.

Comparison with previous works: Yes

Reproducibility artifacts available: none

Results

Summary: The proposed five-stage Q3.5 pipeline CORDIC MAC achieved 58 LUTs, 74 FFs, 1.86 ns critical path delay, and 1.01 pJ power-delay product on FPGA. The fully connected NN on Virtex-7 achieved 95.06% accuracy, 360 clock cycles, 4.450 GOPS, 3.94 GOPS/W, and 1.13 W on-chip power. The 45 nm ASIC evaluation reported 322.7 µW dynamic power, 10.5 µW static power, 2.83 ns delay, and 1.00× relative ADP.

Limitations

No dedicated limitations section was reported; the paper states that limiting pipeline stages can lead to erroneous computation and that pipelining increases area and power overhead.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a performance-centric pipelined CORDIC-based fixed-point MAC architecture for DNN accelerators, using Pareto analysis to select Q3.5 arithmetic and five pipeline stages for improved throughput, area, and power efficiency.

| Raut et al. | 2023 | Classification | CORDIC-based pipelined MAC; FCNN 196:64:32:32:10; LeNet/Tensor CNN | Fixed-point Q3.5 CORDIC pipelining | Virtex-7 FPGA VC707; 45 nm ASIC synthesis | MNIST; CIFAR-10 | 95.06% accuracy; 4.450 GOPS | 360 cycles; 1.86 ns MAC critical path | N/A | N/A | N/A | N/A | HDL / Vivado-Xilinx / Synopsys / TensorFlow | Mixed fixed-point | None | No |
