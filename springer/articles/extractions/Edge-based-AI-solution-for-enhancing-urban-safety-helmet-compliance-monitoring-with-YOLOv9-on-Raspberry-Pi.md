## Paper ID: Edge-based-AI-solution-for-enhancing-urban-safety-helmet-compliance-monitoring-with-YOLOv9-on-Raspberry-Pi

TinyML classification: Near-TinyML — Evaluated on Raspberry Pi edge hardware, with no explicit MCU-class deployment or memory constraints.

### Basic Info

* Authors: Nikunj Tahilramani; Param Ahir; Shruti Saxena; Vandana P. Talreja; Panem Charanarur
* Year: 2025
* Title: Edge-based AI solution for enhancing urban safety: helmet compliance monitoring with YOLOv9 on Raspberry Pi
* Source: Discover Internet of Things, 5:25
* Type: Experimental

### Problem & Context

* Task: Object detection
* Objective: Detect motorcycle helmet use in real time and prevent vehicle ignition when no helmet is detected.
* Application domain: Urban safety, road safety, intelligent transportation systems
* Scenario: Edge, embedded IoT, vehicle-mounted system
* TinyML relevance: Partial
* TinyML justification: The paper targets on-device edge inference on Raspberry Pi, but does not report MCU-class deployment, SRAM/Flash constraints, or bare-metal/RTOS execution.

### Model / Method

* Model: YOLOv9
* Architecture family: CNN
* Techniques: Real-time object detection, edge deployment, data augmentation, Distribution Focal Loss
* Framework: Not reported
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Raspberry Pi 3 Model B+ with Raspberry Pi camera and ignition control interface
* Hardware type: SoC / CPU
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Latency, computational power, network dependence, power constraints, lighting conditions, occlusion, scalability

### Dataset

* Name: Bikes Helmets dataset; Kaggle helmet detection dataset; Raspberry Pi camera images
* Type: Public + private
* Dataset size: Validation set of 97 images with 195 instances; full dataset size not reported
* Number of classes: 2
* Input resolution: 640 × 640
* Data modality: RGB images and video frames

### Metrics

* Accuracy: Not reported
* mAP: mAP50 = 0.967; mAP50-95 = 0.720
* Precision: 0.894
* Recall: 0.943
* F1-score: Not reported
* Latency: 0.2 ms preprocessing, 21.0 ms inference, 4.2 ms postprocessing, approximately 25.4 ms total per image
* FPS: Not reported
* Throughput: Not reported
* Model size: 51.6 MB
* Parameters: Approximately 25.5 million
* MACs / FLOPs: 103.7 GFLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Data augmentation, Mosaic, MixUp, random flipping, scaling, translation, color adjustment, edge deployment on Raspberry Pi
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: Raspberry Pi edge deployment, but no explicit hardware-specific optimization method reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 51.6 MB
* Energy per inference reported: Not reported
* Latency on target device reported: 21.0 ms inference per image reported, but the measurement platform is not clearly separated from the validation setup
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No continuous cloud access reported
* Candidate for Strict TinyML: No
* Reason: The system uses Raspberry Pi edge hardware rather than MCU-class deployment, and it does not report SRAM, Flash, energy, or bare-metal/RTOS evidence.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: YOLOv5
* Comparison with previous works: Yes
* Reproducibility artifacts available: dataset

### Results

* Summary: YOLOv9 achieved 0.894 precision, 0.943 recall, 0.967 mAP50, and 0.720 mAP50-95 for helmet compliance detection. The reported inference time was 21.0 ms per image, with a total processing time of approximately 25.4 ms per image.

### Limitations

* Performance is sensitive to low-light or partially illuminated conditions.
* Occlusions and overlapping objects limit scalability and tracking accuracy in crowded traffic scenarios.
* Power consumption becomes a concern when scaling the system for larger deployments.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: No
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a Raspberry Pi-based edge AI helmet compliance monitoring system using YOLOv9 for real-time helmet detection and vehicle ignition control.

| Paper              | Year | Task             | Model  | Technique                             | Device                  | Dataset                                                                              | Main Metric   | Latency                           | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------------ | ---: | ---------------- | ------ | ------------------------------------- | ----------------------- | ------------------------------------------------------------------------------------ | ------------- | --------------------------------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Tahilramani et al. | 2025 | Object detection | YOLOv9 | Edge deployment and data augmentation | Raspberry Pi 3 Model B+ | Bikes Helmets dataset + Kaggle helmet detection dataset + Raspberry Pi camera images | mAP50 = 0.967 | 21.0 ms inference; ~25.4 ms total | 51.6 MB    | N/A      | N/A   | N/A    | N/A       | N/A      | None          | No            |
