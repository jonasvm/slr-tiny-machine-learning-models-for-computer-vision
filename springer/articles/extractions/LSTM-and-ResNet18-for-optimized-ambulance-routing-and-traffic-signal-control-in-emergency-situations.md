## Paper ID: LSTM-and-ResNet18-for-optimized-ambulance-routing-and-traffic-signal-control-in-emergency-situations

TinyML classification: Near-TinyML — The system uses Raspberry Pi/Arduino and real-time edge/embedded traffic-control components, but the ML evidence is not explicitly MCU-class.

### Basic Info
- Authors: Madallah Alruwaili; Ali Ali; Mohammed Almutairi; Abdulaziz Alsahyan; Mahmood Mohamed
- Year: 2025
- Title: LSTM and ResNet18 for optimized ambulance routing and traffic signal control in emergency situations
- Source: Scientific Reports, 15:6011, https://doi.org/10.1038/s41598-025-89651-4
- Type: Experimental

### Problem & Context
- Task: Classification / audio-visual ambulance detection
- Objective: Detect ambulances in real time using audio and visual signals to prioritize traffic lights and reduce emergency response delays.
- Application domain: Emergency medical services and smart traffic management
- Scenario: Edge / embedded / smart-city traffic-control system
- TinyML relevance: Partial
- TinyML justification: The system uses Raspberry Pi 4 and Arduino UNO for real-time traffic signal prioritization, but the paper does not report MCU-class ML inference, memory constraints, energy, model size, or TensorFlow Lite Micro deployment.

### Model / Method
- Model: LSTM for audio classification, ResNet18-top for image classification, and a fused LSTM + ResNet18 model
- Architecture family: Hybrid CNN / RNN
- Techniques: MFCC feature extraction, ImageNet transfer learning, multimodal audio-visual fusion, empirical risk minimization
- Framework: Python; specific ML framework not reported
- Training type: Transfer learning / fine-tuning for ResNet18; LSTM training details not fully reported
- Inference type: Not reported

### Hardware
- Device: Raspberry Pi 4, Arduino UNO, traffic light LED module, USB camera, audio detection component
- Hardware type: SoC / MCU / Other
- Processor / microcontroller: Raspberry Pi 4 with 1.5 GHz quad-core processor; Arduino UNO with 16 MHz clock speed
- Clock frequency: 1.5 GHz for Raspberry Pi 4; 16 MHz for Arduino UNO
- SRAM / RAM: 4 GB RAM for Raspberry Pi 4; Arduino memory not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Not reported
- Constraints mentioned: Real-time response, latency, computational cost, traffic congestion, system integration

### Dataset
- Name: Dataset for Classification of Specialty Cars; Emergency Vehicle Siren Sounds dataset
- Type: Public
- Dataset size: Fusion model evaluated on 760 samples; full dataset size not reported
- Number of classes: Image/fusion classification uses 2 classes; audio confusion matrix reports ambulance, firetruck, and traffic sounds
- Input resolution: 224×224 pixels for images; 1080p camera capture reported for the system
- Data modality: RGB image / video frames + audio

### Metrics
- Accuracy: LSTM audio classification 98.3%; ResNet18-top image classification 98.1%; proposed fusion model 98.95%
- mAP: Not reported
- Precision: LSTM 98.0%; ResNet18-top 98.0%; proposed fusion model 98.95%
- Recall: LSTM 98.5%; ResNet18-top 98.2%; proposed fusion model 98.95%
- F1-score: LSTM 98.3%; ResNet18-top 98.1%; proposed fusion model 98.95%
- Latency: Traffic light model response time approximately 1 ms; ML inference latency not reported
- FPS: USB camera 30–60 fps
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported for ML inference
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: MFCC preprocessing, ImageNet transfer learning, multimodal fusion
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Not reported
- Hardware-specific optimization: Not reported
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported for ML inference
- Runs without full operating system: Not reported
- Fully on-device inference: Not reported
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper uses Raspberry Pi and Arduino-based traffic-control hardware, but it does not explicitly demonstrate MCU-class ML deployment or report TinyML-level memory, latency, energy, or model-size constraints.

### Benchmarking / Standardization
- Benchmark used: Not reported
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: ImageNet used for pre-training; Kaggle datasets used for evaluation
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Dataset URLs reported; code and model not reported

### Results
- Summary: The proposed fused LSTM + ResNet18 model achieved 98.95% accuracy, precision, recall, and F1-score on 760 samples. The paper reports that multimodal audio-visual fusion outperformed the individual CNN, LSTM, and ResNet18 models for emergency vehicle detection.

### Limitations
- Integration with existing traffic infrastructure may require significant upgrades or coordination with authorities.
- Audio and image capture in public environments raises privacy concerns.
- Real-time large-scale deployment may require high accuracy with low latency and can be computationally expensive.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes, but only for traffic signal response time, not ML inference
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes, dataset URLs only

### Contribution
- This paper proposes an AI-driven emergency traffic management system that combines LSTM-based siren recognition, ResNet18-based ambulance image classification, and Raspberry Pi/Arduino-based traffic signal prioritization.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Alruwaili et al. | 2025 | Audio-visual ambulance classification/detection | LSTM + ResNet18 fusion | MFCC + ImageNet transfer learning + multimodal fusion | Raspberry Pi 4 / Arduino UNO / USB camera | Dataset for Classification of Specialty Cars + Emergency Vehicle Siren Sounds | Fusion accuracy 98.95% | N/A | N/A | 4 GB RAM on Raspberry Pi 4; ML RAM N/A | N/A | N/A | Python; specific framework N/A | N/A | N/A | No |
