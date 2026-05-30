## Paper ID: Light-YOLOv4-An-Edge-Device-Oriented-Target-Detection-Method-for-Remote-Sensing-Images

TinyML classification: Near-TinyML — The paper targets edge-device vision deployment on Jetson TX2 with pruning, distillation, and FP16 quantization, but does not provide MCU-class deployment evidence.

### Basic Info
- Authors: Xiaojie Ma; Kefeng Ji; Boli Xiong; Linbin Zhang; Sijia Feng; Gangyao Kuang
- Year: 2021
- Title: Light-YOLOv4: An Edge-Device Oriented Target Detection Method for Remote Sensing Images
- Source: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, Vol. 14, 2021
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: To design a lightweight YOLOv4-based detector suitable for edge-device deployment by reducing computation, model size, parameters, and inference time.
- Application domain: Remote sensing image target detection
- Scenario: Edge device, embedded remote sensing, UAV/on-orbit satellite-oriented deployment
- TinyML relevance: Partial
- TinyML justification: The paper targets edge-device inference with limited computing resources and memory, but deployment is on NVIDIA Jetson TX2 rather than an MCU-class platform.

### Model / Method
- Model: Light-YOLOv4
- Architecture family: CNN
- Techniques: Sparsity training, channel pruning, layer pruning, knowledge distillation, FP16 quantization, model compression, TensorRT acceleration
- Framework: Darknet; PyTorch 1.14; TensorRT
- Training type: Retraining/fine-tuning with knowledge distillation
- Inference type: On-device

### Hardware
- Device: NVIDIA Jetson TX2
- Hardware type: SoC / GPU edge device
- Processor / microcontroller: NVIDIA Pascal GPU with 256 CUDA cores; Denver 2 dual-core CPU + ARM A57 CPU
- Clock frequency: Not reported
- SRAM / RAM: 8 GB 128-bit LPDDR4
- Flash / ROM / Storage: 32 GB eMMC
- Power consumption: Less than 15 W
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Yes
- Constraints mentioned: Limited computing resources, limited memory, model size, parameter size, FLOPs, inference speed, power consumption

### Dataset
- Name: SSDD; Gaofen Airplane dataset
- Type: SSDD: not reported; Gaofen Airplane dataset: released in the 2020 Gaofen challenge
- Dataset size: SSDD: 1160 images and 2456 ships; Gaofen Airplane: 1000 images and 5609 airplanes
- Number of classes: SSDD: ship detection; Gaofen Airplane: 10 airplane categories in the dataset, but only detection was performed
- Input resolution: YOLO-series input size 416 × 416; Gaofen images 1024 × 1024 cropped into 416 × 416 patches with 100-pixel overlap
- Data modality: SAR remote sensing images; optical remote sensing images

### Metrics
- Accuracy: Not reported
- mAP: SSDD: 0.930 for Light-YOLOv4; Gaofen Airplane: 0.885 for Light-YOLOv4
- Precision: SSDD: not reported for final Light-YOLOv4; Gaofen Airplane: 0.728
- Recall: SSDD: not reported for final Light-YOLOv4; Gaofen Airplane: 0.911
- F1-score: SSDD: 0.902; Gaofen Airplane: 0.809
- Latency: Not reported
- FPS: 15.12 FPS on SSDD using NVIDIA Jetson TX2
- Throughput: 15.12 FPS
- Model size: 3.5 MB
- Parameters: 0.857 M
- MACs / FLOPs: 5.183 G FLOPs
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Less than 15 W for NVIDIA Jetson TX2

### Optimization
- Techniques used: L1 sparsity training, structured channel pruning, structured layer pruning, knowledge distillation, FP16 quantization, TensorRT acceleration
- Quantization: FP16 / PTQ
- Pruning: Yes
- Knowledge distillation: Yes
- Compression method: YOLOv4 compression using sparsity training, channel pruning, layer pruning, knowledge distillation, and FP16 quantization
- Hardware-specific optimization: TensorRT acceleration and layer fusion on NVIDIA Jetson TX2
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: 3.5 MB
- Energy per inference reported: Not reported
- Latency on target device reported: 15.12 FPS reported; latency not reported
- Runs without full operating system: No
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper deploys on NVIDIA Jetson TX2 with Ubuntu 18.04 and 8 GB RAM, without MCU-class, bare-metal, RTOS, SRAM, Flash, or TensorFlow Lite Micro evidence.

### Benchmarking / Standardization
- Benchmark used: SSDD; Gaofen Airplane dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: YOLOv4; YOLOv4-tiny
- Comparison with previous works: YOLOv3; SSD; Faster RCNN; FPN; RetinaNet
- Reproducibility artifacts available: Not reported

### Results
- Summary: Light-YOLOv4 achieved 0.930 mAP and 15.12 FPS on SSDD using NVIDIA Jetson TX2. Compared with YOLOv4, model size, parameter size, and FLOPs were reduced by 98.63%, 98.66%, and 91.30%, while inference speed increased to 4.2×.

### Limitations
- The training process is time-consuming.
- The pruned model cannot make full use of the computing resource.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes Light-YOLOv4, a compressed YOLOv4-based remote sensing target detector using sparsity training, pruning, knowledge distillation, FP16 quantization, and TensorRT acceleration for NVIDIA Jetson TX2 edge deployment.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Ma et al. | 2021 | Object detection | Light-YOLOv4 | Pruning + knowledge distillation + FP16 quantization | NVIDIA Jetson TX2 | SSDD; Gaofen Airplane | mAP 0.930 on SSDD | 15.12 FPS | 3.5 MB | N/A | N/A | N/A | Darknet; PyTorch; TensorRT | FP16 PTQ | None | No |
