Paper ID: Identification-of-irradiated-food-through-hyperspectral-imaging-assisted-by-deep-learning-techniques

Basic Info

Authors: H. M. Nada; Osama A. Omer; Hamada A. H. Esmaiel; A. A. Arafa; M. Ashour

Year: 2025

Title: Identification of irradiated food through hyperspectral imaging assisted by deep learning techniques

Source: Multimedia Tools and Applications, 84:50471–50495

Type: Experimental

Problem & Context

Task: Classification

Objective: Distinguish irradiated food samples from non-irradiated samples using hyperspectral imaging and deep learning.

Application domain: Food safety and quality monitoring

Scenario: Laboratory hyperspectral imaging system for potential industrial food inspection

TinyML relevance: No

TinyML justification: The paper does not report MCU-class, low-power, embedded, edge, or on-device deployment evidence.

Model / Method

Model: PPI/FIPPI-based endmember extraction with LSTM, GRU, and BiLSTM classifiers

Architecture family: RNN

Techniques: Endmember extraction; dimensionality reduction using PCA, MNF, or no reduction

Framework: MATLAB

Training type: Not reported

Inference type: Not reported

Hardware

Device: Hyperspectral laboratory system with hyperspectral camera, controlled illumination array, and processing unit

Hardware type: Other

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Computational intensity, storage, preprocessing, feature extraction, latency, real-time performance, scalability, speed, robustness

Dataset

Name: Not reported

Type: Private

Dataset size: 90 apples captured before and after gamma irradiation

Number of classes: 2

Input resolution: 467×15 double precision

Data modality: Hyperspectral image

Metrics

Accuracy: 94.74% using LSTM-PPI-PCA and BiLSTM-PPI-PCA

mAP: Not reported

Precision: 0.9615 for LSTM-PPI-PCA; 0.9608 for BiLSTM-PPI-PCA

Recall: 0.9245 for LSTM-PPI-PCA and BiLSTM-PPI-PCA

F1-score: 0.9423 for LSTM-PPI-PCA and BiLSTM-PPI-PCA

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: PPI; FIPPI; PCA; MNF; no-reduction feature extraction variants

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Not reported

Hardware-specific optimization: No

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

Reason: The paper reports no MCU-class deployment, memory footprint, flash usage, energy measurement, or latency on constrained hardware.

Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, LSTM, GRU, and BiLSTM were compared across PPI_PCA, PPI_None, PPI_MNF, and FIPPI extraction methods.

Comparison with previous works: No quantitative comparison reported

Reproducibility artifacts available: Dataset available on reasonable request

Results

Summary: The best reported accuracy was 94.74% using LSTM-PPI-PCA and BiLSTM-PPI-PCA for irradiated versus non-irradiated food classification. LSTM-PPI-PCA achieved precision 0.9615, recall 0.9245, and F1-score 0.9423.

Limitations

The paper reports computational intensity of hyperspectral acquisition and processing, storage and preprocessing burden, latency from LSTM/BiLSTM models, need for real-time imaging, and future validation on additional foods such as potatoes and meat.

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

This paper proposes a non-destructive hyperspectral imaging and deep learning framework for classifying gamma-irradiated and non-irradiated food samples.

| Paper       | Year | Task           | Model               | Technique                                                         | Device                                                    | Dataset                   | Main Metric     | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | -------------- | ------------------- | ----------------------------------------------------------------- | --------------------------------------------------------- | ------------------------- | --------------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Nada et al. | 2025 | Classification | LSTM / GRU / BiLSTM | PPI/FIPPI endmember extraction + PCA/MNF dimensionality reduction | Hyperspectral laboratory system / desktop processing unit | Private apple HSI samples | Accuracy 94.74% | N/A     | N/A        | N/A      | N/A   | N/A    | MATLAB    | N/A      | None          | No            |
