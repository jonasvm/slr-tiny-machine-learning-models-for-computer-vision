Paper ID: A-comprehensive-analysis-of-DAC-SDC-FPGA-low-power-object-detection-challenge

TinyML classification: Near-TinyML — The paper targets low-power FPGA/SoC edge platforms for object detection, but does not report MCU-class deployment or Cortex-M/TFLite Micro-level constraints.

Basic Info

Authors: Jingwei Zhang, Guoqing Li, Meng Zhang, Xinye Cao, Yu Zhang, Xiang Li, Ziyang Chen, Jun Yang

Year: 2024

Title: A comprehensive analysis of DAC-SDC FPGA low power object detection challenge

Source: Science China Information Sciences, Vol. 67, Iss. 8, 182401:1–182401:21 

Type: Benchmark / Review

Problem & Context

Task: Object detection

Objective: Present and analyze the LPODC/DAC-SDC UAV object detection challenge from 2018 to 2022, including dataset, hardware platforms, evaluation methods, top FPGA designs, quantization, hardware performance, and total score. 

Application domain: UAV object detection

Scenario: Edge AI, FPGA, SoC, embedded UAV platform

TinyML relevance: Yes

TinyML justification: The paper explicitly focuses on low-power object detection, edge platforms, constrained computational and memory resources, quantization, energy, FPS, and algorithm-hardware co-design for TinyML. 

Model / Method

Model: SSD, HalfSqueezeNet+YOLO, MobileNet+YOLO, SkyNet, ShuffleDet, RectHalfSqzNet, UltraNet, UltraNet bypass

Architecture family: CNN

Techniques: Quantization, binary quantization, fixed-point quantization, depthwise separable convolution, model depth reduction, streaming accelerator architecture, single computation engine architecture, DSP packing, uint-packing, algorithm-hardware co-design

Framework: Verilog hardware description language; high-level synthesis

Training type: Training on LPODC dataset; transfer learning from ImageNet reported for ShuffleDet; otherwise not reported

Inference type: On-device

Hardware

Device: Nvidia Jetson TX2; Xilinx PYNQ Z1; Ultra96 V1; Ultra96 V2

Hardware type: GPU / FPGA / SoC

Processor / microcontroller: Cortex-A9 on PYNQ Z1; Cortex-A53 on Ultra96 V1/V2; FPGA chips XC7Z020 and ZU3EG 

Clock frequency: 233 MHz reported for HiPU; otherwise not reported

SRAM / RAM: PYNQ Z1: 512 MB DDR3 and 4.9 MB BRAM; Ultra96 V1/V2: 2 GB DDR4 and 7.6 MB BRAM 

Flash / ROM / Storage: Not reported

Power consumption: 2022 Top-3: 1413 mW, 1740 mW, 1963 mW

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, throughput, compute, on-chip storage, quantization loss, DSP resources, FPGA resources

Dataset

Name: DJI-UAV / LPODC dataset

Type: Public contest dataset with concealed test set

Dataset size: 100000 training images, 1000 validation images, 52500 concealed test images; 150k images total reported 

Number of classes: 12 categories and 95 subcategories; evaluation does not consider object categories

Input resolution: 640×360

Data modality: RGB UAV images

Metrics

Accuracy: IoU

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 2022 Top-3: 2020.6, 2266.2, 712.8 FPS 

Throughput: 2022 Top-3: 808.2, 906.5, 285.1 GOPS

Model size: Reported weight sizes include 18.04 MB, 0.21 MB, 0.79 MB, 4.61 MB, 63.00 MB, 0.56 MB, 0.80 MB, 2.52 MB, 2.10 MB, and 1.45 MB depending on design

Parameters: Reported model weights include 104k, 210k, 215k, 381k, 440k, 588k, 2365k, and 8257k depending on design

MACs / FLOPs: Reported multiplications include 66M, 174M, 198M, 200M, 213M, 463M, 3997M, and 4006M depending on design

RAM usage: BRAM resource usage reported; runtime RAM peak not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 2022 Top-3: 1413 mW, 1740 mW, 1963 mW

Optimization

Techniques used: Fixed-point quantization, binary quantization, DSP packing, uint-packing, streaming architecture, single computation engine architecture, depthwise separable convolution, model simplification, multi-clock-domain power optimization

Quantization: Mixed precision

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Quantization and model simplification

Hardware-specific optimization: FPGA streaming accelerator, single computation engine, DSP2/DSP4/DSP6 packing, uint-packing, on-chip weight storage, clock-domain optimization

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes

Energy per inference reported: Not reported

Latency on target device reported: FPS reported; latency not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets low-power FPGA/SoC edge deployment, but does not report MCU-class deployment, Cortex-M devices, TFLite Micro, bare-metal/RTOS execution, SRAM peak, Flash usage, or per-inference energy.

Benchmarking / Standardization

Benchmark used: LPODC / DAC-SDC low power object detection challenge

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: DJI-UAV dataset; ImageNet used for ShuffleNetV2 pre-training; ILSVRC and PASCAL VOC mentioned as comparison datasets

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: code / dataset

Results

Summary: The best 2022 designs achieved very high FPGA throughput and low total energy, with SEUer reporting 0.703 IoU, 2020.6 FPS, 808.2 GOPS, 36.7 J total energy, and 1413 mW power. The paper concludes that algorithm-hardware co-design is essential for balancing detection accuracy, throughput, and energy in TinyML-oriented edge vision. 

Limitations

Streaming accelerators require all weights to be quantized and stored in on-chip memory, creating high deployment difficulty and possible quantization loss; network depth and parameter count constrain deployment feasibility. 

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: No

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a comprehensive benchmark analysis of the DAC-SDC/LPODC FPGA low-power UAV object detection challenge, covering datasets, hardware platforms, evaluation criteria, top-performing designs, quantization methods, accelerator architectures, and algorithm-hardware co-design strategies.

| Paper        | Year | Task             | Model    | Technique                                                           | Device              | Dataset         | Main Metric | Latency | Model Size                    | SRAM/RAM               | Flash | Energy       | Framework     | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ---------------- | -------- | ------------------------------------------------------------------- | ------------------- | --------------- | ----------- | ------- | ----------------------------- | ---------------------- | ----- | ------------ | ------------- | -------- | ------------- | ------------- |
| Zhang et al. | 2024 | Object Detection | UltraNet | A4/W4 quantization + DSP6 uint-packing + FPGA streaming accelerator | Ultra96 V2 FPGA SoC | DJI-UAV / LPODC | IoU 0.703   | N/A     | 0.80 MB reported for UltraNet | 2 GB DDR4; 7.6 MB BRAM | N/A   | 36.7 J total | HLS / Verilog | Mixed    | N/A           | No            |
