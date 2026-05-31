## Paper ID: Energy-Efficient-Implementation-of-YOLOv8-Instance-Segmentation-and-Pose-Detection-on-RISC-V-SoC

TinyML classification: Near-TinyML — The work targets a custom RISC-V SoC with low-power edge vision acceleration, but it does not explicitly demonstrate MCU-class deployment or TensorFlow Lite Micro/bare-metal Cortex-M-level constraints.

### Basic Info

* Authors: Hansen Wang; Dongju Li; Tsuyoshi Isshiki
* Year: 2024
* Title: Energy-Efficient Implementation of YOLOv8, Instance Segmentation, and Pose Detection on RISC-V SoC
* Source: IEEE Access, Volume 12, 2024. DOI: 10.1109/ACCESS.2024.3397536.
* Type: Experimental

### Problem & Context

* Task: Object detection; instance segmentation; pose detection
* Objective: Implement end-to-end YOLOv8 inference for object detection, instance segmentation, and pose detection on an energy-efficient programmable RISC-V AIV-SoC.
* Application domain: Healthcare; agriculture; surveillance; autonomous systems; infrastructure inspection
* Scenario: Edge, embedded, resource-constrained, low-power SoC deployment
* TinyML relevance: Yes
* TinyML justification: The paper targets low-power, resource-constrained on-device vision inference using a custom RISC-V SoC, INT8 quantization, on-chip memory constraints, and power-efficiency optimization.

### Model / Method

* Model: YOLOv8s; YOLOv8s-seg; YOLOv8s-pose; ResNet50 for compatibility comparison
* Architecture family: CNN
* Techniques: INT8 fixed-point per-group quantization; post-training symmetric static quantization; piecewise linear function approximation; multi-cycle path; neural network layer scheme optimization; 4-pattern transposed convolution; ping-pong DMA; line-buffer and data-core caching; hardware/software co-design
* Framework: Ultralytics YOLOv8; PyTorch API for GPU comparison; LLVM-C2RTL for hardware design
* Training type: Pre-trained YOLOv8s used for COCO experiments; YOLOv8s trained for Global Wheat 2000 and Roboflow Universe Crack with 100 epochs; transfer learning/from-scratch status not reported
* Inference type: On-device

### Hardware

* Device: Artificial Intelligence Visual System on Chip (AIV-SoC)
* Hardware type: SoC
* Processor / microcontroller: RV32IMASU RISC-V module with Computing Engine
* Clock frequency: 595 MHz
* SRAM / RAM: 4,276 KB memory size; feature map cache constrained to 4 MB
* Flash / ROM / Storage: Not reported
* Power consumption: 202.5 mW in hardware resource table; 0.2 W in hardware comparison table
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: On-chip memory, power, throughput, AXI bandwidth, IO pins, compute, quantization accuracy, cache capacity, input resolution

### Dataset

* Name: COCO val2017; COCO-seg; COCO-Pose; Global Wheat 2000; Roboflow Universe Crack
* Type: Public
* Dataset size: Roboflow Universe Crack: 4029 static images; other dataset sizes not reported
* Number of classes: COCO object detection and segmentation: 80; COCO pose: 1; Global Wheat 2000: 1; Roboflow Universe Crack: 1
* Input resolution: AIV-SoC input resolution: 352 × 352; experiments also report 256, 352, and 640; custom training used default 640
* Data modality: Image

### Metrics

* Accuracy: Not reported
* mAP: COCO object detection at 352 with per-group quantization: 36.5% mAP 0.5-0.95; COCO instance segmentation at 352 with per-group quantization: 29.5% mAP 0.5-0.95; COCO pose detection at 352 with per-group quantization: 42.0% mAP 0.5-0.95; Global Wheat 2000 at 352 with per-group quantization: 62.2% mAP 0.5-0.95 and 95.7% mAP 0.5; Roboflow Universe Crack at 352 with per-group quantization: 25.6% mAP 0.5-0.95 and 73.4% mAP 0.5
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: 67.1 FPS for object detection; 55.2 FPS for instance segmentation; 64.9 FPS for pose detection
* Throughput: 0.58 TOP/s for YOLOv8s; 0.71 TOP/s for YOLOv8s-seg; 0.592 TOP/s for YOLOv8s-pose; 0.455 TOP/s for ResNet50
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: FLOPs obtained using `thop`, but values not reported
* RAM usage: 4,276 KB memory size reported for AIV-SoC
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 0.2 W; 202.5 mW

### Optimization

* Techniques used: INT8 per-group quantization; dynamic fixed-point scheme; PLF approximation for SiLU, sigmoid, and softmax; multi-cycle path; 4-pattern transposed convolution; line-buffer/data-core caching; ping-pong DMA; 64-bit AXI4 optimization; layer implementation in Computing Engine
* Quantization: INT8 PTQ
* Pruning: No
* Knowledge distillation: No
* Compression method: INT8 fixed-point per-group quantization
* Hardware-specific optimization: Custom RISC-V AIV-SoC, custom Computing Engine, SRAM feature map cache, DMA scheme, AXI bandwidth optimization, C2RTL hardware generation
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper targets a custom low-power RISC-V SoC with 4,276 KB memory and 0.2 W power, but it does not report MCU-class deployment, Cortex-M/TensorFlow Lite Micro execution, bare-metal or RTOS execution, or kilobyte-scale SRAM/Flash constraints.

### Benchmarking / Standardization

* Benchmark used: COCO val2017; COCO-seg; COCO-Pose; Global Wheat 2000; Roboflow Universe Crack
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: COCO; Global Wheat 2000
* Comparison with baseline models: Yes, comparison with original floating-point YOLOv8s and per-channel, per-group, and per-tensor INT8 quantization
* Comparison with previous works: Yes, compared with NVIDIA GTX1080Ti, Arria-10 GX1150 FPGA, XC7Z7100 FPGA, K230, and prior RISC-V/YOLO implementations
* Reproducibility artifacts available: Not reported

### Results

* Summary: The AIV-SoC achieved 67.1 FPS for YOLOv8s object detection, 55.2 FPS for YOLOv8s instance segmentation, and 64.9 FPS for YOLOv8s pose detection at 352 × 352. It reported 0.2 W power consumption and energy efficiency of 0.345, 0.282, and 0.338 mJ/GOP for YOLOv8s, YOLOv8s-seg, and YOLOv8s-pose, respectively.

### Limitations

* The chip was not fabricated or validated physically.
* Retail price could not be estimated due to the absence of chip production.
* The architecture is less versatile than GPUs.
* Input resolution is limited to 352 × 352 due to on-chip memory constraints.
* INT8 quantization causes mAP loss, especially for pose detection and smaller targets.
* QAT and hybrid per-group/per-channel quantization are left for future work.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: No
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a programmable RISC-V AIV-SoC for energy-efficient end-to-end YOLOv8 object detection, instance segmentation, and pose detection using INT8 per-group quantization and hardware/software co-design.

| Paper       | Year | Task                                                    | Model                              | Technique                                          | Device         | Dataset                                                               | Main Metric                                                                                       | Latency | Model Size | SRAM/RAM | Flash | Energy                       | Framework                               | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ------------------------------------------------------- | ---------------------------------- | -------------------------------------------------- | -------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------- | ---------- | -------- | ----- | ---------------------------- | --------------------------------------- | -------- | ------------- | ------------- |
| Wang et al. | 2024 | Object detection; instance segmentation; pose detection | YOLOv8s; YOLOv8s-seg; YOLOv8s-pose | INT8 per-group PTQ and hardware/software co-design | RISC-V AIV-SoC | COCO; COCO-seg; COCO-Pose; Global Wheat 2000; Roboflow Universe Crack | 36.5% detection / 29.5% segmentation / 42.0% pose mAP 0.5-0.95 at 352 with per-group quantization | N/A     | N/A        | 4,276 KB | N/A   | 0.345 / 0.282 / 0.338 mJ/GOP | Ultralytics YOLOv8; PyTorch; LLVM-C2RTL | INT8 PTQ | None          | No            |
