## Paper ID: energy-aware-deep-learning-for-real-time-video-analysis-through-pruning-quantization-and-hardware-optimization

TinyML classification: Near-TinyML — evaluated on edge/GPU platforms such as Jetson Nano and NVIDIA A100, with no explicit microcontroller-class deployment.

### Basic Info

* Authors: M. Erdem Isenkul
* Year: 2025
* Title: Energy-aware deep learning for real-time video analysis through pruning, quantization, and hardware optimization
* Source: Journal of Real-Time Image Processing, 22:125
* Type: Experimental

### Problem & Context

* Task: Object detection in real-time video
* Objective: Reduce energy consumption, inference latency, and computational cost in real-time video inference while maintaining detection performance.
* Application domain: Traffic monitoring, aerial surveillance, pedestrian tracking, general object detection, surveillance, autonomous systems, IoT environments
* Scenario: Edge computing, IoT, power-constrained video analytics
* TinyML relevance: Partial
* TinyML justification: The paper targets energy-efficient edge AI video inference using pruning, quantization, and hardware-aware optimization, but does not report MCU-class deployment or microcontroller-level memory constraints.

### Model / Method

* Model: YOLOv8 and MobileNet
* Architecture family: CNN
* Techniques: Pruning, quantization, quantization-aware training, post-training quantization, mixed precision, TensorRT optimization, CUDA graph execution, hardware-aware optimization, frame-rate reduction
* Framework: PyTorch, ONNX, TensorRT, ONNX Runtime
* Training type: Fine-tuning
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson Nano; NVIDIA A100 GPU
* Hardware type: SoC / GPU
* Processor / microcontroller: NVIDIA Jetson Nano; NVIDIA A100 GPU
* Clock frequency: Not reported
* SRAM / RAM: Jetson Nano with 4 GB RAM; NVIDIA A100 with 80 GB RAM
* Flash / ROM / Storage: Not reported
* Power consumption: Relative power and energy reductions reported; absolute power consumption not reported
* Energy per inference: Measured in joules per inference, but absolute values not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Energy, power, latency, memory bandwidth, computational load, model size, inference speed, hardware limitations

### Dataset

* Name: AI City Challenge, VisDrone, Stanford Drone Dataset, Open Images V6
* Type: Public
* Dataset size: Approximately 450,000 annotated frames; 315,000 training frames, 67,500 validation frames, and 67,500 test frames
* Number of classes: Not reported
* Input resolution: AI City Challenge 1920×1080; VisDrone 1920×1080; Stanford Drone Dataset 1280×720; Open Images V6 varies
* Data modality: Video frames and RGB images with bounding-box annotations

### Metrics

* Accuracy: Up to 92% detection accuracy retained after pruning; 85% recognition performance retained with combined optimization
* mAP: mAP@0.5 used; exact final mAP value not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Relative latency reductions reported; absolute latency not reported
* FPS: Source videos ranged from 15 to 60 FPS; low-density scenes reported at 60 FPS and high-density scenes at 30 FPS
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Low-density scenes reported at 5 GFLOPs; high-density scenes reported at 15 GFLOPs
* RAM usage: Low-density scenes reported at 200 MB; high-density scenes reported at 500 MB
* Flash usage: Not reported
* Energy per inference: Relative reductions reported; absolute energy per inference not reported
* Power consumption: Frame-rate reduction from 30 FPS to 15 FPS reduced power by 40%; optimized edge models saved up to 50% power compared with GPUs

### Optimization

* Techniques used: Model pruning, INT8/INT4/FP16 quantization, post-training quantization, quantization-aware training, TensorRT optimization, CUDA graph execution, mixed-precision inference, frame-rate reduction
* Quantization: INT8 / INT4 / FP16 / PTQ / QAT
* Pruning: Yes
* Knowledge distillation: Yes
* Compression method: Pruning and quantization
* Hardware-specific optimization: TensorRT, CUDA graph execution, mixed precision, NVIDIA Nsight profiling
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Relative reductions reported; absolute values not reported
* Latency on target device reported: Relative reductions reported; absolute latency not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper evaluates edge/GPU platforms such as Jetson Nano and NVIDIA A100, but does not report MCU deployment, bare-metal or RTOS execution, TensorFlow Lite Micro, SRAM/Flash constraints, or microcontroller-class inference.

### Benchmarking / Standardization

* Benchmark used: AI City Challenge, VisDrone, Stanford Drone Dataset, Open Images V6
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: PASCAL VOC IoU threshold of 0.5 for mAP evaluation
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset; code available upon request

### Results

* Summary: Pruning reduced energy consumption by up to 35% while retaining 92% detection accuracy. INT8 quantization achieved about 40% energy savings with no more than 3% accuracy loss and about 25% inference acceleration. Combined pruning, quantization, and hardware-aware optimization reduced energy consumption by about 60% while maintaining 85% recognition performance.

### Limitations

* Extreme pruning and INT4 quantization caused noticeable accuracy degradation, especially in dense, high-motion scenes.
* Jetson Nano performance was limited by memory bandwidth in high-resolution traffic datasets.
* The paper does not report MCU-class deployment, absolute SRAM/Flash usage, or absolute energy-per-inference values.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes an energy-aware optimization pipeline for real-time video object detection using pruning, quantization, and hardware-aware inference on edge and GPU platforms.

| Paper          | Year | Task             | Model             | Technique                                          | Device                              | Dataset                                                             | Main Metric                         | Latency                                            | Model Size | SRAM/RAM                             | Flash | Energy                              | Framework               | INT8/QAT       | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | ---------------- | ----------------- | -------------------------------------------------- | ----------------------------------- | ------------------------------------------------------------------- | ----------------------------------- | -------------------------------------------------- | ---------- | ------------------------------------ | ----- | ----------------------------------- | ----------------------- | -------------- | ------------- | ------------- |
| Isenkul et al. | 2025 | Object detection | YOLOv8; MobileNet | Pruning, quantization, hardware-aware optimization | NVIDIA Jetson Nano; NVIDIA A100 GPU | AI City Challenge; VisDrone; Stanford Drone Dataset; Open Images V6 | 92% accuracy retained; mAP@0.5 used | Relative reductions reported; absolute latency N/A | N/A        | 4 GB RAM Jetson Nano; 80 GB RAM A100 | N/A   | Up to 60% combined energy reduction | PyTorch; ONNX; TensorRT | INT8; QAT; PTQ | None          | No            |
