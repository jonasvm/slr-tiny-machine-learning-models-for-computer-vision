## Paper ID: BinaryViT-Binary-Vision-Transformer-for-Hyperspectral-Image-Classification

TinyML classification: Near-TinyML — It uses binary quantization and efficiency analysis for edge/embedded vision, but lacks explicit MCU, Cortex-M, TFLite Micro, or kilobyte-scale deployment evidence.

### Basic Info

* Authors: Xiang Hu, Taolin Liu, Zhe Guo, Yuxiang Tang, Yuanxi Peng, Tong Zhou
* Year: 2025
* Title: BinaryViT: Binary Vision Transformer for Hyperspectral Image Classification
* Source: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, Vol. 18, 2025
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: To propose a binary Vision Transformer architecture for hyperspectral image classification that reduces computational complexity and memory overhead while maintaining competitive accuracy.
* Application domain: Hyperspectral remote sensing, agriculture, land cover classification, planetary hyperspectral analysis
* Scenario: Edge, embedded, IoT, drone-based remote sensing
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained platforms such as FPGAs, embedded CPUs, IoT terminals, and drones, but experiments are conducted on a GPU server and no MCU-class deployment is reported.

### Model / Method

* Model: BinaryViT
* Architecture family: ViT
* Techniques: Binary quantization, self-adaptive softmax binarization, binarized attention, binarized convolutional layers, binarized MLP, multibranch average pooling, PCA preprocessing, straight-through estimator
* Framework: Not reported
* Training type: Not reported
* Inference type: Not reported

### Hardware

* Device: NVIDIA RTX 6000 GPU server used for experiments; FPGAs, embedded CPUs, IoT terminals, and drones are mentioned as target scenarios
* Hardware type: GPU for experiments; FPGA / CPU / embedded / IoT mentioned as target platforms
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: 122 GB RAM on experimental server; target SRAM not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Memory overhead, computational complexity, FLOPs, parameter count, resource-constrained deployment, energy consumption, hardware cost

### Dataset

* Name: WHU-Hi-HongHu; WHU-Hi-HanChuan; QUH-Tangdaowan; WHU-Hi-LongKou; Indian Pines; Salinas; Holden Crater
* Type: Public benchmark
* Dataset size: WHU-Hi-HongHu 940×475; WHU-Hi-HanChuan 1217×303; QUH-Tangdaowan 1740×860; WHU-Hi-LongKou 550×400; Indian Pines 145×145; Salinas 512×217; Holden Crater 418×595
* Number of classes: WHU-Hi-HongHu 22; WHU-Hi-HanChuan 16; QUH-Tangdaowan 18; WHU-Hi-LongKou 9; Indian Pines 16; Salinas 16; Holden Crater 6
* Input resolution: 13×13×30 image patches after PCA dimensionality reduction
* Data modality: Hyperspectral image

### Metrics

* Accuracy: OA 93.21% on WHU-Hi-HongHu; 91.12% on WHU-Hi-HanChuan; 87.83% on QUH-Tangdaowan; 97.28% on WHU-Hi-LongKou; 87.70% on Indian Pines; 96.79% on Salinas; 93.42% on Holden Crater
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Testing time reported on ablation datasets using GPU server: 41.96 s on WHU-Hi-HongHu, 60.82 s on QUH-Tangdaowan, 1.09 s on Indian Pines, and 2.16 s on Holden Crater
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported as file size
* Parameters: Proposed BinaryViT reports 6,358 parameters on WHU-Hi-HongHu, 5,842 on QUH-Tangdaowan, 5,584 on Indian Pines, and 4,294 on Holden Crater in the componentwise binarization analysis
* MACs / FLOPs: Proposed BinaryViT reports 11,494,944 FLOPs on WHU-Hi-HongHu, 11,494,432 on QUH-Tangdaowan, 11,494,176 on Indian Pines, and 11,492,896 on Holden Crater
* RAM usage: Not reported for target device
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Binary quantization of weights, activations, attention, and MLP components; self-adaptive softmax binarization; multibranch average pooling; PCA preprocessing; STE-based gradient approximation
* Quantization: Binary quantization with STE; INT8 / FP16 / QAT / PTQ not reported
* Pruning: No
* Knowledge distillation: No
* Compression method: Binary quantization with reported 32× model memory footprint reduction and more than 99% parameter binarization
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Parameter counts and memory footprint reduction are reported; byte-level model size is not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper discusses resource-constrained edge and embedded deployment but does not report MCU-class hardware, SRAM/Flash usage, TensorFlow Lite Micro, bare-metal/RTOS execution, or target-device energy/latency.

### Benchmarking / Standardization

* Benchmark used: Seven hyperspectral image classification benchmark datasets
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Indian Pines, Salinas, WHU-Hi-HongHu, WHU-Hi-HanChuan, WHU-Hi-LongKou, QUH-Tangdaowan, Holden Crater
* Comparison with baseline models: DCTN, DsFormer, 3D-ConvSST, BinaryViT(fp32), BiBERT, GSB, BHViT
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: BinaryViT achieves competitive hyperspectral image classification accuracy across seven datasets while outperforming other binary models in reported OA. The proposed model reports more than 99% parameter binarization and more than 89% reduction in floating-point computation compared with full-precision counterparts.

### Limitations

* The fixed binarization scheme may struggle to balance general feature compression with domain-specific feature retention.
* Cross-scenario generalization may decline in settings with strong domain-specific characteristics, multimodal data, and high intraclass variability.
* Current GPU architectures lack native support for binary operations, causing binary operations to be emulated through floating-point computations with additional quantization steps.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes BinaryViT, a binary Vision Transformer for hyperspectral image classification that combines self-adaptive softmax binarization and multibranch average pooling to reduce computational complexity while preserving classification accuracy.

| Paper     | Year | Task           | Model     | Technique           | Device                                                      | Dataset                              | Main Metric      | Latency                                 | Model Size                            | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | -------------- | --------- | ------------------- | ----------------------------------------------------------- | ------------------------------------ | ---------------- | --------------------------------------- | ------------------------------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Hu et al. | 2025 | Classification | BinaryViT | Binary quantization | NVIDIA RTX 6000 GPU server; embedded targets discussed only | Seven hyperspectral image benchmarks | OA 87.70%–97.28% | Testing time 1.09–60.82 s on GPU server | 4,294–6,358 parameters; file size N/A | N/A      | N/A   | N/A    | N/A       | N/A      | None          | No            |
