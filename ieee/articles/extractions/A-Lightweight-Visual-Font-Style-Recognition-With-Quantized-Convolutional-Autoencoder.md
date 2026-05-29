## Paper ID: A-Lightweight-Visual-Font-Style-Recognition-With-Quantized-Convolutional-Autoencoder

TinyML classification: Near-TinyML — The paper reports a very small quantized model for edge deployment, but does not provide explicit MCU-class deployment, SRAM/Flash usage, latency, energy, or bare-metal/RTOS evidence.

### Basic Info

* Authors: Moshiur Rahman Tonmoy; Abdul Fattah Rakib; Rashik Rahman; Md. Akhtaruzzaman Adnan; M. F. Mridha; Jie Huang; Jungpil Shin
* Year: 2024
* Title: A Lightweight Visual Font Style Recognition With Quantized Convolutional Autoencoder
* Source: IEEE Open Journal of the Computer Society
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Recognize Bangla font styles from images using a lightweight quantized convolutional autoencoder.
* Application domain: Visual font recognition, document and pattern analysis, image processing, Bangla typography.
* Scenario: Edge devices, mobile apps, tablets, browser extensions, web apps, desktop apps.
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets lightweight deployment on resource-constrained edge devices and reports a compressed model size of around 58 KB.

### Model / Method

* Model: Quantized Convolutional Autoencoder
* Architecture family: CNN
* Techniques: INT8 quantization, quantization-aware training, lightweight convolutional autoencoder, compression
* Framework: TensorFlow
* Training type: From scratch followed by quantization-aware fine-tuning
* Inference type: Not reported

### Hardware

* Device: Not reported
* Hardware type: Other
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Memory, computational complexity, resource-constrained edge devices, low-end computational edge devices

### Dataset

* Name: Bangla VFR dataset
* Type: Synthetic
* Dataset size: 60,000 training/validation images; separate test set of 2,000 images
* Number of classes: 10
* Input resolution: 400 × 400 original generated images; model input reported as 224 × 224 × 1
* Data modality: Grayscale image

### Metrics

* Accuracy: 99.95% without quantization; 99.85% after quantization
* mAP: Not reported
* Precision: 99.95% macro / weighted on test set
* Recall: 99.95% macro / weighted on test set
* F1-score: 99.95% macro / 99.95% weighted on test set
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Around 58 KB after compression
* Parameters: 36,091
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Quantization-aware training, INT8 quantization, model compression
* Quantization: INT8 / QAT
* Pruning: No
* Knowledge distillation: No
* Compression method: INT8 quantization of trained CAE with quantization-aware training and fine-tuning
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Around 58 KB
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Unclear
* Reason: The paper reports a very small quantized model and explicitly targets resource-constrained edge devices, but it does not report MCU deployment, SRAM/Flash usage, latency, energy, or execution without a full operating system.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: ImageNet used only as pretrained weights for baseline CNN models
* Comparison with baseline models: Yes, compared with DenseNet121, InceptionV3, MobileNet, MobileNetV2, ResNet50, VGG16, VGG19, and Xception
* Comparison with previous works: Yes, compared with previous Bangla visual font recognition studies
* Reproducibility artifacts available: Dataset

### Results

* Summary: The proposed CAE achieved 99.95% test accuracy, while the quantized Q-CAE achieved 99.85% test accuracy with a compressed model size of around 58 KB. The model outperformed reported previous Bangla visual font recognition works and several ImageNet-pretrained CNN baselines.

### Limitations

* The model is focused on recognizing Bangla font styles from images containing plain font-style content.
* It may not handle complex design, textual artwork, typography modifications, mixed-font designs, or 3D shapes/designs.
* No real deployment hardware, latency, RAM, Flash, power, or energy measurements are reported.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a lightweight quantized convolutional autoencoder for Bangla visual font style recognition, supported by a newly created synthetic Bangla VFR dataset and comparative evaluation against prior works and CNN baselines.

| Paper         | Year | Task           | Model | Technique                   | Device | Dataset                      | Main Metric                        | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework  | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---: | -------------- | ----- | --------------------------- | ------ | ---------------------------- | ---------------------------------- | ------- | ---------- | -------- | ----- | ------ | ---------- | -------- | ------------- | ------------- |
| Tonmoy et al. | 2024 | Classification | Q-CAE | Quantization-aware training | N/A    | Bangla VFR synthetic dataset | Accuracy: 99.85% Q-CAE; 99.95% CAE | N/A     | ~58 KB     | N/A      | N/A   | N/A    | TensorFlow | INT8/QAT | None          | Unclear       |
