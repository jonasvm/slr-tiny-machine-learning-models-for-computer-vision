## Paper ID: An-Ultra-low-power-Embedded-AI-Fire-Detection-and-Crowd-Counting-System-for-Indoor-Areas

TinyML classification: Strict TinyML — The system explicitly targets an STM32L496VGT6P ARM Cortex-M4 MCU with 1 MB Flash, 320 KB SRAM, TFLM deployment, and measured energy/memory/latency constraints.

### Basic Info

* Authors: Alexios Papaioannou, Charalampos S. Kouzinopoulos, Dimosthenis Ioannidis, Dimitrios Tzovaras
* Year: 2023
* Title: An Ultra-low-power Embedded AI Fire Detection and Crowd Counting System for Indoor Areas
* Source: ACM Transactions on Embedded Computing Systems, Vol. 22, No. 4, Article 61, July 2023
* Type: Experimental

### Problem & Context

* Task: Fire detection classification and crowd counting object detection
* Objective: To develop an ultra-low-power embedded system for indoor fire detection and crowd counting using efficient deep learning methods.
* Application domain: Indoor fire safety, smart buildings, emergency monitoring
* Scenario: MCU-based embedded IoT system
* TinyML relevance: Yes
* TinyML justification: The paper targets an ultra-low-power ARM Cortex-M4 MCU platform with constrained SRAM/Flash, TensorFlow Lite Micro deployment, INT8 quantization, and measured memory, latency, energy, and power consumption.

### Model / Method

* Model: Chain of MLP models for fire detection; custom lightweight YOLOv5 for crowd counting
* Architecture family: CNN and MLP
* Techniques: Lightweight YOLOv5 modification, ShuffleNetV2 backbone, reduced detection layers, reduced PANet, grayscale input, ReLU replacement for SiLU, INT8 quantization, quantization-aware training
* Framework: PyTorch, ONNX, OpenVINO, TensorFlow, TensorFlow Lite Micro
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Custom ultra-low-power embedded platform
* Hardware type: MCU
* Processor / microcontroller: STM32L496VGT6P ARM Cortex-M4 ultra-low-power MCU
* Clock frequency: Up to 80 MHz; 4 MHz during monitoring and 80 MHz during crowd counting
* SRAM / RAM: 320 KB SRAM
* Flash / ROM / Storage: 1 MB Flash
* Power consumption: 51.36 mW average in active mode; 15.2 mW in standby mode with 51.4 mW peak every 10 seconds
* Energy per inference: 3.38e-5 J for MLP execution; 1.03 J for LW-YOLOv5 execution; 1.13 J total active-mode energy cost
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, latency, energy, compute, model size

### Dataset

* Name: Custom fire detection dataset; public indoor fire dataset; custom CERTH/ITI crowd counting dataset
* Type: Public and private
* Dataset size: Fire detection custom dataset has approximately 8,500 data points; crowd counting dataset has 3,680 training images, 1,051 testing images, and 525 evaluation images
* Number of classes: Fire detection has 2 classes; crowd counting detects people/heads
* Input resolution: Crowd counting images captured at 320 × 240 and cropped to 128 × 128
* Data modality: Environmental sensor data, gas sensor data, grayscale images

### Metrics

* Accuracy: 0.974 for selected INT8 fire detection model on custom dataset; approximately 0.98 on public dataset
* mAP: 0.974 mAP@0.5 and 0.619 mAP@0.5:0.95 for selected LW-YOLOv5 crowd counting model
* Precision: 0.954 for selected LW-YOLOv5 crowd counting model
* Recall: 0.969 for selected LW-YOLOv5 crowd counting model
* F1-score: 0.975 for selected INT8 fire detection model
* Latency: 6.80 ms for selected fire detection model; 21.3 s for selected LW-YOLOv5 crowd counting model
* FPS: Not reported
* Throughput: Not reported
* Model size: 13.191 KB for selected fire detection model; 113.3 KB for selected LW-YOLOv5 crowd counting model
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: 3.38e-5 J for MLP execution; 1.03 J for LW-YOLOv5 execution
* Power consumption: 51.36 mW average in active mode; 15.2 mW in standby mode

### Optimization

* Techniques used: Lightweight backbone replacement, reduced detection layers, reduced PANet, grayscale input, ReLU activation, INT8 quantization, quantization-aware training, MCU clock scaling, low-power sleep modes
* Quantization: INT8 QAT
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Lightweight YOLOv5 redesign using ShuffleNetV2 and reduced network components
* Hardware-specific optimization: MCU power-mode configuration, dynamic clock scaling, and TensorFlow Lite Micro deployment
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Yes
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 13.191 KB for selected fire detection model; 113.3 KB for selected LW-YOLOv5 model
* Energy per inference reported: 3.38e-5 J for MLP execution; 1.03 J for LW-YOLOv5 execution
* Latency on target device reported: 6.80 ms for MLP execution; 21.3 s for LW-YOLOv5 execution
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No cloud/offloaded inference reported; wireless communication is used for notification after detection
* Candidate for Strict TinyML: Yes
* Reason: The system is deployed on an STM32L496VGT6P ARM Cortex-M4 MCU with 320 KB SRAM, 1 MB Flash, TensorFlow Lite Micro inference, INT8 quantization, and measured energy, latency, and model-size constraints.

### Benchmarking / Standardization

* Benchmark used: Custom datasets and one public indoor fire dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: YOLOv5s variants and multiple MLP architectures
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The selected INT8 fire detection model achieved 0.974 accuracy, 0.975 F1-score, 13.191 KB model size, and 6.80 ms execution time. The selected LW-YOLOv5 model achieved 0.974 mAP@0.5, 0.619 mAP@0.5:0.95, 113.3 KB model size, and 21.3 s execution time on the MCU platform. The system can operate for approximately two months using a 3.7 V, 7,000 mAh Li-Ion battery.

### Limitations

* The fire detection subsystem could be improved by integrating a low-power CO sensor.
* The system would benefit from gas sensors with lower power consumption.
* The crowd counting subsystem requires more training images from different indoor areas and chaotic emergency scenarios.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an ultra-low-power MCU-based embedded AI system that combines MLP-based fire detection and lightweight YOLOv5-based crowd counting with TensorFlow Lite Micro deployment and measured energy, latency, and model-size constraints.

| Paper              | Year | Task                                                              | Model                          | Technique                                                           | Device                           | Dataset                                                                 | Main Metric                                                                                | Latency                       | Model Size                        | SRAM/RAM                                 | Flash                                    | Energy                          | Framework                                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------------ | ---- | ----------------------------------------------------------------- | ------------------------------ | ------------------------------------------------------------------- | -------------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | ----------------------------- | --------------------------------- | ---------------------------------------- | ---------------------------------------- | ------------------------------- | ----------------------------------------- | -------- | ------------- | ------------- |
| Papaioannou et al. | 2023 | Fire detection classification and crowd counting object detection | Chain of MLP models; LW-YOLOv5 | ShuffleNetV2 lightweight YOLOv5, reduced detection layers, INT8 QAT | STM32L496VGT6P ARM Cortex-M4 MCU | Custom fire dataset; public fire dataset; custom crowd counting dataset | 0.974 mAP@0.5 and 0.619 mAP@0.5:0.95 for crowd counting; 0.974 accuracy for fire detection | 6.80 ms MLP; 21.3 s LW-YOLOv5 | 13.191 KB MLP; 113.3 KB LW-YOLOv5 | 320 KB SRAM available; peak not reported | 1 MB Flash available; usage not reported | 3.38e-5 J MLP; 1.03 J LW-YOLOv5 | PyTorch, ONNX, OpenVINO, TensorFlow, TFLM | INT8 QAT | TFLM          | Yes           |
