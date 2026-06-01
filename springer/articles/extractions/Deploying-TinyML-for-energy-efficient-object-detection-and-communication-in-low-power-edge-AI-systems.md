## Paper ID: Deploying-TinyML-for-energy-efficient-object-detection-and-communication-in-low-power-edge-AI-systems

TinyML classification: Strict TinyML — It explicitly reports MCU-class deployment using ARM Cortex-M4, TensorFlow Lite Micro, 1 MB flash/256 KB SRAM, and sub-MB quantized models.

### Basic Info
- Authors: Ch Madhu Bhushan; Priya Koppuravuri; Nomitha Prasanthi; Firoj Gazi; Md Muzakkir Hussain; Mohammad Abdussami; Aguru Aswani Devi; Jamilurahman Faizi
- Year: 2025
- Title: Deploying TinyML for energy-efficient object detection and communication in low-power edge AI systems
- Source: Scientific Reports
- Type: Experimental

### Problem & Context
- Task: Visual Wake Words / binary person-presence classification
- Objective: Deploy and evaluate an energy-efficient real-time vision inference system on low-power MCU hardware.
- Application domain: Smart devices, industrial monitoring, environmental sensing, IoT
- Scenario: Low-power embedded Edge AI / MCU-based IoT system
- TinyML relevance: Yes
- TinyML justification: The paper explicitly targets MCU-based on-device inference with TensorFlow Lite Micro, strict SRAM/flash limits, model-size constraints, latency, and energy measurements.

### Model / Method
- Model: MobileNetV2 variants, MobileNetV1, and simple CNN models
- Architecture family: CNN
- Techniques: Quantization, pruning, knowledge distillation, model compression, width multiplier scaling, transfer learning
- Framework: TensorFlow Lite Micro; TensorFlow Lite; TensorFlow APIs
- Training type: Transfer learning / fine-tuning
- Inference type: On-device

### Hardware
- Device: Low-power MCU-based platform with camera and Wi-Fi module
- Hardware type: MCU
- Processor / microcontroller: ARM Cortex-M4
- Clock frequency: 64 MHz
- SRAM / RAM: 256 KB SRAM
- Flash / ROM / Storage: 1 MB flash
- Power consumption: Not reported
- Energy per inference: 10.6–22.1 J
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, flash storage, compute, latency, energy, communication reliability, communication latency

### Dataset
- Name: Visual Wake Words (VWW)
- Type: Public
- Dataset size: Full dataset approximately 115,000 training images and 8,000 validation images; sampled subset of 20,000 training, 4,000 validation, and 1,000 test images
- Number of classes: 2
- Input resolution: 96×96, 160×160, 224×224
- Data modality: RGB image

### Metrics
- Accuracy: 0.58–0.89 across evaluated models; quantized MobileNet variants maintained accuracy ≥ 0.85
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: 3.47–14.98 ms per frame on-device
- FPS: Not reported
- Throughput: Not reported
- Model size: Deployable quantized MobileNet footprints of 286–536 KB; full evaluated byte-array range 39.99–1657.67 KB
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: 1 MB flash budget; deployable models reported below 800 KB threshold
- Energy per inference: 10.6–22.1 J
- Power consumption: Not reported

### Optimization
- Techniques used: 8-bit post-training quantization, pruning, knowledge distillation, width multiplier scaling, model compression
- Quantization: INT8 / PTQ
- Pruning: Yes
- Knowledge distillation: Yes
- Compression method: 8-bit post-training quantization was the main effective compression method
- Hardware-specific optimization: TensorFlow Lite Micro deployment and model sizing for MCU flash/SRAM constraints
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Yes
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: 1 MB flash budget; deployable byte arrays reported below 800 KB
- Model size reported: Yes; examples include MV1_Q at 286.54 KB and MV2_T3_Q at 535.90 KB
- Energy per inference reported: 10.6–22.1 J
- Latency on target device reported: 3.47–14.98 ms per frame
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No; communication is used to transmit inference outputs after on-device processing
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly reports MCU-class deployment using ARM Cortex-M4, TensorFlow Lite Micro, 256 KB SRAM, 1 MB flash, sub-MB quantized models, latency, and energy measurements.

### Benchmarking / Standardization
- Benchmark used: Visual Wake Words
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: Yes
- Other standard benchmark: COCO as the source dataset for VWW; ImageNet for pretrained weights
- Comparison with baseline models: Yes; compares MobileNet variants, simple CNNs, quantized and non-quantized models
- Comparison with previous works: Yes
- Reproducibility artifacts available: Dataset

### Results
- Summary: 8-bit post-training quantization reduced model storage by 3–4× and enabled deployable MobileNet footprints of 286–536 KB within the MCU memory budget. Quantized MobileNet variants achieved accuracy above 0.85 with 3.47–14.98 ms latency and 10.6–22.1 J energy per inference, while UDP reduced communication latency compared with TCP.

### Limitations
- The paper does not perform exhaustive benchmarking against all state-of-the-art TinyML approaches such as QAT, MobileNetV3, or MCUNet.
- Pruning did not produce deployable models within the strict MCU memory budget.
- Knowledge distillation produced compact models but with insufficient accuracy.
- Security, packet loss, jitter, and protocol-level network stability require further evaluation.

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
- This paper proposes an MCU-based TinyML deployment framework for energy-efficient Visual Wake Words inference using quantized MobileNet models, TensorFlow Lite Micro, and TCP/UDP communication with system-level evaluation of memory, latency, energy, and model size.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Bhushan et al. | 2025 | Visual Wake Words / binary person-presence classification | MobileNetV2 | 8-bit post-training quantization | ARM Cortex-M4 MCU | Visual Wake Words | Accuracy ≥ 0.85 for quantized MobileNet variants | 3.47–14.98 ms | 286–536 KB | 256 KB SRAM | 1 MB flash | 10.6–22.1 J | TensorFlow Lite Micro | INT8 / PTQ | TFLM | Yes |
