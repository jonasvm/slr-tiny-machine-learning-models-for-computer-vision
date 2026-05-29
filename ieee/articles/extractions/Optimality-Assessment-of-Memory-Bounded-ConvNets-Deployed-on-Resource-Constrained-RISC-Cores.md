## Paper ID: Optimality-Assessment-of-Memory-Bounded-ConvNets-Deployed-on-Resource-Constrained-RISC-Cores

TinyML classification: Strict TinyML — Explicitly evaluates memory-bounded deployment on Cortex-M MCUs using CMSIS-NN and NUCLEO boards with 256–512 kB RAM constraints.

### Basic Info

* Authors: Matteo Grimaldi, Valentino Peluso, Andrea Calimera
* Year: 2019
* Title: Optimality Assessment of Memory-Bounded ConvNets Deployed on Resource-Constrained RISC Cores
* Source: IEEE Access, Volume 7, DOI: 10.1109/ACCESS.2019.2948577
* Type: Methodological

### Problem & Context

* Task: Image classification, facial expression recognition, and keyword spotting
* Objective: Assess memory-bounded ConvNet implementations and quantify the distance between theoretical optimal configurations and hardware-compliant deployments on low-power RISC cores.
* Application domain: IoT applications, robotics, human-machine interface, and retail
* Scenario: Embedded IoT, mobile edge, MCU-class deployment
* TinyML relevance: Yes
* TinyML justification: The paper targets ConvNet deployment on ARM Cortex-M microcontroller-class RISC cores with few hundred KB of RAM and explicit memory constraints.

### Model / Method

* Model: Memory-bounded ConvNets optimized with the Prune-and-Quantize framework
* Architecture family: CNN
* Techniques: Filter pruning, weight quantization, hardware-aware compression, memory-driven heuristic optimization, fixed-point emulation, fine-tuning
* Framework: PyTorch, CMSIS-NN, GNU Arm Embedded toolchain
* Training type: From scratch and fine-tuning
* Inference type: On-device for hardware-compliant models; emulated for non-hardware-compliant bit-widths

### Hardware

* Device: NUCLEO-F412ZG and NUCLEO-F767ZI
* Hardware type: MCU
* Processor / microcontroller: ARM Cortex-M4 and ARM Cortex-M7
* Clock frequency: 100 MHz and 216 MHz
* SRAM / RAM: 256 KB and 512 KB
* Flash / ROM / Storage: 1 MB and 2 MB Flash
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Yes
* Fully on-device inference: Yes
* Constraints mentioned: Memory footprint, on-chip RAM, latency, energy budget, arithmetic bit-width, compute limitations, lack of floating-point support on some MCUs

### Dataset

* Name: CIFAR-10; Speech Commands Dataset; FER2013
* Type: Public
* Dataset size: CIFAR-10 has 50,000 training and 10,000 test images; Speech Commands has 65k audio samples with 56,196 training and 7,518 test samples; FER2013 has 32,297 images with 28,708 training and 3,589 test images
* Number of classes: CIFAR-10 has 10 classes; Speech Commands task has 12 classes; FER2013 has 7 classes
* Input resolution: CIFAR-10 uses 32 × 32 RGB images; Speech Commands uses 32 × 40 spectrogram inputs; FER2013 uses 48 × 48 grayscale images
* Data modality: RGB image, grayscale image, audio spectrogram

### Metrics

* Accuracy: Floating-point baselines are 82.80% for IC, 86.75% for KWS, and 66.48% for FER; best reported PaQ points are 83.10% for IC, 86.80% for KWS, and 66.84% for FER
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: KWS PaQ-8 reports 10–94 ms on NUCLEO-F767ZI and 48–235 ms on NUCLEO-F412ZG depending on target memory
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported as standalone model file size
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Target memory constraints are reported from 33 KB to 1062 KB across benchmark configurations
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Memory-driven filter pruning, fixed-point quantization, pruning-and-quantization co-optimization, hardware-aware memory allocation, fine-tuning
* Quantization: Mixed precision
* Pruning: Yes
* Knowledge distillation: No
* Compression method: Joint filter pruning and weight quantization
* Hardware-specific optimization: Cortex-M-aware memory model, CMSIS-NN deployment, hardware-compliant 8-bit and 16-bit implementations
* Use of CMSIS-NN: Yes
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Target memory constraints are reported, and deployment boards have 256 KB and 512 KB RAM
* Flash usage reported: Not reported
* Model size reported: Not reported as standalone model file size
* Energy per inference reported: Not reported
* Latency on target device reported: Yes, for KWS PaQ-8 on NUCLEO-F412ZG and NUCLEO-F767ZI
* Runs without full operating system: Yes
* Fully on-device inference: Yes
* Communication required during inference: No cloud or offloaded inference reported
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly deploys compressed ConvNets on ARM Cortex-M MCU boards using CMSIS-NN under few-hundred-KB RAM constraints.

### Benchmarking / Standardization

* Benchmark used: CIFAR-10, Speech Commands Dataset, FER2013
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: CIFAR-10, Speech Commands Dataset, FER2013
* Comparison with baseline models: Yes
* Comparison with previous works: No quantitative comparison with previous works reported
* Reproducibility artifacts available: Not reported

### Results

* Summary: The paper shows that hardware-compliant 8-bit PaQ implementations are usually close to Pareto-optimal memory-accuracy configurations. It also reports that memory compression improves latency proportionally on Cortex-M boards for the KWS benchmark.

### Limitations

* Not reported as a dedicated limitations section.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a hardware-aware Prune-and-Quantize framework for exploring memory-accuracy trade-offs and assessing deployable ConvNet configurations on resource-constrained Cortex-M RISC cores.

| Paper           | Year | Task                                                                  | Model    | Technique                            | Device                       | Dataset                            | Main Metric                                       | Latency                                    | Model Size | SRAM/RAM                                  | Flash                           | Energy | Framework         | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---: | --------------------------------------------------------------------- | -------- | ------------------------------------ | ---------------------------- | ---------------------------------- | ------------------------------------------------- | ------------------------------------------ | ---------- | ----------------------------------------- | ------------------------------- | ------ | ----------------- | -------- | ------------- | ------------- |
| Grimaldi et al. | 2019 | Image classification; facial expression recognition; keyword spotting | ConvNets | Memory-driven pruning + quantization | NUCLEO-F412ZG; NUCLEO-F767ZI | CIFAR-10; FER2013; Speech Commands | Top-1 accuracy: 83.10% IC, 86.80% KWS, 66.84% FER | KWS PaQ-8: 10–94 ms on F7; 48–235 ms on F4 | N/A        | 256 KB / 512 KB RAM; target Mt 33–1062 KB | 1 MB / 2 MB capacity; usage N/A | N/A    | PyTorch; CMSIS-NN | Mixed    | CMSIS-NN      | Yes           |
