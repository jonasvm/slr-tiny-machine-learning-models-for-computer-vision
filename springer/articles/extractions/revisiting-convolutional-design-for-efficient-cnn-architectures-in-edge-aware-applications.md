## Paper ID: revisiting-convolutional-design-for-efficient-cnn-architectures-in-edge-aware-applications

TinyML classification: Near-TinyML — the work targets Raspberry Pi 5, Coral Dev Board, and Jetson Nano edge platforms, but does not provide explicit MCU-class deployment evidence.

### Basic Info
- Authors: Onur Erdem Korkmaz
- Year: 2025
- Title: Revisiting convolutional design for efficient CNN architectures in edge-aware applications
- Source: Scientific Reports, 15:44351, Springer Nature
- Type: Benchmark

### Problem & Context
- Task: Classification
- Objective: Systematically evaluate five convolutional operations integrated into ResNet-50 for efficient CNN inference on edge AI platforms.
- Application domain: Edge-aware computer vision
- Scenario: Edge AI, embedded systems, real-time inference, resource-constrained applications
- TinyML relevance: Partial
- TinyML justification: The paper targets edge AI devices such as Raspberry Pi 5, Coral Dev Board, and Jetson Nano, but does not report MCU-class deployment or bare-metal/RTOS execution.

### Model / Method
- Model: ResNet-50 variants with standard 2D spatial, grouped, shuffle, depthwise separable, and shift convolutions
- Architecture family: CNN
- Techniques: Hardware-aware convolutional design, grouped convolution, channel shuffle, depthwise separable convolution, shift operation, runtime decomposition
- Framework: PyTorch
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: Raspberry Pi 5; Google Coral Dev Board; NVIDIA Jetson Nano; CPU; NVIDIA A40 GPU
- Hardware type: CPU / GPU / NPU / SoC
- Processor / microcontroller: Raspberry Pi 5 Quad-core Cortex-A76 @ 2.4GHz; Coral Dev Board Quad-core Cortex-A53 @ 1.5GHz with Edge TPU; Jetson Nano Quad-core Cortex-A57 @ 1.43GHz with 128-core Maxwell GPU; Intel Core i7 CPU; NVIDIA A40 GPU
- Clock frequency: Raspberry Pi 5 2.4GHz; Coral Dev Board 1.5GHz; Jetson Nano 1.43GHz; CPU 2.2GHz
- SRAM / RAM: Raspberry Pi 5 8 GB LPDDR4; Coral Dev Board 1 GB LPDDR4; Jetson Nano 4 GB LPDDR4
- Flash / ROM / Storage: Not reported
- Power consumption: Tiny ImageNet edge-device power ranges were 6.1–7.9 W on Raspberry Pi 5, 1.7–2.5 W on Coral Dev Board, and 4.3–6.0 W on Jetson Nano
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory access, power consumption, latency, computational cost, FLOPs, parameter count, real-time inference

### Dataset
- Name: Tiny-ImageNet; CIFAR-10; CIFAR-100
- Type: Public
- Dataset size: Tiny-ImageNet has 120k images; CIFAR-10 and CIFAR-100 each have 50,000 training and 10,000 test images
- Number of classes: Tiny-ImageNet 200; CIFAR-10 10; CIFAR-100 100
- Input resolution: Tiny-ImageNet 64 × 64; CIFAR-10/100 32 × 32
- Data modality: Image

### Metrics
- Accuracy: Tiny-ImageNet Top-1/Top-5: Standard 61.32%/80.85%; Grouped 62.40%/83.63%; Shuffle 63.13%/85.02%; Depthwise Separable 59.42%/78.27%; Shift 58.13%/77.82%
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Tiny-ImageNet edge-device inference ranged from 17.0–22.1 ms on Raspberry Pi 5, 5.1–7.3 ms on Coral Dev Board, and 4.3–6.1 ms on Jetson Nano
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Tiny-ImageNet variants used 0.92M, 0.51M, 0.37M, 0.24M, and 0.17M parameters for standard, grouped, shuffle, depthwise separable, and shift variants, respectively
- MACs / FLOPs: Tiny-ImageNet variants used 3920M, 2010M, 1660M, 997M, and 345M FLOPs for standard, grouped, shuffle, depthwise separable, and shift variants, respectively
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Tiny-ImageNet edge-device power ranged from 1.7 W to 7.9 W depending on model and platform

### Optimization
- Techniques used: Convolutional operator substitution, grouped convolution, channel shuffle, depthwise separable convolution, shift operation, hardware-aware benchmarking
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Lightweight convolutional design through reduced parameters and FLOPs
- Hardware-specific optimization: Edge-platform runtime profiling and hardware-aware analysis
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Yes
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper evaluates edge AI platforms with relaxed memory and operating-system constraints, and does not provide MCU-class deployment evidence.

### Benchmarking / Standardization
- Benchmark used: Tiny-ImageNet; CIFAR-10; CIFAR-100
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Tiny-ImageNet, CIFAR-10, CIFAR-100
- Comparison with baseline models: Yes, against standard ResNet-50 with 2D spatial convolutions
- Comparison with previous works: Yes, discussed against related edge benchmarking and convolutional design literature
- Reproducibility artifacts available: dataset

### Results
- Summary: Shuffle convolution achieved the highest Tiny-ImageNet Top-1 accuracy at 63.13% while reducing parameters and FLOPs compared with standard ResNet-50. Shift convolution achieved the lowest parameter count and FLOPs and generally provided the fastest or most power-efficient inference across edge platforms, while depthwise separable convolution showed memory-bound inefficiencies.

### Limitations
- The study focuses on offline inference benchmarking rather than online QPS-based deployment.
- CUDA Graphs, Torch Compile, TVM, MNN, KleidiAI, ArmNN, and OpenMP optimizations were not evaluated.
- Memory-bound behavior was inferred mainly from parameters and FLOPs rather than direct low-level memory bandwidth or cache profiling.
- On-device training and fine-tuning were not evaluated.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a systematic hardware-aware benchmark of five convolutional variants integrated into ResNet-50 to analyze accuracy, latency, power consumption, parameters, FLOPs, and runtime behavior across edge AI platforms.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Korkmaz et al. | 2025 | Classification | ResNet-50 variants | Convolutional operator substitution | Raspberry Pi 5; Coral Dev Board; Jetson Nano | Tiny-ImageNet; CIFAR-10; CIFAR-100 | 63.13% Top-1 accuracy | 4.3–22.1 ms | N/A | N/A | N/A | N/A | PyTorch | N/A | None | No |
