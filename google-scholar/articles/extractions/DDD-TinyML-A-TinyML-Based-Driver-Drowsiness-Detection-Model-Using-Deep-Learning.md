## Paper ID: DDD-TinyML-A-TinyML-Based-Driver-Drowsiness-Detection-Model-Using-Deep-Learning

TinyML classification: Strict TinyML — It explicitly targets microcontroller-class deployment with TensorFlow Lite Micro conversion, quantization, and very small model sizes.

### Basic Info
- Authors: Norah N. Alajlan; Dina M. Ibrahim
- Year: 2023
- Title: DDD TinyML: A TinyML-Based Driver Drowsiness Detection Model Using Deep Learning
- Source: Sensors 2023, 23, 5696
- Type: Experimental

### Problem & Context
- Task: Classification
- Objective: Detect driver drowsiness status from face/eye images using lightweight deep learning models.
- Application domain: Driver drowsiness detection / smart transportation
- Scenario: TinyML, IoT, embedded edge, microcontroller-targeted deployment
- TinyML relevance: Yes
- TinyML justification: The paper explicitly targets TinyML deployment on resource-constrained microcontrollers using lightweight models, quantization, TensorFlow Lite, TensorFlow Lite Micro, and C array conversion.

### Model / Method
- Model: SqueezeNet, AlexNet, CNN, MobileNet-V2, MobileNet-V3
- Architecture family: CNN
- Techniques: Quantization-aware training, full-integer quantization, dynamic range quantization, model compression, TensorFlow Lite conversion, TensorFlow Lite Micro C array conversion
- Framework: TensorFlow, TensorFlow Lite, TensorFlow Lite Micro
- Training type: From scratch for SqueezeNet, AlexNet, and CNN; transfer learning / fine-tuning for MobileNet-V2 and MobileNet-V3
- Inference type: TFLite interpreter on host; intended on-device microcontroller inference

### Hardware
- Device: Target devices include OpenMV H7 board, STM32H743VI, STM32 Nucleo-144 H743ZI2, SparkEdge Apollo3 Blue, and Arduino Nano Ple33; experiments were run in Google Colab Pro with GPU P100
- Hardware type: MCU target; GPU used for experimental environment
- Processor / microcontroller: STM32H743VI; STM32 Nucleo-144 H743ZI2; Apollo3 Blue; Arduino Nano Ple33
- Clock frequency: Not reported
- SRAM / RAM: SparkEdge Apollo3 Blue has 384 KB RAM; Arduino Nano Ple33 has 32 KB RAM; Colab Pro environment had 25 GB RAM
- Flash / ROM / Storage: SparkEdge Apollo3 Blue has 1 MB Flash; Arduino Nano Ple33 has 256 KB Flash; Colab Pro had 2 TB storage
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Not reported
- Constraints mentioned: Memory, power, latency, computation, model size, and IoT resource constraints

### Dataset
- Name: YawDD dataset; Closed Eyes in the Wild dataset
- Type: Public
- Dataset size: 3,875 raw images; 7,634 augmented images
- Number of classes: 4
- Input resolution: 192 × 192 × 3 for SqueezeNet and AlexNet; 145 × 145 × 3 for CNN; 224 × 224 × 3 for MobileNet-V2 and MobileNet-V3
- Data modality: RGB image

### Metrics
- Accuracy: MobileNet-V2 0.9960; SqueezeNet 0.9947; AlexNet 0.9911; MobileNet-V3 0.9832; CNN 0.9667–0.9734 depending on phase/reporting
- mAP: Not reported
- Precision: Reported per class; best models reached up to 1.00 precision
- Recall: Reported per class; best models reached up to 1.00 recall
- F1-score: Reported per class; best models reached up to 1.00 F1-score
- Latency: Not reported as per-inference latency on target hardware
- FPS: Not reported
- Throughput: Not reported
- Model size: CNN 0.05 MB; SqueezeNet 0.141 MB; AlexNet 0.58 MB; MobileNet-V3 1.165 MB; MobileNet-V2 1.55 MB using DRQ
- Parameters: CNN 46,574; SqueezeNet 118,900; AlexNet 598,980; MobileNet-V3 1,052,020; MobileNet-V2 1,387,188
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Quantization-aware training, full-integer quantization, dynamic range quantization, TensorFlow Lite conversion, TensorFlow Lite Micro C array conversion
- Quantization: INT8, QAT, PTQ
- Pruning: No
- Knowledge distillation: No
- Compression method: Quantization
- Hardware-specific optimization: TensorFlow Lite Micro C array conversion for microcontroller deployment
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: Yes
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: CNN 0.05 MB; SqueezeNet 0.141 MB; AlexNet 0.58 MB; MobileNet-V3 1.165 MB; MobileNet-V2 1.55 MB
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported
- Runs without full operating system: Not reported
- Fully on-device inference: Not reported
- Communication required during inference: Not reported
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly targets microcontroller-class TinyML deployment using TensorFlow Lite Micro conversion and reports kilobyte- to low-megabyte-scale quantized model sizes, although target-device latency, SRAM, and energy are not measured.

### Benchmarking / Standardization
- Benchmark used: YawDD dataset; Closed Eyes in the Wild dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: YawDD; Closed Eyes in the Wild
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Code

### Results
- Summary: MobileNet-V2 achieved the highest reported accuracy of 0.9960, while the CNN model achieved the smallest quantized model size of 0.05 MB. Dynamic range quantization provided the best model-size reduction with less than approximately 1% accuracy degradation.

### Limitations
- Microcontroller implementation and real-world testing are left as ongoing research, and target-device SRAM, latency, power, and energy are not reported.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Partial
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: No
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a TinyML-based driver drowsiness detection approach using lightweight CNN-based models optimized with TensorFlow Lite quantization and prepared for microcontroller deployment through TensorFlow Lite Micro C array conversion.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Alajlan et al. | 2023 | Classification | SqueezeNet, AlexNet, CNN, MobileNet-V2, MobileNet-V3 | Quantization | Target MCUs; evaluated with TFLite interpreter / Colab Pro P100 | YawDD + CEW | Accuracy 0.9960 | N/A | 0.05–1.55 MB | N/A | N/A | N/A | TensorFlow Lite / TensorFlow Lite Micro | INT8 | TFLM | Yes |
