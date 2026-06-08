Paper ID: tiny-machine-learning-for-high-accuracy-product-quality-inspection

TinyML classification: Strict TinyML — explicitly deploys optimized CNNs on MCU-based cameras under memory, latency, and energy constraints.

Basic Info

Authors: Andrea Albanese, Matteo Nardello, Gianluca Fiacco, Davide Brunelli

Year: 2023

Title: Tiny Machine Learning for High Accuracy Product Quality Inspection

Source: IEEE Sensors Journal, Vol. 23, No. 2, 15 January 2023. 

Type: Experimental

Problem & Context

Task: Classification

Objective: Design, implement, and evaluate an MCU-based tinyML visual inspection system for detecting shape defects and color anomalies in plastic components.

Application domain: Industrial product quality inspection

Scenario: Edge, embedded, Industrial IoT, MCU-based smart cameras

TinyML relevance: Yes

TinyML justification: The paper deploys compressed CNNs directly on MCU-based OpenMV Cam H7 Plus cameras with local inference, memory usage, latency, power, and energy evaluation.

Model / Method

Model: MobileNetV2 and SqueezeNet

Architecture family: CNN

Techniques: Parameter minimization, pruning, full-integer 8-bit quantization, model compression, image preprocessing with Canny algorithm, Blob detection, and Otsu’s method

Framework: TensorFlow

Training type: from scratch

Inference type: on-device

Hardware

Device: OpenMV Cam H7 Plus

Hardware type: MCU

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported as hardware capacity; RAM usage during inference is reported.

Flash / ROM / Storage: Not reported as hardware capacity; Flash usage during inference is reported.

Power consumption: 0.8 W active mode

Energy per inference: MobileNetV2: 192 mJ top camera and 186 mJ side camera; SqueezeNet: 412 mJ top camera and 406 mJ side camera

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, energy, latency, compute, real-time performance, communication bandwidth

Dataset

Name: Custom plastic component inspection dataset

Type: private

Dataset size: Top camera: 10,830 images after augmentation; side cameras: 6,816 images after augmentation

Number of classes: 2 per classifier

Input resolution: 320 × 240 acquisition; 160 × 160 RGB model input

Data modality: RGB image

Metrics

Accuracy: Top camera optimized: 98.9% MobileNetV2, 98.4% SqueezeNet; side cameras optimized: 99.6% MobileNetV2, 98.2% SqueezeNet

mAP: Not reported

Precision: Top camera optimized: 98% MobileNetV2, 99% SqueezeNet; side cameras optimized: 100% MobileNetV2, 100% SqueezeNet

Recall: Top camera optimized: 100% MobileNetV2, 98% SqueezeNet; side cameras optimized: 99% MobileNetV2, 96% SqueezeNet

F1-score: Top camera optimized: 99% MobileNetV2, 98% SqueezeNet; side cameras optimized: 99.5% MobileNetV2, 98% SqueezeNet

Latency: MobileNetV2 total: 240 ms top camera and 233 ms side camera; SqueezeNet total: 515 ms top camera and 508 ms side camera

FPS: 5 FPS MobileNetV2; 2 FPS SqueezeNet

Throughput: Not reported separately

Model size: Optimized Flash usage: 172.26 KB MobileNetV2, 334.35 KB SqueezeNet

Parameters: Table II reports base/modified parameters as MobileNetV2: 412,770 / 176,386 and SqueezeNet: 723,522 / 337,090; Table III reports before/after-pruning nonzero parameters as MobileNetV2: 234,914 / 117,457 and SqueezeNet: 120,930 / 60,456

MACs / FLOPs: Not reported

RAM usage: Optimized model: 381.22 KB MobileNetV2, 455.25 KB SqueezeNet; Float32 model: 1490 KB MobileNetV2, 1780 KB SqueezeNet

Flash usage: Optimized model: 172.26 KB MobileNetV2, 334.35 KB SqueezeNet; Float32 model: 635.29 KB MobileNetV2, 1290 KB SqueezeNet

Energy per inference: MobileNetV2: 192 mJ top camera and 186 mJ side camera; SqueezeNet: 412 mJ top camera and 406 mJ side camera

Power consumption: 0.8 W active mode

Optimization

Techniques used: Parameter minimization, pruning, 8-bit full-integer quantization, compression

Quantization: INT8 full-integer

Pruning: Yes

Knowledge distillation: Not reported

Compression method: Reduced MobileNetV2 blocks from 17 to 14, reduced SqueezeNet fire modules from 8 to 5, polynomial decay pruning with 50% sparsity, and 8-bit quantization of weights, activations, inputs, and outputs

Hardware-specific optimization: Models compressed for deployment on OpenMV Cam H7 Plus MCU cameras

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: RAM usage reported: 381.22 KB MobileNetV2 optimized and 455.25 KB SqueezeNet optimized

Flash usage reported: 172.26 KB MobileNetV2 optimized and 334.35 KB SqueezeNet optimized

Model size reported: Yes

Energy per inference reported: Yes

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Only classification results are sent to the gateway; image processing and neural classification run locally on the MCU cameras

Candidate for Strict TinyML: Yes

Reason: The paper explicitly deploys compressed CNNs on MCU-based cameras and reports local inference, RAM/Flash usage, latency, energy, and power measurements.

Benchmarking / Standardization

Benchmark used: Custom industrial inspection dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, MobileNetV2 versus SqueezeNet and Float32 versus optimized models

Comparison with previous works: Not reported as experimental comparison

Reproducibility artifacts available: not reported

Results

Summary: The optimized MobileNetV2 achieves 98.9% accuracy on top-camera shape-defect classification and 99.6% on side-camera color-defect classification. The optimized system runs on OpenMV Cam H7 Plus with 172.26 KB Flash, 381.22 KB RAM, 233–240 ms total latency, and 186–192 mJ per inference for MobileNetV2.

Limitations

Not reported as a dedicated limitations section; future work includes NAS, continuous learning, expanding detectable anomalies, and improving efficiency using cameras that detect only relevant information.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an MCU-based tinyML visual inspection system using three OpenMV Cam H7 Plus cameras and compressed CNNs for local classification of shape defects and color anomalies in industrial plastic components.

| Albanese et al. | 2023 | Classification | MobileNetV2; SqueezeNet | Parameter minimization, pruning, INT8 quantization | OpenMV Cam H7 Plus | Custom plastic component inspection dataset | Accuracy 98.9–99.6% MobileNetV2 optimized | 233–240 ms MobileNetV2 | 172.26 KB MobileNetV2 optimized Flash | 381.22 KB MobileNetV2 optimized RAM | 172.26 KB MobileNetV2 optimized Flash | 186–192 mJ MobileNetV2 | TensorFlow | INT8 | N/A | Yes |
