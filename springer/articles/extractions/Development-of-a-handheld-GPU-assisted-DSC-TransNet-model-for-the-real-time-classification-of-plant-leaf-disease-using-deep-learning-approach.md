## Paper ID: Development-of-a-handheld-GPU-assisted-DSC-TransNet-model-for-the-real-time-classification-of-plant-leaf-disease-using-deep-learning-approach

TinyML classification: Near-TinyML — The deployment is on an NVIDIA Jetson Nano GPU single-board computer, not an MCU-class platform.

### Basic Info
- Authors: Midhun P. Mathew; Sudheep Elayidom; V. P. Jagathy Raj; K. M. Abubeker
- Year: 2025
- Title: Development of a handheld GPU-assisted DSC-TransNet model for the real-time classification of plant leaf disease using deep learning approach
- Source: Scientific Reports
- Type: Experimental

### Problem & Context
- Task: Classification
- Objective: Real-time classification of bell pepper, grape, and tomato leaf diseases using a hybrid DSC-TransNet deep learning model.
- Application domain: Agriculture / plant disease diagnosis
- Scenario: Edge AI / handheld GPU-assisted agricultural field deployment
- TinyML relevance: Partial
- TinyML justification: The paper targets real-time on-device edge inference on an NVIDIA Jetson Nano with reported latency, RAM usage, model size, and power consumption, but it does not target MCU-class TinyML deployment.

### Model / Method
- Model: DSC-TransNet
- Architecture family: Hybrid CNN + Transformer
- Techniques: Depth-wise separable convolution, transformer encoder blocks, modified VGG19 architecture, attention mechanism, dropout, batch normalization, data augmentation, Bayesian hyperparameter optimization, TensorRT optimizations, quantization-aware training
- Framework: Not reported
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: NVIDIA Jetson Nano single-board computer
- Hardware type: GPU / SoC
- Processor / microcontroller: NVIDIA 128-core Jetson Nano GPU
- Clock frequency: Not reported
- SRAM / RAM: 4 GB RAM capacity; approximately 1 GB RAM usage
- Flash / ROM / Storage: Approximately 1.5 GB disk usage including pre-processed dataset and dependencies
- Power consumption: 5–10 W
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Power, latency, RAM, model size, storage, compute, portability, offline operation, deployment cost

### Dataset
- Name: PlantVillage / public plant leaf disease datasets from Kaggle and GitHub
- Type: Public
- Dataset size: 19,793 non-augmented images; 84,371 images after augmentation and dataset splitting
- Number of classes: 2 for bell pepper, 4 for grape, 10 for tomato
- Input resolution: 256 × 256
- Data modality: Leaf images

### Metrics
- Accuracy: 99.65% for bell pepper, 99.97% for grape, 99.90% for tomato; 99.8% in real-time field analysis
- mAP: Not reported
- Precision: 99.64% for bell pepper, 99.94% for grape, 99.90% for tomato
- Recall: 99.65% for bell pepper, 99.94% for grape, 99.90% for tomato
- F1-score: 99.65% for bell pepper, 99.94% for grape, 99.90% for tomato
- Latency: Approximately 25 ms per image
- FPS: Approximately 40 FPS
- Throughput: Approximately 40 images/second
- Model size: Approximately 15–20 MB compressed
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Approximately 1 GB
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: 5–10 W

### Optimization
- Techniques used: Depth-wise separable convolution, TensorRT optimizations, quantization-aware training, Bayesian hyperparameter optimization, dropout, batch normalization
- Quantization: QAT
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Compressed model size reported as approximately 15–20 MB
- Hardware-specific optimization: TensorRT optimizations for NVIDIA Jetson Nano
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Approximately 15–20 MB compressed
- Energy per inference reported: Not reported
- Latency on target device reported: Approximately 25 ms per image
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: No
- Reason: The model is deployed on an NVIDIA Jetson Nano GPU single-board computer with 4 GB RAM, which is edge AI hardware but not MCU-class TinyML hardware.

### Benchmarking / Standardization
- Benchmark used: PlantVillage / public plant leaf disease datasets
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: dataset

### Results
- Summary: DSC-TransNet achieved very high classification accuracy across bell pepper, grape, and tomato leaf disease datasets, with the best reported accuracy of 99.97% for grape leaves. The model was deployed on NVIDIA Jetson Nano and reported approximately 25 ms latency, 40 images/second throughput, 1 GB RAM usage, and 5–10 W power consumption.

### Limitations
- The evaluation focuses mainly on bell pepper, grape, and tomato leaves.
- Extension to other crops would require additional datasets, domain adaptation, fine-tuning, or transfer learning.
- Larger input resolutions may preserve more detail but increase computational requirements on resource-limited devices.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a handheld GPU-assisted DSC-TransNet model combining depth-wise separable convolution, VGG19-based feature extraction, and transformer encoder blocks for real-time plant leaf disease classification on NVIDIA Jetson Nano.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Mathew et al. | 2025 | Classification | DSC-TransNet | Depth-wise separable convolution + transformer encoder + TensorRT/QAT | NVIDIA Jetson Nano | PlantVillage / public plant disease datasets | Accuracy 99.97% | ~25 ms/image | ~15–20 MB compressed | ~1 GB RAM | N/A | N/A | TensorRT | QAT | None | No |
