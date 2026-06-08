Paper ID: Variable-Resolution-Pixel-Quantization-for-Low-Power-Machine-Vision-Application-on-Edge

TinyML classification: Near-TinyML — relevant low-power edge vision hardware, but no explicit MCU-class deployment evidence.

Basic Info

Authors: Senorita Deb; Sai Sanjeet; Prabir Kumar Biswas; Bibhu Datta Sahoo

Year: 2025

Title: Variable Resolution Pixel Quantization for Low Power Machine Vision Application on Edge

Source: IEEE Journal on Emerging and Selected Topics in Circuits and Systems, Vol. 15, No. 1, March 2025 

Type: Experimental

Problem & Context

Task: Classification

Objective: Reduce average bits-per-pixel needed to represent images while maintaining CNN classification accuracy and reducing ADC power at the edge sensor node.

Application domain: Machine vision

Scenario: Edge sensor / edge computing

TinyML relevance: Partial

TinyML justification: The paper targets low-power edge machine vision and ADC-level power reduction, but does not report MCU-class deployment, SRAM/Flash constraints, or TensorFlow Lite Micro execution.

Model / Method

Model: ResNet50; VGG-style 7-convolutional-layer CNN

Architecture family: CNN

Techniques: Variable-resolution pixel quantization; analog-domain 1D Hadamard Transform; low-bit image compression; ADC channel elimination; fine-tuning

Framework: TensorFlow/Keras ResNet50; MATLAB modeling; Cadence circuit simulation

Training type: Pre-trained without fine-tuning for ImageNet ResNet50 evaluation; fine-tuning for CIFAR-10 VGG-style CNN

Inference type: Hybrid

Hardware

Device: Proposed 1.5-bit Hadamard Transform embedded pipelined ADC; HT PCB prototype

Hardware type: Other

Processor / microcontroller: Not reported

Clock frequency: 50 MHz ADC sampling frequency used in power estimates

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: 15.82 µW for 8-bit pipelined ADC per channel; 15.24 µW for 8-bit SAR ADC per channel; ≈90% theoretical power reduction reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Power consumption, ADC resolution, bits-per-pixel, I/O bandwidth, storage energy, sensor-node hardware complexity

Dataset

Name: CIFAR-10; ImageNet

Type: Public

Dataset size: 50,000 CIFAR-10 images analyzed; 5,000 ImageNet images evaluated; 100 CIFAR-10 test images used for PCB measurement

Number of classes: CIFAR-10: 10; ImageNet: 1000

Input resolution: CIFAR-10: 32 × 32; ImageNet resized to 1024 × 1024, 512 × 512, and 256 × 256; ResNet input resized to 224 × 224

Data modality: RGB image

Metrics

Accuracy: CIFAR-10 VGG-style CNN: 91.01% original 8-bit baseline; 90.65% at 3.5-BPP after fine-tuning; 90.15% at 3-BPP after fine-tuning; measured PCB 3-BPP accuracy reached 90% on 100 CIFAR-10 images 

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: Per-layer VGG-style network parameters reported; total parameters not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Normalized pipelined ADC power per channel: 0.34725 for 6-BPP configuration (8,5,6,5); theoretical ≈90% power reduction reported

Optimization

Techniques used: Analog-domain 1D Hadamard Transform; variable-resolution quantization; reduced BPP; ADC channel elimination; CNN fine-tuning with transformed images

Quantization: Mixed precision

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Hadamard Transform-based image compression with variable bits-per-channel

Hardware-specific optimization: Proposed 1.5-bit Hadamard Transform embedded pipelined ADC and PCB-based analog HT implementation

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

Communication required during inference: Digitized data is transmitted from sensor to processor; cloud communication not reported

Candidate for Strict TinyML: No

Reason: The paper targets low-power edge sensor hardware and CNN image classification but does not report MCU-class deployment, SRAM/Flash usage, bare-metal/RTOS execution, or TFLM/CMSIS-NN inference.

Benchmarking / Standardization

Benchmark used: CIFAR-10; ImageNet

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10; ImageNet

Comparison with baseline models: Yes, baseline bit truncation / baseline quantization is compared with the proposed variable-resolution quantization method

Comparison with previous works: Yes, Table IV compares BPP, network, and accuracy against prior low-bit image/CNN works

Reproducibility artifacts available: not reported

Results

Summary: The proposed method maintains CNN accuracy with low-BPP images, reaching approximately 90% CIFAR-10 accuracy at 3-BPP. The paper reports theoretical ≈90% ADC power reduction and ≈50% memory/I/O energy savings, with PCB measurements showing limited hardware-induced impact at low BPP. 

Limitations

The proposed 1.5-bit EHT ADC was not fabricated as a chip; the PCB implementation used discrete COTS components and a non-optimal topology. Variable-resolution quantization in the PCB experiment was emulated by dropping LSBs from 14-bit oscilloscope measurements using software.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an analog-domain Hadamard Transform-based variable-resolution pixel quantization method and an embedded-HT pipelined ADC architecture to reduce image BPP and ADC power while preserving CNN classification accuracy for edge machine vision.

| Paper      | Year | Task           | Model                   | Technique                                                                | Device                                      | Dataset            | Main Metric                       | Latency | Model Size | SRAM/RAM | Flash | Energy                   | Framework                         | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | -------------- | ----------------------- | ------------------------------------------------------------------------ | ------------------------------------------- | ------------------ | --------------------------------- | ------- | ---------- | -------- | ----- | ------------------------ | --------------------------------- | -------- | ------------- | ------------- |
| Deb et al. | 2025 | Classification | ResNet50; VGG-style CNN | Variable-resolution pixel quantization with analog 1D Hadamard Transform | 1.5-bit EHT pipelined ADC; HT PCB prototype | CIFAR-10; ImageNet | 90.15% CIFAR-10 accuracy at 3-BPP | N/A     | N/A        | N/A      | N/A   | ≈90% ADC power reduction | TensorFlow/Keras; MATLAB; Cadence | Mixed    | None          | No            |
