## Paper ID: Acceleration-of-Urdu-Optical-Character-Recognition-on-Zynq-UltraScale-MPSoC-Using-Deep-Convolutional-Neural-Network

TinyML classification: Near-TinyML — The deployment target is an FPGA/MPSoC edge platform rather than an explicitly MCU-class TinyML platform.

### Basic Info
- Authors: Fauzia Yasir and Majida Kazmi
- Year: 2025
- Title: Acceleration of Urdu Optical Character Recognition on Zynq UltraScale+ MPSoC Using Deep Convolutional Neural Network
- Source: IEEE Access, Volume 13, 2025
- Type: Experimental

### Problem & Context
- Task: Classification
- Objective: Develop a hardware-accelerated Urdu OCR framework using a custom CNN optimized for real-time low-power deployment on a Zynq UltraScale+ MPSoC FPGA platform.
- Application domain: Urdu optical character recognition for low-resource language digitization.
- Scenario: Embedded edge AI / FPGA-based real-time OCR.
- TinyML relevance: Partial
- TinyML justification: The paper targets low-power embedded/edge inference with quantization, latency, power, model-size, and BRAM utilization reporting, but the target platform is an FPGA/MPSoC rather than an MCU-class TinyML device.

### Model / Method
- Model: Custom CNN for Urdu character and digit classification.
- Architecture family: CNN
- Techniques: INT8 quantization, hardware-aware optimization, model compression, DPU-compatible operator selection, subgraph partitioning, operator fusion, batch normalization folding, data reuse optimization, multithreaded inference.
- Framework: TensorFlow 2.3.0, Keras, Xilinx Vitis AI, Vitis AI Runtime.
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: Xilinx ZCU104 evaluation kit with Zynq UltraScale+ MPSoC.
- Hardware type: FPGA / SoC
- Processor / microcontroller: Zynq UltraScale+ XCZU7EV-2FFVC1156 MPSoC with ARM Cortex processing system and DPUCZDX8G B4096 accelerator.
- Clock frequency: 300 MHz
- SRAM / RAM: 30.58% of allocated DPU BRAM and 25% of total FPGA BRAM utilized; SRAM/RAM capacity not reported.
- Flash / ROM / Storage: Not reported
- Power consumption: 1.32 W inference power; 9.52 W idle power; 10.84 W peak power.
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory footprint, BRAM utilization, latency, throughput, power consumption, computational complexity, resource utilization.

### Dataset
- Name: Not reported
- Type: Synthetic
- Dataset size: 336,000 labeled images
- Number of classes: 48
- Input resolution: 32 × 32
- Data modality: Grayscale image

### Metrics
- Accuracy: 96.73% FP32; 94.06% INT8 on ZCU104; 95.93% quantized software testing accuracy.
- mAP: Not reported
- Precision: Macro precision 0.96; micro precision 0.9568.
- Recall: Macro recall 0.96; micro recall 0.9568.
- F1-score: Macro F1-score 0.96; micro F1-score 0.9568.
- Latency: 0.189 ms per character; 0.1847 ms per inference reported in hardware comparison.
- FPS: 4,886.95 FPS; peak 5,285.24 FPS with 3 threads.
- Throughput: 4,886.95 FPS
- Model size: 1.44 MB FP32; 0.36 MB INT8.
- Parameters: 361,136
- MACs / FLOPs: Not reported
- RAM usage: 30.58% of allocated DPU BRAM and 25% of total FPGA BRAM utilized.
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: 1.32 W inference power.

### Optimization
- Techniques used: INT8 quantization, hardware-aware optimization, model compression, DPU-compatible CNN design, batch normalization folding, operator fusion, data reuse optimization, BRAM mapping, multithreaded DPU inference.
- Quantization: INT8; quantization-aware training and calibration-based Vitis AI quantization are reported.
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: FP32-to-INT8 quantization with 75% model-size reduction.
- Hardware-specific optimization: Xilinx Vitis AI compilation for DPUCZDX8G B4096 on ZCU104, with convolution, pooling, reshape, and dense layers mapped to DPU and Softmax executed on the processing system.
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: 1.44 MB FP32; 0.36 MB INT8.
- Energy per inference reported: Not reported
- Latency on target device reported: 0.189 ms per character; 0.1847 ms per inference.
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No cloud communication reported; offline recognition is reported.
- Candidate for Strict TinyML: No
- Reason: The deployment uses an FPGA/MPSoC edge platform rather than an explicitly MCU-class or bare-metal/RTOS TinyML target, and SRAM/Flash usage is not reported in MCU-style constraints.

### Benchmarking / Standardization
- Benchmark used: Custom synthetic Urdu OCR dataset.
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: MNIST is discussed only in prior FPGA OCR comparisons, not used as the main benchmark for the proposed method.
- Comparison with baseline models: Yes; compared against CPU and GPU implementations.
- Comparison with previous works: Yes; compared with existing FPGA-based OCR accelerators.
- Reproducibility artifacts available: Not reported

### Results
- Summary: The INT8 CNN deployed on ZCU104 achieved 94.06% accuracy, 0.189 ms per character, 4,886.95 FPS, and 1.32 W inference power. Quantization reduced model size by 75%, from 1.44 MB FP32 to 0.36 MB INT8, while maintaining real-time OCR performance.

### Limitations
- The framework is limited to isolated printed Urdu characters under controlled input conditions.
- Direct applicability to handwritten recognition, word-level parsing, and scene-text OCR is limited.
- Future work requires enriched datasets, advanced augmentation, architecture modifications, and acceleration of pre-processing and post-processing stages.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a hardware-accelerated Urdu OCR framework using a compact custom CNN, INT8 quantization with Vitis AI, and DPU deployment on Zynq UltraScale+ MPSoC for low-power real-time character recognition.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Yasir et al. | 2025 | Classification | Custom CNN | INT8 quantization and hardware-aware FPGA optimization | Zynq UltraScale+ MPSoC ZCU104 | Synthetic Urdu OCR dataset, 336,000 images | Accuracy 94.06% INT8 | 0.189 ms/character | 0.36 MB INT8 | 30.58% allocated DPU BRAM; 25% total FPGA BRAM | N/A | N/A | TensorFlow/Keras, Vitis AI, VART | INT8 | None | No |
