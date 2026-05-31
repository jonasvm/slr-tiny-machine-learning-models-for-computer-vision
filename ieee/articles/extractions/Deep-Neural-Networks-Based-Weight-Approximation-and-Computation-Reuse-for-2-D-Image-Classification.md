## Paper ID: Deep-Neural-Networks-Based-Weight-Approximation-and-Computation-Reuse-for-2-D-Image-Classification

TinyML classification: Near-TinyML — Relevant to edge/IoT image classification and model-efficiency techniques, but it does not explicitly report MCU, Cortex-M, TFLite Micro, or bare-metal/RTOS deployment.

### Basic Info

* Authors: Mohammed F. Tolba, Huruy Tekle Tesfai, Hani Saleh, Baker Mohammad, Mahmoud Al-Qutayri
* Year: 2022
* Title: Deep Neural Networks-Based Weight Approximation and Computation Reuse for 2-D Image Classification
* Source: IEEE Access
* Type: Methodological

### Problem & Context

* Task: Classification
* Objective: Reduce DNN model size, arithmetic operations, memory access, and computation cost for image recognition on resource-constrained edge devices.
* Application domain: Image recognition / image classification
* Scenario: Edge, IoT, mobile, resource-constrained devices
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained IoT edge devices and reduces memory/computation, but does not report MCU-class deployment or TinyML-specific frameworks.

### Model / Method

* Model: LeNet 300-100, LeNet-5, custom CIFAR-10 CNN, ResNet20, AlexNet, VGG16
* Architecture family: CNN
* Techniques: Linear weight approximation, quadratic weight approximation, fixed-point quantization, computation reuse, data reuse, memory reduction
* Framework: Python
* Training type: Retraining from pre-trained models with approximation during training
* Inference type: Not reported

### Hardware

* Device: Proposed custom PE-array architecture; no physical deployment device reported
* Hardware type: Other
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Memory storage, memory access, computation complexity, arithmetic operations, energy efficiency, power resources, inference cost

### Dataset

* Name: MNIST, Fashion-MNIST, CIFAR-10, CIFAR-100, Tiny ImageNet
* Type: Public
* Dataset size: MNIST: 50,000 training and 10,000 test images; Fashion-MNIST: 60,000 training and 10,000 test images; CIFAR-10: 50,000 training and 10,000 test images; CIFAR-100: 60,000 images; Tiny ImageNet: 100,000 training and 10,000 validation images
* Number of classes: MNIST: 10; Fashion-MNIST: 10; CIFAR-10: 10; CIFAR-100: 100; Tiny ImageNet: 200
* Input resolution: MNIST/Fashion-MNIST: 28 × 28; CIFAR-10/CIFAR-100: 32 × 32; Tiny ImageNet: 64 × 64
* Data modality: Grayscale images for MNIST and Fashion-MNIST; color images explicitly reported for CIFAR-100; images for CIFAR-10 and Tiny ImageNet

### Metrics

* Accuracy: MNIST LeNet-5 up to 98.2%; Fashion-MNIST up to 97.54%; CIFAR-10 VGG16 up to 92%; CIFAR-10 ResNet20 up to 90.3%; CIFAR-100 VGG16 up to 67.8%; Tiny ImageNet VGG16 53%
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Reported as storage memory, including 0.587 KB for MNIST LeNet-5 with 4-bit quantization, 27.15 KB for Fashion-MNIST with 4-bit quantization, and 0.084 MB for CIFAR-10 VGG16 case 2
* Parameters: Reported for multiple models, including 1k parameters for MNIST LeNet-5 case 2, 43.4k parameters for Fashion-MNIST case 2, 0.096M convolution parameters for CIFAR-10 VGG16 case 2, and 0.03M convolution parameters for CIFAR-10 ResNet20 case 1
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Linear approximation, quadratic approximation, fixed-point quantization, computation reuse, data reuse, parameter reduction, memory storage reduction
* Quantization: Mixed fixed-point quantization using 8-bit, 7-bit, 6-bit, 5-bit, and 4-bit cases
* Pruning: No
* Knowledge distillation: No
* Compression method: Weight approximation and fixed-point quantization
* Hardware-specific optimization: Proposed computation reuse and data reuse architecture based on PE arrays
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Yes
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper targets edge and IoT constraints but does not report MCU-class hardware, SRAM/Flash deployment, bare-metal/RTOS execution, TensorFlow Lite Micro, CMSIS-NN, or measured on-device latency/energy.

### Benchmarking / Standardization

* Benchmark used: MNIST, Fashion-MNIST, CIFAR-10, CIFAR-100, Tiny ImageNet
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: CIFAR-10, CIFAR-100, Tiny ImageNet, MNIST, Fashion-MNIST
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed approximation and reuse methods reduce parameters, memory storage, and arithmetic operations across LeNet, ResNet20, AlexNet, and VGG16 image classification experiments. Reported compression includes 1211.3× storage reduction for MNIST LeNet-5 and 700× convolution memory compression for CIFAR-10 VGG16 with small accuracy loss.

### Limitations

* The approximation process increases training time.
* Larger linear approximation intervals can reduce classification accuracy.
* Full ImageNet experiments are not reported because of training cost; Tiny ImageNet is used instead.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: Yes
* Reports latency: No
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: No
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a DNN weight approximation and computation reuse method that uses linear and quadratic approximation with fixed-point quantization to reduce memory storage, arithmetic operations, and computation cost for image classification on resource-constrained edge and IoT-oriented systems.

| Paper        | Year | Task           | Model                                                                 | Technique                                                                               | Device                                                             | Dataset                                                  | Main Metric                                                      | Latency | Model Size                                                   | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | -------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | -------------------------------------------------------- | ---------------------------------------------------------------- | ------- | ------------------------------------------------------------ | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Tolba et al. | 2022 | Classification | LeNet-5, LeNet 300-100, ResNet20, AlexNet, VGG16, custom CIFAR-10 CNN | Linear/quadratic weight approximation, fixed-point quantization, computation/data reuse | Proposed custom PE-array architecture; no physical device reported | MNIST, Fashion-MNIST, CIFAR-10, CIFAR-100, Tiny ImageNet | Accuracy: up to 98.2% on MNIST LeNet-5 and 92% on CIFAR-10 VGG16 | N/A     | 0.587 KB to 58.8 MB reported storage depending on model/case | N/A      | N/A   | N/A    | Python    | Mixed    | None          | No            |
