## Paper ID: DSConvNet-A-Lightweight-Architecture-for-Extracting-Image-Features-From-Depthwise-Separable-Convolution-Network-for-Edge-Devices

TinyML classification: Near-TinyML — The work targets edge-device vision and lightweight inference, but the reported deployment evidence is Jetson/CPU-level rather than MCU-class.

### Basic Info
- Authors: Syed Muhammad Raza; Syed Murtaza Hussain Abidi; Md Masuduzzaman; Soo Young Shin
- Year: 2025
- Title: DSConvNet: A Lightweight Architecture for Extracting Image Features From Depthwise Separable Convolution Network for Edge Devices
- Source: IEEE Access
- Type: Experimental / Methodological

### Problem & Context
- Task: Classification
- Objective: Propose and evaluate a lightweight depthwise separable convolutional architecture for efficient multi-class image classification on resource-constrained edge devices.
- Application domain: Image classification, traffic sign recognition, object/category recognition
- Scenario: Edge, embedded, mobile/embedded AI
- TinyML relevance: Partial
- TinyML justification: The paper targets lightweight edge-device image classification and reports latency/parameter/FLOP efficiency, but does not explicitly demonstrate MCU-class or bare-metal/RTOS TinyML deployment.

### Model / Method
- Model: DSConvNet
- Architecture family: CNN
- Techniques: Depthwise separable convolution, lightweight architecture design, model compression, batch normalization, PReLU activation, dropout, ablation studies
- Framework: NCNN, TFLite, and TensorRT are mentioned as compatible inference frameworks; implementation framework not reported.
- Training type: From scratch
- Inference type: On-device

### Hardware
- Device: NVIDIA Jetson Orin NX; CPU-based experiments without GPU acceleration
- Hardware type: SoC / CPU
- Processor / microcontroller: NVIDIA Jetson Orin NX; CPU processor not reported
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory footprint, parameter count, computational cost, FLOPs, latency, limited computational resources, resource-constrained devices

### Dataset
- Name: GTSRB; BTSC; MNIST; Fashion-MNIST; CIFAR-10; CIFAR-100; Imagewoof; Imagenette; Caltech-101
- Type: Public
- Dataset size: GTSRB 51,839 images; BTSC 7,105 samples; MNIST 70,000 images; Fashion-MNIST 70,000 images; CIFAR-10 60,000 images; CIFAR-100 60,000 images; Caltech-101 approximately 9,000 images; Imagewoof and Imagenette size not reported
- Number of classes: GTSRB 43; BTSC 62; MNIST 10; Fashion-MNIST 10; CIFAR-10 10; CIFAR-100 100; Imagewoof 10; Imagenette 10; Caltech-101 101 object categories plus one background class
- Input resolution: GTSRB/BTSC 32×32 RGB; MNIST/Fashion-MNIST 28×28 grayscale; CIFAR-10/CIFAR-100 32×32 RGB; Imagewoof/Imagenette standardized to 224×224; Caltech-101 resized to 300×200
- Data modality: RGB image and grayscale image

### Metrics
- Accuracy: GTSRB 99.10%; BTSC 98.90%; MNIST 99.49%; Fashion-MNIST 99.19%; CIFAR-10 90.10%; CIFAR-100 60.00%; Imagewoof 87.50%; Imagenette 98.00%; Caltech-101 59.12%
- mAP: Not reported
- Precision: Not reported
- Recall: GTSRB sensitivity/recall 99.15%; BTSC sensitivity/recall 98.80%
- F1-score: GTSRB 99.22%; BTSC 98.85%
- Latency: Jetson Orin NX: GTSRB 15.2 ms; BTSC 18.2 ms; comparison table also reports DSConvNet 2.34 ms on GTSRB and 4.56 ms on BTSC
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: 0.245M on GTSRB/BTSC; 0.30M on MNIST/Fashion-MNIST; 1.70M on Imagewoof/Imagenette; 2.30M on CIFAR-10/CIFAR-100; 2.40M on Caltech-101
- MACs / FLOPs: 11.37M FLOPs for DSConvNet in the lightweight model comparison
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Depthwise separable convolution blocks, 2×2 depthwise kernels, stride-based downsampling, pointwise 1×1 convolution, PReLU, batch normalization, dropout, lightweight architecture design
- Quantization: None
- Pruning: No
- Knowledge distillation: No
- Compression method: Architectural compression through depthwise separable convolution and reduced parameter/FLOP design
- Hardware-specific optimization: Evaluation on Jetson Orin NX; compatibility with NCNN, TFLite, and TensorRT mentioned
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Jetson Orin NX latency reported as 15.2 ms on GTSRB and 18.2 ms on BTSC
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper targets edge-device and embedded AI classification but reports deployment on Jetson/CPU-level hardware without MCU-class memory, flash, energy, RTOS, bare-metal, CMSIS-NN, or TensorFlow Lite Micro evidence.

### Benchmarking / Standardization
- Benchmark used: GTSRB; BTSC; MNIST; Fashion-MNIST; CIFAR-10; CIFAR-100; Imagewoof; Imagenette; Caltech-101
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: CIFAR-10; CIFAR-100; MNIST; Fashion-MNIST; Imagenette; Imagewoof; Caltech-101; GTSRB; BTSC
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: DSConvNet achieved high classification accuracy on traffic sign benchmarks, including 99.10% on GTSRB and 98.90% on BTSC, with 0.245M parameters and 11.37M FLOPs. On Jetson Orin NX, it achieved 95.7% accuracy with 15.2 ms latency on GTSRB and 87.2% accuracy with 18.2 ms latency on BTSC.

### Limitations
- The architecture has not yet been validated on large-scale datasets such as ImageNet.
- The paper reports that DSConvNet has not yet been validated beyond classification tasks such as object detection or semantic segmentation.
- The exclusive use of PReLU may not provide the same advantages across all hardware platforms or datasets.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes DSConvNet, a lightweight depthwise separable convolutional architecture for efficient edge-device multi-class image classification with reduced parameters, FLOPs, and latency.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Raza et al. | 2025 | Classification | DSConvNet | Depthwise separable convolution | NVIDIA Jetson Orin NX; CPU | GTSRB; BTSC; MNIST; Fashion-MNIST; CIFAR-10; CIFAR-100; Imagewoof; Imagenette; Caltech-101 | Accuracy: 99.10% GTSRB; 98.90% BTSC | 15.2 ms GTSRB; 18.2 ms BTSC on Jetson Orin NX | N/A | N/A | N/A | N/A | N/A | FP32 | None | No |
