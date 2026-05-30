## Paper ID: Developing-a-TinyML-Image-Classifier-in-an-Hour

TinyML classification: Strict TinyML — Explicitly targets microcontroller deployment with TensorFlow Lite models, STM32/Arduino MCU boards, and reported memory, latency, and energy constraints.

### Basic Info
- Authors: Riccardo Berta; Ali Dabbous; Luca Lazzaroni; Danilo Pietro Pau; Francesco Bellotti
- Year: 2024
- Title: Developing a TinyML Image Classifier in an Hour
- Source: IEEE Open Journal of the Industrial Electronics Society
- Type: Methodological

### Problem & Context
- Task: Classification
- Objective: To provide an agile Jupyter notebook methodology for developing microcontroller-based intelligent imaging classification sensors with model selection, quantization, deployment export, and hardware benchmarking.
- Application domain: Industrial IoT, ultralow-resolution imaging sensors, waste classification, presence detection, miniature robot detection, and sign language digit recognition.
- Scenario: Edge, embedded, IoT, MCU-based intelligent imaging sensors.
- TinyML relevance: Yes
- TinyML justification: The paper explicitly targets TinyML image classification on MCU-class platforms with memory footprint, latency, energy consumption, quantization, and deployment-ready TensorFlow Lite models.

### Model / Method
- Model: Linear SVM, KNN, Random Forest, MLP, and CNN models selected through the TICE notebook workflow.
- Architecture family: CNN / Classical ML / Other
- Techniques: Hyperparameter tuning, dynamic quantization, static quantization, quantization-aware training, TensorFlow Lite export, hardware benchmarking.
- Framework: Scikit-learn, TensorFlow, Keras, TensorFlow Lite, TensorFlow Lite Micro, STM32Cube.AI, X-CUBE-AI
- Training type: From scratch
- Inference type: On-device

### Hardware
- Device: STM32F091, STM32F401, STM32L4R9I, STM32H7B3I, Arduino Nano 33 BLE Sense Rev2
- Hardware type: MCU
- Processor / microcontroller: STM32 F0, STM32 F4, STM32 L4, STM32 H7, Arduino Nano 33 BLE Sense Rev2
- Clock frequency: 48 MHz, 84 MHz, 120 MHz, 480 MHz, and 64 MHz
- SRAM / RAM: 32 KiB, 96 KiB, 640 KiB, 1400 KiB, and 256 KiB
- Flash / ROM / Storage: 256 KiB, 512 KiB, 2000 KiB, 2000 KiB, and 1000 KiB
- Power consumption: Not reported
- Energy per inference: 0.14–174,810.24 μJ across reported models and devices
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Memory footprint, ROM, RAM, latency, energy consumption, model size, MACC, FLOPs, and computational efficiency

### Dataset
- Name: TOF; Electronic Parts Dataset; Infrared Thermal Dataset; Sign Finger Digits
- Type: Public
- Dataset size: TOF: 4150 images; EPD: 1734 images; ITD: 1770 images; SFD: 3200 images
- Number of classes: TOF: 2; EPD: 3; ITD: 4; SFD: 10
- Input resolution: TOF: up to 8×8; EPD: 30×30; ITD: 32×24; SFD: 32×32
- Data modality: Time-of-flight depth images, grayscale visible-light images, infrared thermal images, and thermal images

### Metrics
- Accuracy: Static-quantized CNN results include TOF: 98.07%, EPD: 99.63%, ITD: 95.99%, and SFD: 99.16%
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: 0.08–3469.08 ms across reported models and devices; best CNN on STM32H7 reports TOF: 0.32 ms, EPD: 30.25 ms, ITD: 21.93 ms, and SFD: 15.06 ms
- FPS: Not reported
- Throughput: Not reported
- Model size: Static-quantized CNN TFLite model sizes range from 12 KiB to 123 KiB
- Parameters: Not reported
- MACs / FLOPs: Best static-quantized CNNs report 15,772 MACC for TOF, 5,277,598 MACC for EPD, 3,446,056 MACC for ITD, and 1,975,764 MACC for SFD
- RAM usage: Static-quantized CNN activation sizes include 1.37 KiB for TOF, 23.48 KiB for EPD, 20.03 KiB for ITD, and 20.03 KiB for SFD
- Flash usage: ROM usage percentages are reported across MCU boards, ranging from 0.36% to 46.83% for best CNN models
- Energy per inference: Best CNN on STM32H7 reports TOF: 72.00 μJ, EPD: 6892.79 μJ, ITD: 4996.80 μJ, and SFD: 3470.40 μJ
- Power consumption: Not reported

### Optimization
- Techniques used: Hyperparameter tuning, TensorFlow Lite conversion, dynamic quantization, static quantization, quantization-aware training, STM32Cube.AI hardware analysis and benchmarking
- Quantization: INT8 PTQ and QAT
- Pruning: No
- Knowledge distillation: No
- Compression method: Quantization
- Hardware-specific optimization: STM32Cube.AI / X-CUBE-AI deployment and benchmarking, TensorFlow Lite Micro deployment on Arduino
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Yes
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: ROM usage percentages and target ROM capacities are reported
- Model size reported: Yes
- Energy per inference reported: Yes
- Latency on target device reported: Yes
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No
- Candidate for Strict TinyML: Yes
- Reason: The paper explicitly targets MCU-class image-classification deployment on STM32 and Arduino boards with reported model size, RAM/ROM usage, latency, and energy per inference.

### Benchmarking / Standardization
- Benchmark used: Four ultralow-resolution image-classification case-study datasets and STM32Cube.AI hardware benchmarking
- MLPerf Tiny mentioned: Yes
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Code

### Results
- Summary: The TICE notebook produced MCU-deployment-ready TinyML image classifiers for four ultralow-resolution datasets in less than one hour per dataset. Quantized CNN models achieved high accuracy while reporting embedded metrics such as ROM/RAM usage, latency, MACC, and energy consumption on STM32 and Arduino MCU boards.

### Limitations
- The evaluation focuses on ultralow-resolution image-classification datasets because the target models are designed to fit typical MCU ROM and RAM constraints.
- Object detection, anomaly detection, time-series processing, and other sensor domains are left as future research directions.

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
- This paper proposes TICE, an agile Jupyter notebook workflow for developing, quantizing, exporting, and benchmarking MCU-deployable TinyML image classifiers for ultralow-resolution imaging sensors.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Berta et al. | 2024 | Classification | CNN / MLP / Classical ML | Quantization and hardware benchmarking | STM32F091, STM32F401, STM32L4R9I, STM32H7B3I, Arduino Nano 33 BLE Sense Rev2 | TOF; EPD; ITD; SFD | Accuracy: up to 99.63% for static-quantized CNN and 100.00% for customized SFD CNN | 0.08–3469.08 ms | 12–123 KiB static-quantized CNN TFLite model size | 1.37–23.48 KiB CNN activation size | 0.36–46.83% ROM usage for best CNN models | 0.14–174,810.24 μJ | TensorFlow Lite; TensorFlow Lite Micro; STM32Cube.AI | INT8/QAT | TFLM | Yes |
