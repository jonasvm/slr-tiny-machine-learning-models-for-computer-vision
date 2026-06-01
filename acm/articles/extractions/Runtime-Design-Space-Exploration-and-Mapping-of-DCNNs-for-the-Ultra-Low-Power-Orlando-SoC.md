## Paper ID: Runtime-Design-Space-Exploration-and-Mapping-of-DCNNs-for-the-Ultra-Low-Power-Orlando-SoC

TinyML classification: Strict TinyML — it explicitly targets an ultra-low-power embedded Orlando SoC with ARM Cortex microcontroller integration, on-chip SRAM constraints, and low-power CNN inference.

### Basic Info

* Authors: Ahmet Erdem; Cristina Silvano; Thomas Boesch; Andrea Carlo Ornstein; Surinder-Pal Singh; Giuseppe Desoli
* Year: 2020
* Title: Runtime Design Space Exploration and Mapping of DCNNs for the Ultra-Low-Power Orlando SoC
* Source: ACM Transactions on Architecture and Code Optimization, Vol. 17, No. 2, Article 11, May 2020
* Type: Methodological

### Problem & Context

* Task: Image classification and object detection
* Objective: Propose a runtime design space exploration and mapping methodology for DCNN workloads on the Orlando ultra-low-power SoC.
* Application domain: Embedded computer vision and IoT intelligent systems
* Scenario: Ultra-low-power embedded SoC
* TinyML relevance: Yes
* TinyML justification: The paper targets ultra-low-power embedded DCNN inference with on-chip memory, accelerator, bandwidth, power, and latency constraints.

### Model / Method

* Model: Runtime DSE and mapping methodology evaluated with VGG-16, Tiny-Yolo(v2), MobileNet, and Pico-Yolo
* Architecture family: CNN
* Techniques: Runtime resource allocation, per-layer accelerator mapping, DVFS selection, feature-map striping, analytical performance/utilization/memory/power modeling, Pareto analysis
* Framework: Not reported
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Orlando ultra-low-power CNN SoC from STMicroelectronics
* Hardware type: SoC
* Processor / microcontroller: ARM Cortex microcontroller, eight DSP clusters, and eight convolutional accelerators
* Clock frequency: 200 MHz at 0.575 V; up to 1.175 GHz at 1.1 V; DVFS configurations from 200 MHz to 1,175 MHz
* SRAM / RAM: Four 1-MB SRAM banks; explored MEMSIZE values from 128 KB to 4 MB
* Flash / ROM / Storage: Not reported
* Power consumption: 41 mW average power reported for AlexNet on Orlando at 200 MHz and 0.575 V; workload results use modeled/normalized power
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: On-chip memory, external memory bandwidth, accelerator allocation, power consumption, execution time, compute utilization

### Dataset

* Name: Not reported
* Type: Not reported
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: 416 × 416 for Tiny-Yolo(v2); 240 × 240 for Pico-Yolo
* Data modality: RGB image

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Execution time modeled and analyzed; no single end-to-end latency value reported
* FPS: Not reported
* Throughput: GOPS/s used for per-layer throughput comparison
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: VGG-16 30.69 GOPs, Tiny-Yolo(v2) 6.93 GOPs, MobileNet 1.14 GOPs, Pico-Yolo 1.08 GOPs per inference
* RAM usage: On-chip memory allocation explored from 128 KB to 4 MB
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Modeled and normalized power/performance analysis; 41 mW cited for AlexNet on Orlando

### Optimization

* Techniques used: Hardware-aware DSE, runtime accelerator mapping, DVFS selection, feature-map striping, memory bandwidth optimization, Pareto filtering
* Quantization: INT8 / mixed precision; 8-bit input features and kernel weights with 16-bit output features
* Pruning: No
* Knowledge distillation: No
* Compression method: Not reported
* Hardware-specific optimization: Yes, for Orlando convolutional accelerators, scratch-pad/on-chip memory, and external bandwidth
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Four 1-MB SRAM banks; explored allocations up to 4 MB
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Execution time modeled and compared with Pico-Yolo board implementation, but no single end-to-end latency value is tabulated
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Yes
* Reason: The work explicitly targets ultra-low-power embedded SoC deployment with ARM Cortex integration, on-chip SRAM constraints, hardware accelerators, and on-device DCNN inference.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: VGG-16, Tiny-Yolo(v2), MobileNet, and Pico-Yolo workloads
* Comparison with baseline models: Yes, adaptive mapping is compared with one-fits-all mapping
* Comparison with previous works: No direct power/performance comparison with state-of-the-art accelerators is performed
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed runtime DSE reduces millions of design points to Pareto sets of 117 to 161 configurations depending on the workload. Adaptive per-layer mapping outperforms or matches one-fits-all mapping across VGG-16, Tiny-Yolo(v2), and MobileNet.

### Limitations

* Multi-batch processing is outside the scope of the work.
* Direct power/performance comparison with other state-of-the-art hardware accelerators is outside the scope.
* The methodology is focused on the Orlando architecture, although the authors state that striping and utilization modeling may generalize to similar architectures.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: No
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a runtime design space exploration and per-layer DCNN mapping methodology for the Orlando ultra-low-power SoC to optimize on-chip memory use, convolutional accelerator allocation, external bandwidth, and power/performance trade-offs.

| Paper        | Year | Task                                    | Model                                       | Technique                                          | Device                          | Dataset | Main Metric                                 | Latency | Model Size | SRAM/RAM                           | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | --------------------------------------- | ------------------------------------------- | -------------------------------------------------- | ------------------------------- | ------- | ------------------------------------------- | ------- | ---------- | ---------------------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Erdem et al. | 2020 | Image classification / object detection | VGG-16; Tiny-Yolo(v2); MobileNet; Pico-Yolo | Runtime DSE and hardware-aware accelerator mapping | Orlando ultra-low-power CNN SoC | N/A     | Power/performance Pareto and CA utilization | N/A     | N/A        | 128 KB–4 MB MEMSIZE; 4 × 1 MB SRAM | N/A   | N/A    | N/A       | Mixed    | None          | Yes           |
