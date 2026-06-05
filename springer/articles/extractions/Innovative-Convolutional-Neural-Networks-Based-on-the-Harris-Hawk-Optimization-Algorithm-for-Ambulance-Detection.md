Paper ID: Innovative-Convolutional-Neural-Networks-Based-on-the-Harris-Hawk-Optimization-Algorithm-for-Ambulance-Detection

TinyML classification: Near-TinyML — Edge-oriented lightweight CNN inference is reported, but no explicit microcontroller, Cortex-M, TFLite Micro, or MCU-level memory/energy constraint is provided.

Basic Info

Authors: Ahmed M. Gab Allah; Amany M. Sarhan; Mahmoud Abdelwahab

Year: 2025

Title: Innovative Convolutional Neural Networks Based on the Harris Hawk Optimization Algorithm for Ambulance Detection

Source: International Journal of Intelligent Transportation Systems Research

Type: Experimental

Problem & Context

Task: Classification

Objective: Classify ambulance and non-ambulance vehicles to support ambulance prioritization in intelligent transportation systems.

Application domain: Intelligent Transportation Systems; ambulance detection; traffic monitoring.

Scenario: Edge/mobile-oriented traffic camera and roadside/in-vehicle emergency traffic management scenario.

TinyML relevance: Partial

TinyML justification: The paper targets lightweight and computationally efficient models for mobile and edge devices, but does not report MCU-class deployment, TinyML framework use, or MCU-level memory, latency, or energy constraints.

Model / Method

Model: MobileNet + Xception ensemble optimized with Harris Hawk Optimization.

Architecture family: Hybrid CNN

Techniques: Transfer learning; ensemble learning; data augmentation; Harris Hawk Optimization for hyperparameter tuning.

Framework: TensorFlow; Keras

Training type: Transfer learning / fine-tuning

Inference type: Not reported

Hardware

Device: Not reported for deployment; experiments were performed on Google Colaboratory servers with NVIDIA Tesla P100-PCIE GPU and 32.0 GB RAM.

Hardware type: GPU for experiments; deployment hardware not reported.

Processor / microcontroller: NVIDIA Tesla P100-PCIE GPU; microcontroller not reported.

Clock frequency: Not reported

SRAM / RAM: 32.0 GB RAM for experimental server; target-device RAM not reported.

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Limited hardware resources, model parameter count, model size, inference time, computational cost, scalability, and real-time applicability.

Dataset

Name: Collected balanced ambulance/non-ambulance dataset

Type: Not reported

Dataset size: 4,749 images; 2,121 ambulance images and 2,628 non-ambulance images.

Number of classes: 2

Input resolution: 224×224 reported in implementation details; 224×244 also stated in preprocessing.

Data modality: Vehicle images

Metrics

Accuracy: 99.86%

mAP: Not reported

Precision: 100%

Recall: 99.7%

F1-score: 99.85%

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported numerically

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Harris Hawk Optimization for hyperparameter tuning; data augmentation; MobileNet + Xception ensemble; transfer learning.

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper is edge/mobile-oriented but does not provide MCU deployment, bare-metal/RTOS execution, TensorFlow Lite Micro, SRAM/Flash usage, energy per inference, or target-device latency evidence.

Benchmarking / Standardization

Benchmark used: Custom collected ambulance/non-ambulance dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes; compared with VGG16, ResNet50, InceptionResNetV2, MobileNet, Xception, DenseNet201, InceptionV3, EfficientNet variants, EfficientFormer, ShuffleNet, and MobileNet+Xception variants.

Comparison with previous works: Yes; compared with related state-of-the-art ambulance detection and vehicle classification methods.

Reproducibility artifacts available: Dataset

Results

Summary: The HHO-optimized MobileNet + Xception model achieved 99.86% accuracy, 100% precision, 99.7% recall, 99.85% F1-score, and 0.9972 MCC. The best hyperparameter configuration used 2048 neurons, AdamW optimizer, 50 epochs, batch size 2, and learning rate 0.0003.

Limitations

Misclassifying an ambulance as a regular vehicle is identified as a critical risk. The paper reports higher computational expense than MobileNet, EfficientFormer, and ShuffleNet, possible scalability issues for larger datasets or real-time contexts, and unverified generalizability to alternative datasets or varied environments.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes an HHO-assisted MobileNet + Xception ensemble deep transfer learning model for binary ambulance image classification in intelligent transportation systems.

| Paper            | Year | Task           | Model                | Technique                       | Device                     | Dataset                                            | Main Metric     | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework        | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---- | -------------- | -------------------- | ------------------------------- | -------------------------- | -------------------------------------------------- | --------------- | ------- | ---------- | -------- | ----- | ------ | ---------------- | -------- | ------------- | ------------- |
| Gab Allah et al. | 2025 | Classification | MobileNet + Xception | HHO hyperparameter optimization | NVIDIA Tesla P100-PCIE GPU | Collected balanced ambulance/non-ambulance dataset | Accuracy 99.86% | N/A     | N/A        | N/A      | N/A   | N/A    | TensorFlow/Keras | N/A      | None          | No            |
