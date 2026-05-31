## Paper ID: RA-MOSAIC-Resource-Adaptive-Edge-AI-Optimization-over-Spatially-Multiplexed-Video-Streams

TinyML classification: Near-TinyML — Evaluated on NVIDIA Jetson edge GPU platforms with YOLOv5 models, without explicit microcontroller-class memory or deployment evidence.

### Basic Info

* Authors: Ila Gokarn, Yigong Hu, Tarek Abdelzaher, Archan Misra
* Year: 2025
* Title: RA-MOSAIC: Resource Adaptive Edge AI Optimization over Spatially Multiplexed Video Streams
* Source: ACM Transactions on Multimedia Computing, Communications, and Applications, Vol. 21, No. 9, Article 247
* Type: Experimental / Methodological

### Problem & Context

* Task: Object detection; automatic license plate recognition
* Objective: Improve the throughput-accuracy tradeoff for real-time AI-based vision perception over multiple concurrent video streams on edge devices.
* Application domain: Drone-based pedestrian detection; automatic license plate recognition; edge video analytics
* Scenario: Edge AI, embedded edge devices, multi-camera video streams, bandwidth-constrained wireless environments
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained edge AI vision on Jetson Nano and Jetson TX2 devices, but does not target microcontroller-class deployment or MCU-level memory constraints.

### Model / Method

* Model: RA-MOSAIC using BACT at the camera node and WACC at the edge node; YOLOv5n for periodic camera-side full-frame detection; TensorRT-optimized YOLOv5s for edge-side object detection
* Architecture family: CNN
* Techniques: Bandwidth-adaptive camera transmission, mixed-resolution frame generation, criticality-aware RoI processing, workload-adaptive canvas construction, spatial multiplexing, RoI tiling, Bloom2Squeeze bin-packing, TensorRT optimization
* Framework: YOLOv5; TensorRT
* Training type: Fine-tuning from a model pre-trained on MS COCO
* Inference type: Hybrid camera-node preprocessing and edge-node inference

### Hardware

* Device: NVIDIA Jetson Nano as camera node; NVIDIA Jetson TX2 as edge node
* Hardware type: SoC / GPU / CPU edge embedded platform
* Processor / microcontroller: Jetson Nano with Quad-core ARM A57 CPU; Jetson TX2 with 256 CUDA-core Pascal GPU, ARMv8 multi-processor architecture, quad-core ARM Cortex-A57 MPCore, and dual-core NVIDIA Denver 2 CPU
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: No
* Constraints mentioned: Computation latency, GPU resource sharing, edge resource contention, wireless bandwidth, throughput, pixel budget, communication overhead, object workload variability

### Dataset

* Name: Okutama-Action; UFPR-ALPR
* Type: Public
* Dataset size: Okutama-Action: 54,664 training frames and 14,210 testing frames from 43 drone sequences; UFPR-ALPR: 3,600 training frames and 1,800 testing frames from 90 sequences
* Number of classes: Not reported
* Input resolution: Okutama-Action: 3840 × 2160 at 30 FPS; UFPR-ALPR: 1920 × 1080 at 30 FPS; edge canvas upper bound: 640 × 640
* Data modality: Video frames

### Metrics

* Accuracy: Reported through object detection accuracy gains and OCR character error rate reductions
* mAP: mAP@0.5 used; RA-MOSAIC reports 14.3% accuracy gain over MOSAIC for pedestrian detection with 6 cameras under bandwidth restriction, 15% gain with 3 cameras under bandwidth restriction, and 26.9% gain over batched inference with 1 camera under bandwidth restriction
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Jetson Nano YOLOv5n full-frame detection averages 48 ms; Jetson TX2 YOLOv5s 640 × 640 canvas inference averages 52 ms; WACC processing overhead is approximately 49 ms for pedestrian detection with 6 cameras and approximately 27 ms for LPR with 3 cameras
* FPS: BACT camera stream frame rate is 29.95 FPS; RA-MOSAIC achieves up to 20 FPS per camera for 6 cameras and 22 FPS per camera for 3 cameras under lower workload
* Throughput: Up to 120 cumulative FPS across 6 cameras; 66 cumulative FPS across 3 cameras in the low-workload bandwidth-constrained pedestrian detection scenario
* Model size: Not reported
* Parameters: YOLOv5n has 1.9M parameters; YOLOv5s has 7.2M parameters
* MACs / FLOPs: YOLOv5s has 16.5 GFLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Criticality-aware RoI selection, mixed-resolution frame transfer, bandwidth-adaptive downsampling, workload-adaptive canvas sizing, spatial RoI multiplexing, Bloom2Squeeze bin-packing, TensorRT optimization
* Quantization: Not reported
* Pruning: No
* Knowledge distillation: No
* Compression method: Mixed-resolution image transmission and RoI-based spatial multiplexing, not neural network compression
* Hardware-specific optimization: TensorRT-optimized YOLOv5 models on NVIDIA Jetson edge devices
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Jetson Nano YOLOv5n full-frame detection averages 48 ms; Jetson TX2 YOLOv5s 640 × 640 canvas inference averages 52 ms
* Runs without full operating system: Not reported
* Fully on-device inference: No
* Communication required during inference: Yes, camera nodes transmit mixed-resolution frames and RoI metadata to the edge node over WiFi
* Candidate for Strict TinyML: No
* Reason: The paper evaluates edge AI vision on NVIDIA Jetson Nano and Jetson TX2 platforms without MCU-class deployment, TensorFlow Lite Micro, CMSIS-NN, SRAM/Flash constraints, or bare-metal/RTOS execution evidence.

### Benchmarking / Standardization

* Benchmark used: Okutama-Action; UFPR-ALPR
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: MS COCO used for pre-training
* Comparison with baseline models: Naive FCFS, Uniform-M, Bandwidth Adaptive FCFS, Bandwidth Adaptive Uniform-M, MOSAIC, batched RoI inference
* Comparison with previous works: Compared with MOSAIC and prior state-of-the-art batched inference over extracted RoI tiles
* Reproducibility artifacts available: Not reported

### Results

* Summary: RA-MOSAIC improves object detection accuracy and throughput over MOSAIC and multiple edge video processing baselines under bandwidth-constrained and dynamic workload conditions. It reports up to 14.3% accuracy gain and 11.11% throughput gain over MOSAIC for 6 concurrent pedestrian-detection camera streams, reaching up to 20 FPS per camera and 120 cumulative FPS.

### Limitations

* Object/RoI arrival patterns and spatial overlaps between camera fields of view are not modeled.
* Dynamic pixel budget estimation is outside the scope of the work.
* Accuracy-aware canvas construction, heterogeneous compute mapping, and distributed workload sharing are left for future work.

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
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes RA-MOSAIC, a resource-adaptive edge AI system that combines bandwidth-adaptive mixed-resolution camera transmission with workload-adaptive canvas-based RoI multiplexing to improve real-time multi-camera vision inference on Jetson edge devices.

| Paper         | Year | Task                    | Model             | Technique                                                                                 | Device                                 | Dataset                   | Main Metric  | Latency                                             | Model Size                       | SRAM/RAM | Flash | Energy | Framework        | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---: | ----------------------- | ----------------- | ----------------------------------------------------------------------------------------- | -------------------------------------- | ------------------------- | ------------ | --------------------------------------------------- | -------------------------------- | -------- | ----- | ------ | ---------------- | -------- | ------------- | ------------- |
| Gokarn et al. | 2025 | Object detection / ALPR | YOLOv5n + YOLOv5s | Bandwidth-adaptive mixed-resolution RoI transmission and workload-adaptive canvas packing | NVIDIA Jetson Nano + NVIDIA Jetson TX2 | Okutama-Action; UFPR-ALPR | mAP@0.5; CER | 48 ms camera detection; 52 ms edge canvas inference | 1.9M parameters; 7.2M parameters | N/A      | N/A   | N/A    | YOLOv5; TensorRT | N/A      | None          | No            |
