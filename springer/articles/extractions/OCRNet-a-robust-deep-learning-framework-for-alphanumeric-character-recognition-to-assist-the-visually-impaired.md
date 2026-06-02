## Paper ID: OCRNet-a-robust-deep-learning-framework-for-alphanumeric-character-recognition-to-assist-the-visually-impaired

TinyML classification: Near-TinyML — The work uses edge/on-device vision deployment on Raspberry Pi, but does not provide explicit MCU-class deployment or Cortex-M-level memory constraints.

### Basic Info
- Authors: Aishwarya Nagasubramanian; Abdulaziz S. Almazyad; Sakthi Abirami Balakrishnan; Bharath Ram MM; Devisowjanya Potti; Mohammed Zakariah; Deema Mohammed AlSekait
- Year: 2025
- Title: OCRNet a robust deep learning framework for alphanumeric character recognition to assist the visually impaired
- Source: Scientific Reports, 15:41344
- Type: Experimental

### Problem & Context
- Task: Optical character recognition / alphanumeric character classification
- Objective: Develop a robust real-time OCR system for recognizing alphanumeric characters and providing audio feedback for visually impaired users.
- Application domain: Assistive technology for visually impaired users
- Scenario: Edge / embedded assistive device
- TinyML relevance: Partial
- TinyML justification: The system is deployed on Raspberry Pi with TFLite quantization and real-time inference, but no MCU-class deployment or kilobyte-scale memory constraints are reported.

### Model / Method
- Model: OCRNet
- Architecture family: Hybrid CNN / RNN
- Techniques: CNN feature extraction, GRU sequential modeling, depthwise separable convolutions, binarization, dilation, erosion, normalization, dropout, kernel regularization, post-training quantization
- Framework: TensorFlow Lite
- Training type: From scratch
- Inference type: On-device

### Hardware
- Device: Raspberry Pi 4 with USB camera and speaker
- Hardware type: CPU / SoC
- Processor / microcontroller: Quad-core Cortex-A72 processor
- Clock frequency: Not reported
- SRAM / RAM: 4 GB RAM
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Limited computational resources, memory consumption, computational load, latency, portability, affordability

### Dataset
- Name: Kaggle OCR dataset
- Type: Public
- Dataset size: 215,450 images
- Number of classes: 62
- Input resolution: 32 × 32
- Data modality: Character images

### Metrics
- Accuracy: 95%
- mAP: Not reported
- Precision: 94%
- Recall: 95%
- F1-score: 96%
- Latency: 120 ms
- FPS: 8.6 FPS
- Throughput: Not reported
- Model size: 50 MB
- Parameters: 15 million
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Depthwise separable convolutions, post-training quantization, TensorFlow Lite conversion, dropout, kernel regularization
- Quantization: INT8 / PTQ
- Pruning: No
- Knowledge distillation: Not reported
- Compression method: INT8 post-training quantization and depthwise separable convolutions
- Hardware-specific optimization: TensorFlow Lite conversion for Raspberry Pi deployment
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: 50 MB
- Energy per inference reported: Not reported
- Latency on target device reported: 120 ms on Raspberry Pi
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No off-device communication reported
- Candidate for Strict TinyML: No
- Reason: The deployment target is Raspberry Pi 4 with 4 GB RAM, not an MCU-class device, and the paper does not report Cortex-M, TensorFlow Lite Micro, SRAM, Flash, or energy constraints.

### Benchmarking / Standardization
- Benchmark used: Kaggle OCR dataset; MNIST; ICDAR 2013; ICDAR 2015; MLT 2017
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: MNIST, ICDAR 2013, ICDAR 2015, MLT 2017
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Dataset

### Results
- Summary: OCRNet achieved 95% accuracy, 94% precision, 95% recall, and 96% F1-score for alphanumeric OCR. The quantized TFLite model ran on Raspberry Pi with 120 ms inference time and 8.6 FPS, using a 50 MB model with 15 million parameters.

### Limitations
- The system is limited to printed alphanumeric text.
- Handwritten and multilingual content are not covered.
- Energy, power, SRAM usage, and Flash usage are not reported.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes OCRNet, a hybrid CNN-GRU OCR model deployed on Raspberry Pi for real-time alphanumeric character recognition with audio feedback for visually impaired users.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Nagasubramanian et al. | 2025 | OCR / Classification | OCRNet | INT8 PTQ + depthwise separable convolutions | Raspberry Pi 4 | Kaggle OCR dataset | Accuracy 95% | 120 ms | 50 MB | 4 GB RAM device; runtime RAM N/A | N/A | N/A | TensorFlow Lite | INT8 PTQ | None | No |
