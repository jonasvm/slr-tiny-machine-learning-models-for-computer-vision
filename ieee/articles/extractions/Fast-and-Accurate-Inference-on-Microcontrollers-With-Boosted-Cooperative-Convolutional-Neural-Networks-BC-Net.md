Paper ID: Fast-and-Accurate-Inference-on-Microcontrollers-With-Boosted-Cooperative-Convolutional-Neural-Networks-BC-Net

TinyML classification: Near-TinyML — The paper targets resource-constrained IoT devices and evaluates image classification, object detection, and segmentation, but experiments are GPU-based and MCU-level deployment is not shown.

Basic Info

Authors: Luca Mocerino; Andrea Calimera

Year: 2021

Title: Fast and Accurate Inference on Microcontrollers With Boosted Cooperative Convolutional Neural Networks (BC-Net)

Source: IEEE Transactions on Circuits and Systems—I: Regular Papers, Vol. 68, No. 1, January 2021, pp. 77–88 

Type: Methodological

Problem & Context

Task: Classification

Objective: Improve CNN inference accuracy-latency trade-off on low-power microcontrollers using cooperative binary and 8-bit CNN execution.

Application domain: Edge AI; IoT; embedded vision; low-power inference

Scenario: Microcontroller-based embedded/on-device inference

TinyML relevance: Yes

TinyML justification: The paper explicitly targets ARM Cortex-M microcontrollers with limited RAM, Flash, latency, and low-power constraints.

Model / Method

Model: Boosted Cooperative Convolutional Neural Network (BC-Net)

Architecture family: CNN

Techniques: INT8 quantization; binarization; conditional inference; cooperative binary/INT8 execution; confidence-threshold control

Framework: CMSIS-NN; extended CMSIS-NN with binary convolution support

Training type: Not reported

Inference type: On-device

Hardware

Device: NUCLEO-F767ZI; STM32H743 board

Hardware type: MCU

Processor / microcontroller: ARM Cortex-M7

Clock frequency: NUCLEO-F767ZI: 216 MHz; STM32H743: 480 MHz rescaled to 216 MHz for evaluation

SRAM / RAM: NUCLEO-F767ZI: 512 kB RAM; STM32H743: 1 MB RAM

Flash / ROM / Storage: 2 MB Flash on both boards

Power consumption: Described as few hundred-mW MCU power envelope; measured power not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory; latency; compute; power; accuracy; limited instruction set; limited SIMD support

Dataset

Name: CIFAR-10; CIFAR-100; Google Speech Commands; FER2013

Type: Public

Dataset size: CIFAR-10/100: 60k images each; Google Speech Commands: 65k samples, 56,196 train and 7,518 test; FER2013: 28,709 train and 7,178 test

Number of classes: CIFAR-10: 10; CIFAR-100: 100; Google Speech Commands: 31; FER2013: 7

Input resolution: CIFAR: 32×32 RGB; Google Speech Commands: 32×32 spectrogram input; FER2013: 48×48 samples, benchmark input reported as 1×44×44

Data modality: RGB image; audio spectrogram; facial image

Metrics

Accuracy: BC-Net FM Top-1 accuracy: IC-10 84.00%; IC-100 66.48%; KS 92.55%; FER 66.48%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: BC-Net LM/FM latency: IC-10 65.29/164.26 ms; IC-100 54.46/202.35 ms; KS 32.56/99.06 ms; FER 174.33/528.37 ms

FPS: Not reported

Throughput: Not reported

Model size: Not reported as file size

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: BC-Net LM/FM memory: IC-10 94/235 kB; IC-100 123/569 kB; KS 90/386 kB; FER 118/705 kB

Flash usage: Board Flash capacity reported as 2 MB; per-model Flash usage not reported

Energy per inference: Not reported

Power consumption: Not reported as measured value

Optimization

Techniques used: INT8 fixed-point quantization; binary neural networks; cooperative binary/INT8 inference; confidence-threshold dynamic control; CMSIS-NN deployment

Quantization: Mixed precision

Pruning: No

Knowledge distillation: No

Compression method: 8-bit fixed-point quantization and binarization

Hardware-specific optimization: CMSIS-NN kernels on ARM Cortex-M7; extended support for binary convolutions

Use of CMSIS-NN: Yes

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: BC-Net FM up to 705 kB RAM on FER; other BC-Net FM values are 235 kB, 569 kB, and 386 kB

Flash usage reported: Board Flash capacity reported as 2 MB; per-model Flash usage not reported

Model size reported: Memory footprint reported; file/model storage size not reported

Energy per inference reported: No

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: Yes

Reason: The paper deploys optimized CNN inference on Cortex-M7 microcontroller boards and reports RAM footprint and latency under MCU-class constraints.

Benchmarking / Standardization

Benchmark used: CIFAR-10; CIFAR-100; Google Speech Commands; FER2013

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR-10; CIFAR-100; Google Speech Commands; FER2013

Comparison with baseline models: FP32; INT8; BNN

Comparison with previous works: CoopNet

Reproducibility artifacts available: Not reported

Results

Summary: BC-Net improves over INT8 quantization with up to 81.49% speed-up at break-even accuracy and up to 3.8% accuracy improvement. It also improves over CoopNet with up to 19% speed-up and up to 3.45% accuracy improvement.

Limitations

The paper does not report energy per inference, measured power, or per-model Flash usage. It also states that more complex scenarios such as ImageNet are out of reach for the targeted MCU segment.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a boosted cooperative CNN inference method that dynamically combines binary and 8-bit quantized networks to improve accuracy and latency on ARM Cortex-M microcontrollers.

| Paper           | Year | Task           | Model  | Technique                                           | Device                   | Dataset                                              | Main Metric           | Latency         | Model Size | SRAM/RAM  | Flash                           | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---- | -------------- | ------ | --------------------------------------------------- | ------------------------ | ---------------------------------------------------- | --------------------- | --------------- | ---------- | --------- | ------------------------------- | ------ | --------- | -------- | ------------- | ------------- |
| Mocerino et al. | 2021 | Classification | BC-Net | Mixed INT8/binary cooperative conditional inference | ARM Cortex-M7 MCU boards | CIFAR-10; CIFAR-100; Google Speech Commands; FER2013 | Accuracy up to 92.55% | 32.56–528.37 ms | N/A        | 90–705 kB | 2 MB board Flash; per-model N/A | N/A    | CMSIS-NN  | INT8     | CMSIS-NN      | Yes           |
