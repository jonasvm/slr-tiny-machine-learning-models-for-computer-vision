## Paper ID: Development-of-an-AI-powered-AR-glasses-system-for-real-time-first-aid-guidance-in-emergency-situations

TinyML classification: Near-TinyML — the system uses embedded edge hardware such as Jetson Nano, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Mohammed Abo-Zahhad; Mostafa N. Zakaria; Farida M. Sharaf; May M. Ismaiel; Habiba Hafrag; Yousef M. Amer
* Year: 2025
* Title: Development of an AI-powered AR glasses system for real-time first aid guidance in emergency situations
* Source: BioData Mining, 18:59
* Type: Experimental

### Problem & Context

* Task: Object detection and burn severity classification
* Objective: Assist untrained bystanders with real-time first aid guidance using AI-based visual detection, AR overlays, and text-to-speech instructions.
* Application domain: Emergency healthcare and first aid assistance
* Scenario: Edge, embedded, wearable AR prototype
* TinyML relevance: Partial
* TinyML justification: The system performs edge-based computer vision on Jetson Nano using lightweight YOLOv5, but it does not report MCU-class deployment or strict SRAM/Flash constraints.

### Model / Method

* Model: YOLOv5s with separate models for chest detection, wound/bleeding detection, burn classification, and first aid kit recognition
* Architecture family: CNN
* Techniques: Transfer learning, data augmentation, lightweight object detection, scenario-specific instruction mapping
* Framework: PyTorch, YOLOv5, OpenCV, PyQt5/Tkinter, pyttsx3, JetPack, CUDA
* Training type: Transfer learning / fine-tuning
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson Nano, Raspberry Pi V2 camera, TFT LCD mounted in VR headset
* Hardware type: SoC / GPU / Other
* Processor / microcontroller: NVIDIA Jetson Nano with 64-bit ARM architecture and CUDA-capable GPU
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: microSD card used; capacity not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Processing power, latency, high-resolution input, multiple detections, battery duration, temperature, energy consumption, real-world lighting, motion blur, and dataset imbalance

### Dataset

* Name: First aid kit component detection dataset; Wound Dataset; Blood Dataset; Skin Burns dataset; chest_area dataset
* Type: Public / not fully reported
* Dataset size: First aid kit: 513 train, 30 validation, 15 test; wound: 2,295 train, 420 validation, 156 test; blood: 77 train, 10 validation, 30 test; burn: 4,164 train, 399 validation, 200 test; chest: 670 train, 50 validation, 50 test
* Number of classes: First aid kit supplies not fully enumerated; bleeding severity classes include light and heavy bleeding; burn has 3 classes; chest has 1 detected class
* Input resolution: 640×640
* Data modality: RGB image / live video

### Metrics

* Accuracy: Not reported
* mAP: Approximately 85% mAP@0.5 across different classes
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Text-to-speech latency typically under 200 ms; maximum multimodal asynchrony ±250 ms
* FPS: Approximately 10 FPS on edge devices
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight YOLOv5s model, transfer learning from pretrained COCO weights, data augmentation, GPU acceleration, confidence threshold filtering
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: GPU acceleration on Jetson Nano
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Approximately 10 FPS on edge devices; no per-inference latency reported
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: No
* Reason: The deployment uses a Linux-based Jetson Nano edge platform and does not provide MCU-class deployment, SRAM/Flash usage, or energy-per-inference evidence.

### Benchmarking / Standardization

* Benchmark used: Custom emergency scenario datasets
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: COCO pretrained weights used for transfer learning
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: dataset

### Results

* Summary: The system achieved approximately 85% mAP@0.5 across emergency-related detection classes and demonstrated real-time guidance using YOLOv5, AR overlays, and text-to-speech on Jetson Nano. The paper reports usability and responsiveness benefits but does not report strict TinyML memory, energy, or MCU deployment metrics.

### Limitations

* Jetson Nano processing limitations can cause inference delays with high-resolution inputs or multiple detections.
* The VR headset prototype is bulky and may reduce comfort during high-stress use.
* External battery dependence limits operational duration and mobility.
* Dataset imbalance and environmental factors such as poor lighting and motion blur affect detection accuracy.
* The system currently supports only four emergency scenarios.
* GUI usability, text-to-speech clarity, lack of haptic feedback, privacy, regulatory approval, and scalability remain challenges.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes an AI-powered AR first aid guidance system that combines YOLOv5-based real-time emergency detection, Jetson Nano edge inference, AR visual overlays, and text-to-speech instructions to support untrained bystanders during emergency response.

| Paper             | Year | Task                                              | Model   | Technique                                        | Device             | Dataset                                               | Main Metric   | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework                           | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------------- | ---- | ------------------------------------------------- | ------- | ------------------------------------------------ | ------------------ | ----------------------------------------------------- | ------------- | ------- | ---------- | -------- | ----- | ------ | ----------------------------------- | -------- | ------------- | ------------- |
| Abo-Zahhad et al. | 2025 | Object detection and burn severity classification | YOLOv5s | Transfer learning and lightweight edge detection | NVIDIA Jetson Nano | First aid kit, wound, blood, burn, and chest datasets | mAP@0.5 ≈ 85% | N/A     | N/A        | N/A      | N/A   | N/A    | PyTorch / YOLOv5 / OpenCV / JetPack | N/A      | None          | No            |
