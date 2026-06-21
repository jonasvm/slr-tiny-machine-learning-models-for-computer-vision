Paper ID: Edge-Computing-Enables-Assessment-of-Student-Community-Building-An-Emotion-Recognition-Method-Based-on-TinyML

Basic Info

Authors: Shuo Liu

Year: 2025

Title: Edge Computing Enables Assessment of Student Community Building: An Emotion Recognition Method Based on TinyML

Source: Internet Technology Letters, 2025, 8:e645

Type: Experimental

Problem & Context

Task: Classification; facial expression recognition / emotion recognition

Objective: Develop an efficient TinyML model for robust facial expression recognition from facial landmark sequences under edge-computing scenarios.

Application domain: Online student community assessment and sentiment analysis

Scenario: Edge computing; mobile devices collect facial videos, with expression recognition shown under a server-side edge-computing workflow.

TinyML relevance: Partial

TinyML justification: The paper explicitly describes the method as a TinyML model for edge devices with limited computing resources, but experiments are conducted using PyTorch on an NVIDIA GeForce RTX 4090 and no MCU-class deployment is reported.

Model / Method

Model: Multi-scale semantic fusion ST-GCN

Architecture family: Other

Techniques: Multi-scale semantic fusion; regional-connected graph construction from 68 facial landmarks; spatiotemporal graph convolution

Framework: PyTorch 1.5

Training type: Not reported

Inference type: Offloaded

Hardware

Device: NVIDIA GeForce RTX 4090 for training and testing; edge/mobile devices mentioned for video collection

Hardware type: GPU

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: No

Constraints mentioned: Computing-resource limitations on intelligent edge devices; model complexity; noise, lighting interference, distortion, and background noise in video data

Dataset

Name: CK+; OSCASA

Type: CK+ public; OSCASA self-built/private

Dataset size: CK+: 593 video sequences from 123 subjects, with 327 labeled sequences; OSCASA: 120 video sequences

Number of classes: CK+: Not reported; OSCASA: 2

Input resolution: Not reported

Data modality: Video; facial landmark sequences with 68 2D facial landmarks

Metrics

Accuracy: 98.2% on CK+; 98.8% on OSCASA

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

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

Techniques used: Facial landmark-based graph representation; regional-connected graph construction; multi-scale semantic fusion; ST-GCN backbone for reduced computational burden

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Not reported

Hardware-specific optimization: Not reported

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: Not reported

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: No

Communication required during inference: Yes

Candidate for Strict TinyML: No

Reason: The paper targets edge/TinyML facial expression recognition but reports experiments on a GPU-based PyTorch setup and does not provide MCU-class deployment, TFLM/CMSIS-NN use, memory footprint, latency, or energy evidence.

Benchmarking / Standardization

Benchmark used: CK+; OSCASA

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CK+

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: dataset

Results

Summary: The proposed multi-scale semantic fusion ST-GCN achieved 98.2% accuracy on CK+ and 98.8% accuracy on OSCASA. It outperformed compared traditional machine learning, CNN-based, landmark-based, and ST-GCN baseline models in the reported experiments.

Limitations

No explicit limitations section is reported. The conclusion states that future research will focus on using multimodal data to further improve model performance.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a multi-scale semantic fusion TinyML ST-GCN model that uses regional-connected facial landmark graph sequences for facial expression recognition in an edge-computing student community assessment scenario.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Liu et al. | 2025 | Classification | Multi-scale semantic fusion ST-GCN | Facial landmark graph representation + multi-scale semantic fusion | NVIDIA GeForce RTX 4090 | CK+; OSCASA | Accuracy 98.2% CK+, 98.8% OSCASA | N/A | N/A | N/A | N/A | N/A | PyTorch | N/A | None | No |
