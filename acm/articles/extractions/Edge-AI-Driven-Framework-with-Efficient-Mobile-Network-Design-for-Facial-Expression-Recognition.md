## Paper ID: Edge-AI-Driven-Framework-with-Efficient-Mobile-Network-Design-for-Facial-Expression-Recognition

TinyML classification: Near-TinyML — evaluated on laptop/smartphone and edge-cloud hardware rather than explicit MCU-class or TensorFlow Lite Micro deployment.

### Basic Info

* Authors: Yirui Wu, Lilai Zhang, Zonghua Gu, Hu Lu, Shaohua Wan
* Year: 2023
* Title: Edge-AI-Driven Framework with Efficient Mobile Network Design for Facial Expression Recognition
* Source: ACM Transactions on Embedded Computing Systems, Vol. 22, No. 3, Article 57
* Type: Methodological

### Problem & Context

* Task: Classification
* Objective: Improve facial expression recognition in the wild using efficient edge-AI inference with lightweight network design and edge-cloud joint execution.
* Application domain: Facial Expression Recognition
* Scenario: Edge, mobile, edge-cloud inference
* TinyML relevance: Partial
* TinyML justification: The paper targets edge AI and resource-constrained mobile/edge devices, but evaluates on laptop and smartphone hardware rather than MCU-class TinyML devices.

### Model / Method

* Model: ShuffleNet V2-based lightweight backbone with ASP and SFP attention modules
* Architecture family: CNN
* Techniques: Lightweight backbone network, spatial attention, channel attention, edge-cloud partial offloading
* Framework: PyTorch
* Training type: Pre-training and fine-tuning
* Inference type: Hybrid

### Hardware

* Device: Laptop computer and Redmi K30 smartphone; cloud simulated by server machine
* Hardware type: CPU / GPU / SoC / Mobile
* Processor / microcontroller: Laptop Intel i7-9750H CPU; smartphone Qualcomm Snapdragon 730G SoC; cloud server 2.1 GHz E5-2620 processor with Titan 1080Ti GPU
* Clock frequency: Laptop 2.60 GHz base and 4.50 GHz maximum turbo; smartphone 2 × 2.2 GHz and 6 × 1.8 GHz; cloud server 2.1 GHz
* SRAM / RAM: Laptop 8 GB memory; smartphone 6 GB memory; cloud server 10 GB memory
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: No
* Constraints mentioned: Limited computing and memory resources, latency, network bandwidth, communication latency, battery power

### Dataset

* Name: RaFD, FER2013, SFEW
* Type: Public
* Dataset size: RaFD: 4,824 images; FER2013: 28,709 training, 3,589 validation, 3,589 test images; SFEW: 958 training, 436 validation, 372 test images
* Number of classes: RaFD: 8; FER2013: 7; SFEW: 7
* Input resolution: 3 × 224 × 224
* Data modality: RGB image

### Metrics

* Accuracy: RaFD 85.57%; FER2013 63.26%; SFEW 56.81%
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Full model inference time: 27.6 ms on laptop, 62.9 ms on phone
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Full model 1.91M; backbone only 1.26M
* MACs / FLOPs: Full model 0.29G MACs; backbone only 0.15G MACs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight ShuffleNet V2 backbone, ASP spatial attention, SFP frequency/channel attention, edge-cloud partial offloading
* Quantization: None
* Pruning: No
* Knowledge distillation: No
* Compression method: Lightweight network design
* Hardware-specific optimization: Partial offloading of attention modules to reduce latency on resource-constrained edge devices
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 27.6 ms on laptop and 62.9 ms on phone for the full model
* Runs without full operating system: No
* Fully on-device inference: No
* Communication required during inference: Yes, for edge-cloud partial offloading
* Candidate for Strict TinyML: No
* Reason: The paper evaluates edge-cloud and smartphone/laptop inference, but does not report MCU-class deployment, bare-metal/RTOS execution, SRAM/Flash constraints, or TensorFlow Lite Micro deployment.

### Benchmarking / Standardization

* Benchmark used: FER2013, RaFD, SFEW
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: ResNet18, ResNet50, MobileNetV2, EfficientFace, MA-Net, RAN
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed full model achieved 85.57% accuracy on RaFD, 63.26% on FER2013, and 56.81% on SFEW. It used 1.91M parameters and 0.29G MACs, with inference times of 27.6 ms on laptop and 62.9 ms on smartphone.

### Limitations

* The approach is evaluated on laptop and smartphone edge devices rather than MCU-class hardware.
* Energy consumption, power consumption, SRAM usage, Flash usage, and embedded deployment framework are not reported.
* The proposed system relies on cloud communication when using partial offloading.

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

* This paper proposes an edge-AI-driven facial expression recognition framework combining a lightweight ShuffleNet V2-based backbone, ASP and SFP attention modules, and edge-cloud joint inference for low-latency FER in the wild.

| Paper     | Year | Task           | Model                                    | Technique                                                    | Device                                     | Dataset             | Main Metric                                        | Latency                       | Model Size | SRAM/RAM                                         | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | -------------- | ---------------------------------------- | ------------------------------------------------------------ | ------------------------------------------ | ------------------- | -------------------------------------------------- | ----------------------------- | ---------- | ------------------------------------------------ | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Wu et al. | 2023 | Classification | ShuffleNet V2-based backbone + ASP + SFP | Lightweight network design and edge-cloud partial offloading | Laptop, Redmi K30 smartphone, cloud server | RaFD, FER2013, SFEW | Accuracy: 85.57% RaFD, 63.26% FER2013, 56.81% SFEW | 27.6 ms laptop; 62.9 ms phone | N/A        | 8 GB laptop RAM; 6 GB phone RAM; 10 GB cloud RAM | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
