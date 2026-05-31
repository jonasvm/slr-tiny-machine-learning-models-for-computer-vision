## Paper ID: Real-Time-Video-Based-Human-Action-Recognition-on-Embedded-Platforms

TinyML classification: Near-TinyML — Evaluated on Nvidia Jetson Xavier NX embedded AI hardware with TensorRT/Linux, not on MCU-class or TFLite Micro deployment.

### Basic Info

* Authors: Ruiqi Wang, Zichen Wang, Peiqi Gao, Mingzhen Li, Jaehwan Jeong, Yihang Xu, Yejin Lee, Carolyn Baum, Lisa Connor, Chenyang Lu
* Year: 2025
* Title: Real-Time Video-Based Human Action Recognition on Embedded Platforms
* Source: ACM Transactions on Embedded Computing Systems, Vol. 24, No. 5s, Article 135
* Type: Experimental

### Problem & Context

* Task: Video-based human action recognition
* Objective: Reduce end-to-end latency for real-time HAR on embedded platforms while maintaining recognition accuracy.
* Application domain: Healthcare monitoring, occupational therapy, driver safety, live video analytics
* Scenario: Embedded real-time video inference
* TinyML relevance: Partial
* TinyML justification: The paper targets embedded on-device computer vision with latency, energy, and memory constraints, but evaluates on Nvidia Jetson Xavier NX rather than MCU-class hardware.

### Model / Method

* Model: RT-HARE with Integrated Motion Feature Extractor (IMFE) and LSTR action recognition module
* Architecture family: Hybrid CNN / Transformer
* Techniques: Knowledge distillation, optical-flow-free motion feature extraction, TensorRT optimization, mixed precision inference, heterogeneous GPU/DLA parallelization exploration
* Framework: PyTorch, ONNX, TensorRT
* Training type: Knowledge distillation for IMFE; LSTR trained on evaluation datasets
* Inference type: On-device

### Hardware

* Device: Nvidia Jetson Xavier NX, Seeed Studio reComputer J2021
* Hardware type: SoC / GPU
* Processor / microcontroller: Six-core Nvidia Carmel ARM CPU, 384-core Nvidia Volta GPU with 48 Tensor Cores
* Clock frequency: CPU clocks maximized to 1.9 GHz
* SRAM / RAM: 8 GB unified RAM
* Flash / ROM / Storage: Not reported
* Power consumption: System-level power measured with tegrastats; exact average power not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Latency, real-time deadline, power, energy, memory footprint, compute

### Dataset

* Name: 50 Salads, GTEA, Drone-Action; ActivityNet subset used for IMFE training
* Type: Public benchmark datasets
* Dataset size: 50 Salads: 50 videos; GTEA: 28 videos; Drone-Action: 240 videos; ActivityNet subset: 4,359 videos
* Number of classes: Not reported
* Input resolution: 256 × 344
* Data modality: Video

### Metrics

* Accuracy: RT-HARE achieved 63.56% on 50 Salads at 30 FPS, 56.03% on GTEA, and 58.52% on Drone-Action
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: RT-HARE achieved F1@10 of 54.41% on 50 Salads at 30 FPS, 43.01% on GTEA, and 25.18% on Drone-Action
* Latency: RT-HARE end-to-end average latency was 55.80 ms on 50 Salads without DLA and 50.09 ms with DLA; 53.73 ms on GTEA; 61.58 ms on Drone-Action
* FPS: Evaluated at 30 FPS, 15 FPS, and 6 FPS depending on dataset and experiment
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Peak memory usage evaluated; exact value not textually reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Measured with tegrastats; exact value not textually reported

### Optimization

* Techniques used: IMFE architecture, knowledge distillation, TensorRT optimization, ONNX export, mixed precision inference, optional GPU/DLA workload parallelization
* Quantization: Mixed precision
* Pruning: No
* Knowledge distillation: Yes
* Compression method: IMFE removes explicit optical flow reconstruction and compresses correlation information through convolutional encoding
* Hardware-specific optimization: TensorRT mixed precision and Jetson GPU/DLA execution
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Yes
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: No
* Reason: The deployment target is a Linux-based Nvidia Jetson Xavier NX embedded AI platform with GPU acceleration and 8 GB RAM, not an MCU-class or bare-metal/RTOS TinyML device.

### Benchmarking / Standardization

* Benchmark used: 50 Salads, GTEA, Drone-Action
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: ActivityNet used for IMFE training
* Comparison with baseline models: RGB-only, TV-L1, RAFT, MemFlow
* Comparison with previous works: Yes
* Reproducibility artifacts available: code / model

### Results

* Summary: RT-HARE reduced average motion feature extraction latency to 37.75 ms on 50 Salads and achieved 55.80 ms end-to-end average latency on Jetson Xavier NX. It maintained competitive HAR accuracy while reducing energy consumption and memory footprint compared with two-stream optical-flow baselines.

### Limitations

* Evaluation is mainly performed on Nvidia Jetson Xavier NX, and broader validation on lower-power SoCs, FPGA-based systems, and more constrained embedded devices is left for future work.
* IMFE still uses 4D correlation volume computation and requires at least minimal parallel AI acceleration.
* Alternative runtime libraries, additional HAR techniques, quantization, pruning, and more diverse real-world conditions are not fully explored.

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
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes RT-HARE, a real-time embedded video-based human action recognition system that uses IMFE to replace explicit optical-flow extraction and reduce latency, energy consumption, and memory footprint on Jetson-class embedded hardware.

| Paper       | Year | Task                     | Model                 | Technique                                                                           | Device                  | Dataset                       | Main Metric                            | Latency                                          | Model Size | SRAM/RAM                                            | Flash | Energy                                                 | Framework                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ------------------------ | --------------------- | ----------------------------------------------------------------------------------- | ----------------------- | ----------------------------- | -------------------------------------- | ------------------------------------------------ | ---------- | --------------------------------------------------- | ----- | ------------------------------------------------------ | ------------------------- | -------- | ------------- | ------------- |
| Wang et al. | 2025 | Human action recognition | RT-HARE / IMFE + LSTR | OF-free motion feature extraction, knowledge distillation, TensorRT mixed precision | Nvidia Jetson Xavier NX | 50 Salads, GTEA, Drone-Action | Accuracy 63.56% on 50 Salads at 30 FPS | 55.80 ms avg end-to-end on 50 Salads without DLA | N/A        | 8 GB RAM; peak memory evaluated but exact value N/A | N/A   | Relative reductions reported; per-inference energy N/A | PyTorch / ONNX / TensorRT | Mixed    | None          | No            |
