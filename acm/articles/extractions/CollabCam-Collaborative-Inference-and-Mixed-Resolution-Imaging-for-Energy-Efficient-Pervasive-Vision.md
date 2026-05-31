## Paper ID: CollabCam-Collaborative-Inference-and-Mixed-Resolution-Imaging-for-Energy-Efficient-Pervasive-Vision

TinyML classification: Near-TinyML — The paper targets edge/embedded vision with Raspberry Pi and edge-node inference, but does not explicitly demonstrate MCU-class TinyML deployment.

### Basic Info
- Authors: Amit Sharma, Vithurson Subasharan, Manoj Gulati, Dhanuja Wanniarachchi, Archan Misra
- Year: 2025
- Title: CollabCam: Collaborative Inference and Mixed-Resolution Imaging for Energy-Efficient Pervasive Vision
- Source: ACM Transactions on Internet Things, Vol. 6, No. 3, Article 17, July 2025
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: Reduce energy consumption and network traffic in multi-camera pervasive vision by combining mixed-resolution imaging with collaborative edge inference.
- Application domain: Multi-camera surveillance, campus monitoring, urban/pervasive vision sensing
- Scenario: Edge, embedded, IoT, pervasive multi-camera vision
- TinyML relevance: Partial
- TinyML justification: The paper targets low-power edge vision using Raspberry Pi camera nodes and energy-aware image transmission, but DNN inference is executed on an edge node and no MCU-class deployment is demonstrated.

### Model / Method
- Model: Collab-YOLO and Collab-SSD
- Architecture family: CNN
- Techniques: Mixed-resolution imaging, collaborative inference, peer-camera bounding-box priors, spatial overlap estimation, coordinate mapping, image down-sampling
- Framework: Darknet for YOLOv3; Keras-based SSD512 implementation; modified Raspberry Pi camera driver
- Training type: Fine-tuning / retraining
- Inference type: Offloaded edge inference

### Hardware
- Device: Raspberry Pi 3B with Raspberry Pi Camera Module v2; edge node for DNN inference
- Hardware type: CPU / SoC / edge device
- Processor / microcontroller: Broadcom BCM2837 quad-core 64-bit ARM Cortex-A53
- Clock frequency: 1.2 GHz
- SRAM / RAM: 1 GB LPDDR2 SDRAM
- Flash / ROM / Storage: Not reported
- Power consumption: Raspberry Pi baseline power consumption approximately 500 mW
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: No
- Constraints mentioned: Energy, network bandwidth, image transmission overhead, resolution, edge computation, communication overhead

### Dataset
- Name: PETS, WILDTRACK, CAMPUS, CityFlow, Unity synthetic datasets
- Type: Public / private / synthetic
- Dataset size: WILDTRACK uses approximately 2,800 frames; CAMPUS includes 1,900+ frames, 7,800 annotated bounding boxes, and 260+ unique persons; PETS size not reported
- Number of classes: Human/person detection in main experiments; car and person in additional multi-class CityFlow/WILDTRACK experiment
- Input resolution: WILDTRACK 1920x1080; PETS 720x576; CAMPUS 1056x1056; Collab-YOLO uses 1056x1056 images; Collab-SSD uses 512x512 images
- Data modality: RGB images / multi-camera video frames

### Metrics
- Accuracy: Reported mainly as object detection mAP
- mAP: Collab-DNNs support approximately 50–60x image-size reduction with about 2–5% mAP loss; Table 1 reports mAP of 0.847 for PETS, 0.683 for WILDTRACK, and 0.807 for CAMPUS with one collaborator at reduced shared-region resolution
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported
- FPS: CAMPUS prototype transfers mixed-resolution images at 8 FPS; other FPS values are used for profiling assumptions
- Throughput: Network traffic reduction of approximately 41–45% across datasets and approximately 40% in live deployment
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Raspberry Pi baseline power consumption approximately 500 mW

### Optimization
- Techniques used: Mixed-resolution image transmission, shared-region down-sampling, collaborative object detection using peer bounding-box priors, camera driver binning/skipping, sensor power optimization
- Quantization: None
- Pruning: No
- Knowledge distillation: No
- Compression method: Image down-sampling and Motion JPEG compression; no model compression reported
- Hardware-specific optimization: Raspberry Pi camera driver modifications for additional binning, row/column skipping, low-resolution capture, and sensor power control
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
- Fully on-device inference: No
- Communication required during inference: Yes
- Candidate for Strict TinyML: No
- Reason: The system uses Raspberry Pi camera nodes and offloads DNN inference to an edge node, with no explicit MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, SRAM, Flash, or fully on-device TinyML deployment evidence.

### Benchmarking / Standardization
- Benchmark used: PETS, WILDTRACK, CAMPUS, CityFlow, Unity synthetic datasets
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: PETS, WILDTRACK, CityFlow
- Comparison with baseline models: Yes, compared against baseline YOLOv3, SSD, independent operation, and partitioned operation
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: CollabCam reduces image size by approximately 50–60x while maintaining object detection accuracy with only about 2–5% mAP loss. The Raspberry Pi prototype reduces system energy by approximately 25–35% and network traffic by approximately 40–45% compared with non-collaborative operation.

### Limitations
- Assumes static cameras with fixed points of view.
- Mobile or PTZ camera scenarios require frequent overlap estimation and coordinate mapping updates.
- Uses spatial correlation only and does not exploit temporal correlation.
- Assumes similar frame rates across collaborating cameras.
- May not suit high-resolution tasks such as license plate recognition.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes CollabCam, an edge-based collaborative multi-camera vision system that combines mixed-resolution imaging with collaborative object detection to reduce energy and network overhead while preserving detection accuracy.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sharma et al. | 2025 | Object detection | Collab-YOLO / Collab-SSD | Mixed-resolution imaging + collaborative inference | Raspberry Pi 3B camera nodes + edge node | PETS / WILDTRACK / CAMPUS / CityFlow / Unity | mAP loss about 2–5% with 50–60x image-size reduction | N/A | N/A | 1 GB RAM available; usage N/A | N/A | 25–35% system energy savings | Darknet / Keras / PiCamera | N/A | None | No |
