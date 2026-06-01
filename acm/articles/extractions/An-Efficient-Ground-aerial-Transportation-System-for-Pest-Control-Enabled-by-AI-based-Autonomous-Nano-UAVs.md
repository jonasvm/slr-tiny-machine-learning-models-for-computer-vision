## Paper ID: An-Efficient-Ground-aerial-Transportation-System-for-Pest-Control-Enabled-by-AI-based-Autonomous-Nano-UAVs

TinyML classification: Strict TinyML — The paper deploys an int8 SSDLite-MobileNetV3 detector on GAP9/STM32-class nano-UAV hardware with reported memory, latency, throughput, and milliwatt-level power constraints.

### Basic Info
- Authors: Luca Crupi; Luca Butera; Alberto Ferrante; Alessandro Giusti; Daniele Palossi
- Year: 2025
- Title: An Efficient Ground-aerial Transportation System for Pest Control Enabled by AI-based Autonomous Nano-UAVs
- Source: ACM Journal of Autonomous Transportation Systems, Vol. 2, No. 4, Article 16, June 2025
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: Detect pest insects onboard autonomous nano-UAVs and use detected hotspots to support efficient ground-aerial pest control.
- Application domain: Precision agriculture / smart farming / pest control in vineyards
- Scenario: Embedded autonomous nano-UAV with onboard AI inference and local path planning
- TinyML relevance: Yes
- TinyML justification: The paper targets ultra-constrained nano-UAV deployment with onboard CNN inference under sub-100 mW computational power constraints, MCU/SoC-class hardware, memory constraints, quantization, latency, and power measurements.

### Model / Method
- Model: SSDLite-MobileNetV3
- Architecture family: CNN
- Techniques: Transfer learning, fine-tuning, INT8 quantization, FP16 deployment, hardware-aware deployment, NE16 accelerator usage, memory hierarchy optimization
- Framework: PyTorch, ONNX, GWT NN-Tool
- Training type: Fine-tuning / transfer learning
- Inference type: On-device

### Hardware
- Device: Crazyflie 2.1 nano-UAV with GAP9Shield, RGB OmniVision OV5647 camera, STM32 MCU, ToF depth sensor, and GWT GAP9 SoC
- Hardware type: MCU / SoC
- Processor / microcontroller: STM32 MCU and RISC-V-based GWT GAP9 SoC with 10 cores and NE16 INT8 accelerator
- Clock frequency: STM32 up to 168 MHz; GAP9 configurations reported at 150 MHz, 240 MHz, and 370 MHz for CL/FC
- SRAM / RAM: GAP9 L1 128 kB, L2 1.6 MB, off-chip RAM 32 MB
- Flash / ROM / Storage: 64 MB off-chip Flash
- Power consumption: 31 mW for INT8 on CL, 34 mW for INT8 on NE16, 41 mW for FP16; paper also reports 33 mW for real-time CNN inference
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, power, latency, compute budget, battery lifetime, low-resolution sensing, onboard real-time inference, communication avoidance

### Dataset
- Name: Butera et al. pest insect dataset
- Type: Private
- Dataset size: More than 3,300 images; 1,422 Popillia japonica, 1,318 Cetonia aurata, and 877 Phyllopertha horticola samples
- Number of classes: 3
- Input resolution: 320 × 240 × 3
- Data modality: RGB image

### Metrics
- Accuracy: Not reported
- mAP: 0.80 for FP32/FP16; 0.79 for INT8
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: 462 ms for FP16, 249 ms for INT8 on CL, 147 ms for INT8 on NE16
- FPS: 2.1 FPS for FP16; 6.8 FPS for INT8 on NE16
- Throughput: 6.8 frame/s on GAP9 NE16
- Model size: Approximately 7 MB FP16 weights; approximately 3.4 MB INT8 weights
- Parameters: 3.44 M
- MACs / FLOPs: 584 MMAC per inference / 0.58 GMAC per inference
- RAM usage: Peak memory 3,622 kB for FP16 and 1,811 kB for INT8
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: 31–41 mW depending on deployment configuration; 34 mW for INT8 on NE16

### Optimization
- Techniques used: INT8 quantization, FP16 deployment, NE16 hardware acceleration, NN-Tool C code generation, tensor tiling, memory hierarchy management
- Quantization: INT8 / FP16
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: INT8 quantization and SSDLite depthwise separable convolutions
- Hardware-specific optimization: GWT NN-Tool deployment for GAP9, NE16 INT8 accelerator, memory hierarchy optimization
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: 1,811 kB peak memory for INT8; 3,622 kB peak memory for FP16
- Flash usage reported: Not reported
- Model size reported: Approximately 3.4 MB INT8 weights; approximately 7 MB FP16 weights
- Energy per inference reported: Not reported
- Latency on target device reported: 147 ms for INT8 on GAP9 NE16
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly deploys an optimized CNN on nano-UAV hardware with STM32/GAP9-class embedded processing, onboard inference, INT8 quantization, peak memory, latency, throughput, and milliwatt-level power measurements.

### Benchmarking / Standardization
- Benchmark used: Custom pest insect detection dataset from Butera et al.
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: COCO used for pre-training
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Code/video for path-planning experiment; dataset not publicly available

### Results
- Summary: The INT8 SSDLite-MobileNetV3 model achieves 0.79 mAP at 6.8 FPS with 147 ms latency and 34 mW power on GAP9 NE16. The full system combines onboard pest detection with local A*-based obstacle avoidance and reduces ground-vehicle pest-control time by up to approximately 20 hours in a simulated 200 × 200 m vineyard.

### Limitations
- The insect dataset was gathered online rather than directly from nano-UAV images.
- Real-world deployment would likely benefit from training on drone-acquired images.
- Outdoor operation is limited by weather conditions such as wind and rain.
- Local path planning may suffer blockages when obstacles fully cover the depth sensor field of view.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes an autonomous ground-aerial pest-control system using nano-UAVs with onboard SSDLite-MobileNetV3 pest detection on GAP9 hardware and MCU-based local path planning to guide targeted ground-robot treatment.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Crupi et al. | 2025 | Object detection | SSDLite-MobileNetV3 | INT8 quantization + NE16 acceleration | Crazyflie 2.1 nano-UAV with GAP9Shield / STM32 / GAP9 | Butera et al. pest insect dataset | mAP 0.79 | 147 ms | 3.4 MB INT8 weights | 1,811 kB peak INT8 memory | N/A | N/A | PyTorch + ONNX + GWT NN-Tool | PTQ | None | Yes |
