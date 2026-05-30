## Paper ID: PG-YOLO-A-Novel-Lightweight-Object-Detection-Method-for-Edge-Devices-in-Industrial-Internet-of-Things

TinyML classification: Near-TinyML — It targets edge-device object detection with pruning, compression, model-size and latency evaluation, but the reported deployment platform is NVIDIA Jetson TX2 rather than an MCU-class device.

### Basic Info
- Authors: Chenhang Dong, Chengxin Pang, Zhengwei Li, Xinhua Zeng, Xing Hu
- Year: 2022
- Title: PG-YOLO: A Novel Lightweight Object Detection Method for Edge Devices in Industrial Internet of Things
- Source: IEEE Access, Volume 10, DOI: 10.1109/ACCESS.2022.3223997
- Type: Methodological

### Problem & Context
- Task: Object detection
- Objective: Develop a smaller and faster object detection model for deployment on edge devices with limited performance in IIoT environments.
- Application domain: Industrial Internet of Things, video surveillance, safety helmet detection
- Scenario: Edge device, IIoT, embedded edge vision
- TinyML relevance: Partial
- TinyML justification: The paper targets lightweight on-device edge inference with model compression and latency reduction, but deployment is evaluated on NVIDIA Jetson TX2 rather than MCU-class hardware.

### Model / Method
- Model: PG-YOLO
- Architecture family: CNN
- Techniques: Ghost modules, LightC3 backbone optimization, sparse training, R-pruning, channel pruning, knowledge distillation, model compression
- Framework: PyTorch
- Training type: From scratch with knowledge distillation
- Inference type: On-device

### Hardware
- Device: NVIDIA Jetson TX2
- Hardware type: SoC / GPU / CPU
- Processor / microcontroller: 256-core NVIDIA Maxwell GPU and dual-core Denver2 CPU
- Clock frequency: Not reported
- SRAM / RAM: 8 GB memory
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Yes
- Constraints mentioned: Limited computing power, storage space, latency, model size, computation, real-time inference

### Dataset
- Name: Safety-Helmet-Wearing Dataset (SHWD)
- Type: Not reported
- Dataset size: 7,571 images; 5,450 training, 1,515 test, 606 validation
- Number of classes: Not reported
- Input resolution: Not reported
- Data modality: Image

### Metrics
- Accuracy: Not reported
- mAP: 0.933 mAP@0.5
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: 32.9 ms on NVIDIA Jetson TX2
- FPS: 30.3 FPS
- Throughput: Not reported
- Model size: 1.6 MB
- Parameters: 0.63M
- MACs / FLOPs: 4.3 GFLOPs
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Ghost convolution replacement, LightC3 backbone simplification, sparse training, R-pruning, channel pruning, knowledge distillation
- Quantization: None
- Pruning: Yes
- Knowledge distillation: Yes
- Compression method: Channel pruning with R-pruning and knowledge distillation
- Hardware-specific optimization: R-pruning restores channels to powers of two to improve GPU inference efficiency
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: 1.6 MB
- Energy per inference reported: Not reported
- Latency on target device reported: 32.9 ms on NVIDIA Jetson TX2
- Runs without full operating system: No
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: No
- Reason: The paper reports edge-device inference on NVIDIA Jetson TX2 with PyTorch and 8 GB memory, but does not provide MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, SRAM, Flash, or energy evidence.

### Benchmarking / Standardization
- Benchmark used: SHWD
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Pascal VOC annotation format mentioned
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: PG-YOLO achieved 0.933 mAP@0.5 with 0.63M parameters, 1.6 MB weights, and 4.3 GFLOPs. On NVIDIA Jetson TX2, it achieved 32.9 ms inference time and 30.3 FPS, reducing model size substantially compared with YOLOv5s while maintaining similar accuracy.

### Limitations
- The paper notes that inference speed does not improve proportionally to the large reduction in model size, and further inference-speed optimization is identified as future work.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: No
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes PG-YOLO, a lightweight YOLOv5-based object detector using Ghost modules, LightC3 backbone optimization, R-pruning, and knowledge distillation for edge-device object detection in IIoT.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Dong et al. | 2022 | Object detection | PG-YOLO | Ghost modules, R-pruning, knowledge distillation | NVIDIA Jetson TX2 | SHWD | 0.933 mAP@0.5 | 32.9 ms | 1.6 MB | 8 GB RAM | N/A | N/A | PyTorch | N/A | None | No |
