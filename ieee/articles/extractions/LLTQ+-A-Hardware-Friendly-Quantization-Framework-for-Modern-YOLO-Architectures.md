## Paper ID: LLTQ+-A-Hardware-Friendly-Quantization-Framework-for-Modern-YOLO-Architectures

TinyML classification: Near-TinyML — it is relevant to edge computer vision through integer-only quantization of YOLO models, but lacks explicit MCU, Cortex-M, TFLite Micro, SRAM/Flash, or MCU-level energy/latency evidence.

### Basic Info

* Authors: Yugwon Seo; Jaemyung Kim; Jin-Ku Kang; Yongwoo Kim
* Year: 2025
* Title: LLTQ+: A Hardware-Friendly Quantization Framework for Modern YOLO Architectures
* Source: IEEE Access, Volume 13, 2025
* Type: Methodological

### Problem & Context

* Task: Object Detection
* Objective: Improve hardware-friendly quantization for modern YOLO object detection architectures while preserving accuracy under integer-only inference.
* Application domain: Real-time computer vision object detection.
* Scenario: Low-power edge devices and resource-constrained hardware platforms.
* TinyML relevance: Partial
* TinyML justification: The paper targets hardware-friendly INT8 quantization and integer-only inference for edge object detection, but does not report MCU-class deployment, SRAM/Flash usage, energy per inference, or execution without a full operating system.

### Model / Method

* Model: LLTQ+ applied to YOLOv7-tiny, YOLOv7, YOLOv9-t, YOLOv9-s, YOLOv10-n, and YOLOv10-s.
* Architecture family: CNN
* Techniques: Quantization-Aware Training, INT8 quantization, power-of-two scale quantization, batch normalization preservation, RepConv quantization, RepConv fusion, integer-only inference conversion.
* Framework: PyTorch
* Training type: Fine-tuning / QAT from pre-trained floating-point baseline
* Inference type: Not reported

### Hardware

* Device: Not reported
* Hardware type: Not reported
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Memory footprint, computational complexity, low-power edge deployment, hardware constraints, integer-only operations, bit-shift-friendly scale factors.

### Dataset

* Name: PASCAL VOC
* Type: Public
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: Not reported
* Data modality: Image

### Metrics

* Accuracy: Not reported
* mAP: YOLOv10-s INT8 achieved 80.6% mAP@0.5 and 61.8% mAP@0.5:0.95; YOLOv9-t INT8 achieved 73.1% mAP@0.5 and 52.9% mAP@0.5:0.95.
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Hardware-friendly quantization, Quantization-Aware Training, batch normalization preservation, RepConv-aware quantization, power-of-two scaling, integer-only inference conversion.
* Quantization: INT8 / QAT
* Pruning: No
* Knowledge distillation: No
* Compression method: INT8 quantization with power-of-two scale factors.
* Hardware-specific optimization: Scale factors constrained to powers of two to replace multiplication and division with bit-shift operations during inference.
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper is relevant to hardware-friendly edge AI object detection, but it does not provide explicit MCU-class deployment evidence or TinyML-level memory, latency, energy, or framework details.

### Benchmarking / Standardization

* Benchmark used: PASCAL VOC
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: PASCAL VOC
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: LLTQ+ consistently improves or preserves YOLO object detection accuracy under 8-bit quantization compared with LLTQ and other quantization methods. The method reports strong INT8 results on PASCAL VOC, including 80.6% mAP@0.5 and 61.8% mAP@0.5:0.95 for YOLOv10-s.

### Limitations

* YOLOv10 INT8 results include partial floating-point operations in the attention module due to current hardware limitations.
* Evaluation is limited to the PASCAL VOC dataset.
* The SiLU activation function shows larger quantization performance drops than ReLU-based models.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: No
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes LLTQ+, a hardware-friendly Quantization-Aware Training framework for YOLO architectures that preserves batch normalization and RepConv structures during training while enabling INT8 integer-only inference through power-of-two quantization.

| Paper      | Year | Task             | Model                                | Technique                          | Device | Dataset    | Main Metric                                        | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | ---------------- | ------------------------------------ | ---------------------------------- | ------ | ---------- | -------------------------------------------------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Seo et al. | 2025 | Object Detection | YOLOv7-tiny, YOLOv7, YOLOv9, YOLOv10 | Hardware-friendly QAT quantization | N/A    | PASCAL VOC | YOLOv10-s INT8: 80.6% mAP@0.5 / 61.8% mAP@0.5:0.95 | N/A     | N/A        | N/A      | N/A   | N/A    | PyTorch   | INT8/QAT | N/A           | No            |
