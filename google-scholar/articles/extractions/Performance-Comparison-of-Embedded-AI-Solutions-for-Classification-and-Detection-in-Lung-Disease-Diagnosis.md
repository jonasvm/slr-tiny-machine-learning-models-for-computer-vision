## Paper ID: Performance-Comparison-of-Embedded-AI-Solutions-for-Classification-and-Detection-in-Lung-Disease-Diagnosis

TinyML classification: Near-TinyML — Evaluated on Raspberry Pi 4 and edge-compatible deployment, without explicit MCU-class or TensorFlow Lite Micro deployment evidence.

### Basic Info
- Authors: Md Sabbir Ahmed; Stefano Giordano; Davide Adami
- Year: 2025
- Title: Performance Comparison of Embedded AI Solutions for Classification and Detection in Lung Disease Diagnosis
- Source: Applied Sciences, 15(17), 9345
- Type: Experimental / Benchmark

### Problem & Context
- Task: Classification and object detection
- Objective: Assess the performance and deployability of deep learning classification and detection models for lung disease diagnosis in embedded settings.
- Application domain: Medical imaging; chest X-ray lung disease diagnosis
- Scenario: Edge, embedded, mobile clinical environments, surgical environments
- TinyML relevance: Partial
- TinyML justification: The paper targets embedded edge deployment on Raspberry Pi 4 with quantized models, but does not target MCU-class deployment or ultra-low-memory TinyML platforms.

### Model / Method
- Model: ResNet101, DenseNet201, MobileNetV3-Large, EfficientNetV2-B0, InceptionResNetV2, Xception, YOLOv8n
- Architecture family: CNN
- Techniques: Transfer learning, data augmentation, post-training quantization, TensorFlow Lite conversion, ONNX export, lightweight detection
- Framework: TensorFlow, Keras, TensorFlow Lite, PyTorch, Ultralytics, ONNX
- Training type: Fine-tuning from ImageNet pretrained weights for classification; COCO-pretrained fine-tuning for YOLOv8n
- Inference type: On-device for classification; detection not deployed and proposed for accelerator/offloaded execution

### Hardware
- Device: Raspberry Pi 4 Model B
- Hardware type: SoC / CPU
- Processor / microcontroller: ARM Cortex-A72
- Clock frequency: Not reported
- SRAM / RAM: 4 GB RAM
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Yes for classification; No for detection in this work
- Constraints mentioned: Latency, compute, memory footprint, resource-constrained embedded hardware, detection computational demands

### Dataset
- Name: Five-class chest X-ray classification dataset based on Vantaggiato et al.; VinBigData Chest X-ray Abnormalities Detection dataset subset
- Type: Public
- Dataset size: 2020 classification images; 9875 augmented classification images; 3296 detection images
- Number of classes: 5 classification classes; 14 detection classes
- Input resolution: 224 × 224 or 299 × 299 for classification training; 2566 × 2566 PNG for Raspberry Pi inference input; 640 × 640 for YOLOv8n detection
- Data modality: Chest X-ray images

### Metrics
- Accuracy: MobileNetV3-Large reached 62.0% validation accuracy on the base dataset and 63.4% on the augmented dataset
- mAP: YOLOv8n achieved 27.6% mAP@0.5 and 14.7% mAP@0.5:0.95
- Precision: Detection precision reached 1.00 at confidence threshold 0.872
- Recall: Not reported
- F1-score: Detection F1-score peaked at 0.31 at confidence threshold 0.091
- Latency: MobileNetV3-Large 429.6 ms; EfficientNetV2-B0 623.0 ms; DenseNet201 1388.2 ms; Xception 1644.4 ms; ResNet101 1908.2 ms; InceptionResNetV2 2300.7 ms
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Data augmentation, early stopping, learning-rate reduction, TensorFlow Lite conversion, post-training quantization, ONNX export
- Quantization: INT8 / FP16 post-training quantization
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: TensorFlow Lite post-training quantization
- Hardware-specific optimization: TensorFlow Lite inference on Raspberry Pi 4; ONNX export for edge accelerators
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Yes, Raspberry Pi 4 latency from 429.6 ms to 2300.7 ms
- Runs without full operating system: No
- Fully on-device inference: Yes for classification; No for detection in this work
- Communication required during inference: No for classification; detection is proposed for offloading or accelerator-based execution
- Candidate for Strict TinyML: No
- Reason: The deployment target is Raspberry Pi 4 with Ubuntu and 4 GB RAM, without MCU-class hardware, TensorFlow Lite Micro, bare-metal/RTOS execution, SRAM/Flash constraints, or energy-per-inference reporting.

### Benchmarking / Standardization
- Benchmark used: Raspberry Pi 4 edge inference benchmark; VinBigData detection evaluation
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: COCO format; ImageNet pretrained weights; COCO pretrained weights
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Dataset

### Results
- Summary: MobileNetV3-Large provided the best edge speed–accuracy trade-off among classification models, with 429.6 ms total latency on Raspberry Pi 4. YOLOv8n achieved 27.6% mAP@0.5 for thoracic abnormality detection but was not deployed on Raspberry Pi. The study supports a hybrid embedded AI pipeline combining fast on-device classification with spatially interpretable detection.

### Limitations
- Classification and detection used separate datasets, preventing joint optimization.
- The full hybrid classification-detection pipeline was not implemented end-to-end.
- YOLOv8n was not deployed on Raspberry Pi due to computational demands.
- Dataset size and class imbalance limited detection performance.
- No direct clinical expert validation of interpretability or usability was performed.
- Demographic annotations were incomplete, limiting fairness and bias analysis.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: No
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a modular embedded AI framework for lung disease diagnosis that combines quantized Raspberry Pi-based chest X-ray classification with a lightweight YOLOv8n detection component for spatial interpretability.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Ahmed et al. | 2025 | Classification + detection | MobileNetV3-Large; EfficientNetV2-B0; ResNet101; DenseNet201; Xception; InceptionResNetV2; YOLOv8n | PTQ, TFLite conversion, ONNX export | Raspberry Pi 4 Model B | Five-class CXR dataset; VinBigData CXR | 63.4% validation accuracy; 27.6% mAP@0.5 | 429.6 ms best classification latency | N/A | 4 GB RAM | N/A | N/A | TensorFlow Lite, PyTorch, Ultralytics, ONNX | INT8 / PTQ | None | No |
