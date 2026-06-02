## Paper ID: In-sensor-compressing-via-programmable-optoelectronic-sensors-based-on-van-der-Waals-heterostructures-for-intelligent-machine-vision

TinyML classification: Near-TinyML — relevant to edge/on-device machine vision using efficient in-sensor computing, but no explicit microcontroller-class deployment or MCU-level constraints are reported.

### Basic Info
- Authors: Haoxin Huang, Shuhui Shi, Jiajia Zha, Yunpeng Xia, Huide Wang, Peng Yang, Long Zheng, Songcen Xu, Wei Wang, Yi Ren, Yongji Wang, Ye Chen, Hau Ping Chan, Johnny C. Ho, Yang Chai, Zhongrui Wang, Chaoliang Tan
- Year: 2025
- Title: In-sensor compressing via programmable optoelectronic sensors based on van der Waals heterostructures for intelligent machine vision
- Source: Nature Communications
- Type: Experimental

### Problem & Context
- Task: Video classification and in-sensor visual data compression
- Objective: Develop a programmable optoelectronic sensor that integrates sensing, memory, compression, and computing for efficient machine vision at the edge.
- Application domain: Intelligent machine vision, video compression, spectral imaging, edge visual systems
- Scenario: Edge, in-sensor computing, intelligent vision system
- TinyML relevance: Partial
- TinyML justification: The paper targets compact and energy-efficient edge machine vision through in-sensor compression and CNN classification, but does not report MCU-class deployment or microcontroller-level memory constraints.

### Model / Method
- Model: Programmable Photoinduced Memory Sensor (PPMS) with CNN-based classification of compressed images
- Architecture family: CNN / Other
- Techniques: In-sensor compression, snapshot compressive imaging, in-sensor convolution, optoelectronic memory, hardware-based encoding
- Framework: Not reported
- Training type: Not reported
- Inference type: On-device / in-sensor computing demonstrated conceptually

### Hardware
- Device: 2D van der Waals heterostructure-based programmable optoelectronic sensor and 3 × 3 sensor array
- Hardware type: Other
- Processor / microcontroller: Not reported
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Not reported
- Constraints mentioned: Bandwidth, storage, latency, power consumption, hardware footprint, system complexity

### Dataset
- Name: Kobe motion video data; Bird hyperspectral data; Weizmann Human Action Dataset
- Type: Public
- Dataset size: Weizmann dataset experiment reports 990 samples
- Number of classes: 10 human action classes for classification
- Input resolution: 256 × 256 for Kobe video frames; 1021 × 703 for Bird hyperspectral data
- Data modality: Binarized video frames, hyperspectral images, compressed 2D visual representations

### Metrics
- Accuracy: 93.18% for compressed-frame classification; 83.43% for single-frame classification; 94.21% for all-frame classification
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported
- FPS: 1000 fps reported as potential frame rate of PPMS encoder
- Throughput: Not reported
- Model size: Not reported
- Parameters: Convolutional parameters reduced by 69% for compressed-frame strategy compared with all-frame classification
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: In-sensor compression, in-sensor convolution, snapshot compressive imaging, optoelectronic AND gate, compressed-frame classification without decompression
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Snapshot compressive imaging using programmable optoelectronic sensor
- Hardware-specific optimization: Sensor-level integration of perception, encoding, compression, memory, and computing
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported
- Runs without full operating system: Not reported
- Fully on-device inference: Not reported
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper presents compact edge-oriented in-sensor machine vision hardware, but does not explicitly target MCU-class deployment or report MCU-level SRAM, Flash, latency, energy, or bare-metal execution evidence.

### Benchmarking / Standardization
- Benchmark used: Weizmann Human Action Dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: The PPMS compressed dynamic videos and hyperspectral data into 2D encodings with an 8:1 compression ratio. Compressed-frame video classification achieved 93.18% accuracy, outperforming single-frame classification at 83.43% and approaching all-frame classification at 94.21%.

### Limitations
- Practical SCI implementation is more complex and requires balancing decompression algorithms and compression processes.
- Device noise level should be improved for high-fidelity pixel value transmission and compression.
- The demonstrated sensor array is small-scale, with scalability only indicated as future potential.

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
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a programmable 2D van der Waals optoelectronic sensor that integrates sensing, memory, snapshot compression, and in-sensor CNN-oriented computing for compact edge machine vision.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Huang et al. | 2025 | Video classification / in-sensor compression | PPMS + CNN | In-sensor snapshot compressive imaging | 2D vdW optoelectronic sensor array | Weizmann Human Action Dataset | Accuracy 93.18% | N/A | N/A | N/A | N/A | N/A | N/A | N/A | None | No |
