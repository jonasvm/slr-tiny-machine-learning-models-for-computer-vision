## Paper ID: Real-time-sugarcane-stem-health-detection-with-YOLOv8-tinier-and-RepNCSP-ELAN

TinyML classification: Near-TinyML — The work targets edge AI platforms such as Jetson Nano and Raspberry Pi 4B, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Pushpendra Kumar, Shraddha Arora, Shaveta Arora
* Year: 2025
* Title: Real time sugarcane stem health detection with YOLOv8 tinier and RepNCSP ELAN
* Source: Scientific Reports, 15:43672, https://doi.org/10.1038/s41598-025-27502-y
* Type: Methodological

### Problem & Context

* Task: Object detection
* Objective: Detect and classify sugarcane stems as Fit or Unfit in real time.
* Application domain: Precision agriculture / sugarcane stem health monitoring
* Scenario: Edge AI / embedded agricultural automation
* TinyML relevance: Partial
* TinyML justification: The paper targets lightweight real-time edge deployment on resource-constrained devices, but does not report MCU-class deployment or MCU-level memory constraints.

### Model / Method

* Model: RepNCSP-ELAN-YOLOv8n / YOLOv8 tinier
* Architecture family: CNN
* Techniques: Lightweight backbone redesign, RepNCSP-ELAN blocks, CSP-style feature partitioning, ELAN-style feature aggregation, re-parameterization
* Framework: Ultralytics YOLO / PyTorch; TorchScript; ONNX; TensorRT; MNN; NCNN
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: Jetson Nano; Raspberry Pi 4B; NVIDIA Tesla T4 GPU for training and some inference benchmarking
* Hardware type: SoC / GPU / CPU
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Model size, inference latency, FPS, parameters, GFLOPs, resource-constrained edge deployment

### Dataset

* Name: Sugarcane stem health detection dataset; brain-tumor benchmark dataset
* Type: Self-curated and publicly available for the sugarcane dataset; public benchmark for the brain-tumor dataset
* Dataset size: 3839 original sugarcane images; 9753 augmented images
* Number of classes: 2
* Input resolution: Original 3072 × 4080 pixels; cropped to 3072 × 3072 pixels; resized to 640 × 640 pixels
* Data modality: Field images; RGB not explicitly reported

### Metrics

* Accuracy: Not reported
* mAP: 90.1% mAP@50; 64.2% mAP@95
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 14.33 ms/image on PyTorch/Tesla T4; 22–25 ms on Jetson Nano; 320–350 ms on Raspberry Pi 4B
* FPS: 69.79 FPS on PyTorch/Tesla T4; 46–48 FPS on Jetson Nano; 3.1–3.6 FPS on Raspberry Pi 4B
* Throughput: Not reported
* Model size: 4.6 MB PyTorch; 8.7 MB ONNX; 13.6 MB TensorRT
* Parameters: 2.2 million
* MACs / FLOPs: 7.2 GFLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight RepNCSP-ELAN backbone, re-parameterization, reduced parameters, reduced GFLOPs, deployment format conversion
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Architecture-level lightweight redesign
* Hardware-specific optimization: TensorRT, ONNX, MNN, and NCNN deployment formats
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 4.6 MB PyTorch; 8.7 MB ONNX; 13.6 MB TensorRT
* Energy per inference reported: Not reported
* Latency on target device reported: 22–25 ms on Jetson Nano; 320–350 ms on Raspberry Pi 4B
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper validates edge deployment on Jetson Nano and Raspberry Pi 4B, but does not report MCU-class hardware, bare-metal or RTOS execution, TensorFlow Lite Micro, SRAM/Flash usage, or MCU-level energy constraints.

### Benchmarking / Standardization

* Benchmark used: Self-curated sugarcane stem health dataset; Ultralytics brain-tumor benchmark dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Brain-tumor detection dataset
* Comparison with baseline models: YOLOv8n, YOLOv9n, YOLOv10n, YOLOv11n, YOLOv12n
* Comparison with previous works: Yes
* Reproducibility artifacts available: Code; dataset

### Results

* Summary: The proposed RepNCSP-ELAN-YOLOv8n achieves 90.1% mAP@50, 64.2% mAP@95, 2.2 million parameters, 7.2 GFLOPs, and 4.6 MB model size. It demonstrates real-time edge performance on Jetson Nano and limited but functional deployment on Raspberry Pi 4B.

### Limitations

* Generalization to other agricultural or medical datasets under different imaging conditions requires further validation.
* Additional ablation experiments directly on edge devices are needed.
* The model may remain susceptible to extreme noise, occlusion, and highly imbalanced datasets.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a lightweight RepNCSP-ELAN-YOLOv8n object detector for real-time sugarcane stem health detection optimized for resource-constrained edge AI deployment.

| Paper        | Year | Task             | Model                | Technique                                                 | Device                       | Dataset                                 | Main Metric                | Latency                                                                | Model Size     | SRAM/RAM | Flash | Energy | Framework                                       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ---------------- | -------------------- | --------------------------------------------------------- | ---------------------------- | --------------------------------------- | -------------------------- | ---------------------------------------------------------------------- | -------------- | -------- | ----- | ------ | ----------------------------------------------- | -------- | ------------- | ------------- |
| Kumar et al. | 2025 | Object detection | RepNCSP-ELAN-YOLOv8n | Lightweight RepNCSP-ELAN backbone and re-parameterization | Jetson Nano; Raspberry Pi 4B | Sugarcane stem health detection dataset | mAP@50 90.1%; mAP@95 64.2% | 14.33 ms on T4; 22–25 ms on Jetson Nano; 320–350 ms on Raspberry Pi 4B | 4.6 MB PyTorch | N/A      | N/A   | N/A    | PyTorch; TorchScript; ONNX; TensorRT; MNN; NCNN | N/A      | None          | No            |
