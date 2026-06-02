## Paper ID: Approximating-vision-transformers-for-edge-variational-inference-and-mixed-precision-for-multi-modal-data

TinyML classification: Near-TinyML — evaluated for edge deployment and Jetson/GPU-class optimization without explicit microcontroller-class evidence.

### Basic Info

* Authors: Dewant Katare; Sam Leroux; Marijn Janssen; Aaron Yi Ding
* Year: 2025
* Title: Approximating vision transformers for edge: variational inference and mixed-precision for multi-modal data
* Source: Computing, 107:71, Springer
* Type: Methodological

### Problem & Context

* Task: Semantic segmentation and object detection
* Objective: Optimize vision transformers for edge deployment by reducing parameters, FLOPs, latency, energy consumption, and memory demand while maintaining accuracy.
* Application domain: Autonomous driving and edge AI perception
* Scenario: Edge, autonomous system, resource-constrained deployment
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained edge AI and evaluates latency, energy, memory, and model-compression metrics, but it does not report MCU-class deployment.

### Model / Method

* Model: VI-ViT / LiTeViT optimized from RangeViT variants
* Architecture family: ViT
* Techniques: Variational inference, mixed-precision quantization, quantization-aware training, approximate inference, TensorRT optimization, layer fusion, DVFS
* Framework: NVIDIA TensorRT
* Training type: Not reported
* Inference type: On-device edge inference

### Hardware

* Device: NVIDIA Jetson Xavier NX for edge deployment; DelftBlue supercomputer with Intel Xeon processors and NVIDIA V100 GPUs for training
* Hardware type: SoC / GPU
* Processor / microcontroller: NVIDIA Jetson Xavier NX; Intel Xeon and NVIDIA V100 GPUs for training
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported; energy per batch reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, compute, latency, energy, power, battery, communication, and edge-resource constraints

### Dataset

* Name: nuScenes; Waymo Open Dataset
* Type: Public
* Dataset size: nuScenes has 1,000 scenes, with 28,130 training and 6,019 validation point cloud scans; Waymo size not reported
* Number of classes: nuScenes has 16 semantic classes; Waymo evaluation reports vehicle and pedestrian classes
* Input resolution: Not reported
* Data modality: Camera images and LiDAR point clouds

### Metrics

* Accuracy: Not reported
* mAP: LiTeViT-1 70.5%, LiTeViT-2 71.2%, LiTeViT-3 78.3% on nuScenes energy evaluation table
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: LiTeViT-1 122.9 ms, LiTeViT-2 145.1 ms, LiTeViT-3 155.2 ms
* FPS: Not reported
* Throughput: Speedup up to 1.95× reported
* Model size: Not reported
* Parameters: LiTeViT-1 10.3M, LiTeViT-2 16.7M, LiTeViT-3 19.1M
* MACs / FLOPs: LiTeViT-1 24.4 GFLOPs, LiTeViT-2 32.1 GFLOPs, LiTeViT-3 33.7 GFLOPs
* RAM usage: Memory usage reported graphically versus precision level, but exact tabular values are not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Variational inference, mixed-precision quantization, quantization-aware training, approximate inference, TensorRT conversion, FP16/INT8 precision optimization, layer fusion, DVFS
* Quantization: Mixed precision / QAT / INT8 / FP16 / FP8
* Pruning: No
* Knowledge distillation: No
* Compression method: Variational inference with mixed-precision quantization
* Hardware-specific optimization: TensorRT optimization, FP16/INT8 calibration, layer fusion, and DVFS for NVIDIA Jetson Xavier NX
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Parameters reported, but byte-level model size not reported
* Energy per inference reported: Not reported; energy per batch reported
* Latency on target device reported: LiTeViT-1 122.9 ms, LiTeViT-2 145.1 ms, LiTeViT-3 155.2 ms
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The deployment target is edge/GPU-class hardware such as NVIDIA Jetson Xavier NX, with no evidence of MCU-class deployment, TensorFlow Lite Micro, CMSIS-NN, SRAM/Flash constraints, or execution without a full operating system.

### Benchmarking / Standardization

* Benchmark used: nuScenes; Waymo Open Dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: nuScenes; Waymo Open Dataset
* Comparison with baseline models: Yes, including TransFusion, RangeViT, BEVFusion, VPFNet, and FusionViT
* Comparison with previous works: Yes
* Reproducibility artifacts available: code

### Results

* Summary: LiTeViT models reduce parameters, GFLOPs, latency, and energy consumption compared with baseline models while maintaining competitive mIoU and mAP. LiTeViT-1 achieves 10.3M parameters, 24.4 GFLOPs, 122.9 ms latency, and 72.9% mIoU, while LiTeViT-3 reaches 78.3% mAP with 379.6 mJ per batch.

### Limitations

* The paper acknowledges environmental variability and the need for diverse training datasets.
* The paper notes that some tests are run on general GPU devices and that custom accelerators remain a future exploration.

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
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a variational-inference and mixed-precision quantization approach for approximating and optimizing multimodal vision transformers for edge AI deployment.

| Paper         | Year | Task                            | Model            | Technique                                            | Device                  | Dataset                      | Main Metric                       | Latency        | Model Size | SRAM/RAM | Flash | Energy               | Framework | INT8/QAT  | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | ------------------------------- | ---------------- | ---------------------------------------------------- | ----------------------- | ---------------------------- | --------------------------------- | -------------- | ---------- | -------- | ----- | -------------------- | --------- | --------- | ------------- | ------------- |
| Katare et al. | 2025 | Segmentation / object detection | LiTeViT / VI-ViT | Variational inference + mixed-precision quantization | NVIDIA Jetson Xavier NX | nuScenes; Waymo Open Dataset | mAP up to 78.3%; mIoU up to 74.6% | 122.9–155.2 ms | N/A        | N/A      | N/A   | 121.0–379.6 mJ/batch | TensorRT  | Mixed/QAT | None          | No            |
