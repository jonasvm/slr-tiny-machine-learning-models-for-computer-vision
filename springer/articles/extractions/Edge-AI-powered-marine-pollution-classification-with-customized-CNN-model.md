Paper ID: Edge-AI-powered-marine-pollution-classification-with-customized-CNN-model

TinyML classification: Near-TinyML — Evaluated on Raspberry Pi edge hardware with TensorFlow Lite, without explicit MCU-class memory, latency, or energy constraints.

Basic Info

Authors: Sanjai Palanisamy; Talal Bonny; Nida Nasir; Mohammad Al Shabi; Ahmed Al Shammaa

Year: 2025

Title: Edge AI-powered marine pollution classification with customized CNN model

Source: Neural Computing and Applications, 37:6449–6463, DOI 10.1007/s00521-024-10959-9 

Type: Experimental

Problem & Context

Task: Classification

Objective: Classify the level of marine pollution in underwater ocean regions into Clean, High Polluted, and Low Polluted classes.

Application domain: Marine pollution / ocean litter monitoring.

Scenario: Edge AI, embedded camera-based monitoring, Raspberry Pi deployment, underwater/coastal monitoring.

TinyML relevance: Partial

TinyML justification: The paper deploys a CNN-based image classifier on Raspberry Pi using TensorFlow Lite, but does not target MCU-class or bare-metal TinyML deployment.

Model / Method

Model: Customized CNN model compared with DenseNet121, Inception-ResNetV2, InceptionV3, VGG-19, VGG-16, ResNet50, and MobileNet.

Architecture family: CNN

Techniques: Custom shallow CNN, data preprocessing, data augmentation, WandB hyperparameter optimization, TensorFlow Lite deployment.

Framework: TensorFlow/Keras, TensorFlow Lite, WandB

Training type: From scratch for the proposed customized CNN; transfer learning for preexisting CNN baselines.

Inference type: On-device

Hardware

Device: Raspberry Pi 4 Model B with Raspberry Pi camera and LCD screen.

Hardware type: SoC / CPU

Processor / microcontroller: Quad-core ARM Cortex-A72 64-bit

Clock frequency: 1.5 GHz

SRAM / RAM: At least 4 GB or 8 GB RAM required to deploy the CNN model on Raspberry Pi; exact RAM usage not reported.

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Storage, computation, RAM requirement, latency, energy efficiency, reduced cloud reliance, image clarity, underwater visibility, and cost.

Dataset

Name: Not reported

Type: Private + synthetic

Dataset size: 2000 images reported; Table 1 lists 2016 images across classes.

Number of classes: 3

Input resolution: 96 × 96 reported for preprocessing; Raspberry Pi screenshots report 256 × 256 image shape.

Data modality: RGB image

Metrics

Accuracy: 99.5%

mAP: Not reported

Precision: 99.8%

Recall: 99.8%

F1-score: 99.8%

Latency: 0.065–0.25 s shown in Raspberry Pi classification screenshots; aggregate latency not reported.

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: 1,621,011

MACs / FLOPs: Not reported

RAM usage: Exact usage not reported; at least 4 GB or 8 GB RAM required for Raspberry Pi deployment.

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Shallow CNN architecture, data augmentation, invalid image removal, WandB hyperparameter tuning, TensorFlow Lite conversion.

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: TensorFlow Lite conversion and shallow CNN design for Raspberry Pi deployment.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is Raspberry Pi 4 with 4 GB or 8 GB RAM rather than an MCU-class, bare-metal, RTOS, or TensorFlow Lite Micro platform.

Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: none

Results

Summary: The proposed customized CNN achieved 99.5% accuracy and 99.8% precision, recall, and F1-score, outperforming the evaluated preexisting CNN models. The model was converted to TensorFlow Lite and demonstrated on Raspberry Pi for on-device marine pollution image classification.

Limitations: The paper reports limitations in collecting valid images, preparing a dataset that fits all situations, underwater image quality issues, turbid water, high-speed boat motion, and lack of real-world testing beyond prototype feasibility.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a customized shallow CNN model deployed with TensorFlow Lite on Raspberry Pi for classifying underwater marine pollution levels from images.

| Palanisamy et al. | 2025 | Classification | Customized CNN | Shallow CNN + data augmentation + TFLite deployment | Raspberry Pi 4 Model B | Custom marine pollution image dataset | Accuracy 99.5% | 0.065–0.25 s | N/A | ≥4 GB or 8 GB RAM required; exact usage N/A | N/A | N/A | TensorFlow Lite | N/A | None | No |
