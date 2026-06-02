## Paper ID: Nutritional-assessment-system-integrating-semantic-segmentation-and-point-cloud-modeling-techniques

TinyML classification: Near-TinyML — The work targets embedded edge hardware such as Jetson AGX Xavier/Raspberry Pi 5 rather than explicit MCU-class deployment.

### Basic Info
- Authors: Chin-Hsuan Lin; Jung-Tang Huang
- Year: 2025
- Title: Nutritional assessment system integrating semantic segmentation and point cloud modeling techniques
- Source: Scientific Reports, 15:39313
- Type: Experimental

### Problem & Context
- Task: Semantic segmentation, object detection, object tracking, and RGB-D point-cloud volume estimation
- Objective: Automatically monitor home meals by identifying food items, estimating food volume and composition, and supporting nutritional assessment.
- Application domain: Home-based dietary monitoring and nutritional assessment for older adults and chronic-disease care.
- Scenario: Edge, embedded, IoT, smart home, wearable-assisted monitoring.
- TinyML relevance: Partial
- TinyML justification: The system uses an embedded edge platform, Nvidia Jetson AGX Xavier, and mentions Raspberry Pi 5 as a possible substitute, but it does not target MCU-class deployment or report strict TinyML memory, energy, or bare-metal constraints.

### Model / Method
- Model: YOLOv5, MOSSE tracker, DeepLabv3+, Vision Transformer, RANSAC, ICP, DBSCAN, Delaunay triangulation.
- Architecture family: Hybrid CNN / Transformer / Classical point-cloud processing
- Techniques: Object detection, object tracking, semantic segmentation, point-cloud registration, point-cloud clustering, Z-axis origin correction, localized surface projection, Delaunay triangulation, residual RGB point-cloud compression, Hungarian matching.
- Framework: Python implementation; specific deep-learning framework not reported.
- Training type: Not reported
- Inference type: Hybrid edge system with real-time computation on Jetson AGX Xavier and cloud/database upload for data access and visualization.

### Hardware
- Device: Nvidia Jetson AGX Xavier; Intel RealSense D435 depth camera; optional Raspberry Pi 5 substitution.
- Hardware type: SoC / GPU / Edge device / Depth camera / Other
- Processor / microcontroller: Not reported
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Yes, for real-time computation on the Jetson AGX Xavier; cloud/database upload is used for storage and visualization.
- Constraints mentioned: Computational cost, near real-time processing, camera distance, lighting, surface reflectivity, point-cloud sparsity, communication/cloud upload, and robustness in real dining environments.

### Dataset
- Name: Not reported
- Type: Private
- Dataset size: One two-person household trial over approximately two to three months; exact dataset size not reported.
- Number of classes: Not reported
- Input resolution: Not reported
- Data modality: RGB-D images, depth point clouds, RGB images, IMU posture data, BLE Beacon location data.

### Metrics
- Accuracy: Not reported
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported
- FPS: 30 FPS camera sampling reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Distance-threshold filtering, dynamic Z-axis origin correction, RANSAC-ICP registration, DBSCAN clustering, localized surface projection, Delaunay triangulation, and residual RGB point-cloud compression.
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Residual RGB point clouds compressed into 2D images for semantic segmentation; model compression not reported.
- Hardware-specific optimization: Not reported
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported
- Runs without full operating system: No
- Fully on-device inference: Yes, for edge computation on Jetson AGX Xavier; cloud/database upload is used for data management.
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper targets Jetson AGX Xavier and optional Raspberry Pi 5 edge deployment rather than MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, or kilobyte-scale memory-constrained deployment.

### Benchmarking / Standardization
- Benchmark used: Not reported
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Not reported
- Comparison with previous works: Yes, comparison with related dietary assessment and food volume estimation studies in Table 4.
- Reproducibility artifacts available: Dataset available from corresponding author on reasonable request.

### Results
- Summary: The system achieved a maximum volume estimation error of 12.97%, average weight estimation errors below ±10% when sequencing was not applied, and nutrient estimation errors within 20% for protein, fat, carbohydrates, and calories; dietary fiber error reached approximately 28.55%.

### Limitations
- Flexible containers may deform and reduce point-cloud registration and segmentation accuracy.
- Transparent containers cannot be reliably captured by structured-light depth sensing.
- Clear soup-type foods cannot be accurately measured because the depth map may not reflect liquid volume changes.
- Point-cloud segmentation can be affected by camera angle, distance, lighting, surface reflectivity, and sparse point-cloud density.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a home-based nutritional assessment system that combines edge computing, RGB-D sensing, semantic segmentation, object tracking, and point-cloud modeling to estimate meal volume, composition, eating speed, and nutrient intake.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Lin et al. | 2025 | Semantic segmentation / object detection / point-cloud volume estimation | YOLOv5 + DeepLabv3+ + ViT | RGB-D point-cloud modeling with RANSAC, ICP, DBSCAN, and Delaunay triangulation | Nvidia Jetson AGX Xavier + Intel RealSense D435 | Private home meal data | Maximum volume estimation error: 12.97% | N/A | N/A | N/A | N/A | N/A | Python | N/A | None | No |
