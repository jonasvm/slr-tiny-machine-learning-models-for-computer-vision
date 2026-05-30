## Paper ID: Design-and-Implementation-of-Tiny-Deep-Neural-Networks-for-Landing-Pad-Detection-on-UAVs

TinyML classification: Strict TinyML — explicitly deploys tiny CNNs on STM32F746NG ARM Cortex-M7 microcontrollers with MCU-level Flash/SRAM, latency, and energy constraints.

### Basic Info
- Authors: Edoardo Ragusa, Tommaso Taccioli, Alessio Canepa, Rodolfo Zunino, Paolo Gastaldo
- Year: 2024
- Title: Design and Implementation of Tiny Deep Neural Networks for Landing Pad Detection on UAVs
- Source: IEEE Access, Volume 12, DOI: 10.1109/ACCESS.2024.3454363
- Type: Methodological

### Problem & Context
- Task: Landing-pad detection / segmentation-based object localization
- Objective: Design lightweight CNN architectures for landing-pad detection on low-power commercial microcontrollers used in small-size UAVs.
- Application domain: UAV autonomous landing
- Scenario: Embedded onboard inference on small-size drones
- TinyML relevance: Yes
- TinyML justification: The paper targets low-power commercial STM32 microcontrollers and reports latency, RAM, flash, FLOPs, parameters, power, and energy constraints.

### Model / Method
- Model: Tiny CNN landing-pad detector with NAS-designed Student backbone and customized segmentation head
- Architecture family: CNN
- Techniques: Neural Architecture Search, knowledge distillation, hardware-aware architecture selection, lightweight segmentation head customization
- Framework: Keras, TensorFlow Lite, STM32 X-Cube-AI
- Training type: Knowledge distillation for Student architectures followed by end-to-end retraining
- Inference type: On-device

### Hardware
- Device: STM32F746NG microcontroller; Raspberry Pi 4 used as Cortex-A baseline
- Hardware type: MCU; CPU baseline
- Processor / microcontroller: ARM Cortex-M7 32-bit RISC core; Raspberry Pi 4 with 1.5 GHz quad-core ARM Cortex-A72 baseline
- Clock frequency: STM32F746NG up to 216 MHz; Raspberry Pi 4 1.5 GHz
- SRAM / RAM: STM32F746NG has 320 Kbytes SRAM; 8 Mbyte SDRAM added; peak RAM for STM32TINY 160×160 is 1.39 MiB
- Flash / ROM / Storage: STM32F746NG has 1 Mbyte Flash; STM32TINY uses 22.12 KiB Flash
- Power consumption: STM32F746NG peak power consumption declared as 345 mW
- Energy per inference: 0.518 J estimated for STM32TINY
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory, power, latency, compute, communication, FLOPs, parameters, Flash, RAM

### Dataset
- Name: Not reported
- Type: Private / custom captured dataset
- Dataset size: 21 videos; 29,415 frames; 9,200 training frames; 20,215 test images
- Number of classes: Not reported
- Input resolution: 320×320 for distillation; 160×160 for STM32 and STM32_TINY deployment experiments
- Data modality: RGB video frames / images captured with a GoPro camera

### Metrics
- Accuracy: Not reported
- mAP: Not reported
- Precision: Precision-recall analysis reported; exact numeric value not reported
- Recall: Precision-recall analysis reported; exact numeric value not reported
- F1-score: Not reported
- Latency: STM32TINY 160×160: 1.5 s on STM32 and 32.5 ms on Raspberry Pi
- FPS: STM32 frame rate lower than 1 FPS; Raspberry Pi supports real-time inference for proposed architectures
- Throughput: Not reported
- Model size: STM32TINY uses 22.12 KiB Flash
- Parameters: STM32TINY has 6K parameters
- MACs / FLOPs: STM32TINY has 27 MFLOPs at 160×160 and 110 MFLOPs at 320×320
- RAM usage: STM32TINY uses 1.39 MiB peak RAM at 160×160 and 5.57 MiB at 320×320
- Flash usage: STM32TINY uses 22.12 KiB Flash
- Energy per inference: 0.518 J estimated for STM32TINY
- Power consumption: 345 mW peak power consumption for STM32F746NG

### Optimization
- Techniques used: Neural Architecture Search, knowledge distillation, hardware-aware selection using FLOPs, customized segmentation head, reduced input size, reduced filters
- Quantization: None / FP32
- Pruning: No
- Knowledge distillation: Yes
- Compression method: Hardware-aware NAS and architecture reduction
- Hardware-specific optimization: STM32 X-Cube-AI optimization and memory indexing tuned to use external memory when necessary
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not as SRAM-only; peak RAM reported as 1.39 MiB for STM32TINY 160×160
- Flash usage reported: 22.12 KiB for STM32TINY
- Model size reported: 6K parameters and 22.12 KiB Flash for STM32TINY
- Energy per inference reported: 0.518 J estimated for STM32TINY
- Latency on target device reported: 1.5 s for STM32TINY 160×160 on STM32
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly deploys a tiny CNN on an STM32F746NG ARM Cortex-M7 microcontroller and reports MCU-level latency, RAM, Flash, parameters, power, and energy constraints.

### Benchmarking / Standardization
- Benchmark used: Custom landing-pad dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: COCO mentioned only for SSD-lite MobileNetV3 pretraining
- Comparison with baseline models: Yes; Teacher model, previous landing-pad detector, and SSD-lite MobileNetV3
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: The proposed NAS and distillation strategy generated tiny CNNs that reduce parameters and FLOPs compared with the Teacher model. STM32TINY achieved 1.5 s latency on STM32 at 160×160 with 6K parameters, 22.12 KiB Flash, 1.39 MiB RAM, and estimated energy of 0.518 J.

### Limitations
- STM32 frame rate was lower than 1 FPS, which is incompatible with some fine-grained control operations.
- The architecture search currently requires significant GPU time.
- Quantization-aware training and testing on additional applications are left as future work.

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
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a hardware-aware NAS and knowledge-distillation strategy for designing tiny CNN landing-pad detectors that can be deployed on STM32 ARM Cortex-M microcontrollers for onboard UAV vision.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Ragusa et al. | 2024 | Landing-pad detection / segmentation-based localization | Tiny CNN landing-pad detector | NAS + knowledge distillation | STM32F746NG ARM Cortex-M7 | Custom landing-pad video dataset | Precision/Recall analysis | 1.5 s on STM32TINY 160×160 | 22.12 KiB Flash / 6K parameters | 1.39 MiB peak RAM | 22.12 KiB | 0.518 J | Keras + TensorFlow Lite + STM32 X-Cube-AI | FP32 | None | Yes |
