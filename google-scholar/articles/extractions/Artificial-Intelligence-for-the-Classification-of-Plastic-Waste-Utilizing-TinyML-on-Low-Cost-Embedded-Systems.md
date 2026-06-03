## Paper ID: Artificial-Intelligence-for-the-Classification-of-Plastic-Waste-Utilizing-TinyML-on-Low-Cost-Embedded-Systems

TinyML classification: Strict TinyML — targets MCU-class deployment with Cortex-M0+, TinyML, and explicit 185.4K ROM, 88K RAM, and 249 ms latency constraints.

### Basic Info
- Authors: Jutarut Chaoraingern; Vittaya Tipsuwanporn; Arjin Numsomran
- Year: 2023
- Title: Artificial Intelligence for the Classification of Plastic Waste Utilizing TinyML on Low-Cost Embedded Systems
- Source: International Journal on Advanced Science, Engineering and Information Technology, Vol. 13, No. 6
- Type: Experimental

### Problem & Context
- Task: Classification
- Objective: Classify PET plastic bottles, HDPE plastic bottles, and unknown objects using an embedded TinyML vision prototype.
- Application domain: Plastic waste classification and segregation
- Scenario: Embedded, low-cost machine vision, industrial integration
- TinyML relevance: Yes
- TinyML justification: The paper deploys a quantized MobileNetV2 model on an Arducam Pico4ML embedded microcontroller platform with reported ROM, RAM, and latency constraints.

### Model / Method
- Model: MobileNetV2
- Architecture family: CNN
- Techniques: Quantization, transfer learning, model complexity reduction with alpha = 0.05, Edge Impulse EON compiler optimization
- Framework: TensorFlow Lite, Edge Impulse, EON compiler
- Training type: Transfer learning
- Inference type: On-device

### Hardware
- Device: Arducam Pico4ML
- Hardware type: MCU
- Processor / microcontroller: RP2040 SoC with dual ARM Cortex-M0+ cores
- Clock frequency: Not reported
- SRAM / RAM: 88 K RAM
- Flash / ROM / Storage: 185.4 K ROM
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, latency, compute, low-cost embedded deployment, communication integration

### Dataset
- Name: Not reported
- Type: Private
- Dataset size: 78 images
- Number of classes: 3
- Input resolution: Captured at 320 × 320 pixels and resized to 32 × 32 pixels for the model
- Data modality: Grayscale image

### Metrics
- Accuracy: 100%
- mAP: Not reported
- Precision: PET 95.8%, HDPE 93.8%, Unknown 95%
- Recall: Not reported
- F1-score: 1.00 for each class in validation
- Latency: 249 ms
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: 88 K
- Flash usage: 185.4 K ROM
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Quantization, MobileNetV2 alpha reduction, Edge Impulse EON compiler optimization, grayscale preprocessing, image resizing
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: EON compiler optimization
- Hardware-specific optimization: Deployment compiled for Arducam Pico4ML target device
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: 88 K RAM
- Flash usage reported: 185.4 K ROM
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: 249 ms
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: Yes
- Reason: The model is deployed on an MCU-class Arducam Pico4ML/Cortex-M0+ embedded platform with explicit ROM, RAM, and latency measurements.

### Benchmarking / Standardization
- Benchmark used: Not reported
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: MobileNetV1 and Conv2D
- Comparison with previous works: Not reported
- Reproducibility artifacts available: Not reported

### Results
- Summary: MobileNetV2 achieved 100% validation accuracy and average precision above 90% across the three classes. The quantized model achieved 249 ms latency on the Arducam Pico4ML using 185.4 K ROM and 88 K RAM.

### Limitations
- The dataset is very small, with only 78 collected images.
- Future work focuses on cloud data management and visualization for improved waste collection and disposal efficiency.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a TinyML-based plastic waste classification prototype using MobileNetV2 deployed on a low-cost Arducam Pico4ML embedded vision device with RS485 Modbus integration.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Chaoraingern et al. | 2023 | Classification | MobileNetV2 | Quantization + EON compiler optimization | Arducam Pico4ML | Private plastic bottle image dataset | Accuracy 100% | 249 ms | N/A | 88 K RAM | 185.4 K ROM | N/A | TensorFlow Lite, Edge Impulse | N/A | N/A | Yes |
