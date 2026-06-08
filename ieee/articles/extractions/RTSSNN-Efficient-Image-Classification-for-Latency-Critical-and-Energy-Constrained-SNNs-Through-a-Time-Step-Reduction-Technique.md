Paper ID: RTSSNN-Efficient-Image-Classification-for-Latency-Critical-and-Energy-Constrained-SNNs-Through-a-Time-Step-Reduction-Technique

TinyML classification: Near-TinyML — Edge AI vision work on Raspberry Pi with quantized SNNs, but no explicit MCU-class deployment.

Basic Info

Authors: Nada AbuHamra; Baker Mohammad; Muhammad Umair Khan; Mahmoud Al-Qutayri

Year: 2025

Title: RTSSNN: Efficient Image Classification for Latency-Critical and Energy-Constrained SNNs Through a Time-Step Reduction Technique

Source: IEEE Internet of Things Journal, Vol. 12, No. 19 

Type: Methodological

Problem & Context

Task: Classification

Objective: Reduce inference time-steps, latency, computational cost, and energy-related operations in rate-coded quantized SNNs while maintaining classification accuracy.

Application domain: Image classification, traffic sign recognition, mobile face recognition, mobile digit classification, autonomous vehicle traffic sign recognition.

Scenario: Edge, IoT, power-constrained, latency-critical embedded/edge inference.

TinyML relevance: Partial

TinyML justification: The paper targets latency-critical and energy-constrained edge devices and evaluates inference on Raspberry Pi 4, but does not report MCU-class deployment, bare-metal execution, TensorFlow Lite Micro, or SRAM/Flash constraints.

Model / Method

Model: RTSSNN

Architecture family: Other

Techniques: Time-step reduction, quantization, compact fully connected layer insertion, skipping spike-encoding preprocessing, quantization-aware training.

Framework: snntorch, brevitas, PyTorch

Training type: Not reported

Inference type: On-device

Hardware

Device: Raspberry Pi 4; AMD Ryzen 7 4700U laptop

Hardware type: CPU / SoC

Processor / microcontroller: Raspberry Pi 4 processor not reported; AMD Ryzen 7 4700U laptop processor

Clock frequency: Not reported

SRAM / RAM: Raspberry Pi 4 RAM not reported; laptop RAM 16 GB

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, compute, energy, resource constraints.

Dataset

Name: MNIST; FashionMNIST; GTSRB; CIFAR-10; N-MNIST

Type: Not reported

Dataset size: Full test datasets used; exact size not reported

Number of classes: MNIST: 10; FashionMNIST: 10; GTSRB: 43; CIFAR-10: 10; N-MNIST: 10

Input resolution: Not reported

Data modality: Grayscale image; RGB image; dynamic neuromorphic image data

Metrics

Accuracy: MNIST 4-bit RTSSNN: 99.29%; MNIST 1-bit RTSSNN: 98.97%; FashionMNIST 4-bit RTSSNN: 91.05%; GTSRB 4-bit RTSSNN: 98.94%; CIFAR-10 deep 4-bit RTSSNN: 80.20%; CIFAR-10 shallow 4-bit RTSSNN: 75.61%; N-MNIST 4-bit RTSSNN: 94.17%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: RP4 average batch inference time: MNIST 0.58 s, FashionMNIST 1.19 s, GTSRB 0.41 s, binary MNIST 0.77 s; RP4 full-test runtime: MNIST 4-bit 364.66 s, MNIST 1-bit 481.52 s, FashionMNIST 746.85 s, GTSRB 201.03 s

FPS: Not reported

Throughput: Batch size 16 on Raspberry Pi 4; batch size 128 on laptop

Model size: Modified model size increases of 15.65%, 14.78%, 11.23%, 14.85%, and 0.23% for quantized MNIST, FashionMNIST, GTSRB, binary MNIST, and CIFAR-10 SNN models, respectively

Parameters: Not reported

MACs / FLOPs: Operations savings of 9x, 4x, 4.9x, and 4x reported for selected models; absolute MACs/FLOPs not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Reduced time-step technique, compact FC layer, 4-bit quantization, 1-bit quantization, quantization-aware training, removal of separate spike-encoding preprocessing.

Quantization: QAT

Pruning: No

Knowledge distillation: No

Compression method: Quantization

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper evaluates on Raspberry Pi 4 and laptop platforms but does not report MCU-class deployment, SRAM/Flash usage, bare-metal or RTOS execution, or TensorFlow Lite Micro/CMSIS-NN use.

Benchmarking / Standardization

Benchmark used: MNIST; FashionMNIST; GTSRB; CIFAR-10; N-MNIST

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10; MNIST; FashionMNIST; GTSRB; N-MNIST

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: RTSSNN reduced time-steps by 3x on MNIST, 2x on FashionMNIST, and 2.2x on GTSRB while maintaining accuracy. On Raspberry Pi 4, runtime reductions were 2.3x, 1.5x, and 1.9x for MNIST, FashionMNIST, and GTSRB, respectively. The method was most effective for shallow SNNs on static image datasets.

Limitations

The method was less effective on dynamic N-MNIST and provided only marginal improvement on deeper CIFAR-10 networks.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a reduced time-step technique for quantized rate-coded SNNs that adds a compact final fully connected layer to exploit LIF neuron periodicity and reduce edge inference latency while maintaining image classification accuracy.

| Paper           | Year | Task           | Model  | Technique                          | Device         | Dataset                                       | Main Metric                                               | Latency                                                    | Model Size                             | SRAM/RAM | Flash | Energy                          | Framework                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---- | -------------- | ------ | ---------------------------------- | -------------- | --------------------------------------------- | --------------------------------------------------------- | ---------------------------------------------------------- | -------------------------------------- | -------- | ----- | ------------------------------- | ------------------------- | -------- | ------------- | ------------- |
| AbuHamra et al. | 2025 | Classification | RTSSNN | Time-step reduction + quantization | Raspberry Pi 4 | MNIST; FashionMNIST; GTSRB; CIFAR-10; N-MNIST | Accuracy: 99.29% MNIST, 91.05% FashionMNIST, 98.94% GTSRB | RP4 batch: 0.58 s MNIST, 1.19 s FashionMNIST, 0.41 s GTSRB | N/A; modified models +0.23% to +15.65% | N/A      | N/A   | 4x–9x operations/energy savings | snntorch/Brevitas/PyTorch | QAT      | None          | No            |
