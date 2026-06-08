Paper ID: Energy-Efficient-Federated-Learning-for-Edge-Real-Time-Vision-via-Joint-Data-Computation-and-Communication-Design

TinyML classification: Near-TinyML — targets wireless edge CV devices and energy-efficient on-device FL, but does not explicitly report MCU/Cortex-M/TFLite Micro deployment or MCU-level memory constraints.

Basic Info

Authors: Xiangwang Hou; Jingjing Wang; Fangming Guan; Jun Du; Chunxiao Jiang; Yong Ren

Year: 2025

Title: Energy-Efficient Federated Learning for Edge Real-Time Vision via Joint Data, Computation, and Communication Design

Source: IEEE Journal on Selected Areas in Communications, Vol. 43, No. 12, December 2025 

Type: Methodological

Problem & Context

Task: Classification

Objective: Minimize overall energy consumption for federated learning in real-time edge computer vision by jointly optimizing data, computation, and communication strategies.

Application domain: Real-time computer vision over wireless edge devices, including applications such as autonomous driving, robotics, and VR/AR.

Scenario: Wireless edge federated learning with camera-equipped devices, a base station, and an edge server.

TinyML relevance: Partial

TinyML justification: The paper targets energy-constrained edge CV and on-device federated training, but does not report MCU-class deployment, TensorFlow Lite Micro, SRAM/Flash limits, or bare-metal/RTOS execution.

Model / Method

Model: FedDPQ framework; ResNet-18 used for image classification experiments; pre-trained diffusion model used for data augmentation.

Architecture family: CNN

Techniques: Federated learning, diffusion-based data augmentation, model pruning, stochastic gradient quantization, transmission power control, Bayesian optimization, block coordinate descent.

Framework: Not reported

Training type: Not reported

Inference type: Not reported

Hardware

Device: Camera-equipped wireless edge devices coordinated by a base station and edge server; 100 simulated devices in experiments.

Hardware type: CPU / Other

Processor / microcontroller: Not reported

Clock frequency: Device computational resource fu sampled from U[20, 50] MHz.

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Transmission power range 0.01 W to 0.1 W; measured device power consumption not reported.

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Energy, computation, communication, limited local data, non-i.i.d. data, transmission outage, unreliable wireless links, convergence.

Dataset

Name: CIFAR-10

Type: public

Dataset size: 60,000 images; 50,000 training and 10,000 testing.

Number of classes: 10

Input resolution: 32 × 32 pixels

Data modality: RGB image

Metrics

Accuracy: Test accuracy reported in figures; exact numeric values not reported.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Training delay reported in figures; inference latency not reported.

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Transmission power range 0.01 W to 0.1 W; measured power consumption not reported.

Optimization

Techniques used: Diffusion-based data augmentation, model pruning, stochastic gradient quantization, adaptive transmission power control, Bayesian optimization.

Quantization: Stochastic gradient quantization with quantization level δ from 6 to 16 bits.

Pruning: Yes

Knowledge distillation: Not reported

Compression method: Model pruning and gradient quantization.

Hardware-specific optimization: Transmission power control and CPU/communication energy modeling; no hardware backend-specific optimization reported.

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

Reason: The paper addresses resource-constrained wireless edge FL, but provides no MCU-class deployment, memory footprint, embedded inference framework, or bare-metal/RTOS evidence.

Benchmarking / Standardization

Benchmark used: CIFAR-10

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10

Comparison with baseline models: Traditional FL, FedDPQ-noDA, FedDPQ-noPQ, FedDPQ-noPC.

Comparison with previous works: Related work is discussed; experiments compare mainly against FL baselines and ablation variants.

Reproducibility artifacts available: Not reported

Results

Summary: FedDPQ achieves better energy efficiency, convergence speed, and test accuracy than the evaluated FL baselines under different data heterogeneity and device participation settings. Ablation results indicate that diffusion augmentation, pruning, quantization, and power control each contribute to energy, delay, and accuracy improvements.

Limitations

No explicit limitations section is provided. Future work includes integrating split learning for extreme computational constraints and low-overhead fine-tuning strategies such as LoRA.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes FedDPQ, an ultra energy-efficient federated learning framework for real-time edge computer vision that jointly optimizes diffusion-based data augmentation, model pruning, gradient quantization, and transmission power control.

| Paper      | Year | Task           | Model              | Technique                                                             | Device                          | Dataset  | Main Metric                        | Latency                                       | Model Size | SRAM/RAM | Flash | Energy                                          | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | -------------- | ------------------ | --------------------------------------------------------------------- | ------------------------------- | -------- | ---------------------------------- | --------------------------------------------- | ---------- | -------- | ----- | ----------------------------------------------- | --------- | -------- | ------------- | ------------- |
| Hou et al. | 2025 | Classification | ResNet-18 / FedDPQ | Diffusion augmentation, pruning, gradient quantization, power control | Simulated wireless edge devices | CIFAR-10 | Test accuracy / energy consumption | Training delay plotted; inference latency N/A | N/A        | N/A      | N/A   | Total training energy plotted; exact values N/A | N/A       | N/A      | None          | No            |
