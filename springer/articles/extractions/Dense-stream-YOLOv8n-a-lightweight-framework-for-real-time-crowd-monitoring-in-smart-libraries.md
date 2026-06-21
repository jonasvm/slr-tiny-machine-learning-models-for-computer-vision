Paper ID: Dense-stream-YOLOv8n-a-lightweight-framework-for-real-time-crowd-monitoring-in-smart-libraries

Basic Info

Authors: Zini Chen; Xuming Xie; Taorong Qiu; Leiyue Yao

Year: 2025

Title: Dense-stream YOLOv8n: a lightweight framework for real-time crowd monitoring in smart libraries

Source: Scientific Reports, 15:11618 

Type: Experimental

Problem & Context

Task: Object detection

Objective: Real-time pedestrian flow monitoring and counting in high-density, occluded, side-view smart library environments.

Application domain: Smart libraries; crowd monitoring; pedestrian flow analysis.

Scenario: Edge; smart building surveillance; real-time video monitoring.

TinyML relevance: Partial

TinyML justification: The paper targets lightweight real-time edge-device detection using pruning and knowledge distillation, but does not report MCU-class deployment, SRAM/Flash constraints, TFLite Micro, or bare-metal/RTOS execution.

Model / Method

Model: Dense-Stream YOLOv8n

Architecture family: CNN

Techniques: Lightweight DensityNet module; pruning; knowledge distillation; baseline region counting algorithm.

Framework: Ultralytics 8.0.135; OpenCV 4.6.0.66; Python 3.8.19; Numpy 1.24.4.

Training type: Fine-tuning

Inference type: On-device

Hardware

Device: Windows 11 desktop with Intel Core i5-12400F CPU and NVIDIA GeForce RTX 4060 GPU.

Hardware type: CPU / GPU

Processor / microcontroller: 12th Gen Intel(R) Core(TM) i5-12400F @ 2.50 GHz; NVIDIA GeForce RTX 4060.

Clock frequency: 2.50 GHz CPU

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Latency; compute; model complexity; storage requirements; resource-constrained edge devices.

Dataset

Name: Nanchang University Library pedestrian flow dataset; ShanghaiTech Crowd Counting Dataset and AudioVisual used for generalization testing.

Type: Private; public datasets used for generalization testing.

Dataset size: 5350 images; 3745 training, 1070 testing, 535 validation.

Number of classes: 1 target class; person.

Input resolution: 640 × 640

Data modality: Video frames converted to RGB images.

Metrics

Accuracy: 99.41% dense sample counting accuracy; 99.88% sparse sample counting accuracy.

mAP: mAP@0.5 = 0.990; mAP@0.5:0.95 = 0.861.

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 254.0 FPS in model comparison; 34.13 FPS dense sample and 34.89 FPS sparse sample on GPU; 5.14 FPS dense sample and 5.53 FPS sparse sample on CPU.

Throughput: Not reported

Model size: 2.04M parameters

Parameters: 2.04M

MACs / FLOPs: 4.0 GFLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: DensityNet lightweight convolutional enhancement; sparsity-regularized global pruning; knowledge distillation from YOLOv8l to YOLOv8n; baseline region counting.

Quantization: Not reported

Pruning: Yes

Knowledge distillation: Yes

Compression method: Sparsity regularization and global pruning based on weight thresholds.

Hardware-specific optimization: Not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes; 2.04M parameters.

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The work reports lightweight edge-oriented detection but evaluates on Windows desktop CPU/GPU hardware and provides no MCU-class deployment, SRAM/Flash footprint, energy-per-inference, TFLite Micro, or OS-less execution evidence.

Benchmarking / Standardization

Benchmark used: Private smart library pedestrian flow dataset; ShanghaiTech Crowd Counting Dataset; AudioVisual.

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ShanghaiTech Crowd Counting Dataset; AudioVisual.

Comparison with baseline models: Yes; YOLOv8n, YOLOv8l, YOLOv8n-DensityNet, YOLOv8n-DensityNet-compress.

Comparison with previous works: Yes; DDOD, Faster R-CNN, SSD, YOLOv11n, YOLOv8n, and other modified YOLOv8 models.

Reproducibility artifacts available: none

Results

Summary: Dense-Stream YOLOv8n achieved mAP@0.5 of 0.990, mAP@0.5:0.95 of 0.861, 254.0 FPS, 4.0 GFLOPs, and 2.04M parameters. Counting simulations reported 99.41% accuracy in dense samples and 99.88% in sparse samples.

Limitations: Performance degrades under extreme occlusion, complex lighting conditions, dense pedestrian overlap, and non-side-view perspectives.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a lightweight Dense-Stream YOLOv8n framework combining DensityNet, pruning, knowledge distillation, and a baseline region counting algorithm for real-time pedestrian flow monitoring in smart libraries.

| Paper       | Year | Task             | Model                | Technique                                     | Device                                    | Dataset                                       | Main Metric                       | Latency | Model Size   | SRAM/RAM | Flash | Energy | Framework                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ---------------- | -------------------- | --------------------------------------------- | ----------------------------------------- | --------------------------------------------- | --------------------------------- | ------- | ------------ | -------- | ----- | ------ | ------------------------- | -------- | ------------- | ------------- |
| Chen et al. | 2025 | Object Detection | Dense-Stream YOLOv8n | DensityNet + pruning + knowledge distillation | Intel i5-12400F CPU + NVIDIA RTX 4060 GPU | Private smart library pedestrian flow dataset | mAP@0.5 0.990; mAP@0.5:0.95 0.861 | N/A     | 2.04M params | N/A      | N/A   | N/A    | Ultralytics/OpenCV/Python | N/A      | None          | No            |
