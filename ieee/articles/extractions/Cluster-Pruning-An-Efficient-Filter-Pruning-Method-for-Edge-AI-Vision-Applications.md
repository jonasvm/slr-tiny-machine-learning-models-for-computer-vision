## Paper ID: Cluster-Pruning-An-Efficient-Filter-Pruning-Method-for-Edge-AI-Vision-Applications

### Basic Info
- Authors: Chinthaka Gamanayake, Lahiru Jayasinghe, Benny Kai Kiat Ng, Chau Yuen
- Year: 2020
- Title: Cluster Pruning: An Efficient Filter Pruning Method for Edge AI Vision Applications
- Source: IEEE Journal of Selected Topics in Signal Processing, Vol. 14, No. 4
- Type: Methodological

### Problem & Context
- Task: Object detection; people counting using object detection, tracking, and counting
- Objective: Propose a hardware-aware cluster pruning method to reduce inference latency and mitigate accuracy degradation in edge-AI vision applications.
- Application domain: Edge-AI vision; real-time people head counting for smart-building control
- Scenario: Edge, IoT, embedded, low-cost vision system
- TinyML relevance: Partial
- TinyML justification: The paper targets resource-constrained edge/IoT vision inference and deploys models on Raspberry Pi 3 with Intel Movidius-NCS, but it does not report MCU-class deployment, TensorFlow Lite Micro, CMSIS-NN, SRAM/Flash constraints, or execution without a full operating system.

### Model / Method
- Model: SSD-MobileNet; SSD-SqueezeNet; proposed Cluster Pruning method
- Architecture family: CNN
- Techniques: Structured filter pruning; cluster pruning; hardware-aware pruning; intermediate fine-tuning
- Framework: Caffe; Movidius Neural Computing Software Development Kit; mvNCCompiler; OpenCV
- Training type: From scratch on Pascal-VOC for SSD-MobileNet; fine-tuning on Head-Counting dataset; SSD-SqueezeNet pre-trained on Pascal-VOC and fine-tuned on Head-Counting dataset
- Inference type: On-device

### Hardware
- Device: Raspberry Pi 3; Raspberry Pi 3 with Intel Movidius-NCS; 2.10 GHz Intel-Xeon CPU; 2.10 GHz Intel-Xeon CPU with Nvidia GTX-1080Ti; Nvidia Jetson-TX2
- Hardware type: CPU / GPU / NPU / SoC / Other
- Processor / microcontroller: Intel Movidius-NCS / Myriad-VPU; Intel-Xeon CPU; Nvidia GTX-1080Ti; Nvidia Jetson-TX2; Raspberry Pi 3
- Clock frequency: 2.10 GHz for Intel-Xeon CPU
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory consumption, computation complexity, FLOPs, inference latency, hardware workload imbalance, low-cost IoT deployment

### Dataset
- Name: Pascal-VOC; Head-Counting dataset
- Type: Pascal-VOC: public; Head-Counting: private / own-created
- Dataset size: Pascal-VOC: 11,530 training/validation images, 27,450 ROI annotated objects, 6,929 segmentations, 4,952 testing images; Head-Counting: 2,622 training/validation images, 786 testing images
- Number of classes: Pascal-VOC: 20; Head-Counting: 1
- Input resolution: Head-Counting images captured at 304 × 304 and resized to 300 × 300
- Data modality: RGB image / video frames

### Metrics
- Accuracy: 95% correct people counting rate for the edge-AI application
- mAP: Used as object detection accuracy metric; exact numerical mAP values not reported in text
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Without pruning / filter pruning / cluster pruning inference time in ms: Raspberry Pi 3: 4778.18 / 4756.14 / 4461.64; Raspberry Pi 3 + NCS: 84.92 / 86.63 / 82.37; CPU: 215.22 / 215.61 / 195.85; GPU: 22.33 / 21.89 / 21.74; TX2: 104.23 / 97.54 / 94.03
- FPS: Without pruning / filter pruning / cluster pruning FPS: Raspberry Pi 3: 0.186 / 0.192 / 0.204; Raspberry Pi 3 + NCS: 6.346 / 6.331 / 6.427; CPU: 4.467 / 4.940 / 5.031; GPU: 42.389 / 48.450 / 49.361; TX2: 10.335 / 10.659 / 11.004
- Throughput: Reported as FPS
- Model size: Not reported
- Parameters: Approximately 1.25% of parameters pruned in the edge-AI application experiment
- MACs / FLOPs: FLOPs discussed as a pruning objective; exact values not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Cluster pruning; filter pruning; hardware-aware profiling; intermediate fine-tuning
- Quantization: None
- Pruning: Yes
- Knowledge distillation: No
- Compression method: Structured filter pruning using clusters of filters ranked by minimum weight criteria
- Hardware-specific optimization: Yes; optimum cluster size selected from hardware latency and accuracy response; cluster size of 8 identified for Movidius-NCS
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
- Reason: The paper reports edge-AI deployment on Raspberry Pi 3, Intel Movidius-NCS, Jetson-TX2, CPU, and GPU platforms, but does not provide MCU-class deployment, SRAM/Flash usage, energy per inference, TensorFlow Lite Micro, CMSIS-NN, or OS-free execution evidence.

### Benchmarking / Standardization
- Benchmark used: Pascal-VOC; Head-Counting dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Pascal-VOC
- Comparison with baseline models: Yes; conventional filter pruning and unpruned models
- Comparison with previous works: Yes, in related methodology discussion
- Reproducibility artifacts available: Not reported

### Results
- Summary: Cluster pruning reduced inference latency compared with filter pruning across tested hardware setups. In the edge-AI application, cluster pruning achieved inference-time gains of 6.80% on Raspberry Pi 3, 3.00% on Raspberry Pi 3 + NCS, 9.00% on CPU, 2.64% on GPU, and 9.78% on TX2.

### Limitations
- The method requires empirical hardware profiling to identify optimum cluster size.
- The experiments focus on SSD-MobileNet and SSD-SqueezeNet.
- The paper identifies future work on ablation studies for filter-ranking criteria, integration with Network Slimming, extension to AMC and NetAdapt, and evaluation on additional architectures and datasets.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a hardware-aware cluster pruning method that removes convolutional filters in structured groups to improve latency and preserve accuracy for edge-AI vision applications.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Gamanayake et al. | 2020 | Object detection | SSD-MobileNet; SSD-SqueezeNet | Cluster pruning | Raspberry Pi 3 + Intel Movidius-NCS | Pascal-VOC; Head-Counting | 95% people counting rate | 82.37 ms on Raspberry Pi 3 + NCS after cluster pruning | N/A | N/A | N/A | N/A | Caffe; Movidius NCSDK; mvNCCompiler | N/A | None | No |
