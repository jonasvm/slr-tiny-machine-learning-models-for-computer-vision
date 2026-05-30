## Paper ID: Patch-and-Model-Size-Characterization-for-On-Device-Efficient-ViTs-on-Small-Datasets-Using-12-Quantitative-Metrics

TinyML classification: Near-TinyML — Evaluated for on-device edge AI using platforms such as NVIDIA Jetson TX2 rather than explicit MCU-class, Cortex-M, TFLite Micro, or kilobyte-scale deployment.

### Basic Info

* Authors: Jurn-Gyu Park; Aidar Amangeldi; Nail Fakhrutdinov; Meruyert Karzhaubayeva; Dimitrios Zorbas
* Year: 2025
* Title: Patch and Model Size Characterization for On-Device Efficient-ViTs on Small Datasets Using 12 Quantitative Metrics
* Source: IEEE Access, Volume 13, 2025; DOI 10.1109/ACCESS.2025.3536471
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Characterize and optimize efficient Vision Transformer configurations for small datasets under multi-objective accuracy, latency, memory, power, energy, parameter, and MAC constraints.
* Application domain: General computer vision image classification on small datasets; motivated by privacy-sensitive domains such as healthcare and medicine.
* Scenario: Edge AI, mobile, embedded, on-device ML
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained mobile and edge AI devices and reports latency, memory, power, energy, parameters, and MACs, but evaluation uses an NVIDIA Jetson TX2 edge GPU device and laptop GPU rather than MCU-class hardware.

### Model / Method

* Model: ViT-Tiny variants, including ViT-Ti/16 and ViT-Ti/32, with patch-size and model-size variations.
* Architecture family: ViT
* Techniques: Hierarchical and local search with characterization (HelLo), patch-size tuning, model-size tuning, layer reduction, hidden-dimension tuning, attention-head tuning, MLP-size tuning, multi-objective metric evaluation.
* Framework: TensorFlow; PyTorch additionally used for comparison.
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson TX2 edge AI device; NVIDIA RTX3060 6GB based laptop also used.
* Hardware type: GPU / SoC / Edge device
* Processor / microcontroller: NVIDIA Jetson TX2 with 256-core NVIDIA Pascal GPU, Dual-Core NVIDIA Denver 2 64-bit CPU, Quad-Core ARM Cortex-A57 MPCore; laptop with Intel Quad Core i5-11 Gen CPU and NVIDIA RTX3060 6GB GPU.
* Clock frequency: Jetson TX2 CPU 2.04 GHz; Jetson TX2 memory 1.9 GHz; laptop GPU 1.7 GHz; laptop CPU 3.1 GHz; laptop CPU memory 1.6 GHz; laptop GPU memory 1.6 GHz.
* SRAM / RAM: Jetson TX2 8GB 128-bit LPDDR4; laptop CPU 16GB DDR4 SDRAM and GPU 6GB GDDR6 memory.
* Flash / ROM / Storage: Jetson TX2 32GB eMMC 5.1; laptop 512GB SSD.
* Power consumption: Jetson TX2 power budget 7.5W / 15W; measured power examples include 7117 mW for ViT-Ti/32 baseline and 8798 mW for ViT-Ti/16 baseline.
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, energy, latency, training time, inference time, compute/MACs, model parameters, edge-device resource constraints.

### Dataset

* Name: CIFAR-10
* Type: Public
* Dataset size: 60,000 color images
* Number of classes: 10
* Input resolution: Original 32 × 32 pixels; resized to 224 × 224 pixels.
* Data modality: RGB image

### Metrics

* Accuracy: ViT-Ti/16 baseline 80.14%; ViT-Ti/32 baseline 80.09%; ViT-Ti/16 L+D+M optimized configuration 78.66% within 2% accuracy degradation.
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: ViT-Ti/16 baseline 61 ms on laptop and 264 ms on edge; ViT-Ti/32 baseline 24 ms on laptop and 78 ms on edge; ViT-Ti/16 L+D+M optimized configuration 24 ms on laptop and 87 ms on edge.
* FPS: Not reported
* Throughput: Not reported
* Model size: File size not reported; model size characterized through parameters and MACs.
* Parameters: ViT-Ti/16 baseline 5.68M; ViT-Ti/32 baseline 6.09M; ViT-Ti/16 L+D+M optimized configuration 0.71M.
* MACs / FLOPs: ViT-Ti/16 baseline 1.26G MACs; ViT-Ti/32 baseline 0.28G MACs; ViT-Ti/16 L+D+M optimized configuration 0.19G MACs.
* RAM usage: ViT-Ti/16 baseline 3978 MB laptop GPU memory and 5133 MB edge memory; ViT-Ti/32 baseline 1524 MB laptop GPU memory and 3962 MB edge memory; ViT-Ti/16 L+D+M optimized configuration 1461 MB laptop GPU memory and 2674 MB edge memory.
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: ViT-Ti/16 baseline 8798 mW; ViT-Ti/32 baseline 7117 mW; ViT-Ti/16 L+D+M optimized configuration 7243 mW.

### Optimization

* Techniques used: HelLo hierarchical and local optimization/tuning, patch-size selection, layer reduction, hidden-dimension reduction, MLP-size reduction, attention-head variation, ablation study.
* Quantization: None
* Pruning: Not reported
* Knowledge distillation: No
* Compression method: Model-size reduction through hyper-parameter tuning, including layers, hidden dimension, MLP size, and attention heads.
* Hardware-specific optimization: Device-related characterization on NVIDIA Jetson TX2 using latency, memory, power, energy, and tegrastats measurements.
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Parameters and MACs reported; file size not reported.
* Energy per inference reported: Not reported
* Latency on target device reported: Yes
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper evaluates efficient ViTs on an NVIDIA Jetson TX2 edge GPU/SoC and laptop GPU, but does not report MCU-class deployment, bare-metal or RTOS execution, TensorFlow Lite Micro, CMSIS-NN, SRAM/Flash footprints, or kilobyte-scale embedded constraints.

### Benchmarking / Standardization

* Benchmark used: CIFAR-10
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: CIFAR-10
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Code

### Results

* Summary: The HelLo method achieved improvements up to 85% in MACs, 67.2% in inference latency, 77.7% in training latency/time, 63.3% in GPU memory, 73.8% in energy consumption, and 263.0% in FoM with up to 2% accuracy degradation. Larger patch size and model-size tuning improved latency, memory, and energy efficiency on mobile/edge platforms.

### Limitations

* Evaluation used only the CIFAR-10 dataset, which may limit generalizability to other datasets.
* The paper reports future work on medium-sized datasets and deeper investigation of inference/training differences, GPU parallelism, and memory parallelism on specific frameworks.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a hierarchical and local optimization/tuning method called HelLo to characterize and optimize efficient ViT patch size and model size for resource-constrained mobile and edge AI devices using twelve quantitative metrics.

| Paper       | Year | Task           | Model                    | Technique                       | Device            | Dataset  | Main Metric                                | Latency                                       | Model Size                    | SRAM/RAM                                        | Flash | Energy                       | Framework            | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | -------------- | ------------------------ | ------------------------------- | ----------------- | -------- | ------------------------------------------ | --------------------------------------------- | ----------------------------- | ----------------------------------------------- | ----- | ---------------------------- | -------------------- | -------- | ------------- | ------------- |
| Park et al. | 2025 | Classification | ViT-Tiny / Efficient ViT | HelLo hierarchical local tuning | NVIDIA Jetson TX2 | CIFAR-10 | Accuracy 78.66%; up to 85.0% MAC reduction | 87 ms edge / 24 ms laptop for ViT-Ti/16 L+D+M | 0.71M parameters / 0.19G MACs | 2674 MB edge memory / 1461 MB laptop GPU memory | N/A   | 6286 J/epoch training energy | TensorFlow / PyTorch | N/A      | None          | No            |
