## Paper ID: A-Novel-Approach-for-Efficient-Detection-of-Lotus-Seedpod-Maturity-Using-Compressed-Models

TinyML classification: Near-TinyML — It targets compressed edge/mobile vision deployment on Jetson Xavier NX rather than explicit MCU, TFLite Micro, or bare-metal constraints.

### Basic Info

* Authors: Tao Tang, Min Jin, Gaohong Yu, Rui Feng, Bingliang Ye
* Year: 2025
* Title: A Novel Approach for Efficient Detection of Lotus Seedpod Maturity Using Compressed Models
* Source: IEEE Access
* Type: Experimental

### Problem & Context

* Task: Object detection
* Objective: Efficient and accurate detection of lotus seedpod maturity in complex natural environments.
* Application domain: Smart agriculture, lotus seedpod harvesting robots
* Scenario: Edge/mobile agricultural robot deployment
* TinyML relevance: Partial
* TinyML justification: The paper targets compressed on-device object detection for resource-limited mobile terminals and deploys the model on NVIDIA Jetson Xavier NX, but does not report MCU-class deployment or bare-metal/RTOS constraints.

### Model / Method

* Model: Compressed YOLOv5s-based lotus seedpod maturity detection model
* Architecture family: CNN
* Techniques: Channel pruning, sparse training, model compression, fine-tuning, data augmentation, transfer learning
* Framework: PyTorch
* Training type: Transfer learning and fine-tuning
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson Xavier NX mobile terminal
* Hardware type: SoC / GPU / edge AI device
* Processor / microcontroller: NVIDIA Jetson Xavier NX with 384 NVIDIA Volta GPU cores and 48 tensor cores
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Limited computational resources, storage capacity, model size, inference time, computational load, real-time detection

### Dataset

* Name: Lotus seedpod image dataset
* Type: Private
* Dataset size: 15,433 images after augmentation; 4,978 high-quality original images after filtering
* Number of classes: 2
* Input resolution: 640 × 640 pixels for training; original images collected at 6000 × 4000 pixels
* Data modality: RGB image

### Metrics

* Accuracy: Not reported
* mAP: 99.2%
* Precision: 98.9%
* Recall: 98.1%
* F1-score: Not reported
* Latency: Inference time reduced by 26.92%; absolute latency not reported
* FPS: 416.67 frames per second
* Throughput: 416.67 frames per second
* Model size: 3.95 MB
* Parameters: 1.90 M
* MACs / FLOPs: 5.8 G FLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Sparse training, channel pruning, model fine-tuning, channel-level model compression
* Quantization: None
* Pruning: Yes
* Knowledge distillation: No
* Compression method: Channel pruning based on Batch Normalization scaling factors with sparse training and fine-tuning
* Hardware-specific optimization: Deployment validation on Jetson Xavier NX
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 3.95 MB
* Energy per inference reported: Not reported
* Latency on target device reported: 416.67 frames per second on NVIDIA Jetson Xavier NX
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper deploys the compressed model on NVIDIA Jetson Xavier NX, an edge AI platform, without explicit MCU-class, TensorFlow Lite Micro, bare-metal, SRAM, Flash, or energy evidence.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Faster R-CNN, SSD, YOLOv5, YOLOv7-tiny, YOLOv10, YOLOv11
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The compressed model reduced parameters, model size, and inference time by 72.96%, 70.96%, and 26.92%, respectively, while achieving 99.2% mAP with only a 0.20% decrease from the original model. The deployed Jetson Xavier NX prototype achieved a 3.95 MB model size and 416.67 FPS for real-time lotus seedpod maturity detection.

### Limitations

* Not reported

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a compressed YOLOv5s-based lotus seedpod maturity detection method using sparse training, channel pruning, and fine-tuning for real-time deployment on a Jetson Xavier NX edge device.

| Paper       | Year | Task             | Model              | Technique       | Device                  | Dataset                             | Main Metric | Latency    | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ---------------- | ------------------ | --------------- | ----------------------- | ----------------------------------- | ----------- | ---------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Tang et al. | 2025 | Object detection | Compressed YOLOv5s | Channel pruning | NVIDIA Jetson Xavier NX | Private lotus seedpod image dataset | mAP 99.2%   | 416.67 FPS | 3.95 MB    | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
