Paper ID: Transfer-learning-based-lightweight-MobileNetV2-with-CBAM-attention-for-rice-leaf-nutrient-deficiency-detection

TinyML classification: Strict TinyML — The paper explicitly evaluates deployment on Arduino Nano 33 BLE, an MCU-class Cortex-M4 platform, with reported embedded memory and latency constraints.

Basic Info

Authors: Nitya Ranjan Manihira; Prabira Kumar Sethy

Year: 2025

Title: Transfer learning-based lightweight MobileNetV2 with CBAM attention for rice leaf nutrient deficiency detection

Source: Neural Computing and Applications, 37:27179–27198 

Type: Experimental

Problem & Context

Task: Classification

Objective: Automatically classify rice leaf nutrient deficiencies into healthy, nitrogen-deficient, phosphorus-deficient, and potassium-deficient classes.

Application domain: Precision agriculture; rice nutrient deficiency diagnosis.

Scenario: Mobile, drone, and edge AI deployment suitability claimed.

TinyML relevance: Partial

TinyML justification: The paper targets lightweight CNN inference for resource-constrained devices such as smartphones, drones, and edge AI devices, but does not report MCU-class deployment or TinyML-specific memory/energy constraints.

Model / Method

Model: MobileNetV2 + CBAM + custom classification head

Architecture family: CNN

Techniques: Transfer learning, CBAM attention, data augmentation, dropout, early stopping, learning-rate scheduling.

Framework: MATLAB

Training type: Transfer learning / fine-tuning

Inference type: Not reported

Hardware

Device: Not reported; suitability claimed for smartphones, farm drones, and edge AI devices.

Hardware type: Not reported

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Computational overhead, latency, resource-constrained deployment, mobile/edge suitability.

Dataset

Name: Nutrient Deficiency Symptoms in Rice

Type: Public

Dataset size: 1,679 images

Number of classes: 4

Input resolution: 224 × 224 × 3

Data modality: RGB image

Metrics

Accuracy: Test accuracy 98.81%; validation accuracy 98.02%; five independent runs reported overall accuracy 98.46% ± 0.64%

mAP: Not reported

Precision: 0.98 ± 0.01; class-wise precision: Healthy 1.00, Nitrogen 0.98462, Phosphorus 0.98039, Potassium 0.98246

Recall: 0.98 ± 0.01; class-wise recall: Healthy 1.00, Nitrogen 0.9697, Phosphorus 1.00, Potassium 0.98246

F1-score: 0.98 ± 0.01; class-wise F1-score: Healthy 1.00, Nitrogen 0.9771, Phosphorus 0.9901, Potassium 0.98246

Latency: 31.02 ms average inference time, ±3.11 ms standard deviation

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: 3.4 M

MACs / FLOPs: Approximately 310 MFLOPs per forward pass

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Lightweight MobileNetV2 backbone, CBAM attention, transfer learning, data augmentation, dropout, early stopping, learning-rate scheduling.

Quantization: None

Pruning: No

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

Latency on target device reported: No; latency is reported, but the target deployment device is not specified.

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper does not report MCU-class hardware, SRAM/Flash usage, TensorFlow Lite Micro, bare-metal/RTOS execution, or energy measurements.

Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes; MobileNetV2 without CBAM achieved 92.16% accuracy.

Comparison with previous works: Yes; Table 2 compares the proposed model with prior crop nutrient deficiency models.

Reproducibility artifacts available: Dataset

Results

Summary: The proposed MobileNetV2-CBAM model achieved 98.81% test accuracy and macro-average AUC of 0.9999 for four-class rice leaf nutrient deficiency classification. It reported 31.02 ms average inference time, approximately 310 MFLOPs, and 3.4 M parameters, with suitability claimed for mobile, drone, and edge AI deployment.

Limitations

The dataset is relatively small and collected under controlled conditions, which may limit generalization to real-world environments. The model is trained and validated only for rice crops, and future work suggests pruning, quantization, broader datasets, mobile optimization, and explainability improvements.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a transfer learning-based lightweight MobileNetV2 model enhanced with CBAM attention for rice leaf nutrient deficiency classification.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Manihira et al. | 2025 | Classification | MobileNetV2 + CBAM | Transfer learning + CBAM attention | N/A | Nutrient Deficiency Symptoms in Rice | Accuracy 98.81% | 31.02 ms | N/A | N/A | N/A | N/A | MATLAB | N/A | None | No |
