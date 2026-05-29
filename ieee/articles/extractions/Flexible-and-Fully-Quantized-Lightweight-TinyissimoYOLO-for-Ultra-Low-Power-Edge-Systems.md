## Paper ID: Flexible-and-Fully-Quantized-Lightweight-TinyissimoYOLO-for-Ultra-Low-Power-Edge-Systems

TinyML classification: Strict TinyML — The paper explicitly targets MCU-class platforms including ARM Cortex-M devices and GAP9/MAX78000 ultra-low-power MCUs with reported memory, latency, energy, and quantized model constraints.

### Basic Info
- Authors: Julian Moosmann; Hanna Müller; Nicky Zimmerman; Georg Rutishauser; Luca Benini; Michele Magno
- Year: 2024
- Title: Flexible and Fully Quantized Lightweight TinyissimoYOLO for Ultra-Low-Power Edge Systems
- Source: IEEE Access
- Type: Experimental / Benchmark / Methodological

### Problem & Context
- Task: Object detection
- Objective: Deploy and evaluate flexible, fully quantized TinyissimoYOLO variants for real-time object detection on ultra-low-power edge systems and MCU-class platforms.
- Application domain: Ultra-low-power edge computer vision; embedded vision; IoT; smart cameras.
- Scenario: Edge, embedded, IoT, MCU-based ultra-low-power inference.
- TinyML relevance: Yes
- TinyML justification: The paper targets microcontroller-class platforms, sub-millijoule inference energy, memory footprints below 1 MB, INT8 quantized models, and fully on-device object detection.

### Model / Method
- Model: TinyissimoYOLO / flexible TinyissimoYOLO
- Architecture family: CNN
- Techniques: INT8 quantization, quantization-aware training, hardware-aware deployment, architecture scaling by input resolution, number of classes, and first-layer kernel size.
- Framework: QuantLab, PyTorch, ONNX, DORY, TensorFlow Lite Micro, ai8x-synthesis, NNTool / GAP SDK
- Training type: From scratch followed by quantization-aware training
- Inference type: On-device

### Hardware
- Device: GAP9, MAX78000, STM32H7A3, STM32L4R9, Apollo4b
- Hardware type: MCU / SoC / CNN accelerator
- Processor / microcontroller: GAP9 RISC-V multi-core MCU with NE16 accelerator; MAX78000 ARM Cortex-M4 with CNN accelerator; STM32H7A3 ARM Cortex-M7; STM32L4R9 ARM Cortex-M4; Apollo4b ARM Cortex-M4
- Clock frequency: GAP9 up to 370 MHz; MAX78000 50 MHz; STM32H7A3 up to 280 MHz; STM32L4R9 up to 120 MHz; Apollo4b up to 192 MHz
- SRAM / RAM: GAP9 has 128 KiB L1 scratchpad and 1.5 MiB L2 memory; MAX78000 has 442 kB CNN weight memory; for TY:10-3-112 approximately 512 kB RAM required
- Flash / ROM / Storage: GAP9 has 2 MiB on-chip flash; TY:10-3-112 requires at least 1 MB Flash
- Power consumption: GAP9 TY:3-3-88 single-core 26.14 mW; GAP9 TY:3-3-88 multi-core peak 55.76 mW; GAP9 NE16 TY:3-3-88 peak 70.30 mW; GAP9 NE16 energy-efficient 20.04 mW
- Energy per inference: GAP9 NE16 TY:3-3-88 149 µJ at 370 MHz and 105 µJ at 150 MHz; GAP9 NE16 TY:10-3-112 245 µJ at 370 MHz and 177 µJ at 150 MHz; GAP9 multi-core TY:3-3-88 490 µJ at 150 MHz and 721 µJ at 370 MHz
- Execution without full OS: Yes
- Fully on-device inference: Yes
- Constraints mentioned: Memory, power, latency, compute, model size, input resolution, number of classes, hardware accelerator memory, MCU deployment constraints.

### Dataset
- Name: PascalVOC
- Type: Public
- Dataset size: Not reported
- Number of classes: 3, 10, and 20 classes evaluated
- Input resolution: 88 × 88, 112 × 112, and 224 × 224 pixels
- Data modality: RGB image

### Metrics
- Accuracy: Not reported
- mAP: Up to 67% mAP for TY:20-7-224; 56.4% mAP for TY:20-7-112; 63.1% mAP for TY:10-3-112; 61.8% mAP for TY:3-3-88
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: GAP9 NE16 TY:3-3-88 2.12 ms at 370 MHz and 5.24 ms at 150 MHz; GAP9 NE16 TY:10-3-112 3.46 ms at 370 MHz and 8.54 ms at 150 MHz; GAP9 multi-core TY:3-3-88 11.3 ms at 370 MHz and 27.87 ms at 150 MHz; GAP9 single-core TY:3-3-88 69.77 ms
- FPS: GAP9 NE16 TY:10-3-112 can perform 285 inferences per second
- Throughput: GAP9 NE16 TY:3-3-88 41.22 MAC/cycle; GAP9 NE16 TY:10-3-112 42.84 MAC/cycle; GAP9 multi-core TY:10-3-112 8.74 MAC/cycle
- Model size: TinyissimoYOLO variants from 441 KiB to 2.36 MiB; TY:10-3-112 702 KiB; TY:20-7-112 907 KiB
- Parameters: TinyissimoYOLO variants from 440,592 to 2,360,448 parameters; TY:10-3-112 702,448 parameters
- MACs / FLOPs: TinyissimoYOLO variants from 32 MMACs to 317 MMACs; deployable 112 × 112 variants up to 57 MMACs
- RAM usage: TY:10-3-112 requires approximately 512 kB RAM; in-between calculations need at most approximately 375 kB memory
- Flash usage: TY:10-3-112 requires at least 1 MB Flash
- Energy per inference: GAP9 NE16 TY:3-3-88 105–149 µJ; GAP9 NE16 TY:10-3-112 177–245 µJ
- Power consumption: GAP9 TY:3-3-88 single-core 26.14 mW; GAP9 NE16 TY:3-3-88 peak 70.30 mW; GAP9 NE16 TY:3-3-88 energy-efficient 20.04 mW

### Optimization
- Techniques used: INT8 quantization, quantization-aware training, integer-only deployment, hardware-aware deployment, tiling, parallelization, use of CNN accelerators.
- Quantization: INT8 / QAT
- Pruning: No
- Knowledge distillation: No
- Compression method: 8-bit quantization
- Hardware-specific optimization: Yes; GAP9 NE16 accelerator, GAP9 multi-core RISC-V cluster, MAX78000 CNN accelerator, DORY tiling, NNTool deployment, ai8x-synthesis deployment.
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: Yes
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: For TY:10-3-112, approximately 512 kB RAM required; intermediate calculations need at most approximately 375 kB memory
- Flash usage reported: TY:10-3-112 requires at least 1 MB Flash; GAP9 has 2 MiB on-chip flash
- Model size reported: Yes; 441 KiB to 2.36 MiB depending on variant
- Energy per inference reported: Yes; as low as 105 µJ on GAP9 NE16 for TY:3-3-88 and 177 µJ for TY:10-3-112 at 150 MHz
- Latency on target device reported: Yes; as low as 2.12 ms on GAP9 NE16 for TY:3-3-88
- Runs without full operating system: Yes
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: Yes
- Reason: The paper reports MCU-class deployment, INT8 quantized inference, memory requirements, model size, latency, power, and energy per inference on ultra-low-power platforms without cloud/offloaded inference.

### Benchmarking / Standardization
- Benchmark used: PascalVOC
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: PascalVOC
- Comparison with baseline models: Yes; YOLOv1, MCUNet, MCUNetV2, MBv2+CMSIS
- Comparison with previous works: Yes
- Reproducibility artifacts available: Code / model not fully reported; QuantLab, DORY, TensorFlow Lite Micro, GAP SDK, and ai8x-synthesis are mentioned as tools/frameworks

### Results
- Summary: TinyissimoYOLO variants achieved real-time object detection on MCU-class platforms with INT8 quantization. GAP9 NE16 achieved the best latency and energy, reaching 2.12 ms and 149 µJ for TY:3-3-88, and 3.46 ms and 245 µJ for TY:10-3-112.

### Limitations
- MAX78000 deployment is constrained by 442 kB accelerator weight memory.
- Larger TinyissimoYOLO variants with higher resolution and more classes cannot fit the MAX78000.
- Some platform evaluations use platform-specific deployment flows on untrained networks and do not evaluate resulting model accuracy for all targets.

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
- This paper proposes a flexible, fully quantized TinyissimoYOLO deployment and benchmarking pipeline for real-time ultra-low-power object detection on multiple MCU-class edge platforms.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Moosmann et al. | 2024 | Object detection | TinyissimoYOLO | INT8 quantization + QAT + hardware-aware deployment | GAP9 NE16; GAP9 RISC-V cluster; MAX78000; STM32H7A3; STM32L4R9; Apollo4b | PascalVOC | mAP up to 67% | 2.12 ms on GAP9 NE16 TY:3-3-88; 3.46 ms on GAP9 NE16 TY:10-3-112 | 441 KiB–2.36 MiB | TY:10-3-112 requires approx. 512 kB RAM | TY:10-3-112 requires at least 1 MB Flash | 105 µJ–245 µJ on GAP9 NE16 depending on variant/configuration | QuantLab; PyTorch; ONNX; DORY; TFLM; NNTool; ai8x-synthesis | INT8/QAT | TFLM | Yes |
