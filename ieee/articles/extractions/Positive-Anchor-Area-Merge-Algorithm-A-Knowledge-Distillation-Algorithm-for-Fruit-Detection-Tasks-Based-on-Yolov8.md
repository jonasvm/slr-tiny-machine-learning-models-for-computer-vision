## Paper ID: Positive-Anchor-Area-Merge-Algorithm-A-Knowledge-Distillation-Algorithm-for-Fruit-Detection-Tasks-Based-on-Yolov8

TinyML classification: Near-TinyML — The paper reports embedded deployment on Raspberry Pi 4B, but does not provide explicit MCU-class or TensorFlow Lite Micro deployment evidence.

### Basic Info

* Authors: Xiangqun Shi, Xian Zhang, Yifan Su, Xun Zhang
* Year: 2025
* Title: Positive Anchor Area Merge Algorithm: A Knowledge Distillation Algorithm for Fruit Detection Tasks Based on Yolov8
* Source: IEEE Access, Volume 13, 2025, DOI: 10.1109/ACCESS.2025.3544361
* Type: Methodological

### Problem & Context

* Task: Object detection
* Objective: Improve YOLOv8 fruit detection accuracy using knowledge distillation while maintaining low resource overhead for embedded deployment.
* Application domain: Agriculture, fruit detection, fruit sorting, fruit monitoring, yield-related visual detection
* Scenario: Embedded / edge agricultural vision
* TinyML relevance: Partial
* TinyML justification: The paper targets embedded real-time fruit detection and deploys the model on Raspberry Pi 4B, but it does not report MCU-class deployment, bare-metal/RTOS execution, TensorFlow Lite Micro, SRAM/Flash limits, or energy per inference.

### Model / Method

* Model: YOLOv8-lite; teacher model YOLOv8s; student model YOLOv8n
* Architecture family: CNN
* Techniques: Knowledge distillation, Positive Anchor Area Merge Algorithm, parallel teacher-student distillation network, distillation loss modification, positive anchor assignment merging
* Framework: Ultralytics YOLOv8 version 1.34; PyTorch 2.0.1; Python 3.10.14
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Raspberry Pi 4B with 5-megapixel external camera
* Hardware type: SoC
* Processor / microcontroller: Not reported for deployment; training used Intel Core i7-11800H
* Clock frequency: Not reported for deployment; training CPU base frequency 2.3 GHz
* SRAM / RAM: Not reported for deployment; training system used 16 GB RAM
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Resource consumption, model size, memory footprint, runtime efficiency, inference speed, embedded deployment

### Dataset

* Name: Self-constructed fruit dataset
* Type: Private
* Dataset size: Over 3,000 training images per category
* Number of classes: 3
* Input resolution: 640 × 640 RGB
* Data modality: RGB image

### Metrics

* Accuracy: Not reported
* mAP: mAP(50) 99.469%; mAP(50-95) 96.94%
* Precision: 99.969%
* Recall: 99.354%
* F1-score: Not reported
* Latency: 11.7 ms mean inference speed; approximately 90 ms per frame on Raspberry Pi 4B
* FPS: Not reported
* Throughput: Not reported
* Model size: 24 MB
* Parameters: 3.15M
* MACs / FLOPs: 8.7G FLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Knowledge distillation, positive anchor area merging, YOLOv8 loss-function modification
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Yes
* Compression method: Teacher-student knowledge distillation from YOLOv8s to YOLOv8n
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 24 MB
* Energy per inference reported: Not reported
* Latency on target device reported: Approximately 90 ms per frame on Raspberry Pi 4B
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The model is deployed on Raspberry Pi 4B rather than MCU-class hardware and lacks reported SRAM, Flash, energy, RTOS/bare-metal, or TensorFlow Lite Micro evidence.

### Benchmarking / Standardization

* Benchmark used: Self-constructed fruit dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: COCO is mentioned as background, but not used as the evaluation benchmark.
* Comparison with baseline models: Yes; YOLOv8n, YOLOv8s, YOLOv6n, YOLOv6s, YOLOv5n, YOLOv5s, YOLOv5n-p6, YOLOv5s-p6
* Comparison with previous works: Not reported
* Reproducibility artifacts available: Not reported

### Results

* Summary: YOLOv8-lite achieved 99.469% mAP(50), 99.969% precision, and 99.354% recall with 24 MB model size, 3.15M parameters, and 8.7G FLOPs. The deployed Raspberry Pi 4B system reached approximately 90 ms per frame for real-time fruit detection.

### Limitations

* The paper reports weaker performance on mAP(50-95) compared with its mAP(50) results, indicating reduced robustness in more complex detection scenarios.
* The conclusion states that improving sensitivity to subtle object differences and reducing false positives remain future challenges.

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

* This paper proposes a YOLOv8-based knowledge distillation method called Positive Anchor Area Merge Algorithm to improve fruit object detection accuracy by merging teacher and student positive anchor regions during training.

| Paper      | Year | Task             | Model       | Technique              | Device          | Dataset                        | Main Metric     | Latency                         | Model Size | SRAM/RAM | Flash | Energy | Framework                    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | ---------------- | ----------- | ---------------------- | --------------- | ------------------------------ | --------------- | ------------------------------- | ---------- | -------- | ----- | ------ | ---------------------------- | -------- | ------------- | ------------- |
| Shi et al. | 2025 | Object detection | YOLOv8-lite | Knowledge distillation | Raspberry Pi 4B | Self-constructed fruit dataset | mAP(50) 99.469% | ~90 ms/frame on Raspberry Pi 4B | 24 MB      | N/A      | N/A   | N/A    | Ultralytics YOLOv8 / PyTorch | N/A      | N/A           | No            |
