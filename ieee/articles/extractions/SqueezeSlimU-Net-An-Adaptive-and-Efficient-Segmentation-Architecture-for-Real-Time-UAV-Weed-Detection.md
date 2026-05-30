## Paper ID: SqueezeSlimU-Net-An-Adaptive-and-Efficient-Segmentation-Architecture-for-Real-Time-UAV-Weed-Detection

TinyML classification: Near-TinyML — The work targets resource-constrained UAV edge vision on NVIDIA Jetson Nano, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Alina L. Machidon, Andraž Krašovec, Veljko Pejović, Octavian M. Machidon
* Year: 2025
* Title: SqueezeSlimU-Net: An Adaptive and Efficient Segmentation Architecture for Real-Time UAV Weed Detection
* Source: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, Vol. 18, 2025
* Type: Experimental

### Problem & Context

* Task: Segmentation
* Objective: To propose an adaptive and efficient deep learning architecture for real-time UAV-based weed segmentation under resource constraints.
* Application domain: Precision agriculture
* Scenario: UAV edge computing / on-board UAV vision
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained on-device UAV inference with latency, energy, and model-parameter evaluation, but deployment is on NVIDIA Jetson Nano rather than MCU-class hardware.

### Model / Method

* Model: SqueezeSlimU-Net (SSU-Net)
* Architecture family: CNN
* Techniques: Slimmable neural networks, SqueezeNet fire modules, switchable batch normalization, dynamic network width adaptation, lightweight segmentation architecture
* Framework: PyTorch
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson Nano 4 GB
* Hardware type: SoC / GPU edge platform
* Processor / microcontroller: NVIDIA Jetson Nano 4 GB board
* Clock frequency: Not reported
* SRAM / RAM: 4 GB RAM
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: SSU-Net reports approximately 0.033 mAh at 25%, 0.053 mAh at 50%, 0.074 mAh at 75%, and 0.094 mAh at 100% network width
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Energy consumption, inference latency, computational load, battery life, model parameters, real-time FPS, limited UAV onboard processing capacity

### Dataset

* Name: AgriAdapt Weed Detection dataset; Tobacco Aerial Dataset
* Type: Public
* Dataset size: 497 aerial images from the AgriAdapt partition; 936 images from the Tobacco campaign 2 partition
* Number of classes: Original labels include background, crop/salad, and weeds; experiments use binary weed detection by merging background and crop
* Input resolution: 512 × 512 pixels
* Data modality: UAV aerial images

### Metrics

* Accuracy: SSU-Net 100% reports 90.47% on AgriAdapt and 90.97% on Tobacco
* mAP: Not reported
* Precision: Not reported
* Recall: SSU-Net 100% reports 62.89% on AgriAdapt and 61.20% on Tobacco
* F1-score: SSU-Net 100% reports 71.91% on AgriAdapt and 73.57% on Tobacco
* Latency: SSU-Net reports approximately 0.09 s at 25%, 0.11 s at 50%, 0.15 s at 75%, and 0.24 s at 100% network width
* FPS: SSU-Net reports 9.09 FPS at 25%, 6.67 FPS at 50%, 5.13 FPS at 75%, and 4.25 FPS at 100% network width
* Throughput: 4.25–9.09 FPS depending on network width
* Model size: Not reported
* Parameters: 2.5M parameters for SSU-Net 100%
* MACs / FLOPs: Not reported for SSU-Net
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: 0.033–0.094 mAh depending on SSU-Net network width
* Power consumption: Not reported

### Optimization

* Techniques used: Slimmable neural networks, SqueezeNet fire modules, switchable batch normalization, runtime width adaptation, input-based adaptation strategy
* Quantization: Not reported
* Pruning: No for the proposed SSU-Net; pruning is used as a comparison baseline
* Knowledge distillation: No
* Compression method: SqueezeNet fire modules combined with slimmable neural network width scaling
* Hardware-specific optimization: Evaluated on NVIDIA Jetson Nano, but no low-level hardware-specific optimization is reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: 0.033–0.094 mAh depending on SSU-Net width
* Latency on target device reported: 0.09–0.24 s per inference depending on SSU-Net width
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper evaluates on a Linux-based NVIDIA Jetson Nano edge platform and does not report MCU-class deployment, TensorFlow Lite Micro, Cortex-M hardware, or kilobyte-scale SRAM/Flash constraints.

### Benchmarking / Standardization

* Benchmark used: AgriAdapt Weed Detection dataset; Tobacco Aerial Dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Code and public datasets

### Results

* Summary: SSU-Net achieves real-time UAV weed segmentation on NVIDIA Jetson Nano with 4.25–9.09 FPS depending on width. It reduces inference energy consumption by up to 65% with only a small accuracy or IoU reduction and uses fewer parameters than several state-of-the-art segmentation models.

### Limitations

* Requires high-quality training datasets that capture diverse weed appearances, sizes, shapes, and environmental conditions.
* Requires an efficient adaptation algorithm to maximize real-time dynamic width selection under changing operational conditions.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes SqueezeSlimU-Net, an adaptive lightweight U-Net-based segmentation architecture that combines SqueezeNet fire modules and slimmable neural networks for real-time energy-efficient UAV weed detection on edge hardware.

| Paper           | Year | Task         | Model            | Technique                                             | Device                  | Dataset                                          | Main Metric                                              | Latency                                  | Model Size           | SRAM/RAM                      | Flash | Energy                        | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---: | ------------ | ---------------- | ----------------------------------------------------- | ----------------------- | ------------------------------------------------ | -------------------------------------------------------- | ---------------------------------------- | -------------------- | ----------------------------- | ----- | ----------------------------- | --------- | -------- | ------------- | ------------- |
| Machidon et al. | 2025 | Segmentation | SqueezeSlimU-Net | Slimmable Squeeze U-Net with dynamic width adaptation | NVIDIA Jetson Nano 4 GB | AgriAdapt Weed Detection; Tobacco Aerial Dataset | IoU: 58.28% AgriAdapt and 59.67% Tobacco at SSU-Net 100% | 0.09–0.24 s per inference; 4.25–9.09 FPS | N/A; 2.5M parameters | 4 GB RAM device; peak RAM N/A | N/A   | 0.033–0.094 mAh per inference | PyTorch   | N/A      | None          | No            |
