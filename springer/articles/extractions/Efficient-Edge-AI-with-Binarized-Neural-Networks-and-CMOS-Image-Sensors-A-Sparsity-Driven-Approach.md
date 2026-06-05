Paper ID: Efficient-Edge-AI-with-Binarized-Neural-Networks-and-CMOS-Image-Sensors-A-Sparsity-Driven-Approach

The paper proposes BNN-based edge image classification with sensor-level sparsity, ADC power reduction, model-size analysis, and Cortex-M7 latency evaluation.

Basic Info

Authors: Wilfred Kisku; Amandeep Kaur; Deepak Mishra

Year: 2026

Title: Efficient Edge-AI with Binarized Neural Networks and CMOS Image Sensors: A Sparsity-Driven Approach 

Source: Circuits, Systems, and Signal Processing, 45:557–573

Type: Experimental / Methodological

Problem & Context

Task: Classification

Objective: Reduce acquisition power, memory demand, and computation for edge image classification by combining CMOS image sensor-level sparsity, reduced ADC precision, and BNN inference.

Application domain: Edge AI vision / intelligent imaging systems

Scenario: Edge, embedded, low-power imaging, MCU, Raspberry Pi

TinyML relevance: Yes

TinyML justification: The paper targets low-power edge inference, reports BNN model memory, ADC power reduction, and inference latency on Cortex-M7 MCU and Raspberry Pi 5.

Model / Method

Model: BNN versions of AlexNet, VGG, ResNet, SqueezeNet, and modified MobileNet

Architecture family: CNN

Techniques: Binarized neural networks, binary weights/activations, analog-domain Sobel edge extraction, sensor-directed sparsity, ADC precision reduction to 4/3/2/1 bits, INT8 deployment optimization

Framework: Larq; Edge Impulse; TFLite-optimized BNNs

Training type: Not reported

Inference type: On-device

Hardware

Device: Cortex-M7; Raspberry Pi 5; NVIDIA L4 server for training

Hardware type: MCU / CPU / GPU

Processor / microcontroller: Cortex-M7; Raspberry Pi 5 processor not specified; NVIDIA L4 GPU for training

Clock frequency: Cortex-M7 216 MHz; Raspberry Pi 5 2.4 GHz

SRAM / RAM: Not reported for deployment; NVIDIA L4 server has 22.5 GB GPU RAM for training

Flash / ROM / Storage: Not reported

Power consumption: 15.61 mW for 8-bit ADC on 32×32 pixel array; 0.86 mW for 4-bit ADC on 32×32 pixel array

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power, latency, computation, ADC conversion cost, accuracy-efficiency trade-off

Dataset

Name: CIFAR-10; STL-10; CIFAR-100

Type: Public

Dataset size: Not reported

Number of classes: CIFAR-100 has 100 classes; 10-output models used for CIFAR-10/STL-10

Input resolution: CIFAR-10 32×32; STL-10 96×96; CIFAR-100 32×32

Data modality: Grayscale image and edge-extracted image

Metrics

Accuracy: CIFAR-10 best reported Top-1 accuracy 75.14% with ResNet at [4,1]; STL-10 best reported Top-1 accuracy 87.54% with VGG at [4,1]; MobileNet [4,1] Top-1 accuracy 59.92%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Cortex-M7: AlexNet 609 ms, VGG 563 ms, ResNet 590 ms, SqueezeNet 14 ms, MobileNet 359 ms; Raspberry Pi 5: AlexNet 55 ms, VGG 53 ms, ResNet 63 ms, SqueezeNet 2 ms, MobileNet 37 ms

FPS: Not reported

Throughput: Not reported

Model size: 8-bit memory: AlexNet 0.89 MiB, VGG 3.19 MiB, ResNet 1.34 MiB, SqueezeNet 0.093 MiB, MobileNet 4.58 MiB; 32-bit memory: AlexNet 28.29 MiB, VGG 101.36 MiB, ResNet 42.63 MiB, SqueezeNet 2.80 MiB, MobileNet 145.05 MiB

Parameters: Not reported for proposed BNNs

MACs / FLOPs: AlexNet 46.6M MACs; VGG 229M MACs; ResNet 555M MACs; SqueezeNet 8.25M MACs; MobileNet 177M MACs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: ADC power reduced from 15.61 mW to 0.86 mW for a 32×32 pixel array when moving from 8-bit to 4-bit ADC precision

Optimization

Techniques used: Sensor-directed sparsity, analog Sobel filtering, reduced ADC resolution, BNN binarization, grouped convolutions, pointwise convolutions, INT8 deployment optimization

Quantization: INT8 deployment optimization; binary weights/activations; ADC input precision reduction to 4/3/2/1 bits

Pruning: No

Knowledge distillation: No

Compression method: Binarization and reduced input acquisition precision

Hardware-specific optimization: CMOS image sensor and ADC co-design with analog-domain edge extraction

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

Candidate for Strict TinyML: Yes

Reason: The paper reports BNN deployment latency on Cortex-M7 MCU and evaluates memory- and power-oriented optimizations, although SRAM, Flash, and energy per inference are not reported.

Benchmarking / Standardization

Benchmark used: CIFAR-10; STL-10; CIFAR-100

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10; STL-10; CIFAR-100

Comparison with baseline models: Yes

Comparison with previous works: Not reported

Reproducibility artifacts available: Not reported

Results

Summary: The proposed pipeline reduces ADC power from 15.61 mW to 0.86 mW for a 32×32 pixel array while maintaining usable classification accuracy with BNNs. The best reported [4,1] Top-1 accuracy is 75.14% on CIFAR-10 with ResNet and 87.54% on STL-10 with VGG, while SqueezeNet achieves the lowest reported latency of 14 ms on Cortex-M7 and 2 ms on Raspberry Pi 5.

Limitations

Reducing ADC precision from 4-bit to 1-bit causes an approximate 10% accuracy drop. The paper states that BNN binarization can limit representational capacity and that the proposed sensor-level hardware modifications may require custom silicon, creating deployment challenges.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a sensor-driven sparsity pipeline that combines analog-domain edge extraction, reduced ADC precision, and binarized neural networks to reduce power and memory requirements for edge image classification.

| Paper        | Year | Task           | Model                                               | Technique                                             | Device                     | Dataset                     | Main Metric           | Latency                            | Model Size     | SRAM/RAM | Flash | Energy | Framework                                  | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | -------------- | --------------------------------------------------- | ----------------------------------------------------- | -------------------------- | --------------------------- | --------------------- | ---------------------------------- | -------------- | -------- | ----- | ------ | ------------------------------------------ | -------- | ------------- | ------------- |
| Kisku et al. | 2026 | Classification | BNN AlexNet / VGG / ResNet / SqueezeNet / MobileNet | Sensor-level sparsity + BNN + ADC precision reduction | Cortex-M7 / Raspberry Pi 5 | CIFAR-10; STL-10; CIFAR-100 | Top-1 Accuracy 87.54% | 14–609 ms Cortex-M7; 2–63 ms RPi-5 | 0.093–4.58 MiB | N/A      | N/A   | N/A    | Larq / Edge Impulse / TFLite-optimized BNN | INT8     | None          | Yes           |
