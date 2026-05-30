## Paper ID: FSSA-A-Fully-Serial-and-Mixed-Precision-Systolic-Array-for-Vision-Transformer-Acceleration-on-Edge

TinyML classification: Near-TinyML — targets edge Vision Transformer acceleration on FPGA/ASIC-style hardware, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Iraj Moghaddasi; Byeong-Gyu Nam
* Year: 2025
* Title: FSSA: A Fully Serial and Mixed-Precision Systolic Array for Vision Transformer Acceleration on Edge
* Source: IEEE Access
* Type: Experimental / Methodological

### Problem & Context

* Task: Image classification
* Objective: Accelerate Vision Transformer inference on resource-constrained edge devices using a fully serial mixed-precision systolic array.
* Application domain: Edge AI computer vision
* Scenario: Edge devices, FPGA demonstration, ASIC-style accelerator evaluation
* TinyML relevance: Partial
* TinyML justification: The paper targets edge-based Vision Transformer acceleration with power, area, latency, precision, and energy-efficiency constraints, but does not report MCU-class deployment or SRAM/Flash-constrained execution.

### Model / Method

* Model: FSSA accelerator evaluated with Vision Transformer models, including Swin-T, Swin-B, ViT, DeiT, and Swin variants
* Architecture family: Transformer / ViT
* Techniques: Bit-serial processing, mixed-precision inference, layer-wise bit-precision adjustment, bit-sparsity exploitation, systolic array acceleration, weight-stationary dataflow
* Framework: Verilog RTL, Synopsys EDA tools, Python simulation/profiling, FPGA implementation
* Training type: Fine-tuning
* Inference type: Hybrid / edge accelerator-based

### Hardware

* Device: DE1-SoC board with Cyclone-V SoC for FPGA demonstration; 28 nm synthesized accelerator for evaluation
* Hardware type: FPGA / ASIC accelerator / NPU-style systolic array
* Processor / microcontroller: Cyclone-V SoC; 28 nm synthesized FSSA accelerator
* Clock frequency: 403 MHz maximum frequency for FSSA
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: 0.035 W dynamic power and 0.0006 W leakage power for FSSA
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Area, power, latency, energy efficiency, compute complexity, bit precision, sparsity, resource constraints

### Dataset

* Name: CIFAR100; ImageNet
* Type: Public
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: Not reported
* Data modality: RGB image

### Metrics

* Accuracy: Accuracy preservation under reduced bit precision is evaluated; exact final accuracy values are not reported as scalar results
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 2.48 ns for FSSA 8-bit × 8-bit operation latency
* FPS: Not reported
* Throughput: 0.103 TOPS at 8-bit; 0.412 TOPS at 4-bit; 1.648 TOPS at 2-bit
* Model size: Not reported
* Parameters: ViT 86M; DeiT-B 86M; Swin-B 88M; PVT-B 61M; PiT-B 73M; CvT-13 20.1M; T2T-ViT-14 81.7M; LeViT-192 10.1M; GCViT-B 80.9M
* MACs / FLOPs: ViT, Swin, and DeiT are reported as requiring 12.89, 15.66, and 12.98 billion MACs, respectively
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 0.035 W dynamic power and 0.0006 W leakage power for FSSA

### Optimization

* Techniques used: Bit-serial systolic array design, mixed-precision inference, bit-precision adjustment, bit-sparsity exploitation, sparsity-aware serial MAC units
* Quantization: Mixed precision
* Pruning: No model pruning reported; bit-sparsity exploitation is used
* Knowledge distillation: Not reported
* Compression method: Bit-precision reduction and bit-sparsity exploitation
* Hardware-specific optimization: Yes, RTL-level accelerator design synthesized in 28 nm and validated on FPGA
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 2.48 ns array-level operation latency reported; full inference latency not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper targets edge FPGA/ASIC-style Vision Transformer acceleration but does not provide explicit MCU-class deployment, SRAM/Flash constraints, TensorFlow Lite Micro deployment, or bare-metal/RTOS evidence.

### Benchmarking / Standardization

* Benchmark used: Swin-T on CIFAR100 and ImageNet; 28 nm synthesis; FPGA demonstration
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: CIFAR100; ImageNet
* Comparison with baseline models: Yes, compared with bit-parallel systolic array and serial/parallel systolic array baselines
* Comparison with previous works: Yes, compared with existing precision-scalable NPU designs
* Reproducibility artifacts available: Not reported

### Results

* Summary: A 16 × 128 FSSA achieves 68% PDP improvement and 83% EDP improvement compared with the bit-parallel baseline. Layer-wise mixed precision provides 31% speedup, and bit-sparsity exploitation provides additional speedup without reported accuracy loss.

### Limitations

* Not reported

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: No
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a fully serial mixed-precision systolic array accelerator for efficient Vision Transformer inference on edge devices using bit-serial processing, dynamic precision adjustment, and bit-sparsity exploitation.

| Paper             | Year | Task                 | Model                       | Technique                                                                | Device                                                | Dataset            | Main Metric                              | Latency                     | Model Size | SRAM/RAM | Flash | Energy | Framework                                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------------- | ---: | -------------------- | --------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------- | ------------------ | ---------------------------------------- | --------------------------- | ---------- | -------- | ----- | ------ | ----------------------------------------- | -------- | ------------- | ------------- |
| Moghaddasi et al. | 2025 | Image classification | Swin-T / Vision Transformer | Bit-serial mixed-precision systolic array with bit-sparsity exploitation | DE1-SoC Cyclone-V FPGA; 28 nm synthesized accelerator | CIFAR100; ImageNet | 68% PDP improvement; 83% EDP improvement | 2.48 ns array-level latency | N/A        | N/A      | N/A   | N/A    | Verilog RTL / Synopsys / Python profiling | Mixed    | None          | No            |
