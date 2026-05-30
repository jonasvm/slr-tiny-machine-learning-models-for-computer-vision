## Paper ID: A-Real-Time-Object-Detection-Processor-With-XNOR-Based-Variable-Precision-Computing-Unit

TinyML classification: Near-TinyML — evaluated on FPGA/Zynq UltraScale+ embedded hardware with quantization and low-power optimization, not on MCU-class hardware.

### Basic Info
- Authors: Wonjae Lee, Kukbyung Kim, Woohyun Ahn, Jinho Kim, Dongsuk Jeon
- Year: 2023
- Title: A Real-Time Object Detection Processor With XNOR-Based Variable-Precision Computing Unit
- Source: IEEE Transactions on Very Large Scale Integration (VLSI) Systems
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: Design an algorithm-hardware co-optimized real-time object detection system using a compact binarized neural network and an FPGA-based processor.
- Application domain: Real-time embedded computer vision
- Scenario: Embedded FPGA / edge hardware
- TinyML relevance: Partial
- TinyML justification: The paper targets low-power, resource-constrained embedded object detection with quantization, model-size reduction, on-chip memory, latency, throughput, and power reporting, but it does not target MCU-class deployment.

### Model / Method
- Model: Proposed binarized object detection model with DenseToRes layers and YOLOv2-like detection scheme
- Architecture family: CNN / Binarized Neural Network
- Techniques: Binarization, mixed-precision quantization, DenseToRes layers, layer fusion, XNOR-based variable-precision processing, output-stationary processing, on-chip parameter storage
- Framework: PyTorch; Xilinx Vivado 2018.3
- Training type: Teacher-guided transfer learning with ResNet-34 and two-step binarized training
- Inference type: On-device inference on FPGA with CPU-based pre-processing and post-processing

### Hardware
- Device: Xilinx ZCU102 evaluation board
- Hardware type: FPGA / SoC
- Processor / microcontroller: Xilinx Zynq UltraScale+ MPSoC with ARM Cortex-A53 cores and programmable FPGA logic
- Clock frequency: FPGA at 300 MHz; ARM Cortex-A53 at 1.2 GHz
- SRAM / RAM: Unified feature map memory with 21,632 512-bit words; 10.775 Mb BRAM allocated for activations; 15.750 Mb BRAM allocated for parameters
- Flash / ROM / Storage: Not reported
- Power consumption: 6.58 W
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Yes
- Constraints mentioned: Memory access, external DRAM bandwidth, hardware resources, power budget, latency, throughput, model size, computational complexity

### Dataset
- Name: ImageNet; PASCAL VOC 2007 + 2012; PASCAL VOC 2007 test set
- Type: Public
- Dataset size: Not reported
- Number of classes: 20 for PASCAL VOC object detection
- Input resolution: 416 × 416 × 3
- Data modality: Image / video frames

### Metrics
- Accuracy: 65.54% ImageNet validation accuracy for the backbone network
- mAP: 64.92% on PASCAL VOC 2007 test set
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: 15.5 ms
- FPS: 64.51 frames/s
- Throughput: 64.51 frames/s
- Model size: 1.80 MB
- Parameters: Not reported
- MACs / FLOPs: 9.95 GOPs; 40.84 BitGOPs
- RAM usage: 10.775 Mb activation BRAM allocated; 15.750 Mb parameter BRAM allocated
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: 6.58 W

### Optimization
- Techniques used: Binarized neural network design, mixed-precision quantization, DenseToRes layer, layer fusion, XNOR-based variable-precision MAC unit, output-stationary processing, full on-chip parameter storage
- Quantization: Mixed precision with 1-bit, 2-bit, and 8-bit quantization
- Pruning: No
- Knowledge distillation: Yes, using ResNet-34 as a teacher network with distributional loss
- Compression method: Binary and mixed-precision quantization to reduce model size and memory access
- Hardware-specific optimization: FPGA-specific variable-precision XNOR processing element, output-stationary dataflow, BRAM-based on-chip storage, removal of external DRAM access
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: 10.775 Mb activation BRAM allocated; 15.750 Mb parameter BRAM allocated
- Flash usage reported: Not reported
- Model size reported: 1.80 MB
- Energy per inference reported: Not reported
- Latency on target device reported: 15.5 ms on FPGA at 300 MHz
- Runs without full operating system: No
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The deployment uses an FPGA/SoC platform with Linux-based processing and does not provide MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, or Cortex-M evidence.

### Benchmarking / Standardization
- Benchmark used: PASCAL VOC 2007 test set; ImageNet validation set
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: ImageNet; PASCAL VOC
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: The proposed binarized object detection model achieves 64.92% mAP on PASCAL VOC 2007 with a 1.80 MB model size. The FPGA implementation achieves 15.5 ms latency, 64.51 frames/s throughput, and 6.58 W power consumption while removing external DRAM access.

### Limitations
- Not reported

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
- This paper proposes an algorithm-hardware co-optimized real-time object detection system combining a binarized DenseToRes object detector with an FPGA-based XNOR variable-precision processor that stores model parameters on-chip and avoids external DRAM access.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Lee et al. | 2023 | Object detection | Binarized DenseToRes object detector | Mixed-precision quantization + XNOR variable-precision FPGA processor | Xilinx ZCU102 / Zynq UltraScale+ MPSoC FPGA | PASCAL VOC 2007 + 2012; PASCAL VOC 2007 test | 64.92% mAP | 15.5 ms | 1.80 MB | 10.775 Mb activation BRAM; 15.750 Mb parameter BRAM | N/A | N/A | PyTorch; Xilinx Vivado 2018.3 | Mixed | None | No |
