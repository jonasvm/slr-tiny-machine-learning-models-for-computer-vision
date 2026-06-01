## Paper ID: Improving-Performance-Power-Programmability-in-Space-Avionics-with-Edge-Devices-VBN-on-Myriad2-SoC

TinyML classification: Near-TinyML — evaluated on a Myriad2 SoC/FPGA edge platform with watt-level power, without explicit MCU-class or TensorFlow Lite Micro deployment.

### Basic Info

* Authors: Vasileios Leon, George Lentaris, Evangelos Petrongonas, Dimitrios Soudris, Gianluca Furano, Antonis Tavoularis, David Moloney
* Year: 2021
* Title: Improving Performance-Power-Programmability in Space Avionics with Edge Devices: VBN on Myriad2 SoC
* Source: ACM Transactions on Embedded Computing Systems, Vol. 20, No. 3, Article 22
* Type: Experimental

### Problem & Context

* Task: Vision-based navigation / satellite pose tracking
* Objective: Evaluate Intel Movidius Myriad2 SoC as a low-power edge device for spacecraft vision-based navigation and propose a development methodology and avionics architecture.
* Application domain: Space avionics
* Scenario: Embedded edge computing for on-board spacecraft processing
* TinyML relevance: Partial
* TinyML justification: The paper targets low-power embedded edge vision on a Myriad2 SoC with watt-level power and on-device processing, but it does not target MCU-class TinyML deployment.

### Model / Method

* Model: Classical computer vision pipeline for 6D satellite pose tracking
* Architecture family: Other
* Techniques: Multi-core parallelization, SIMD optimization, memory optimization, dynamic task assignment, hardware-aware optimization
* Framework: Custom Myriad2 C/C++ support framework using the Myriad Development Kit
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Intel Movidius Myriad2 MA2450 on EoT board, combined with FPGA-based SpaceWire transcoding
* Hardware type: SoC / DSP / FPGA
* Processor / microcontroller: Myriad2 SoC with two LEON4 processors and 12 SHAVE VLIW DSP cores; Xilinx XC6SLX150 FPGA for transcoding
* Clock frequency: 600 MHz for LEON4 and SHAVE subsystems
* SRAM / RAM: 512 MB on-chip DDR; 2 MB CMX scratchpad memory; SHAVE shared 256 KB L2 cache; LOS 64 KB L1 and 256 KB L2 cache; LRT 8 KB L1 and 32 KB L2 cache
* Flash / ROM / Storage: Not reported
* Power consumption: 0.8 to 1.1 W for the full system including CIF image reception; 0.9 W average for the CV pipeline; 1.2 W measured externally on the EoT board
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Power consumption, throughput, real-time processing, memory, performance per watt, communication bandwidth, embedded programmability

### Dataset

* Name: Synthetic ENVISAT rendezvous image dataset
* Type: Synthetic
* Dataset size: Two sequences of 1,000 images
* Number of classes: Not applicable
* Input resolution: 1024 × 1024
* Data modality: 8-bit grayscale image sequence

### Metrics

* Accuracy: Alignment error around 1%; edge detection accuracy 99%; depth rendering and edge matching accuracy 100%
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 263–388 ms per frame for the final CV algorithm; average 325 ms per frame for the 20–30 m sequence; average 235 ms per frame for the 50 m sequence
* FPS: 2.6 to 3.8 FPS for the 20–30 m sequence; 3.8 to 4.9 FPS for the 50 m sequence
* Throughput: 2.6 to 4.9 FPS
* Model size: Not applicable
* Parameters: Not applicable
* MACs / FLOPs: Not reported
* RAM usage: Around 20 MB total memory for the integrated CV pipeline and CIF module
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 0.8 to 1.1 W full system; 0.9 W average CV pipeline

### Optimization

* Techniques used: Multi-core SHAVE acceleration, SIMD computation, dynamic task assignment, minimal buffering, in-place processing, cache optimization, scratchpad memory optimization, task partitioning, function-level scheduling
* Quantization: None
* Pruning: No
* Knowledge distillation: No
* Compression method: Memory reduction through minimal buffering and in-place processing
* Hardware-specific optimization: Yes, optimized for Myriad2 SHAVE cores, CMX scratchpad memory, DMA, cache hierarchy, and SIMD instructions
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not applicable
* Energy per inference reported: Not reported
* Latency on target device reported: 263–388 ms per frame for the final CV algorithm
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Input frames are received through SpaceWire/CIF, but processing is performed on-device
* Candidate for Strict TinyML: No
* Reason: The deployment uses a Myriad2 SoC and FPGA-based embedded edge architecture rather than an MCU-class or TensorFlow Lite Micro TinyML platform.

### Benchmarking / Standardization

* Benchmark used: Synthetic ENVISAT pose tracking image sequences
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes, compared against initial LEON4 porting
* Comparison with previous works: Yes, compared with rad-hard CPUs, Zynq FPGA, ARM-based SoC FPGA, and mobile GPU-related implementations
* Reproducibility artifacts available: Not reported

### Results

* Summary: The optimized Myriad2 implementation achieved 2.6 to 4.9 FPS on 1024 × 1024 grayscale satellite pose tracking images with 0.8 to 1.1 W power consumption. The system achieved 8.5 to 12× speedup over the baseline including I/O and approximately 10× acceleration over modern rad-hard CPUs.

### Limitations

* Radiation qualification and hardening of the proposed architecture are outside the scope of the paper.
* Robustness under extreme lighting conditions is left for future research.
* Fault-tolerance techniques supported by the framework are described as part of a distinct or future study.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a low-power Myriad2-based embedded avionics architecture and programming framework for accelerating a spacecraft vision-based navigation pipeline on edge hardware.

| Paper       | Year | Task                    | Model                 | Technique                               | Device             | Dataset                     | Main Metric                      | Latency          | Model Size | SRAM/RAM                                  | Flash | Energy | Framework                                       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ----------------------- | --------------------- | --------------------------------------- | ------------------ | --------------------------- | -------------------------------- | ---------------- | ---------- | ----------------------------------------- | ----- | ------ | ----------------------------------------------- | -------- | ------------- | ------------- |
| Leon et al. | 2021 | Satellite pose tracking | Classical CV pipeline | Multi-core SIMD and memory optimization | Myriad2 SoC + FPGA | Synthetic ENVISAT sequences | 2.6–4.9 FPS; ~1% alignment error | 263–388 ms/frame | N/A        | ~20 MB total memory; 512 MB DDR; 2 MB CMX | N/A   | N/A    | Myriad Development Kit + custom C/C++ framework | N/A      | None          | No            |
