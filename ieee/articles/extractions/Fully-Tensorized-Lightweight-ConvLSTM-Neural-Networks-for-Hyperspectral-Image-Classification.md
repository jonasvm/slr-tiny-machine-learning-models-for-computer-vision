Paper ID: Fully-Tensorized-Lightweight-ConvLSTM-Neural-Networks-for-Hyperspectral-Image-Classification

TinyML classification: Near-TinyML — edge/TinyML-relevant efficient vision model compression is reported, but no explicit MCU-class deployment or constraints are provided.

Basic Info

Authors: Tian-Yu Ma; Heng-Chao Li; Yu-Bang Zheng; Qian Du; Antonio Plaza

Year: 2025

Title: Fully Tensorized Lightweight ConvLSTM Neural Networks for Hyperspectral Image Classification

Source: IEEE Transactions on Neural Networks and Learning Systems, Vol. 36, No. 8, August 2025 

Type: Methodological

Problem & Context

Task: Classification

Objective: Reduce ConvLSTM model complexity for hyperspectral image spatial–spectral classification while maintaining or improving classification performance.

Application domain: Hyperspectral remote sensing image classification

Scenario: Resource-constrained environments are mentioned as motivation, but experiments are performed on a desktop PC with GPU.

TinyML relevance: Partial

TinyML justification: The paper targets lightweight model compression with reduced parameters and FLOPs, but does not report MCU-class, embedded, or on-device deployment.

Model / Method

Model: ETTCL2DNN; ETTCL3DNN

Architecture family: RNN

Techniques: Tensor train decomposition; tensor-sequenced convolution; ETTConv; ETTConv3D; ETTConvLSTM; ETTConvLSTM3D; cascade-then-map weight compression; PCA preprocessing; GAP layer

Framework: PyTorch 1.12.0; Python 3.8.0 

Training type: Not reported

Inference type: Not reported

Hardware

Device: Desktop PC with Intel Core i7-10700K CPU and NVIDIA GeForce RTX 3080 GPU 

Hardware type: CPU / GPU

Processor / microcontroller: Intel Core i7-10700K; NVIDIA GeForce RTX 3080

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Model complexity; parameters; FLOPs; computing resources; storage resources; overfitting risk

Dataset

Name: Indian Pines; University of Pavia; Houston

Type: public

Dataset size: Indian Pines: 145 × 145 × 200, 10,249 samples; University of Pavia: 610 × 340, 103 spectral bands, 42,776 samples; Houston: 349 × 1905, 144 spectral bands, 15,029 samples 

Number of classes: Indian Pines: 16; University of Pavia: 9; Houston: 15

Input resolution: ETTCL2DNN window sizes: 27, 27, and 13 for IN, UP, and HU; ETTCL3DNN window sizes: 27, 21, and 13 for IN, UP, and HU

Data modality: Hyperspectral image cubes

Metrics

Accuracy: ETTCL3DNN OA: 98.96 ± 0.21% on Indian Pines; 97.31 ± 0.36% on University of Pavia; 82.83 ± 0.78% on Houston 

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: ETTCL2DNN: 65.82K / 91.91K / 29.01K on IN / UP / HU; ETTCL3DNN: 225.66K / 365.51K / 207.11K on IN / UP / HU 

MACs / FLOPs: ETTCL2DNN: 272.85M / 325.54M / 71.81M on IN / UP / HU; ETTCL3DNN: 1.84G / 1.29G / 265.02M on IN / UP / HU 

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Tensor train model compression; tensor-sequenced convolution; cascade-then-map joint ConvLSTM weight compression; GAP-based parameter reduction

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Fully tensorized ConvLSTM using ETTConv / ETTConv3D and tensor train format

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: No

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports lightweight model compression and desktop GPU experiments, but no MCU-class deployment, SRAM/Flash usage, bare-metal/RTOS execution, TensorFlow Lite Micro, or embedded inference measurements.

Benchmarking / Standardization

Benchmark used: Indian Pines; University of Pavia; Houston

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Hyperspectral remote sensing benchmark datasets

Comparison with baseline models: Yes; SVM, 3-D CNN, HybridSN, ABi-LSTM, SSCL2DNN, SSTTCL2DNN, 3DSSCRN, SSCL3DNN, and GSC-VIT

Comparison with previous works: Yes

Reproducibility artifacts available: dataset

Results

Summary: ETTCL3DNN achieved the highest reported OA among the proposed models on the three HSI datasets. ETTCL2DNN achieved lower parameter counts than ETTCL3DNN while still improving accuracy over several ConvLSTM baselines. 

Limitations: ETTCL3DNN still has higher FLOPs than 3DSSCRN and GSC-VIT, and the authors state that this could be addressed by weight quantization in future work. 

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes fully tensorized lightweight 2-D and 3-D ConvLSTM neural networks using tensor train-based ETTConv and cascade-then-map compression for low-complexity hyperspectral image classification.

| Paper     | Year | Task           | Model                 | Technique                         | Device                          | Dataset                                    | Main Metric                        | Latency | Model Size                         | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | -------------- | --------------------- | --------------------------------- | ------------------------------- | ------------------------------------------ | ---------------------------------- | ------- | ---------------------------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Ma et al. | 2025 | Classification | ETTCL2DNN / ETTCL3DNN | Tensor train ConvLSTM compression | Intel Core i7-10700K + RTX 3080 | Indian Pines; University of Pavia; Houston | OA 98.96% IN, 97.31% UP, 82.83% HU | N/A     | 225.66K params on IN for ETTCL3DNN | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
