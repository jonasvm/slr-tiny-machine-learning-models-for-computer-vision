## Paper ID: PRDTinyML-deep-learning-based-TinyML-based-pedestrian-detection-model-in-autonomous-vehicles-for-smart-cities

TinyML classification: Strict TinyML — The paper explicitly targets microcontroller-deployable TinyML models with quantization, very small model sizes, TFLite Micro conversion, and C-array deployment.

### Basic Info
- Authors: Norah N. Alajlan, Abeer I. Alhujaylan, Dina M. Ibrahim
- Year: 2025
- Title: PRDTinyML: deep learning-based TinyML-based pedestrian detection model in autonomous vehicles for smart cities
- Source: Indonesian Journal of Electrical Engineering and Computer Science, Vol. 39, No. 1, pp. 283–309
- Type: Experimental

### Problem & Context
- Task: Classification / pedestrian-rider recognition
- Objective: Develop lightweight deep learning models for pedestrian and rider recognition in autonomous vehicle smart-city scenarios.
- Application domain: Smart transportation, autonomous vehicles, smart cities
- Scenario: Edge, embedded, IoT, autonomous system
- TinyML relevance: Yes
- TinyML justification: The paper explicitly targets TinyML and microcontroller-deployable lightweight models using TFLite/TFLite Micro conversion, quantization, and C-array model generation.

### Model / Method
- Model: SqueezeNet, AlexNet, CNN, MobileNet-V2, MobileNet-V3
- Architecture family: CNN
- Techniques: Quantization, QAT, PTQ, full integer quantization, dynamic range quantization, model compression, TFLite conversion, TFLite Micro C-array conversion
- Framework: TensorFlow, TensorFlow Lite, TensorFlow Lite Micro
- Training type: From scratch for SqueezeNet, AlexNet, and CNN; transfer learning / fine-tuning for MobileNet-V2 and MobileNet-V3
- Inference type: On-device intended; evaluated using TFLite interpreter on host computer

### Hardware
- Device: Target microcontroller not reported; experiments implemented on Google Colab Pro
- Hardware type: MCU targeted; GPU used for implementation environment
- Processor / microcontroller: GPU processor P100 for Colab; target microcontroller not reported
- Clock frequency: Not reported
- SRAM / RAM: 25 GB RAM for Colab; target SRAM/RAM not reported
- Flash / ROM / Storage: 2 TB Colab storage; target Flash/ROM not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Not reported
- Constraints mentioned: Memory footprint, model size, power, latency, computation, IoT resource constraints

### Dataset
- Name: EuroCity Persons (ECP)
- Type: Public
- Dataset size: Over 47,300 images and over 238,200 annotated person instances
- Number of classes: 2 main classes: pedestrian and rider; rider includes 7 object types
- Input resolution: SqueezeNet 192×192×3; CNN 145×145×3; MobileNet-V2 224×224×3; MobileNet-V3 224×224×3; AlexNet input resolution inconsistently reported
- Data modality: Day and night road traffic images

### Metrics
- Accuracy: Best reported MobileNet-V3 accuracy was 99.66% for day images and 99.56% for night images; best interpreter accuracy was 99.64% for MobileNet-V3 with DRQ on SSD day images
- mAP: Not reported
- Precision: Reported for pedestrian/rider evaluation; MobileNet-V3 achieved 100% precision for pedestrian and rider in Table 8
- Recall: Reported for pedestrian/rider evaluation; MobileNet-V3 achieved 99% recall for pedestrian and 100% recall for rider in Table 8
- F1-score: Reported for pedestrian/rider evaluation; MobileNet-V3 achieved 100% F1-score for pedestrian and rider in Table 8
- Latency: Interpreter time reported, but target-device latency not reported
- FPS: Not reported
- Throughput: Not reported
- Model size: CNN 0.07 MB DRQ; SqueezeNet 0.161 MB DRQ; AlexNet 0.69 MB DRQ; MobileNet-V2 1.95 MB DRQ; MobileNet-V3 1.813 MB DRQ / 1.824 MB FIQ
- Parameters: SqueezeNet 121,500; AlexNet 486,960; CNN 39,554; MobileNet-V2 1,256,178; MobileNet-V3 1,039,180
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Quantization aware training, full integer quantization, dynamic range quantization, TensorFlow Lite conversion, TensorFlow Lite Micro C-array conversion
- Quantization: INT8 / QAT / PTQ
- Pruning: No
- Knowledge distillation: No
- Compression method: QAT, FIQ, and DRQ quantization
- Hardware-specific optimization: TFLite Micro conversion to C array for microcontroller compilation
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: Yes
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Yes; smallest model was CNN with 0.07 MB after DRQ
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported
- Runs without full operating system: Not reported
- Fully on-device inference: Not reported
- Communication required during inference: Not reported
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly targets microcontroller-deployable TinyML models and uses TFLite Micro C-array conversion, but it does not report real MCU SRAM, Flash, energy, or target-device latency.

### Benchmarking / Standardization
- Benchmark used: EuroCity Persons dataset
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: ImageNet used for MobileNet pretraining
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Not reported

### Results
- Summary: The paper reports that MobileNet-V3 and MobileNet-V2 achieved the highest accuracy, with MobileNet-V3 reaching 99.66% for day images and MobileNet-V2 reaching 99.56% for night images. Quantization reduced model sizes substantially, with the smallest compressed CNN model reaching 0.07 MB and less than 1% reported accuracy loss after optimization.

### Limitations
- Not reported

### Practical Reporting Checklist Evidence
- Reports hardware clearly: No
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a TinyML-based pedestrian and rider recognition approach using five lightweight CNN-based models optimized with quantization and converted to TensorFlow Lite/TensorFlow Lite Micro for microcontroller-oriented deployment.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Alajlan et al. | 2025 | Classification / pedestrian-rider recognition | SqueezeNet, AlexNet, CNN, MobileNet-V2, MobileNet-V3 | Quantization with QAT, FIQ, and DRQ | Microcontroller targeted; Colab Pro P100 used experimentally | EuroCity Persons | Accuracy: 99.66% day / 99.56% night | Target-device latency N/A | 0.07 MB smallest; 1.813 MB MobileNet-V3 DRQ | N/A | N/A | N/A | TensorFlow Lite / TensorFlow Lite Micro | INT8, QAT, PTQ | TFLM | Yes |
