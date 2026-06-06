Paper ID: LDMRes-Net-A-Lightweight-Neural-Network-for-Efficient-Medical-Image-Segmentation-on-IoT-and-Edge-Devices

TinyML classification: Near-TinyML — The work targets IoT and edge platforms but does not explicitly report MCU-class deployment or Cortex-M/TFLite Micro-level constraints.

Basic Info

Authors: Shahzaib Iqbal; Tariq M. Khan; Syed S. Naqvi; Asim Naveed; Muhammad Usman; Haroon Ahmed Khan; Imran Razzak

Year: 2024

Title: LDMRes-Net: A Lightweight Neural Network for Efficient Medical Image Segmentation on IoT and Edge Devices 

Source: IEEE Journal of Biomedical and Health Informatics, Vol. 28, No. 7, July 2024

Type: Experimental

Problem & Context

Task: Segmentation

Objective: Efficient retinal vessel and hard exudate segmentation for medical image analysis on IoT and edge platforms.

Application domain: Medical imaging; ophthalmology; retinal image analysis.

Scenario: IoT and edge devices.

TinyML relevance: Partial

TinyML justification: The paper targets lightweight medical image segmentation for IoT and edge platforms and reports low parameters and model size, but does not report MCU-class deployment or TinyML-specific deployment constraints.

Model / Method

Model: LDMRes-Net

Architecture family: CNN

Techniques: Dual multiscale residual blocks; lightweight encoder-decoder design; optimal filter selection; sparsity-promoting composite constraints to eliminate unnecessary filters.

Framework: Not reported

Training type: Not reported

Inference type: Not reported

Hardware

Device: Not reported

Hardware type: Not reported

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Resource constraints, computational efficiency, model size, training time, inference time, memory requirements.

Dataset

Name: DRIVE; CHASE_DB; STARE; HRF; ARIA; IOSTAR; ORVS; IDRiD

Type: Public

Dataset size: DRIVE 40 images; CHASE_DB 20 images; STARE 28 images; HRF 45 images; ARIA 142 images; IOSTAR 30 images; ORVS 49 images; IDRiD 81 images

Number of classes: Binary segmentation foreground/background

Input resolution: 640 × 640 for retinal vessel datasets; IDRiD uses 640 × 640 patches from 3200 × 4480 resized images

Data modality: RGB retinal fundus images

Metrics

Accuracy: DRIVE 97.02%; STARE 97.64%; CHASE_DB 97.55%; HRF 97.11%; ARIA 95.81%; IOSTAR 96.57%; ORVS 97.55%; IDRiD 98.35%

mAP: Not reported

Precision: Not reported

Recall: Reported as sensitivity: DRIVE 83.58%; STARE 84.07%; CHASE_DB 85.95%; HRF 80.78%; ARIA 74.18%; IOSTAR 81.52%; ORVS 78.97%; IDRiD 96.33%

F1-score: DRIVE 83.09%; STARE 84.24%; CHASE_DB 81.94%; HRF 80.20%; ARIA 71.49%; IOSTAR 82.81%; ORVS 77.98%; IDRiD 95.05%

Latency: 5.5 ms

FPS: Not reported

Throughput: Not reported

Model size: 0.58 MB

Parameters: 0.072 M

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Lightweight CNN architecture; dual multiscale residual block; optimal number of filters; composite constraints for sparsity and redundancy reduction.

Quantization: Not reported

Pruning: Yes, filter elimination by sparsity-promoting composite constraints is reported.

Knowledge distillation: Not reported

Compression method: Joint sparsity promotion and redundancy reduction through composite constraints.

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 0.58 MB

Energy per inference reported: Not reported

Latency on target device reported: 5.5 ms, but target device not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports a lightweight model for IoT and edge platforms, but does not provide MCU-class hardware deployment, SRAM/Flash usage, TFLite Micro/CMSIS-NN use, OS-less execution, or energy measurements.

Benchmarking / Standardization

Benchmark used: DRIVE; STARE; CHASE_DB; HRF; ARIA; IOSTAR; ORVS; IDRiD

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: LDMRes-Net achieves strong retinal vessel and hard exudate segmentation performance across multiple public datasets while using 0.072 M parameters, 0.58 MB model size, and 5.5 ms inference time. The paper reports higher or competitive accuracy and F1-score compared with several lightweight and segmentation baselines.

Limitations

Not reported

Practical Reporting Checklist Evidence

Reports hardware clearly: No

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

This paper proposes LDMRes-Net, a lightweight dual multiscale residual CNN for efficient retinal vessel and hard exudate segmentation on IoT and edge platforms.

| Paper        | Year | Task         | Model      | Technique                                                                           | Device | Dataset                                                | Main Metric                                  | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | ------------ | ---------- | ----------------------------------------------------------------------------------- | ------ | ------------------------------------------------------ | -------------------------------------------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Iqbal et al. | 2024 | Segmentation | LDMRes-Net | Dual multiscale residual lightweight CNN with sparsity-promoting filter elimination | N/A    | DRIVE; STARE; CHASE_DB; HRF; ARIA; IOSTAR; ORVS; IDRiD | Accuracy 97.02% on DRIVE; F1 95.05% on IDRiD | 5.5 ms  | 0.58 MB    | N/A      | N/A   | N/A    | N/A       | N/A      | None          | No            |
