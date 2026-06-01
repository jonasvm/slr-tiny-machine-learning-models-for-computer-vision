## Paper ID: ISRLUT-Integer-Only-FHD-Image-Super-Resolution-Based-on-Neural-Lookup-Table-and-Near-Memory-Computing

TinyML classification: Near-TinyML — The paper targets edge vision acceleration on FPGA and ASIC platforms, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Tianshuo Lu, Jianyang Ding, Bowen Jiang, Huachen Zhang, Wei Xu, and Zhilei Chai
* Year: 2025
* Title: ISRLUT: Integer-Only FHD Image Super-Resolution Based on Neural Lookup Table and Near-Memory Computing
* Source: ACM Transactions on Reconfigurable Technology and Systems, Vol. 18, No. 4, Article 50
* Type: Experimental

### Problem & Context

* Task: Image super-resolution
* Objective: To enable efficient real-time FHD image super-resolution on resource-constrained edge devices using integer-only Neural LUT inference and near-memory computing.
* Application domain: Edge image processing and image super-resolution
* Scenario: Edge, embedded, mobile, IoT, FPGA, ASIC
* TinyML relevance: Partial
* TinyML justification: The paper targets low-power edge and embedded image processing with small storage, low power, integer-only inference, and hardware acceleration, but does not report MCU-class deployment.

### Model / Method

* Model: ISRLUT / Neural LUT-based super-resolution accelerator
* Architecture family: Other
* Techniques: Integer-only inference, Neural LUT, LUT compression, Separable Mapping Strategy, Bit Split, Dynamic Discretization Method, layered biased uniform quantization, near-memory computing, tile-based buffer overlap, private cache, RFHash
* Framework: PyTorch for training; custom LUT conversion script; SystemVerilog HDL for hardware implementation
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Xilinx ZCU102 FPGA evaluation board and 55 nm ASIC implementation
* Hardware type: FPGA / SoC / ASIC
* Processor / microcontroller: Zynq UltraScale+ MPSoC with dual-core ARM Cortex-A53 Processing System and Programmable Logic; custom ISRLUT ASIC core
* Clock frequency: FPGA 100 MHz; ASIC 300 MHz; ASIC operating range reported as 200–600 MHz
* SRAM / RAM: ASIC SRAM size 168 KB with private cache; base ASIC SRAM 144 KB; FPGA BRAM usage 60 blocks with private cache
* Flash / ROM / Storage: 29.6 KB for x2, 32.1 KB for x3, and 36.9 KB for x4 model storage
* Power consumption: 0.0337 W for 55 nm ASIC; 1.79 W for FPGA with private cache
* Energy per inference: Not reported; 0.11 nJ/pixel reported for x4
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, latency, compute, hardware resources, DDR access, on-chip memory overflow, floating-point overhead

### Dataset

* Name: DIV2K for training; Set5, Set14, BSD100, Urban100, and Manga109 for evaluation
* Type: Public
* Dataset size: Not reported
* Number of classes: Not applicable
* Input resolution: 48 × 48 × 3 training input patches; FHD target resolution used for hardware and MAC evaluation
* Data modality: RGB image

### Metrics

* Accuracy: Not applicable; PSNR and SSIM reported for super-resolution
* mAP: Not applicable
* Precision: Not applicable
* Recall: Not applicable
* F1-score: Not applicable
* Latency: LUT access reduced from 3 cycles to 1 cycle with private cache; device-level latency in ms not reported
* FPS: 78 FPS for x2 FHD and 118 FPS for x4 FHD on ASIC
* Throughput: 154.2 Mpixels/s for x2 and 245.3 Mpixels/s for x4
* Model size: 29.6 KB for x2, 32.1 KB for x3, and 36.9 KB for x4
* Parameters: Not reported
* MACs / FLOPs: 0.104G MACs for x2, 0.058G MACs for x3, and 0.024G MACs for x4
* RAM usage: ASIC SRAM size 168 KB with private cache; FPGA BRAM usage 60 blocks with private cache
* Flash usage: Not reported
* Energy per inference: Not reported; 0.11 nJ/pixel reported for x4
* Power consumption: 0.0337 W for ASIC and 1.79 W for FPGA with private cache

### Optimization

* Techniques used: Neural LUT operator mapping, integer-only inference, LUT compression, SMS, Bit Split, DDM, layered biased uniform quantization, near-memory computing, private cache, RFHash, tile-based buffer overlap
* Quantization: INT8 / UINT8 integer-only inference
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Separable Mapping Strategy, Bit Split, Dynamic Discretization Method, and layered biased uniform quantization
* Hardware-specific optimization: Yes; near-memory computing, private cache, PE-level LUT buffers, RFHash, tile-based buffer overlap, and FPGA/ASIC implementation
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported; ASIC SRAM size reported as 168 KB with private cache
* Flash usage reported: Not reported
* Model size reported: 29.6 KB for x2, 32.1 KB for x3, and 36.9 KB for x4
* Energy per inference reported: Not reported; 0.11 nJ/pixel reported for x4
* Latency on target device reported: FPS and throughput reported, but per-inference latency in ms not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No cloud communication reported; off-chip DDR access is discussed as a hardware memory bottleneck
* Candidate for Strict TinyML: No
* Reason: The paper targets FPGA and ASIC edge acceleration and does not provide evidence of MCU-class deployment, ARM Cortex-M, TensorFlow Lite Micro, CMSIS-NN, bare-metal execution, or RTOS-based inference.

### Benchmarking / Standardization

* Benchmark used: Set5, Set14, BSD100, Urban100, Manga109
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: DIV2K training dataset and standard super-resolution benchmark datasets
* Comparison with baseline models: Bilinear, Bicubic, SRCNN, FSRCNN, VDSR, EDSR, SRLUT, MuLUT, SPF-LUT
* Comparison with previous works: ERVSR, UArch, SIFNPU, HDSuper, GLNPU, ACNPU, eCNN, SRNPU, SRSoC, and other SR hardware accelerators
* Reproducibility artifacts available: Not reported

### Results

* Summary: ISRLUT achieves 30.21 dB PSNR and 0.8616 SSIM on Set5 for x4 super-resolution using 36.9 KB storage and 0.024G MACs. The 55 nm ASIC implementation consumes 0.0337 W, reaches 118 FPS for x4 FHD processing, and reports 7278.6 Mpixels/s/W power efficiency.

### Limitations

* Training memory usage is high, with approximately 38 GB GPU memory reported for a 3-layer network with 48 × 48 × 3 input and batch size 32.
* Future work is needed to extend the architecture to broader vision tasks and adaptive reconfigurability.

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

* This paper proposes ISRLUT, an integer-only Neural LUT hardware accelerator with near-memory computing and private caching for real-time low-power FHD image super-resolution on FPGA and ASIC edge platforms.

| Paper     | Year | Task                   | Model               | Technique                                         | Device                         | Dataset                                        | Main Metric              | Latency            | Model Size | SRAM/RAM                              | Flash | Energy           | Framework                                           | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | ---------------------- | ------------------- | ------------------------------------------------- | ------------------------------ | ---------------------------------------------- | ------------------------ | ------------------ | ---------- | ------------------------------------- | ----- | ---------------- | --------------------------------------------------- | -------- | ------------- | ------------- |
| Lu et al. | 2025 | Image super-resolution | ISRLUT / Neural LUT | Integer-only Neural LUT and near-memory computing | Xilinx ZCU102 FPGA; 55 nm ASIC | DIV2K; Set5; Set14; BSD100; Urban100; Manga109 | PSNR 30.21 dB on Set5 x4 | 118 FPS for x4 FHD | 36.9 KB    | 168 KB ASIC SRAM; 60 FPGA BRAM blocks | N/A   | 0.11 nJ/pixel x4 | PyTorch + custom LUT conversion + SystemVerilog HDL | INT8     | None          | No            |
