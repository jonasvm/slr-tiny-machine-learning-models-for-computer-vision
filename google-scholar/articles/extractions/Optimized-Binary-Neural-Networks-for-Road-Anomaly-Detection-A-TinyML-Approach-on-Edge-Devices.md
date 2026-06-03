## Paper ID: Optimized-Binary-Neural-Networks-for-Road-Anomaly-Detection-A-TinyML-Approach-on-Edge-Devices

TinyML classification: Strict TinyML — explicitly deploys the optimized model on an ARM Cortex-M0 microcontroller with reported model size, latency, and memory-efficiency constraints.

### Basic Info

* Authors: Amna Khatoon; Weixing Wang; Asad Ullah; Limin Li; Mengfei Wang
* Year: 2024
* Title: Optimized Binary Neural Networks for Road Anomaly Detection: A TinyML Approach on Edge Devices
* Source: Computers, Materials & Continua, Tech Science Press, vol. 80, no. 1
* Type: Experimental

### Problem & Context

* Task: Road anomaly detection and road image segmentation/classification
* Objective: Optimize a Binary Neural Network for road anomaly detection on constrained edge devices using TinyML-oriented compression and quantization.
* Application domain: Road infrastructure monitoring, smart cities, traffic management, autonomous navigation support
* Scenario: Edge, embedded, IoT, microcontroller-based road monitoring
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets TinyML deployment on constrained devices and reports deployment on an ARM Cortex-M0 microcontroller with memory and latency optimization.

### Model / Method

* Model: CBin-NN / optimized Binary Neural Network; U-Net with Gabor filtering is also described for road image processing
* Architecture family: CNN / Binary CNN
* Techniques: Binarization, quantization, pruning, model compression, batch normalization fusion, loop unrolling, XNOR/PopCount operations, bit-packing, PReLU, channel-wise max pooling
* Framework: CBin-NN, platform-independent C; PyTorch 1.7.0 reported for experiments
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: ARM Cortex-M0 microcontroller
* Hardware type: MCU
* Processor / microcontroller: ARM Cortex-M0
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, latency, compute, power/energy, communication, resource-constrained deployment

### Dataset

* Name: Massachusetts roads dataset
* Type: Public
* Dataset size: 1171 images
* Number of classes: 2
* Input resolution: 1500 × 1500 pixels
* Data modality: Remotely sensed road images

### Metrics

* Accuracy: 78.8%
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 0.6 ms
* FPS: Not reported
* Throughput: Not reported
* Model size: 2.3 KB
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: 28× activation memory reduction reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Binarization, quantization, pruning, model compression, bit-packing, XNOR/PopCount, batch normalization fusion, loop unrolling, PReLU, CPU cache optimization
* Quantization: Mixed binary and 8-bit quantized inputs
* Pruning: Yes
* Knowledge distillation: Not reported
* Compression method: Binary neural network compression with binarized weights/activations, bit-packing, pruning, and quantized inputs
* Hardware-specific optimization: Cortex-M-oriented CBin-NN operators, loop unrolling, batch normalization fusion, cache-oriented optimization
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 2.3 KB
* Energy per inference reported: Not reported
* Latency on target device reported: 0.6 ms on MCU
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly reports deployment on an ARM Cortex-M0 microcontroller with MCU-level model size and latency results.

### Benchmarking / Standardization

* Benchmark used: Massachusetts roads dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: TF-LiteMicro H-CNN, MicroTVM SVM, CMSIS-NN SVM, TinyEngine CNN
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset

### Results

* Summary: The proposed CBin-NN / BNN_Micro achieved 78.8% accuracy, 2.3 KB model size, and 0.6 ms latency on the reported MCU setup. The paper reports a 28× memory reduction and 25% inference speed improvement with a 2.5% accuracy decrease.

### Limitations

* The paper reports limitations related to constrained computing resources and training datasets.
* Generalizability is limited because the main experiments use the Massachusetts roads dataset, with future evaluation suggested on additional datasets.
* Binarization can reduce accuracy, and high-resolution images require tiling for TinyML deployment.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes an optimized Binary Neural Network-based TinyML approach for road anomaly detection on edge devices using quantization, pruning, and model compression for MCU-class deployment.

| Paper          | Year | Task                                  | Model               | Technique                                        | Device        | Dataset                     | Main Metric     | Latency | Model Size | SRAM/RAM                        | Flash | Energy | Framework             | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | ------------------------------------- | ------------------- | ------------------------------------------------ | ------------- | --------------------------- | --------------- | ------- | ---------- | ------------------------------- | ----- | ------ | --------------------- | -------- | ------------- | ------------- |
| Khatoon et al. | 2024 | Road anomaly detection / segmentation | CBin-NN / BNN_Micro | Binarization, quantization, pruning, compression | ARM Cortex-M0 | Massachusetts roads dataset | Accuracy: 78.8% | 0.6 ms  | 2.3 KB     | 28× activation memory reduction | N/A   | N/A    | CBin-NN / C / PyTorch | Mixed    | None          | Yes           |
