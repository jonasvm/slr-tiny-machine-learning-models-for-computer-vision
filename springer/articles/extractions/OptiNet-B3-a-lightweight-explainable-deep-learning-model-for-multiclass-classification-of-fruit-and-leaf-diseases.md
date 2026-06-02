## Paper ID: OptiNet-B3-a-lightweight-explainable-deep-learning-model-for-multiclass-classification-of-fruit-and-leaf-diseases

TinyML classification: Near-TinyML — targets lightweight real-time vision on mobile/edge devices, but does not explicitly report microcontroller-class deployment or MCU-level constraints.

### Basic Info

* Authors: Kothakota Naveen; D. Ajitha
* Year: 2025
* Title: OptiNet-B3: a lightweight explainable deep learning model for multiclass classification of fruit and leaf diseases
* Source: Scientific Reports, 15:41890
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Multiclass classification of fruit and leaf diseases in apples, bananas, and oranges.
* Application domain: Precision agriculture / plant disease diagnosis
* Scenario: Mobile and edge deployment
* TinyML relevance: Partial
* TinyML justification: The paper targets lightweight real-time deployment on mobile and edge devices, but does not report MCU-class deployment, TensorFlow Lite Micro, bare-metal execution, or MCU-level memory constraints.

### Model / Method

* Model: OptiNet-B3
* Architecture family: CNN
* Techniques: Mish activation, CBAM attention, Group Normalization, Knowledge Distillation, dropout, data augmentation, Grad-CAM explainability
* Framework: Not reported
* Training type: Fine-tuning / transfer learning
* Inference type: Not reported

### Hardware

* Device: GPU
* Hardware type: GPU
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: 16 GB RAM
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Computational cost, inference time, model size, memory-constrained environments, mobile and edge deployment

### Dataset

* Name: Fruits D-I; Leaves D-II
* Type: Public
* Dataset size: Fruits D-I: 13,602 images; Leaves D-II: 11,199 images
* Number of classes: Fruits D-I: 6 classes; Leaves D-II: 8 classes
* Input resolution: 300 × 300 × 3
* Data modality: RGB image

### Metrics

* Accuracy: 98.12% on Fruits D-I; 99.23% on Leaves D-II
* mAP: Not reported
* Precision: 98.20% on Fruits D-I; 99.30% on Leaves D-II
* Recall: 97.90% on Fruits D-I; 99.00% on Leaves D-II
* F1-score: 98.05% on Fruits D-I; 99.15% on Leaves D-II
* Latency: 8.2 ms inference time
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: 12 M
* MACs / FLOPs: 1.8B FLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Mish activation, CBAM, Group Normalization, Knowledge Distillation, dropout, data augmentation
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Yes
* Compression method: Knowledge distillation
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 8.2 ms inference time, but target device not specified beyond GPU/mobile/edge suitability
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper reports a lightweight CNN suitable for mobile and edge deployment, but provides no explicit MCU-class deployment, SRAM/Flash usage, TensorFlow Lite Micro, CMSIS-NN, or bare-metal/RTOS evidence.

### Benchmarking / Standardization

* Benchmark used: Fruits D-I and Leaves D-II datasets from Kaggle
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: DenseNet121, ResNet50, MobileNetV3, InceptionV3
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset

### Results

* Summary: OptiNet-B3 achieved 98.12% accuracy on the fruit dataset and 99.23% accuracy on the leaf dataset. The model used 12 M parameters, 1.8B FLOPs, and 8.2 ms inference time, outperforming DenseNet121, ResNet50, MobileNetV3, and InceptionV3.

### Limitations

* The datasets were collected under relatively controlled conditions and may not fully represent real-world field variability.
* Rare disease classes are underrepresented.
* Real-world mobile and edge deployments may face additional constraints such as limited processing power, energy consumption, connectivity, and farmer-facing interface requirements.
* The current framework performs image-level classification and does not localize disease regions through segmentation.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes OptiNet-B3, a lightweight explainable CNN-based model integrating Mish activation, CBAM, Group Normalization, and Knowledge Distillation for multiclass fruit and leaf disease classification.

| Paper         | Year | Task           | Model      | Technique                                           | Device | Dataset                 | Main Metric               | Latency | Model Size | SRAM/RAM  | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---: | -------------- | ---------- | --------------------------------------------------- | ------ | ----------------------- | ------------------------- | ------- | ---------- | --------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Naveen et al. | 2025 | Classification | OptiNet-B3 | Knowledge distillation + CBAM + Group Normalization | GPU    | Fruits D-I; Leaves D-II | Accuracy: 98.12% / 99.23% | 8.2 ms  | N/A        | 16 GB RAM | N/A   | N/A    | N/A       | N/A      | N/A           | No            |
