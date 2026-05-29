## Paper ID: Light-Weight-Semantic-Segmentation-Network-for-UAV-Remote-Sensing-Images

TinyML classification: Near-TinyML — It targets lightweight UAV/edge vision, but does not explicitly report MCU-class deployment or MCU-level memory constraints.

### Basic Info

* Authors: Siyu Liu; Jian Cheng; Leikun Liang; Haiwei Bai; Wanli Dang
* Year: 2021
* Title: Light-Weight Semantic Segmentation Network for UAV Remote Sensing Images
* Source: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, Vol. 14
* Type: Experimental

### Problem & Context

* Task: Segmentation
* Objective: Propose a lightweight semantic segmentation network with fewer parameters for UAV remote sensing images.
* Application domain: UAV remote sensing image analysis
* Scenario: UAV / edge-oriented remote sensing
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained UAV remote sensing and low-memory onboard/mobile devices, but does not report MCU-class deployment.

### Model / Method

* Model: LWN and LWN-A-F
* Architecture family: CNN
* Techniques: Lightweight CNN design, multiscale feature fusion, spatial attention, channel attention, early fusion
* Framework: PyTorch
* Training type: Transfer learning / fine-tuning
* Inference type: Not reported

### Hardware

* Device: GTX 2080Ti for experiments
* Hardware type: GPU
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Memory, storage, model parameters, deployment difficulty on UAV/mobile devices

### Dataset

* Name: ISPRS Vaihingen; UAVid; UDD6
* Type: Public
* Dataset size: ISPRS Vaihingen has 33 patches; UAVid has 42 UAV image sequences with 10 images each; UDD6 has 141 UAV-borne images
* Number of classes: ISPRS Vaihingen has 6 classes; UAVid has 8 classes; UDD6 has 6 classes
* Input resolution: Training patches split into 512 × 512 with 25% overlap; UAVid images include 4K resolution; UDD6 images are 4000 × 3000 or 4096 × 2160
* Data modality: RGB image and remote sensing image bands

### Metrics

* Accuracy: 88.85% OA on ISPRS Vaihingen; 87.66% OA on UAVid; 88.93% OA on UDD6 for LWN-A-F
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: 87.62 mean F1 on ISPRS Vaihingen; 86.79 mean F1 on UDD6 for LWN-A-F
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: 9M for LWN; 15M for LWN-A-F
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight architecture design, reduced channels, 1 × 1 convolution for channel reduction, multiscale feature fusion, spatial attention, channel attention, early fusion
* Quantization: Not reported
* Pruning: No
* Knowledge distillation: No
* Compression method: Architectural lightweighting through fewer channels and reduced parameters
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
* Reason: The paper proposes a lightweight UAV semantic segmentation model but does not provide MCU-class hardware deployment, SRAM/Flash usage, energy, or latency evidence.

### Benchmarking / Standardization

* Benchmark used: ISPRS Vaihingen; UAVid; UDD6
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset

### Results

* Summary: LWN-A-F achieved 78.38 mIoU and 88.85% OA on ISPRS Vaihingen, 69.02 mIoU and 87.66% OA on UAVid, and 77.19 mIoU and 88.93% OA on UDD6. The proposed models use fewer parameters than larger segmentation networks such as SegNet and DeepLab-V3+.

### Limitations

* The paper does not report deployment on real UAV hardware, MCU-class platforms, memory usage, latency, energy, or power consumption.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a lightweight attention-based semantic segmentation network for UAV remote sensing images using multiscale feature fusion and spatial/channel attention modules.

| Paper      | Year | Task         | Model   | Technique                                                    | Device     | Dataset                      | Main Metric         | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | ------------ | ------- | ------------------------------------------------------------ | ---------- | ---------------------------- | ------------------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Liu et al. | 2021 | Segmentation | LWN-A-F | Lightweight CNN with attention and multiscale feature fusion | GTX 2080Ti | ISPRS Vaihingen; UAVid; UDD6 | 69.02 mIoU on UAVid | N/A     | N/A        | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
