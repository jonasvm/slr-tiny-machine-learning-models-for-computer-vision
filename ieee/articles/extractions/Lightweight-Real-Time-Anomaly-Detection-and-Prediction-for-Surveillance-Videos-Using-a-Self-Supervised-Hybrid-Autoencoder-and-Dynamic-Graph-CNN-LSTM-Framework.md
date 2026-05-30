## Paper ID: Lightweight-Real-Time-Anomaly-Detection-and-Prediction-for-Surveillance-Videos-Using-a-Self-Supervised-Hybrid-Autoencoder-and-Dynamic-Graph-CNN-LSTM-Framework

TinyML classification: Near-TinyML — The paper reports lightweight edge-oriented video inference and compression but does not provide explicit MCU-class deployment evidence.

### Basic Info
- Authors: Abdulla S. AlShamsi; Najah AbuAli
- Year: 2025
- Title: Lightweight Real-Time Anomaly Detection and Prediction for Surveillance Videos Using a Self-Supervised Hybrid Autoencoder and Dynamic Graph CNN-LSTM Framework
- Source: IEEE Access
- Type: Experimental

### Problem & Context
- Task: Anomaly detection
- Objective: Detect and predict anomalies in surveillance videos with high accuracy and real-time efficiency.
- Application domain: Video surveillance and public safety
- Scenario: Edge-oriented real-time surveillance / resource-constrained surveillance environments
- TinyML relevance: Partial
- TinyML justification: The paper targets lightweight real-time inference with pruning, quantization-aware training, model-size reduction, and edge-device relevance, but does not report MCU-class deployment.

### Model / Method
- Model: Hybrid convolutional Autoencoder + Dynamic Graph CNN-LSTM with self-supervised prediction module
- Architecture family: Hybrid CNN / GNN / RNN
- Techniques: Structured pruning, quantization-aware training, PCA dimensionality reduction, self-supervised learning
- Framework: Not reported
- Training type: From scratch
- Inference type: Not reported

### Hardware
- Device: Test system with RTX 4090; Jetson Xavier NX estimated
- Hardware type: GPU / SoC
- Processor / microcontroller: RTX 4090; Jetson Xavier NX
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Not reported
- Constraints mentioned: Latency, computational complexity, memory footprint, real-time processing, resource-constrained deployment

### Dataset
- Name: UCF-Crime
- Type: Public
- Dataset size: 1,900 untrimmed surveillance videos totaling 128 hours
- Number of classes: 14 classes, including 13 anomaly types plus normal scenes
- Input resolution: 64 × 64 for baseline; 32 × 32 for optimized model
- Data modality: Surveillance video frames / RGB image data

### Metrics
- Accuracy: 98% for the optimized model
- mAP: Not reported
- Precision: 0.98 for the optimized model
- Recall: 0.94 for the optimized model
- F1-score: 0.96 for the optimized model
- Latency: ∼1.22 ms/frame total inference time for the optimized model
- FPS: Not reported as FPS; ∼27 simultaneous 30 fps feeds estimated on the RTX 4090 test system
- Throughput: ∼959–1011 images/s for preprocessing, CNN feature extraction, and graph construction; ∼24,383 samples/s for graph inference
- Model size: 0.54 MB after pruning and quantization
- Parameters: 161,742 parameters for the optimized model
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: PCA dimensionality reduction, structured pruning, quantization-aware training
- Quantization: QAT
- Pruning: Yes
- Knowledge distillation: No
- Compression method: Structured pruning and quantization-aware training
- Hardware-specific optimization: Not reported
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: 0.54 MB
- Energy per inference reported: Not reported
- Latency on target device reported: ∼1.22 ms/frame on RTX 4090 test system; ∼12.2 ms/frame estimated for Jetson Xavier NX
- Runs without full operating system: Not reported
- Fully on-device inference: Not reported
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper reports lightweight edge-oriented inference but provides no explicit MCU-class deployment, SRAM/Flash usage, bare-metal or RTOS execution, TensorFlow Lite Micro, or MCU-level energy evidence.

### Benchmarking / Standardization
- Benchmark used: UCF-Crime
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: UCF-Crime
- Comparison with baseline models: Yes, compared against Base, Tuned PCA32, and Optimized variants
- Comparison with previous works: Yes, compared with C3D+SVM, T-CNN, Motion + T-CNN, 3D ConvNet, SVM on C3D, C3D, TDS-Net, BN-WVAD, SSAGAN, and IBaggedFCNet
- Reproducibility artifacts available: Not reported

### Results
- Summary: The optimized model achieved 98% multiclass accuracy, 0.99 multiclass ROC-AUC, 0.91 binary anomaly ROC-AUC, 0.54 MB model size, and ∼1.22 ms/frame inference time after pruning and quantization-aware training.

### Limitations
- The optimized model reduced anomaly detection sensitivity compared with the uncompressed baseline.
- Real-world deployment tests on edge devices are suggested as future work.
- Open-set anomaly recognition and incremental learning are identified as future research needs.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a lightweight real-time surveillance-video anomaly detection framework combining a convolutional autoencoder, Dynamic Graph CNN-LSTM, self-supervised prediction, PCA reduction, structured pruning, and quantization-aware training.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| AlShamsi et al. | 2025 | Anomaly detection | Hybrid Autoencoder + Dynamic Graph CNN-LSTM | Pruning + QAT + PCA | RTX 4090 test system; Jetson Xavier NX estimated | UCF-Crime | 98% accuracy; 0.99 multiclass ROC-AUC | ∼1.22 ms/frame | 0.54 MB | N/A | N/A | N/A | N/A | QAT | None | No |
