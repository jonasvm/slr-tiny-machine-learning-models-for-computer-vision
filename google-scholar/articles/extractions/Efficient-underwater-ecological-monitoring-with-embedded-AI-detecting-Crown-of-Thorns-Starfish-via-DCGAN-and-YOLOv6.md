## Paper ID: Efficient-underwater-ecological-monitoring-with-embedded-AI-detecting-Crown-of-Thorns-Starfish-via-DCGAN-and-YOLOv6

TinyML classification: Near-TinyML — evaluated for embedded/edge platforms such as Jetson Nano, Coral TPU, and NVIDIA Xavier, without explicit MCU-class constraints.

### Basic Info

* Authors: Mohan Jyothimurugan, S. Pavithra, J. Deepika Roselind
* Year: 2025
* Title: Efficient underwater ecological monitoring with embedded AI: detecting Crown-of-Thorns Starfish via DCGAN and YOLOv6
* Source: Frontiers in Marine Science, 12:1658205
* Type: Experimental

### Problem & Context

* Task: Object detection
* Objective: Detect Crown-of-Thorns Starfish in underwater imagery using a real-time embedded AI framework.
* Application domain: Underwater ecological monitoring and coral reef conservation
* Scenario: Embedded edge deployment for underwater drones, reef monitoring stations, and real-time drone feeds
* TinyML relevance: Partial
* TinyML justification: The paper targets embedded/edge deployment and low-latency inference, but does not report MCU-class deployment or microcontroller-level memory constraints.

### Model / Method

* Model: YOLOv6, Faster R-CNN, DCGAN
* Architecture family: Hybrid CNN
* Techniques: Synthetic data augmentation with DCGAN, INT8 post-training quantization, pruning, TensorRT acceleration, ONNX export
* Framework: PyTorch, TensorFlow, ONNX Runtime, TensorRT
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson Nano; also mentions Coral TPU and NVIDIA Xavier as embedded deployment targets
* Hardware type: SoC / GPU / NPU
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Latency, memory footprint, computational cost, power efficiency, real-time inference, embedded deployment

### Dataset

* Name: CSIRO Crown-of-Thorns Starfish Detection Dataset
* Type: Public / synthetic
* Dataset size: 2,437 annotated real images and 13,000 synthetic images
* Number of classes: Not reported
* Input resolution: 512×512 pixels
* Data modality: RGB underwater images

### Metrics

* Accuracy: Not reported
* mAP: YOLOv6 mAP@50 = 0.938; Faster R-CNN mAP@50 = 0.945; Faster R-CNN mAP@50:95 = 0.872
* Precision: YOLOv6 = 0.927; Faster R-CNN = 0.946
* Recall: YOLOv6 = 0.903; Faster R-CNN = 0.917
* F1-score: YOLOv6 = 0.915; Faster R-CNN = 0.931
* Latency: YOLOv6 = ~28 ms/frame on NVIDIA Jetson Nano; Faster R-CNN = ~120 ms/frame
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: YOLOv6 = approximately 37 million parameters; Faster R-CNN = approximately 140 million parameters
* MACs / FLOPs: YOLOv6 = around 95 GFLOPs; Faster R-CNN = over 206 GFLOPs
* RAM usage: YOLOv6 memory footprint = ~250 MB; Faster R-CNN memory demand = approximately 700 MB
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: DCGAN-based synthetic augmentation, INT8 post-training quantization, pruning, ONNX Runtime acceleration, TensorRT acceleration
* Quantization: INT8
* Pruning: Yes
* Knowledge distillation: Not reported
* Compression method: Pruning and post-training quantization
* Hardware-specific optimization: TensorRT and ONNX Runtime acceleration for embedded edge devices
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: ~28 ms/frame on NVIDIA Jetson Nano
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The deployment evidence is based on edge platforms such as Jetson Nano, Coral TPU, and NVIDIA Xavier, with no MCU-class deployment or SRAM/Flash constraints reported.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: MS COCO and PASCAL VOC appear in benchmark comparisons for baseline models
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: YOLOv6 achieved 0.927 precision, 0.903 recall, 0.915 F1-score, and 0.938 mAP@50 with ~28 ms/frame inference on Jetson Nano. Faster R-CNN achieved higher accuracy but required ~120 ms/frame, making it more suitable for offline or lab-based validation.

### Limitations

* Performance degrades under heavy turbidity, poor illumination, occlusion, and coral structures visually similar to starfish.
* The paper notes possible overfitting to DCGAN-generated synthetic images and the need for external testing on new reef imagery.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a hybrid underwater object detection framework combining DCGAN-based synthetic data generation, enhanced Faster R-CNN, and YOLOv6 for real-time embedded detection of Crown-of-Thorns Starfish.

| Paper                | Year | Task             | Model                         | Technique                                                    | Device             | Dataset                                                                   | Main Metric           | Latency      | Model Size | SRAM/RAM                 | Flash | Energy | Framework                                   | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------------- | ---: | ---------------- | ----------------------------- | ------------------------------------------------------------ | ------------------ | ------------------------------------------------------------------------- | --------------------- | ------------ | ---------- | ------------------------ | ----- | ------ | ------------------------------------------- | -------- | ------------- | ------------- |
| Jyothimurugan et al. | 2025 | Object detection | YOLOv6 / Faster R-CNN / DCGAN | DCGAN augmentation, pruning, INT8 PTQ, TensorRT acceleration | NVIDIA Jetson Nano | CSIRO Crown-of-Thorns Starfish Detection Dataset + synthetic DCGAN images | YOLOv6 mAP@50 = 0.938 | ~28 ms/frame | N/A        | ~250 MB memory footprint | N/A   | N/A    | PyTorch, TensorFlow, ONNX Runtime, TensorRT | INT8 PTQ | None          | No            |
