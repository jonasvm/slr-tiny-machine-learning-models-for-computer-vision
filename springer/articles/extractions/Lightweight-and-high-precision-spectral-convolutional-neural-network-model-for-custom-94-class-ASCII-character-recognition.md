## Paper ID: Lightweight-and-high-precision-spectral-convolutional-neural-network-model-for-custom-94-class-ASCII-character-recognition

TinyML classification: Near-TinyML — relevant edge-oriented computer vision work with lightweight/resource-efficient OCR models, but without explicit microcontroller-class deployment or MCU-level constraints.

### Basic Info

* Authors: Ibrahim Y. Alshareef; Ab Al-Hadi Ab Rahman; Nuzhat Khan; Shahriyar Masud Rizvi; Ali Manzak; Mohd Shahrizal Rusli; Mohammed Sultan Mohammed; Mohamed Khalafalla Hassan
* Year: 2025
* Title: Lightweight and high-precision spectral convolutional neural network model for custom 94-class ASCII character recognition
* Source: Neural Computing and Applications, 37:16883–16904, DOI: 10.1007/s00521-025-11376-2
* Type: Experimental

### Problem & Context

* Task: Classification / optical character recognition
* Objective: Develop a lightweight spectral CNN model for accurate 94-class ASCII character recognition with reduced computational workload and memory cost.
* Application domain: Optical character recognition for printed ASCII characters
* Scenario: Mobile edge computing / resource-constrained environments
* TinyML relevance: Partial
* TinyML justification: The paper targets lightweight CNN inference for mobile edge and resource-constrained environments, but it does not report MCU-class deployment, TensorFlow Lite Micro, SRAM/Flash limits, or bare-metal/RTOS execution.

### Model / Method

* Model: Spectral CNN variants based on VGG7, LeNet5, and AlexNet
* Architecture family: CNN
* Techniques: Spectral-domain CNN processing, single FFT transformation, no inverse FFT, spectral output feature map size optimization, spectral depth optimization, top-d frequency component selection
* Framework: Jupyter platform
* Training type: Not reported
* Inference type: Not reported

### Hardware

* Device: Host workstation
* Hardware type: CPU + GPU
* Processor / microcontroller: 12th Gen Intel Core-i7 CPU and NVIDIA GeForce GTX 3060 GPU
* Clock frequency: CPU 2.5 GHz; GPU 1807 MHz
* SRAM / RAM: 64 GB DDR6 RAM; 8 GB GDDR5 VRAM
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Computational complexity, memory access cost, inference time, energy efficiency, low-resource deployment

### Dataset

* Name: Custom 94-class ASCII character image dataset; MNIST used for comparison
* Type: Custom public dataset for 94-class ASCII; public dataset for MNIST
* Dataset size: 94-class ASCII: 19,078 training samples and 4,770 testing samples; MNIST: 60,000 training samples and 10,000 testing samples
* Number of classes: 94 for ASCII dataset; 10 for MNIST
* Input resolution: 64 × 64 for ASCII character images
* Data modality: Grayscale character images

### Metrics

* Accuracy: 94-class ASCII test accuracy: Spectral VGG7 96.88%, Spectral LeNet5 98.75%, Spectral AlexNet 95.00%; MNIST proposed VGG7 97.50%
* mAP: Not reported
* Precision: 94-class ASCII: Spectral VGG7 98.96%, Spectral LeNet5 99.38%, Spectral AlexNet 96.56%
* Recall: 94-class ASCII: Spectral VGG7 96.88%, Spectral LeNet5 98.75%, Spectral AlexNet 95.00%
* F1-score: 94-class ASCII: Spectral VGG7 97.46%, Spectral LeNet5 98.96%, Spectral AlexNet 95.42%
* Latency: Inference time: Spectral VGG7 0.21 s/image, Spectral LeNet5 0.29 s/image, Spectral AlexNet 0.66 s/image
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Spectral VGG7 28,219 FLOPs, Spectral LeNet5 76,578 FLOPs, Spectral AlexNet 51,597,160 FLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Spectral-domain computation, removal of inverse FFT, output feature map size reduction, output feature map depth reduction, frequency-component selection
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Spectral feature map size and depth optimization
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper does not report MCU-class deployment, SRAM/Flash constraints, TensorFlow Lite Micro, CMSIS-NN, or execution without a full operating system.

### Benchmarking / Standardization

* Benchmark used: Custom 94-class ASCII dataset; MNIST
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: MNIST
* Comparison with baseline models: Yes, spectral CNN models are compared with spatial-domain VGG7, LeNet5, and AlexNet models.
* Comparison with previous works: Yes, the proposed spectral CNN models are compared with previous spectral CNN implementations.
* Reproducibility artifacts available: Dataset

### Results

* Summary: The spectral CNN models achieved high OCR classification performance on the custom 94-class ASCII dataset, with Spectral LeNet5 reaching 98.75% test accuracy and 99.38% precision. Spectral VGG7 had the lowest reported computational workload and memory cost, with 28,219 FLOPs, memory cost of 7,338 units, and 0.21 s/image inference time.

### Limitations

* Practical deployment requires addressing hardware compatibility, efficient spectral computation on embedded processors, and energy optimization.
* Training was conducted on a GPU workstation, and real-world inference on embedded GPUs, mobile AI accelerators, and FPGA-based implementations remains future work.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a lightweight spectral CNN approach for 94-class ASCII character recognition that removes inverse FFT operations and applies spectral feature map size and depth optimization to reduce computational workload and memory cost while maintaining high OCR accuracy.

| Paper            | Year | Task                 | Model        | Technique                                                      | Device                                       | Dataset                       | Main Metric          | Latency      | Model Size | SRAM/RAM              | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---- | -------------------- | ------------ | -------------------------------------------------------------- | -------------------------------------------- | ----------------------------- | -------------------- | ------------ | ---------- | --------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Alshareef et al. | 2025 | Classification / OCR | Spectral CNN | Spectral-domain CNN without IFFT + OFM size/depth optimization | Intel Core-i7 + GeForce GTX 3060 workstation | Custom 94-class ASCII + MNIST | 98.75% test accuracy | 0.21 s/image | N/A        | 64 GB RAM / 8 GB VRAM | N/A   | N/A    | Jupyter   | N/A      | None          | No            |
