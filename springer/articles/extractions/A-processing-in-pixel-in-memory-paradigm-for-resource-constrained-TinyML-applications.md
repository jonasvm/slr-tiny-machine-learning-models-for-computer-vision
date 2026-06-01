## Paper ID: A-processing-in-pixel-in-memory-paradigm-for-resource-constrained-TinyML-applications

TinyML classification: Strict TinyML — it explicitly addresses visual TinyML for low-power microcontroller-class constraints, including peak memory around hundreds of KB and energy/latency optimization.

### Basic Info

* Authors: Gourav Datta; Souvik Kundu; Zihan Yin; Ravi Teja Lakkireddy; Joe Mathai; Ajey P. Jacob; Peter A. Beerel; Akhilesh R. Jaiswal
* Year: 2022
* Title: A processing-in-pixel-in-memory paradigm for resource-constrained TinyML applications
* Source: Scientific Reports
* Type: Methodological

### Problem & Context

* Task: Visual wake words
* Objective: Reduce sensor-to-processor bandwidth, ADC cost, latency, and energy-delay product for TinyML vision workloads by embedding early CNN processing inside the pixel array.
* Application domain: Low-power embedded vision and intelligent image sensors
* Scenario: Embedded, IoT, on-device, sensor-level processing
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets visual TinyML, resource-constrained sensor intelligence, low-power microcontrollers, and memory-constrained Visual Wake Words inference.

### Model / Method

* Model: P2M custom MobileNetV2 and baseline MobileNetV2
* Architecture family: CNN
* Techniques: Processing-in-pixel-in-memory, analog in-pixel convolution, batch normalization fusion, shifted ReLU, reduced first-layer channels, large kernel/stride, INT8 quantization, circuit-algorithm co-design
* Framework: PyTorch
* Training type: From scratch
* Inference type: Hybrid on-device sensor/downstream processing

### Hardware

* Device: Proposed P2M CMOS image sensor with downstream processing unit
* Hardware type: Other
* Processor / microcontroller: Not reported
* Clock frequency: 2 GHz ADC counter clock
* SRAM / RAM: 270 KB on-chip SRAM reported for the P2M model; peak memory also reported as 0.30 MB at 560 × 560 input
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, compute, bandwidth, ADC cost, latency, energy, communication

### Dataset

* Name: Visual Wake Words using COCO2014 images
* Type: Public
* Dataset size: 115k training images; validation size not reported
* Number of classes: 2
* Input resolution: 560 × 560; 225 × 225; 115 × 115
* Data modality: RGB image

### Metrics

* Accuracy: 89.90% for P2M custom MobileNetV2 at 560 × 560; 91.37% for baseline MobileNetV2 at 560 × 560
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 36.1 ms in-pixel convolution latency with 8 channels; up to 2.15× delay improvement reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: 0.27 G MAdds for P2M custom model at 560 × 560; 1.93 G MAdds for baseline
* RAM usage: 0.30 MB at 560 × 560; 0.049 MB at 225 × 225; 0.013 MB at 115 × 115
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: In-pixel analog convolution, bandwidth reduction, reduced channels, large stride/kernel, BN fusion, shifted ReLU, INT8 quantization, circuit-algorithm co-design
* Quantization: INT8
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: First-layer feature-map bandwidth reduction and reduced-channel P2M custom CNN design
* Hardware-specific optimization: P2M circuit-algorithm co-design for CMOS image sensor constraints
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: 270 KB on-chip SRAM; 0.30 MB peak memory at 560 × 560 input
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Simulated delay reported; physical target-device latency not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Sensor-to-downstream-processor communication is still required, but reduced by the P2M approach
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly targets visual TinyML for low-power microcontroller-class memory budgets and reports peak SRAM/memory constraints, although the hardware results are based on proposed circuit-level simulation rather than a named MCU deployment.

### Benchmarking / Standardization

* Benchmark used: Visual Wake Words
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: Yes
* Other standard benchmark: COCO2014
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: dataset

### Results

* Summary: The P2M custom MobileNetV2 achieved 89.90% accuracy on Visual Wake Words at 560 × 560 with 0.27 G MAdds and 0.30 MB peak memory. The approach reports approximately 21× bandwidth reduction, up to 7.81× energy reduction, and up to 16.76× EDP advantage over baseline implementations.

### Limitations

* Fixed transistor-based weights in the first layers lack programmability unless replaced by programmable non-volatile memory technologies.
* Physical deployment on a named MCU or commercial target device is not reported.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a processing-in-pixel-in-memory CMOS image sensor paradigm that embeds early CNN operations inside the pixel array to reduce bandwidth, memory, latency, and energy costs for resource-constrained visual TinyML applications.

| Paper        | Year | Task              | Model                  | Technique                                           | Device                                                     | Dataset                      | Main Metric     | Latency                                                     | Model Size | SRAM/RAM                         | Flash | Energy                                                   | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | ----------------- | ---------------------- | --------------------------------------------------- | ---------------------------------------------------------- | ---------------------------- | --------------- | ----------------------------------------------------------- | ---------- | -------------------------------- | ----- | -------------------------------------------------------- | --------- | -------- | ------------- | ------------- |
| Datta et al. | 2022 | Visual Wake Words | P2M custom MobileNetV2 | Processing-in-pixel-in-memory and INT8 quantization | Proposed CMOS image sensor with downstream processing unit | Visual Wake Words / COCO2014 | 89.90% accuracy | 36.1 ms in-pixel convolution; up to 2.15× delay improvement | N/A        | 270 KB SRAM; 0.30 MB peak memory | N/A   | Up to 7.81× energy reduction; up to 16.76× EDP advantage | PyTorch   | INT8     | N/A           | Yes           |
