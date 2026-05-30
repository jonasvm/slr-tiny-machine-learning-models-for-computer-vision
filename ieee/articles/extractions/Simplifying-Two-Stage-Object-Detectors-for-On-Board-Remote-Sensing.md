## Paper ID: Simplifying-Two-Stage-Object-Detectors-for-On-Board-Remote-Sensing

TinyML classification: Near-TinyML — Edge/on-board vision relevance is explicit, but the reported hardware is GPU/Orin NX rather than microcontroller-class TinyML.

### Basic Info

* Authors: Jaemin Kang; Hoeseok Yang; Hyungshin Kim
* Year: 2025
* Title: Simplifying Two-Stage Object Detectors for On-Board Remote Sensing
* Source: IEEE Access, Volume 13, 2025
* Type: Methodological

### Problem & Context

* Task: Object detection
* Objective: Reduce the computational overhead of two-stage remote sensing object detectors while preserving detection accuracy for on-board inference.
* Application domain: Remote sensing imagery
* Scenario: On-board AI for UAVs or satellites; embedded/edge inference
* TinyML relevance: Partial
* TinyML justification: The paper targets on-device/on-board object detection under computational and power constraints, but evaluation is on embedded GPU/edge hardware rather than MCU-class TinyML platforms.

### Model / Method

* Model: Simplified two-stage detectors applied to Oriented R-CNN, LSKNet-T, and LSKNet-S
* Architecture family: CNN
* Techniques: Feature pyramid simplification, single-feature regression, progressive feature aggregation, group dilation, Hybrid ATSS, high-pass filtering, reduced RoI count
* Framework: MMRotate; TensorRT FP16 for NVIDIA Orin NX FPS measurement
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: NVIDIA Orin NX; NVIDIA RTX 4090; NVIDIA RTX 3090
* Hardware type: SoC / GPU
* Processor / microcontroller: NVIDIA Orin NX
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Computational resources, power budget, inference delay, throughput, GFLOPs, RoI count

### Dataset

* Name: DOTA-v2.0
* Type: Not reported
* Dataset size: 11,268 photos and 1,793,658 instances
* Number of classes: 18
* Input resolution: Images cropped to 1024 × 1024 with stride of 200 pixels; original images range from 800 to 4,000 pixels in width and height
* Data modality: Remote sensing images

### Metrics

* Accuracy: Not reported
* mAP: Oriented R-CNN baseline 60.3%; Ours-O-RCNN 61.4%; LSKNet-T baseline 60.7%; Ours-LSKNet-T 62.6%; LSKNet-S baseline 64.0%; Ours-LSKNet-S 66.0%
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Oriented R-CNN baseline 50.8 FPS on RTX 4090 and 7.9 FPS on Orin NX; Ours-O-RCNN with 3,000 RoIs achieved 67.0 FPS on RTX 4090 and 11.6 FPS on Orin NX
* Throughput: 31.8% throughput improvement while maintaining average accuracy; 1.48× speedup on NVIDIA Orin NX with 3,000 RoIs
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Ours-O-RCNN 130.5 GFLOPs vs. 211.4 GFLOPs baseline; Ours-LSKNet-T 55.7 GFLOPs vs. 132.8 GFLOPs baseline; Ours-LSKNet-S 96.0 GFLOPs vs. 173.7 GFLOPs baseline
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Single-feature detector simplification, FPN removal, progressive feature aggregation, group dilation, Hybrid ATSS, high-pass filter, RoI reduction
* Quantization: FP16
* Pruning: No
* Knowledge distillation: No
* Compression method: Model simplification by replacing feature pyramid regression with single-feature regression
* Hardware-specific optimization: TensorRT FP16 evaluation on NVIDIA Orin NX
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: FPS reported on NVIDIA Orin NX; latency not directly reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper evaluates on NVIDIA Orin NX and GPU platforms and does not report MCU-class deployment, SRAM/Flash constraints, TensorFlow Lite Micro, CMSIS-NN, or bare-metal/RTOS execution.

### Benchmarking / Standardization

* Benchmark used: DOTA-v2.0
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: DOTA-v2.0
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed method reduced GFLOPs by up to 58.1% while improving mAP by 1.6 percentage points for LSKNet-T. On Oriented R-CNN, reducing RoIs to 3,000 achieved 67.0 FPS on RTX 4090 and 11.6 FPS on NVIDIA Orin NX while maintaining comparable mAP.

### Limitations

* Accuracy for large objects decreases compared with the baseline.
* The high-pass filter provides limited accuracy improvement and can increase noise or false positives.
* The method was evaluated only on two-stage detectors, and further research is required for one-stage detectors.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a model simplification method for two-stage remote sensing object detectors that replaces feature pyramid regression with single-feature regression and uses Hybrid ATSS and high-pass filtering to reduce computation while preserving accuracy.

| Paper       | Year | Task             | Model                   | Technique                                                          | Device         | Dataset   | Main Metric | Latency                  | Model Size | SRAM/RAM | Flash | Energy | Framework                | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------- | ----------------------- | ------------------------------------------------------------------ | -------------- | --------- | ----------- | ------------------------ | ---------- | -------- | ----- | ------ | ------------------------ | -------- | ------------- | ------------- |
| Kang et al. | 2025 | Object detection | Oriented R-CNN / LSKNet | Single-feature FPN simplification + Hybrid ATSS + high-pass filter | NVIDIA Orin NX | DOTA-v2.0 | mAP 62.6%   | N/A; 11.6 FPS on Orin NX | N/A        | N/A      | N/A   | N/A    | MMRotate / TensorRT FP16 | FP16     | None          | No            |
