Paper ID: Category-Correlation-and-Adaptive-Knowledge-Distillation-for-Compact-Cloud-Detection-in-Remote-Sensing-Images

TinyML classification: Near-TinyML — Edge/embedded satellite relevance is explicit, but no MCU-class deployment or MCU-level constraints are reported.

Basic Info

Authors: Zhujun Yang; Zhiyuan Yan; Xian Sun; Wenhui Diao; Yiran Yang; Xinming Li

Year: 2022

Title: Category Correlation and Adaptive Knowledge Distillation for Compact Cloud Detection in Remote Sensing Images

Source: IEEE Transactions on Geoscience and Remote Sensing 

Type: Methodological

Problem & Context

Task: Segmentation

Objective: Improve compact cloud detection in remote sensing images using category correlation and adaptive knowledge distillation.

Application domain: Remote sensing cloud detection

Scenario: Edge / embedded satellite vision

TinyML relevance: Partial

TinyML justification: The paper targets compact models for resource-constrained intelligent satellites, but does not report MCU-class deployment, SRAM/Flash constraints, or bare-metal/RTOS execution.

Model / Method

Model: CAKD framework with ResNet50 teacher and compact student networks including MobileNetV2 and ResNet18-h.

Architecture family: CNN

Techniques: Knowledge distillation, category correlation distillation, pixel-adaptive distillation, lightweight CNN backbone.

Framework: PyTorch 1.3

Training type: Transfer learning for teacher and MobileNetV2 using ImageNet pretraining; ResNet18-h trained from scratch.

Inference type: Not reported

Hardware

Device: NVIDIA Tesla-P100 GPU for DCNN inference timing; RTX-2080Ti GPU for experiments; Intel Core i7-7700 CPU for traditional baselines.

Hardware type: GPU / CPU

Processor / microcontroller: Intel Core i7-7700 CPU reported for traditional baselines; microcontroller not reported.

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Storage memory, computing resources, parameters, FLOPs, inference time.

Dataset

Name: Landsat 8 Cloud Cover Assessment Validation Data; Landsat 7 Cloud Cover Assessment Validation Data; AIR-CD; HRC-WHU; GF-1 WFV Cloud and Cloud Shadow Cover Validation Data.

Type: Public / not fully reported

Dataset size: Landsat 8 uses 64 selected images; Landsat 7 uses 44 selected images; AIR-CD has 34 images; HRC-WHU has 150 images; GF-1 has 108 scenes.

Number of classes: Landsat 8 and Landsat 7 use 3 classes; AIR-CD and HRC-WHU use 2 classes; GF-1 uses 3 classes.

Input resolution: Landsat 8 and Landsat 7 original images around 7000 × 6000 and sliced to 512 × 512; AIR-CD original size 7300 × 6908 and sliced to 512 × 512; HRC-WHU 1280 × 720; GF-1 around 17000 × 16000.

Data modality: Remote sensing images; RGB, visible bands, NIR, SWIR, TIR, and multispectral imagery depending on dataset.

Metrics

Accuracy: OA 92.26% on Landsat 8, 93.68% on Landsat 7, 96.95% on AIR-CD, 94.50% on HRC-WHU, and 97.15% on GF-1 for MobileNetV2 with CAKD.

mAP: Not reported

Precision: PA 90.62% on Landsat 8, 87.94% on Landsat 7, 95.51% on AIR-CD, 94.39% on HRC-WHU, and 93.03% on GF-1 for MobileNetV2 with CAKD.

Recall: UA 90.75% on Landsat 8, 86.74% on Landsat 7, 95.39% on AIR-CD, 94.30% on HRC-WHU, and 89.84% on GF-1 for MobileNetV2 with CAKD.

F1-score: 90.68% on Landsat 8, 87.32% on Landsat 7, 95.45% on AIR-CD, 94.34% on HRC-WHU, and 91.33% on GF-1 for MobileNetV2 with CAKD.

Latency: MobileNetV2 with CAKD reports 18.7 s on a Landsat 8 full image, 88.4 s on a GF-1 full image, and 0.081 s per 512 × 512 subimage.

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: 2.31M for MobileNetV2 with CAKD; 3.29M for ResNet18-h with CAKD.

MACs / FLOPs: 4.63G FLOPs for MobileNetV2 with CAKD; 14.64G FLOPs for ResNet18-h with CAKD.

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Category correlation and adaptive knowledge distillation using CRC, CCD, and PAD modules.

Quantization: None

Pruning: No

Knowledge distillation: Yes

Compression method: Teacher-student knowledge distillation into compact CNN student models.

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 2.31M parameters and 4.63G FLOPs for MobileNetV2; storage size not reported.

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper targets compact satellite edge vision but does not report MCU-class deployment, SRAM/Flash usage, bare-metal execution, TensorFlow Lite Micro, or energy measurements.

Benchmarking / Standardization

Benchmark used: Landsat 8, Landsat 7, AIR-CD, HRC-WHU, and GF-1 cloud detection datasets.

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet used for pretraining.

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: MobileNetV2 with CAKD achieves 83.32% mIoU on Landsat 8, 79.06% mIoU on Landsat 7, 91.42% mIoU on AIR-CD, 89.31% mIoU on HRC-WHU, and 85.17% mIoU on GF-1. The method improves compact student models while keeping MobileNetV2 at 2.31M parameters and 4.63G FLOPs.

Limitations

The paper reports that high-resolution remote sensing scenes remain difficult because ground objects and illumination can cause teacher model errors, which can affect knowledge distillation.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a category correlation and adaptive knowledge distillation framework for compact cloud detection in remote sensing images.

| Paper       | Year | Task         | Model                 | Technique              | Device                | Dataset                                     | Main Metric              | Latency                        | Model Size | SRAM/RAM | Flash | Energy | Framework   | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ------------ | --------------------- | ---------------------- | --------------------- | ------------------------------------------- | ------------------------ | ------------------------------ | ---------- | -------- | ----- | ------ | ----------- | -------- | ------------- | ------------- |
| Yang et al. | 2022 | Segmentation | MobileNetV2 with CAKD | Knowledge distillation | NVIDIA Tesla-P100 GPU | Landsat 8; Landsat 7; AIR-CD; HRC-WHU; GF-1 | 83.32% mIoU on Landsat 8 | 0.081 s per 512 × 512 subimage | N/A        | N/A      | N/A   | N/A    | PyTorch 1.3 | N/A      | None          | No            |
