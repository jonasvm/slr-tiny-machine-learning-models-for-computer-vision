Paper ID: A-Low-Cost-Low-Power-and-Real-Time-Image-Detector-for-Grape-Leaf-Esca-Disease-Based-on-a-Compressed-CNN

TinyML classification: Strict TinyML — Explicit MCU-class deployment on an ARM Cortex-M7 platform with memory, latency, and real-time embedded constraints.

Basic Info

Authors: Laura Falaschetti; Lorenzo Manoni; Romel Calero Fuentes Rivera; Danilo Pau; Gianfranco Romanazzi; Oriana Silvestroni; Valeria Tomaselli; Claudio Turchetti

Year: 2021

Title: A Low-Cost, Low-Power and Real-Time Image Detector for Grape Leaf Esca Disease Based on a Compressed CNN

Source: IEEE Journal on Emerging and Selected Topics in Circuits and Systems, Vol. 11, No. 3, September 2021 

Type: Experimental / Methodological

Problem & Context

Task: Classification

Objective: Real-time classification of grape leaf Esca disease using a compressed CNN on a low-cost, low-power embedded vision platform.

Application domain: Precision agriculture / viticulture / plant disease detection

Scenario: Embedded, MCU-based, on-device vision system mounted on an agricultural vehicle.

TinyML relevance: Yes

TinyML justification: The paper implements a compressed CNN on an OpenMV Cam STM32H7 Plus with an ARM Cortex-M7 MCU under memory, latency, and real-time embedded constraints.

Model / Method

Model: LR-Net

Architecture family: CNN

Techniques: CP tensor decomposition, low-rank CNN compression, post-training quantization, fine-tuning, TensorFlow Lite conversion, STM32Cube.AI conversion.

Framework: TensorFlow/Keras 2.4.0, TensorFlow Lite Converter, STM32Cube.AI 5.2.0, OpenMV firmware 3.9.3, Tensorly.

Training type: From scratch for FR-Net; fine-tuning after CP decomposition for LR-Net.

Inference type: On-device

Hardware

Device: OpenMV Cam STM32H7 Plus

Hardware type: MCU

Processor / microcontroller: STM32H743II ARM Cortex-M7

Clock frequency: 480 MHz

SRAM / RAM: 1 MB SRAM, 32 MB off-chip SDRAM, 31 MB frame buffer stack RAM available for model and scratch RAM.

Flash / ROM / Storage: 2 MB on-chip Flash, 32 MB off-chip Flash.

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Yes

Fully on-device inference: Yes

Constraints mentioned: Memory, latency, computational complexity, model storage, real-time inference, low cost, low power.

Dataset

Name: ESCA-dataset

Type: Not reported

Dataset size: 1,770 original images; 24,780 images after all augmentation transformations; 17,700 images considered after data augmentation.

Number of classes: 2

Input resolution: Original images: 1920 × 1080 and 1280 × 720; CNN input: 64 × 64 × 3.

Data modality: RGB image

Metrics

Accuracy: 0.980 on OpenMV Cam STM32H7 Plus; 0.984 on desktop for LR-Net.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 64.213 ms/image on OpenMV Cam STM32H7 Plus; 12.044 ms/image on desktop.

FPS: 15.574 FPS on OpenMV Cam STM32H7 Plus.

Throughput: 15.574 FPS

Model size: 25.094 KB memory cost for LR-Net; 13,015 ROM bytes on OpenMV Cam STM32H7 Plus.

Parameters: 12,204

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: 13,015 ROM bytes

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: CP tensor decomposition, low-rank CNN compression, post-training quantization, layer-wise fine-tuning, TensorFlow Lite conversion, STM32Cube.AI conversion.

Quantization: INT8 / PTQ

Pruning: No

Knowledge distillation: No

Compression method: CANDECOMP/PARAFAC tensor decomposition applied to convolutional and dense layers.

Hardware-specific optimization: STM32Cube.AI conversion to executable C code for OpenMV Cam STM32H7 Plus.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: 13,015 ROM bytes

Model size reported: 25.094 KB memory cost; 13,015 ROM bytes

Energy per inference reported: Not reported

Latency on target device reported: 64.213 ms/image

Runs without full operating system: Yes

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: Yes

Reason: The paper reports deployment of a compressed CNN on an ARM Cortex-M7 MCU-based OpenMV Cam with real-time latency and memory/storage constraints.

Benchmarking / Standardization

Benchmark used: ESCA-dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: USPS, MNIST, AT&T, COIL-20, and CIFAR-10 used for tensor decomposition comparison.

Comparison with baseline models: Yes; compared with FR-Net, MobileNet V1, MobileNet V2, MobileNet V3, ResNet, LeNet, SqueezeNet, ShuffleNet variants, Improved ShuffleNet variants, and PeleeNet.

Comparison with previous works: Yes; compared against state-of-the-art lightweight CNN architectures.

Reproducibility artifacts available: code / model

Results

Summary: LR-Net achieved 0.980 accuracy, 64.213 ms/image latency, 15.574 FPS, and 13,015 ROM bytes on the OpenMV Cam STM32H7 Plus. It was the only evaluated network meeting the 68 ms real-time design constraint.

Limitations

The paper focuses only on Esca disease detection and does not address plant geolocalization. Energy per inference and numeric power consumption are not reported.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a CP-decomposed low-rank CNN image detector for real-time grape leaf Esca disease classification on an OpenMV STM32H7 Plus MCU-based embedded vision platform.

| Falaschetti et al. | 2021 | Classification | LR-Net | CP tensor decomposition + PTQ | OpenMV Cam STM32H7 Plus | ESCA-dataset | Accuracy 0.980 | 64.213 ms/image | 25.094 KB | N/A | 13,015 ROM bytes | N/A | TensorFlow Lite / STM32Cube.AI | INT8 / PTQ | None | Yes |
