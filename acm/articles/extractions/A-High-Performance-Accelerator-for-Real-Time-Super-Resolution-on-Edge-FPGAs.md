## Paper ID: A-High-Performance-Accelerator-for-Real-Time-Super-Resolution-on-Edge-FPGAs

TinyML classification: Near-TinyML — The work targets embedded FPGA/edge platforms rather than explicit MCU-class or Cortex-M/TFLite Micro deployment.

### Basic Info

* Authors: Hongduo Liu, Yijian Qian, Youqiang Liang, Bin Zhang, Zhaohan Liu, Tao He, Wenqian Zhao, Jiangbo Lu, Bei Yu
* Year: 2024
* Title: A High-Performance Accelerator for Real-Time Super-Resolution on Edge FPGAs
* Source: ACM Transactions on Design Automation of Electronic Systems, Vol. 29, No. 3, Article 53
* Type: Experimental

### Problem & Context

* Task: Image super-resolution
* Objective: To design a lightweight super-resolution network and a real-time accelerator for edge FPGA deployment.
* Application domain: Image and video enhancement for high-definition display, video streaming, satellite imaging, surveillance, and medical imaging.
* Scenario: Edge embedded FPGA acceleration.
* TinyML relevance: Partial
* TinyML justification: The paper targets constrained edge FPGA deployment with power, latency, memory, bandwidth, and resource limitations, but does not target MCU-class TinyML deployment.

### Model / Method

* Model: Lightweight adaptive filter-based super-resolution network derived from LAPAR.
* Architecture family: CNN
* Techniques: Quantization, hardware-aware optimization, DSP cascade optimization, scalable cache strategy, constraint-based resource allocation, network simplification.
* Framework: SystemVerilog, Vivado 2021.1, customized Linux based on Xilinx Petalinux.
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Kria KV260 and ZCU104 embedded FPGA boards.
* Hardware type: FPGA / SoC
* Processor / microcontroller: Xilinx Zynq UltraScale+ MPSoC; KV26 and XCZU7EV FPGA devices.
* Clock frequency: 200 MHz SR frequency and 400 MHz DSP frequency on KV260; 250 MHz SR frequency and 500 MHz DSP frequency on ZCU104.
* SRAM / RAM: Not reported; BRAM usage reported as 116 BRAMs on KV260 and 134 BRAMs on ZCU104.
* Flash / ROM / Storage: Not reported
* Power consumption: 16.85 W on KV260 for 540p to 1080p; 23.81 W on ZCU104 for 720p to 1440p.
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, latency, computation, DSP resources, BRAM resources, bandwidth, communication between on-chip and off-chip memory.

### Dataset

* Name: DIV2K, Flickr2K, Set5, Set14, BSDS100, Urban100
* Type: Public benchmark
* Dataset size: Set5 has 5 images, Set14 has 14 images, BSDS100 has 100 images, and Urban100 has 100 images; DIV2K and Flickr2K sizes not reported.
* Number of classes: Not applicable
* Input resolution: 540 × 960 for the target SR network; 540p to 1080p and 720p to 1440p deployment settings.
* Data modality: Image / video frames; Y-channel image processing reported.

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 27.94 ms for 540p to 1080p on KV260; 39.74 ms for 720p to 1440p on ZCU104.
* FPS: 35.79 FPS for 540p to 1080p on KV260; 25.16 FPS for 720p to 1440p on ZCU104.
* Throughput: 987 GOPS on KV260; 1234 GOPS on ZCU104.
* Model size: Not reported
* Parameters: 103K
* MACs / FLOPs: 6G MACs
* RAM usage: Not reported; on-chip memory reported as 4176 KB for Ours-1 and 4824 KB for Ours-2.
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 16.85 W on KV260; 23.81 W on ZCU104.

### Optimization

* Techniques used: Lightweight SR network design, INT8/fixed-point quantization, DSP cascade optimization, two-clock-domain DSP design, scalable row-buffer cache strategy, and constraint programming for resource allocation.
* Quantization: INT8 / fixed-point; activations are quantized to 8 bits and weights to 9 bits, and AdaRound 8-bit quantization is reported.
* Pruning: No
* Knowledge distillation: No
* Compression method: Quantization and network simplification.
* Hardware-specific optimization: DSP cascade optimization, BRAM-aware cache strategy, bandwidth-aware dataflow, and FPGA resource allocation.
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 27.94 ms on KV260 and 39.74 ms on ZCU104.
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The deployment targets embedded FPGA boards running a customized Linux system, not MCU-class hardware or bare-metal/RTOS TinyML platforms.

### Benchmarking / Standardization

* Benchmark used: Set5, Set14, BSDS100, Urban100
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: DIV2K and Flickr2K for training; Set5, Set14, BSDS100, and Urban100 for evaluation.
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed FPGA accelerator achieves 35.79 FPS at 540p to 1080p on KV260 and 25.16 FPS at 720p to 1440p on ZCU104. It reports higher throughput and energy efficiency than compared GPU, AI chip, FPGA automation, and prior FPGA SR accelerator solutions.

### Limitations

* The accelerator processes only the Y channel, while color space conversion and other operations are handled by the ARM CPU.
* Higher resolutions such as 4K require larger parallel factors and higher-end FPGA hardware.
* Better SR quality may require more layers, which would increase hardware resource requirements.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a lightweight adaptive filter-based super-resolution network and a hardware-optimized real-time accelerator for embedded FPGA deployment.

### Comparative Table

| Paper      | Year | Task                   | Model                                        | Technique                                                          | Device              | Dataset                        | Main Metric                 | Latency             | Model Size      | SRAM/RAM                         | Flash | Energy | Framework                               | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | ---------------------- | -------------------------------------------- | ------------------------------------------------------------------ | ------------------- | ------------------------------ | --------------------------- | ------------------- | --------------- | -------------------------------- | ----- | ------ | --------------------------------------- | -------- | ------------- | ------------- |
| Liu et al. | 2024 | Image super-resolution | Lightweight adaptive filter-based SR network | INT8/fixed-point quantization and FPGA hardware-aware acceleration | Kria KV260 / ZCU104 | Set5, Set14, BSDS100, Urban100 | Set5 PSNR/SSIM 37.14/0.9566 | 27.94 ms / 39.74 ms | 103K parameters | 4176 KB / 4824 KB on-chip memory | N/A   | N/A    | SystemVerilog, Vivado 2021.1, Petalinux | INT8     | None          | No            |
