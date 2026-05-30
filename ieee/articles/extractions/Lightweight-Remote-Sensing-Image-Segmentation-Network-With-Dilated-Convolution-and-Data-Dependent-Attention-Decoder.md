## Paper ID: Lightweight-Remote-Sensing-Image-Segmentation-Network-With-Dilated-Convolution-and-Data-Dependent-Attention-Decoder

TinyML classification: Near-TinyML — The work targets efficient edge/embedded vision segmentation but is evaluated on GPU/workstation-style platforms and does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Luyang Liu; Savath Saypadith; Ittetsu Taniguchi; Jinjia Zhou; Hiroki Nishikawa; Takao Onoye
* Year: 2025
* Title: Lightweight Remote Sensing Image Segmentation Network With Dilated Convolution and Data-Dependent Attention Decoder
* Source: IEEE Access, Volume 13, DOI: 10.1109/ACCESS.2025.3631504
* Type: Experimental

### Problem & Context

* Task: Segmentation
* Objective: To propose a lightweight encoder-decoder network for accurate and efficient remote sensing image segmentation under constrained computational budgets.
* Application domain: Remote sensing, urban planning, infrastructure monitoring, environmental analysis, UAV mapping, emergency monitoring
* Scenario: Edge, embedded, UAV/on-board remote sensing systems
* TinyML relevance: Partial
* TinyML justification: The paper targets lightweight and edge-friendly segmentation with model size, FLOPs, peak memory, and latency analysis, but does not report MCU-class deployment or TinyML-specific execution.

### Model / Method

* Model: MobileNetV2 encoder with Light Dilated Convolution module and data-dependent attention decoder
* Architecture family: CNN
* Techniques: Depthwise separable dilated convolution, cascaded dilated convolution, lightweight encoder, SE attention, data-dependent upsampling, tiling-with-overlap inference
* Framework: PyTorch
* Training type: Not reported
* Inference type: Not reported

### Hardware

* Device: Not reported for deployment; experiments conducted on a workstation with NVIDIA RTX 3070 GPU and Intel Core i7-11700 CPU
* Hardware type: GPU / CPU
* Processor / microcontroller: Intel Core i7-11700 CPU; microcontroller not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported; peak GPU memory allocation reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Model size, parameters, FLOPs, peak GPU memory allocation, inference latency, computational cost, memory usage

### Dataset

* Name: WHU Building Dataset; Massachusetts Building Dataset; Foggy WHU Building Dataset; WHU Road Dataset
* Type: Public; synthetic fog variant generated from WHU Building Dataset
* Dataset size: WHU Building Dataset has 8,189 aerial images; WHU Road Dataset has 8,974 satellite images; Massachusetts Building Dataset size not reported
* Number of classes: Not reported
* Input resolution: 512×512 for WHU Building and WHU Road; 1024×1024 for Massachusetts Building
* Data modality: Remote sensing aerial/satellite images

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: 94.77% on WHU Building; 87.06% on Massachusetts Building; 83.78% on WHU Road
* Recall: 93.64% on WHU Building; 70.38% on Massachusetts Building; 79.37% on WHU Road
* F1-score: 94.20% on WHU Building; 77.84% on Massachusetts Building; 81.51% on WHU Road; 93.64% on fog-simulated WHU Building at β=1.0
* Latency: 110.00 ms per 512×512 WHU Building image
* FPS: Not reported
* Throughput: Not reported
* Model size: 7.22 MB
* Parameters: 1.89M
* MACs / FLOPs: 1.79 GFLOPs for 512×512 input; 7.17 GFLOPs for 1024×1024 input
* RAM usage: Peak GPU memory allocation of 42.94 MB for 512×512 input and 129.94 MB for 1024×1024 input
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight MobileNetV2 encoder, Light Dilated Convolution module, depthwise separable convolutions, SE attention, data-dependent upsampling
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Architectural lightweight design using MobileNetV2, depthwise separable dilated convolutions, and reduced-complexity decoder
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 7.22 MB
* Energy per inference reported: Not reported
* Latency on target device reported: 110.00 ms per image on experimental workstation hardware, not on a TinyML target device
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper does not report MCU-class deployment, bare-metal/RTOS execution, TensorFlow Lite Micro, CMSIS-NN, SRAM/Flash usage, or energy measurements on a microcontroller-class device.

### Benchmarking / Standardization

* Benchmark used: WHU Building Dataset; Massachusetts Building Dataset; WHU Road Dataset; fog-simulated WHU Building Dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed model achieves 89.04% IoU on WHU Building using 1.89M parameters, 7.22 MB model size, 1.79 GFLOPs, and 42.94 MB peak GPU memory. It also achieves 63.72% IoU on Massachusetts Building and 68.79% IoU on WHU Road, outperforming lightweight baselines while remaining much smaller than D-LinkNet.

### Limitations

* Formal statistical testing is not reported and is proposed as future work.
* Hardware-specific acceleration and real target-device deployment are not evaluated.
* The robustness evaluation focuses on fog simulation only.
* Multi-class and instance segmentation are left for future work.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a lightweight remote sensing semantic segmentation network combining a MobileNetV2 encoder, Light Dilated Convolution module, and data-dependent attention decoder to improve the accuracy-efficiency trade-off for resource-constrained geospatial vision tasks.

| Paper      | Year | Task         | Model                                                | Technique                                                                                     | Device                                        | Dataset                                                                    | Main Metric                | Latency         | Model Size | SRAM/RAM                 | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | ------------ | ---------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------- | -------------------------------------------------------------------------- | -------------------------- | --------------- | ---------- | ------------------------ | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Liu et al. | 2025 | Segmentation | MobileNetV2 + LDC + data-dependent attention decoder | Lightweight CNN with depthwise separable dilated convolution and SE/data-dependent upsampling | NVIDIA RTX 3070 GPU + Intel Core i7-11700 CPU | WHU Building; Massachusetts Building; WHU Road; fog-simulated WHU Building | IoU 89.04% on WHU Building | 110.00 ms/image | 7.22 MB    | 42.94 MB peak GPU memory | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
