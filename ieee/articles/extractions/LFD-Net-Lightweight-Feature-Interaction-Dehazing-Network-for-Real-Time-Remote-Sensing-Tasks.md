## Paper ID: LFD-Net-Lightweight-Feature-Interaction-Dehazing-Network-for-Real-Time-Remote-Sensing-Tasks

TinyML classification: Near-TinyML — The work targets lightweight edge-oriented computer vision, but experiments are reported on PC/GPU hardware rather than explicit MCU-class platforms.

### Basic Info

* Authors: Yizhu Jin, Jiaxing Chen, Feng Tian, and Kun Hu
* Year: 2023
* Title: LFD-Net: Lightweight Feature-Interaction Dehazing Network for Real-Time Remote Sensing Tasks
* Source: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, Vol. 16, 2023
* Type: Experimental

### Problem & Context

* Task: Image dehazing / image restoration; downstream object detection
* Objective: To design a lightweight real-time remote sensing image dehazing network that improves visual quality and downstream object detection under hazy conditions.
* Application domain: Remote sensing, space-air-ground land observation, traffic monitoring, autonomous navigation, disaster relief
* Scenario: Edge-oriented remote sensing terminal platforms and real-time vision tasks
* TinyML relevance: Partial
* TinyML justification: The paper targets lightweight edge-oriented real-time vision under limited power and compute resources, but reports experiments on PC/GPU hardware without MCU-class deployment evidence.

### Model / Method

* Model: LFD-Net
* Architecture family: CNN
* Techniques: Lightweight CNN design, reformulated atmospheric scattering model, multiscale convolution, gated fusion module, channelwise attention, pixelwise attention, elementwise feature interaction
* Framework: Not reported
* Training type: Training on RESIDE OTS and fine-tuning on AID for remote sensing experiments
* Inference type: Not reported

### Hardware

* Device: PC with R9-5900HX CPU (E5-1650) and NVIDIA RTX-3080 GPU
* Hardware type: CPU / GPU
* Processor / microcontroller: R9-5900HX CPU (E5-1650); NVIDIA RTX-3080 GPU
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Limited power, limited computing resources, computational cost, inference efficiency, data transmission cost, real-time response

### Dataset

* Name: RESIDE OTS, SOTS, HSTS; O-HAZE; AID; RICE / RICE1; DAIR-V2X; VisDrone2019
* Type: Public benchmark datasets and synthetic hazy image variants for DAIR-V2X and VisDrone2019
* Dataset size: SOTS: 492 JPG images; O-HAZE: 45 JPG images; RICE1: 500 PNG images; DAIR-V2X: 100 selected images; VisDrone2019: 100 selected images
* Number of classes: Not reported
* Input resolution: Not reported
* Data modality: RGB image

### Metrics

* Accuracy: Not reported
* mAP: mAP@0.5 improved by 4.73% on DAIR-V2X and 0.81% on VisDrone2019 after LFD-Net dehazing
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: 54.41 on SOTS; 14.65 on O-HAZE; 45.51 on RICE1
* Throughput: 54.41 FPS on SOTS; 14.65 FPS on O-HAZE; 45.51 FPS on RICE1
* Model size: Not reported
* Parameters: 0.086M
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight architecture design, atmospheric scattering model reformulation, gated fusion, attention mechanism, elementwise feature interaction, reduced parameter count
* Quantization: Not reported
* Pruning: No
* Knowledge distillation: No
* Compression method: Lightweight architecture design; no explicit pruning or quantization-based compression reported
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
* Reason: The paper reports lightweight edge-oriented computer vision experiments, but does not provide MCU-class hardware, SRAM, Flash, energy, bare-metal, RTOS, TensorFlow Lite Micro, or CMSIS-NN deployment evidence.

### Benchmarking / Standardization

* Benchmark used: RESIDE SOTS, HSTS, O-HAZE, RICE1, DAIR-V2X, VisDrone2019
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: SOTS, O-HAZE, RICE1, DAIR-V2X, VisDrone2019
* Comparison with baseline models: DCP, AOD-Net, GridDehazeNet, Wavelet-U-Net, GCA-Net, FFA-Net, D4, MSBDN, DehazeFormer
* Comparison with previous works: Yes
* Reproducibility artifacts available: code / model

### Results

* Summary: LFD-Net achieved 54.41 FPS on SOTS, 14.65 FPS on O-HAZE, and 45.51 FPS on RICE1, with 0.086M parameters. After dehazing, YOLOv5-based mAP@0.5 improved by 4.73% on DAIR-V2X and 0.81% on VisDrone2019.

### Limitations

* The paper states that there is no dataset with built-in synthetic hazed images for object detection, so synthetic hazy images were generated.
* The paper notes that randomly selected real-world hazy images may not be representative of specific datasets and that accurately verifying generalization is challenging.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes LFD-Net, a lightweight CNN-based feature-interaction dehazing network using a reformulated atmospheric scattering model, gated fusion, and attention mechanisms for real-time remote sensing vision tasks.

| Paper      | Year | Task                                            | Model   | Technique                                             | Device                                        | Dataset                                            | Main Metric                | Latency           | Model Size             | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | ----------------------------------------------- | ------- | ----------------------------------------------------- | --------------------------------------------- | -------------------------------------------------- | -------------------------- | ----------------- | ---------------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Jin et al. | 2023 | Image dehazing / object detection preprocessing | LFD-Net | Lightweight CNN with ASM, gated fusion, and attention | PC with R9-5900HX CPU and NVIDIA RTX-3080 GPU | RESIDE/SOTS, O-HAZE, RICE1, DAIR-V2X, VisDrone2019 | mAP@0.5 +4.73% on DAIR-V2X | 54.41 FPS on SOTS | N/A; 0.086M parameters | N/A      | N/A   | N/A    | N/A       | N/A      | None          | No            |
