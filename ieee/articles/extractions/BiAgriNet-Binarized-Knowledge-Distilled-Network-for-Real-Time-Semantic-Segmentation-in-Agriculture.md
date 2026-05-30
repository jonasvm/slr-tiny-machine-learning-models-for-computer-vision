## Paper ID: BiAgriNet-Binarized-Knowledge-Distilled-Network-for-Real-Time-Semantic-Segmentation-in-Agriculture

TinyML classification: Near-TinyML — The work is evaluated on NVIDIA Jetson AGX Orin rather than explicit MCU-class hardware, despite strong model-size, binarization, latency, and energy evidence.

### Basic Info

* Authors: Hassan Khan; Sunbal Iftikhar; Rory Ward; Steven Davy; John G. Breslin
* Year: 2025
* Title: BiAgriNet: Binarized Knowledge-Distilled Network for Real-Time Semantic Segmentation in Agriculture
* Source: IEEE Access, Volume 13, 2025
* Type: Methodological

### Problem & Context

* Task: Semantic segmentation
* Objective: Develop a lightweight, binarized, knowledge-distilled network for real-time agricultural semantic segmentation in resource-constrained environments.
* Application domain: Precision agriculture, crop-weed classification, agricultural field robotics
* Scenario: Edge / embedded agricultural systems
* TinyML relevance: Partial
* TinyML justification: The paper targets real-time, low-power, memory-efficient embedded segmentation and reports model size, FLOPs, FPS, power, and energy on Jetson AGX Orin, but does not report MCU-class deployment.

### Model / Method

* Model: BiAgriNet
* Architecture family: CNN
* Techniques: Full weight-and-activation binarization, binary neural network, knowledge distillation, grouped dilated ASPP, XNOR binarization, teacher-student training
* Framework: PyTorch
* Training type: From scratch with frozen full-precision teacher guidance
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson AGX Orin
* Hardware type: SoC / embedded GPU
* Processor / microcontroller: NVIDIA Jetson AGX Orin
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: 15 W active power; 5 W idle-to-active increase reported for BiAgriNet
* Energy per inference: 0.028 J/frame
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory footprint, power, latency, compute, energy efficiency, real-time throughput, embedded deployment

### Dataset

* Name: PhenoBench; CWFID
* Type: Public
* Dataset size: PhenoBench has 1,407 training images and 772 validation images; CWFID has 60 RGB images with 162 crop plants and 332 weeds
* Number of classes: PhenoBench has 3 classes; CWFID uses crop, weed, and implicit background
* Input resolution: 1024 × 1024
* Data modality: RGB image

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: 180 FPS on PhenoBench; 187 FPS on CWFID
* Throughput: 12 FPS/W
* Model size: 0.8 MB on PhenoBench; 0.9 MB on CWFID
* Parameters: 0.8 MB memory footprint reported as parameter memory; parameter count not reported
* MACs / FLOPs: 0.62 G FLOPs on PhenoBench; 0.65 G FLOPs on CWFID
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: 0.028 J/frame
* Power consumption: 15 W active power; 5 W idle-to-active increase
* mIoU: 85.6% on PhenoBench; 86.7% on CWFID

### Optimization

* Techniques used: 1-bit binarization, XNOR binary convolutions, teacher-student knowledge distillation, grouped dilated ASPP, lightweight decoder, straight-through estimator
* Quantization: QAT
* Pruning: No
* Knowledge distillation: Yes
* Compression method: Full weight-and-activation binarization to ±1 with scaling factors
* Hardware-specific optimization: Energy and throughput evaluated on NVIDIA Jetson AGX Orin
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 0.8 MB on PhenoBench; 0.9 MB on CWFID
* Energy per inference reported: 0.028 J/frame
* Latency on target device reported: FPS reported, but latency in milliseconds not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper reports strong embedded edge efficiency evidence, but the target hardware is NVIDIA Jetson AGX Orin rather than an MCU-class or bare-metal/RTOS device.

### Benchmarking / Standardization

* Benchmark used: PhenoBench; CWFID
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: BiAgriNet achieves 85.6% mIoU on PhenoBench with 0.8 MB model size, 0.62 G FLOPs, 180 FPS, and 0.028 J/frame on Jetson AGX Orin. On CWFID, it achieves 86.7% mIoU, 0.9 MB model size, 0.65 G FLOPs, and 187 FPS.

### Limitations

* The paper reports future work to deploy BiAgriNet on edge devices for practical validation.
* The paper does not report MCU-class deployment, SRAM usage, flash usage, or execution without a full operating system.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes BiAgriNet, a fully binarized knowledge-distilled CNN for real-time agricultural semantic segmentation with low model size, low FLOPs, high FPS, and reduced energy per frame on embedded edge hardware.

| Paper       | Year | Task                  | Model     | Technique                                   | Device                 | Dataset           | Main Metric                                   | Latency | Model Size     | SRAM/RAM | Flash | Energy        | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | --------------------- | --------- | ------------------------------------------- | ---------------------- | ----------------- | --------------------------------------------- | ------- | -------------- | -------- | ----- | ------------- | --------- | -------- | ------------- | ------------- |
| Khan et al. | 2025 | Semantic segmentation | BiAgriNet | 1-bit binarization + knowledge distillation | NVIDIA Jetson AGX Orin | PhenoBench; CWFID | 85.6% mIoU on PhenoBench; 86.7% mIoU on CWFID | N/A     | 0.8 MB; 0.9 MB | N/A      | N/A   | 0.028 J/frame | PyTorch   | QAT      | None          | No            |
