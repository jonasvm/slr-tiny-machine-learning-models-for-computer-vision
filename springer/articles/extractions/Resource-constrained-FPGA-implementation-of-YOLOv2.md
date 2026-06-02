## Paper ID: Resource-constrained-FPGA-implementation-of-YOLOv2

TinyML classification: Near-TinyML — Targets low-resource FPGA edge hardware rather than explicit MCU-class deployment.

### Basic Info

* Authors: Zhichao Zhang; M. A. Parvez Mahmud; Abbas Z. Kouzani
* Year: 2022
* Title: Resource-constrained FPGA implementation of YOLOv2
* Source: Neural Computing and Applications, 34, 16989–17006
* Type: Experimental

### Problem & Context

* Task: Object detection
* Objective: Implement YOLOv2 on a low-resource FPGA edge IoT platform with reduced on-chip memory usage, off-chip memory access, and power consumption.
* Application domain: Computer vision-based IoT edge devices
* Scenario: Edge, embedded, IoT
* TinyML relevance: Partial
* TinyML justification: The paper targets low-resource and low-power edge inference, but the deployment is on an FPGA/SoC platform rather than MCU-class hardware.

### Model / Method

* Model: YOLOv2
* Architecture family: CNN
* Techniques: INT8 post-training quantization, FPGA-specific dataflow optimization, cross-layer dataflow, multi-level buffers, data reuse, PE array acceleration
* Framework: Vivado HLS 2019; Vivado 2019
* Training type: Pretrained YOLOv2 model used; no reconfiguration or tuning reported
* Inference type: On-device

### Hardware

* Device: ZCU104 platform with Xilinx Zynq UltraScale+ MPSoC ZU7EV FPGA
* Hardware type: FPGA / SoC
* Processor / microcontroller: Xilinx Zynq UltraScale+ MPSoC ZU7EV FPGA with quad-core ARM Cortex-A53 processor
* Clock frequency: 200 MHz
* SRAM / RAM: 11 Mb BRAM available; 8.23 Mbits BRAM utilized; 2 GB DDR4 memory
* Flash / ROM / Storage: Not reported
* Power consumption: 4.8 W
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: On-chip memory, off-chip memory access, power consumption, throughput, resource utilization, compute efficiency

### Dataset

* Name: PASCAL VOC 2007 and PASCAL VOC 2012
* Type: Public
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: 416 × 416
* Data modality: RGB image

### Metrics

* Accuracy: Not reported
* mAP: 75%
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: 2.16 FPS
* Throughput: 100.33 GOP/s
* Model size: 50.6 MB weights
* Parameters: 50,676,061 weights
* MACs / FLOPs: 34.90 GOP
* RAM usage: 8.23 Mbits BRAM utilized
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 4.8 W

### Optimization

* Techniques used: INT8 post-training quantization, scalable cross-layer dataflow, filter-level data reuse, multi-level sliding buffers, PE array parallelization, optimized off-chip/on-chip data transfer
* Quantization: INT8 PTQ
* Pruning: No
* Knowledge distillation: No
* Compression method: INT8 quantization
* Hardware-specific optimization: FPGA-specific dataflow, buffering, PE array, AXI-Stream and M_AXI data-transfer optimization
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: 8.3 Mbits on-chip memory / 8.23 Mbits BRAM utilization
* Flash usage reported: Not reported
* Model size reported: 50.6 MB weights
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper targets FPGA-based low-resource edge inference with 2 GB DDR4 and 50.6 MB weights, without explicit MCU-class, Cortex-M, bare-metal, RTOS, TensorFlow Lite Micro, SRAM/Flash-level TinyML deployment evidence.

### Benchmarking / Standardization

* Benchmark used: PASCAL VOC 2007 and PASCAL VOC 2012
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: PASCAL VOC
* Comparison with baseline models: Not reported
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The FPGA implementation achieves 75% mAP on PASCAL VOC with 50.6 MB INT8 YOLOv2 weights. It uses 8.23 Mbits BRAM, consumes 4.8 W, reaches 100.33 GOP/s throughput, and runs at approximately 2.16 FPS.

### Limitations

* The large size of YOLOv2 conflicts with low-resource edge requirements and limits speed performance.
* The implementation supports only 8-bit precision operation.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: No
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a resource-constrained FPGA implementation of YOLOv2 using scalable cross-layer dataflow, multi-level buffering, and INT8 quantization to reduce memory usage and power consumption for low-resource edge IoT object detection.

| Paper        | Year | Task             | Model  | Technique                                     | Device                                       | Dataset              | Main Metric | Latency | Model Size      | SRAM/RAM                   | Flash | Energy | Framework                     | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | ---------------- | ------ | --------------------------------------------- | -------------------------------------------- | -------------------- | ----------- | ------- | --------------- | -------------------------- | ----- | ------ | ----------------------------- | -------- | ------------- | ------------- |
| Zhang et al. | 2022 | Object detection | YOLOv2 | Resource-constrained FPGA dataflow + INT8 PTQ | Xilinx Zynq UltraScale+ MPSoC ZU7EV / ZCU104 | PASCAL VOC 2007/2012 | mAP 75%     | N/A     | 50.6 MB weights | 8.23 Mbits BRAM; 2 GB DDR4 | N/A   | N/A    | Vivado HLS 2019 / Vivado 2019 | INT8 PTQ | None          | No            |
