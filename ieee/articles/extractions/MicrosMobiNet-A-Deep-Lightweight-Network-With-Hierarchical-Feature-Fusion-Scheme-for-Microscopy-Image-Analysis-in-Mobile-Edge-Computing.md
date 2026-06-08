Paper ID: MicrosMobiNet-A-Deep-Lightweight-Network-With-Hierarchical-Feature-Fusion-Scheme-for-Microscopy-Image-Analysis-in-Mobile-Edge-Computing

TinyML classification: Near-TinyML — The deployment is on an Android smartphone/mobile-edge platform, not an explicitly MCU-class or Cortex-M/TFLite Micro target.

Basic Info

Authors: Sumona Biswas; Shovan Barma

Year: 2024

Title: MicrosMobiNet: A Deep Lightweight Network With Hierarchical Feature Fusion Scheme for Microscopy Image Analysis in Mobile-Edge Computing

Source: IEEE Internet of Things Journal, Vol. 11, No. 5, 1 March 2024 

Type: Experimental

Problem & Context

Task: Classification

Objective: Design and validate a lightweight deep network for bright-field microscopy image analysis on mobile-edge computing platforms.

Application domain: Microscopy image analysis; plant microscopy; histopathology cancer cell analysis.

Scenario: Mobile-edge computing; smartphone-based on-device inference.

TinyML relevance: Partial

TinyML justification: The paper targets lightweight on-device microscopy image classification on a smartphone/mobile-edge device, but does not report MCU-class deployment or microcontroller-level memory constraints.

Model / Method

Model: MicrosMobiNet

Architecture family: CNN

Techniques: Depth-wise separable convolution; multiscale feature extraction; hierarchical feature fusion; residual connection; TensorFlow Lite float32 deployment optimization.

Framework: TensorFlow; TensorFlow Lite

Training type: Not reported

Inference type: On-device

Hardware

Device: Redmi Note Pro7 smartphone

Hardware type: Mobile

Processor / microcontroller: Octa-core Qualcomm Snapdragon 675 processor

Clock frequency: Not reported

SRAM / RAM: 4 GB device memory; 13.52 MB maximum memory during inference

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Memory, speed, power, computational complexity, limited computational power, edge-device resource constraints.

Dataset

Name: Foldscope Plant Microscopy Data Set; Traditional Plant Microscopy Data Set; Lung and Colon Cancer Histopathological Image Data Set

Type: Not reported

Dataset size: FPM: 34,657 images; TPM: 15,938 images; LCC: 25,000 images

Number of classes: FPM/TPM multiclass: 3 weight classes; multilabel: 5 labels; LCC: 5 cancer/benign subclasses

Input resolution: 224 × 224 × 3

Data modality: Bright-field RGB microscopy images

Metrics

Accuracy: Up to 98.43% for plant microscopy multilabel classification; 96.52% for LCC multiclass classification; 98.33% on smartphone deployment

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Up to 98.03 for plant microscopy multilabel classification; 91.30 for LCC multiclass classification

Latency: 140.25 ± 0.32 ms on Redmi Note Pro7

FPS: Not reported

Throughput: Not reported

Model size: 7.42 MB on edge device

Parameters: 1.9M

MACs / FLOPs: 42M FLOPs

RAM usage: 13.52 MB maximum memory during inference

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Depth-wise separable convolution; hierarchical feature fusion; multiscale feature extraction; residual connection; TensorFlow Lite float32 optimization.

Quantization: None / FP32

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Lightweight CNN architecture using depth-wise separable convolution and hierarchical feature fusion.

Hardware-specific optimization: TensorFlow Lite optimization for Android smartphone deployment.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 7.42 MB

Energy per inference reported: Not reported

Latency on target device reported: 140.25 ± 0.32 ms

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The target deployment is an Android smartphone with 4 GB memory, not a microcontroller-class platform or bare-metal/RTOS/TensorFlow Lite Micro system.

Benchmarking / Standardization

Benchmark used: TensorFlow benchmark profiling tool for inference time and memory on edge device

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet used for pretrained baseline models

Comparison with baseline models: VGG16; ResNet50; Xception; InceptionV3; EfficientNetB0; MobileNetV1; MobileNetV2; ShuffleNetV1; ShuffleNetV2

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset

Results

Summary: MicrosMobiNet achieved up to 98.43% accuracy and 98.03 F1-score on plant microscopy multilabel classification, and 96.52% accuracy with 91.30 F1-score on LCC multiclass classification. On Redmi Note Pro7, it achieved 98.33% accuracy, 140.25 ± 0.32 ms latency, 13.52 MB memory usage, and 7.42 MB model size.

Limitations

The paper states that kernel specifications, kernel order, and factorized convolution strategies could be further optimized; performance should also be verified on other microscopy datasets, magnification ranges, modalities, segmentation, and detection tasks.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes MicrosMobiNet, a lightweight CNN with depth-wise separable convolution, multiscale feature extraction, hierarchical feature fusion, and residual connections for on-device bright-field microscopy image classification on mobile-edge platforms.

| Paper         | Year | Task           | Model         | Technique                                                      | Device                     | Dataset       | Main Metric                                | Latency          | Model Size | SRAM/RAM     | Flash | Energy | Framework       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | -------------- | ------------- | -------------------------------------------------------------- | -------------------------- | ------------- | ------------------------------------------ | ---------------- | ---------- | ------------ | ----- | ------ | --------------- | -------- | ------------- | ------------- |
| Biswas et al. | 2024 | Classification | MicrosMobiNet | Depth-wise separable convolution + hierarchical feature fusion | Redmi Note Pro7 smartphone | FPM; TPM; LCC | Accuracy 98.43%; on-device accuracy 98.33% | 140.25 ± 0.32 ms | 7.42 MB    | 13.52 MB RAM | N/A   | N/A    | TensorFlow Lite | FP32     | None          | No            |
