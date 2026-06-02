## Paper ID: random-resistive-memory-based-deep-extreme-point-learning-machine-for-unified-visual-processing

TinyML classification: Near-TinyML — it uses edge AI hardware with a resistive-memory chip and Xilinx ZYNQ SoC, but does not provide explicit MCU-class deployment evidence.

### Basic Info
- Authors: Shaocong Wang; Yizhao Gao; Yi Li; Woyu Zhang; Yifei Yu; Bo Wang; Ning Lin; Hegan Chen; Yue Zhang; Yang Jiang; Dingchen Wang; Jia Chen; Peng Dai; Hao Jiang; Peng Lin; Xumeng Zhang; Xiaojuan Qi; Xiaoxin Xu; Hayden So; Zhongrui Wang; Dashan Shang; Qi Liu; Kwang-Ting Cheng; Ming Liu
- Year: 2025
- Title: Random resistive memory-based deep extreme point learning machine for unified visual processing
- Source: Nature Communications, 16:960, DOI 10.1038/s41467-025-56079-3
- Type: Experimental

### Problem & Context
- Task: 3D point cloud segmentation; event-based gesture recognition; image classification
- Objective: To unify heterogeneous visual sensor data as point sets and process them using a hardware-software co-designed resistive-memory-based deep extreme point learning machine.
- Application domain: Edge-side intelligent machines using LiDAR, dynamic vision sensors, and frame cameras
- Scenario: Edge AI, embedded visual processing, multi-sensor intelligent systems
- TinyML relevance: Partial
- TinyML justification: The paper targets energy-efficient edge AI hardware and on-device visual processing, but it does not report MCU-class deployment or microcontroller-level memory constraints.

### Model / Method
- Model: Random resistive memory-based Deep Extreme Point Learning Machine
- Architecture family: Other
- Techniques: In-memory computing, random fixed weights, sparse resistive memory arrays, weight sharing, point-set representation, hardware-software co-design
- Framework: Not reported
- Training type: Readout-layer training with fixed random encoder/decoder weights
- Inference type: Hybrid

### Hardware
- Device: 40 nm random resistive memory compute-in-memory chip with Xilinx ZYNQ SoC on PCB
- Hardware type: SoC / Other
- Processor / microcontroller: Xilinx ZYNQ SoC
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: 135.11 μJ for ShapeNet segmentation; 31.12 μJ for DVS128 Gesture recognition; 44.68 μJ for Fashion-MNIST classification
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Energy consumption, training complexity, memory footprint, von Neumann bottleneck, hardware footprint, resistive memory read noise

### Dataset
- Name: ShapeNet; DVS128 Gesture; Fashion-MNIST
- Type: Public benchmark datasets
- Dataset size: ShapeNet: 16,874 point clouds; DVS128 Gesture: Not reported; Fashion-MNIST: Not reported
- Number of classes: ShapeNet: 16 object types and 50 part classes; DVS128 Gesture: 10 gesture classes; Fashion-MNIST: 10 classes
- Input resolution: ShapeNet: 2048 points per point cloud; DVS128 Gesture: 128 × 128 sensor with 1024 sampled events per segment; Fashion-MNIST: 28 × 28 grayscale images
- Data modality: 3D point cloud, event stream, grayscale image

### Metrics
- Accuracy: ShapeNet hardware accuracy 83.79%; DVS128 Gesture hardware accuracy 78.73%; Fashion-MNIST hardware accuracy 77.20%
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: ShapeNet: 100.01k total, 94.16k fixed; DVS128 Gesture: 67.59k total, 62.47k fixed; Fashion-MNIST: 100.00k total, 91.81k fixed
- MACs / FLOPs: ShapeNet DEPLM forward pass 131.40 MOPs; ShapeNet backward pass 47.92 MOPs; ShapeNet weight update 11.70 KOPs; Fashion-MNIST overall training complexity 60.26 MOPs
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: ShapeNet 135.11 μJ; DVS128 Gesture 31.12 μJ; Fashion-MNIST 44.68 μJ
- Power consumption: Not reported

### Optimization
- Techniques used: Resistive-memory in-memory computing, sparse random weights, fixed random backbone, trainable readout layer, weight sharing, point-set unification
- Quantization: Not reported
- Pruning: No
- Knowledge distillation: No
- Compression method: Fixed random weights, sparse resistive arrays, weight sharing
- Hardware-specific optimization: Resistive memory crossbar vector-matrix multiplication and hybrid analog-digital processing
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: 135.11 μJ for ShapeNet; 31.12 μJ for DVS128 Gesture; 44.68 μJ for Fashion-MNIST
- Latency on target device reported: Not reported
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper uses a custom resistive-memory chip and Xilinx ZYNQ SoC for edge AI, but does not report MCU-class deployment, TensorFlow Lite Micro, CMSIS-NN, SRAM/Flash usage, or bare-metal/RTOS execution.

### Benchmarking / Standardization
- Benchmark used: ShapeNet; DVS128 Gesture; Fashion-MNIST
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: ModelNet and ImageNet-100 are mentioned in supplementary experiments
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: code / dataset

### Results
- Summary: The hardware DEPLM achieved 66.28% mIoU and 83.79% accuracy on ShapeNet, 78.73% accuracy on DVS128 Gesture, and 77.20% accuracy on Fashion-MNIST. The system reported energy-efficiency improvements of 6.78×, 21.04×, and 15.79×, with training cost reductions of 70.12%, 89.46%, and 85.61% across the three tasks.

### Limitations
- Hardware DEPLM accuracy is lower than fully trained baselines due to fixed random weights and hardware read noise.
- Long-tail ShapeNet classes such as bag, car, and motorbike show degraded performance due to conductance fluctuation and limited samples.
- Distance calculation and readout layers are still performed on the digital component of the hybrid system.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a random resistive-memory-based deep extreme point learning machine that unifies point cloud, event stream, and image processing for energy-efficient edge-side visual AI.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Wang et al. | 2025 | Segmentation; event recognition; classification | DEPLM | Resistive-memory in-memory computing with sparse fixed random weights | 40 nm RRAM chip + Xilinx ZYNQ SoC | ShapeNet; DVS128 Gesture; Fashion-MNIST | ShapeNet: 66.28% mIoU; DVS128: 78.73% accuracy; Fashion-MNIST: 77.20% accuracy | N/A | N/A | N/A | N/A | 135.11 μJ; 31.12 μJ; 44.68 μJ | N/A | N/A | None | No |
