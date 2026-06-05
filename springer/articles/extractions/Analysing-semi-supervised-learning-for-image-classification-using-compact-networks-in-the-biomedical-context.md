Paper ID: Analysing-semi-supervised-learning-for-image-classification-using-compact-networks-in-the-biomedical-context

TinyML classification: Near-TinyML — Uses compact/efficient models for edge-oriented biomedical image classification, but reports no microcontroller-class deployment or MCU-level constraints.

## Basic Info

Authors: Adrián Inés; Andrés Díaz-Pinto; César Domínguez; Jónathan Heras; Eloy Mata; Vico Pascual

Year: 2024

Title: Analysing semi-supervised learning for image classification using compact networks in the biomedical context

Source: Soft Computing, 28, 8931–8943 

Type: Experimental / Benchmark / Methodological

## Problem & Context

Task: Classification

Objective: Analyse compact networks combined with semi-supervised learning methods for biomedical image classification.

Application domain: Biomedical imaging

Scenario: Edge/mobile-oriented biomedical image classification; experimental evaluation on GPU/CPU, not embedded deployment.

TinyML relevance: Partial

TinyML justification: The paper studies compact, quantized, and hardware-aware networks for resource-limited edge/mobile scenarios, but does not report MCU-class deployment or MCU-level memory, latency, or energy constraints.

## Model / Method

Model: ConvNeXt_tiny; MobileNet v2; MobileViT_s; ResNet-18; SqueezeNet; ShuffleNet v2; FBNet; MixNet; MNasNet; ResNet-18 quantized; ResNet-50 quantized; ResNet-50; ResNet-101; EfficientNet-B3

Architecture family: CNN / Hybrid CNN / ViT / Other

Techniques: Semi-supervised learning; plain distillation; data distillation; model distillation; data and model distillation; FixMatch; MixMatch; quantization; NAS-based compact networks; transfer learning; data augmentation

Framework: PyTorch; FastAI; PyTorch quantization API

Training type: Transfer learning / fine-tuning

Inference type: Not reported

## Hardware

Device: Intel Xeon W-2145 CPU for inference timing; NVIDIA RTX 2080 Ti GPU with 11 GB RAM for training

Hardware type: CPU / GPU

Processor / microcontroller: Intel Xeon W-2145 CPU; no microcontroller reported

Clock frequency: 3.70 GHz

SRAM / RAM: 32 GB system RAM; 11 GB GPU RAM

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Computational resources, memory, power consumption, latency, model size, and resource-limited edge/mobile environments

## Dataset

Name: Blindness; Chest X-ray; Fungi; HAM10000; ISIC; Kvasir; Open Sprayer; Plants; Retinal OCT; Tobacco

Type: Public

Dataset size: Blindness 3,662; Chest X-ray 2,355; Fungi 1,204; HAM10000 10,015; ISIC 1,500; Kvasir 8,000; Open Sprayer 6,697; Plants 5,500; Retinal OCT 84,484; Tobacco 3,492

Number of classes: Blindness 5; Chest X-ray 2; Fungi 4; HAM10000 7; ISIC 7; Kvasir 8; Open Sprayer 2; Plants 12; Retinal OCT 4; Tobacco 10

Input resolution: Not reported

Data modality: Biomedical images, X-ray images, OCT images, dermatoscopic images, gastrointestinal images, plant images, drone images, and document images

## Metrics

Accuracy: Not reported for target biomedical datasets

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Best reported mean F1-score was 85.6 with ConvNeXt_tiny using Model Distillation; best base compact model was ConvNeXt_tiny with 83.9 mean F1-score

Latency: 14–301 ms per image on Intel Xeon W-2145 CPU

FPS: Not reported

Throughput: Not reported

Model size: 0.36–512 MB depending on model

Parameters: 0.3M–44.5M parameters depending on model

MACs / FLOPs: 0.5G–41G FLOPs depending on model; not reported for quantized models

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

## Optimization

Techniques used: Compact networks; quantized networks; semi-supervised distillation; consistency regularization; transfer learning; data augmentation; NAS-designed architectures

Quantization: Not reported as INT8/FP16/QAT/PTQ; integer quantized ResNet-18 and ResNet-50 were evaluated

Pruning: No

Knowledge distillation: Yes

Compression method: Compact architectures and quantized ResNet models

Hardware-specific optimization: Hardware-aware compact networks considered, but no hardware-specific deployment optimization reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

## Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes; 0.36–512 MB

Energy per inference reported: Not reported

Latency on target device reported: No; only CPU inference timing was reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper does not report microcontroller-class deployment, SRAM/Flash constraints, OS-less execution, TensorFlow Lite Micro, CMSIS-NN, or energy measurements.

## Benchmarking / Standardization

Benchmark used: Ten biomedical image classification datasets

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet used for pretrained model features and transfer learning

Comparison with baseline models: Yes; standard-size ResNet-50, ResNet-101, and EfficientNet-B3 were compared with compact and quantized models

Comparison with previous works: Yes

Reproducibility artifacts available: code / model / dataset splits

## Results

Summary: Compact networks such as ConvNeXt_tiny, FBNet, MixNet, MNasNet, and ResNet-18 achieved performance comparable to standard-size models. Semi-supervised methods, especially Data Distillation and Model Distillation, improved compact models while preserving efficiency advantages. Quantized models reduced model size and inference time but generally had lower F1-scores than NAS and manually designed compact models.

Limitations: The paper states that users may need to test several combinations of compact architectures and semi-supervised methods; integration into smartphones and edge devices is left as future work.

## Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

## Contribution

This paper proposes a comparative study and Python library for combining compact neural networks with semi-supervised learning methods for biomedical image classification.

| Paper       | Year | Task           | Model                           | Technique                                             | Device                                        | Dataset                      | Main Metric   | Latency         | Model Size  | SRAM/RAM | Flash | Energy | Framework        | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | -------------- | ------------------------------- | ----------------------------------------------------- | --------------------------------------------- | ---------------------------- | ------------- | --------------- | ----------- | -------- | ----- | ------ | ---------------- | -------- | ------------- | ------------- |
| Inés et al. | 2024 | Classification | Compact CNN/Hybrid/ViT networks | Semi-supervised learning + compact/quantized networks | Intel Xeon W-2145 CPU; NVIDIA RTX 2080 Ti GPU | 10 biomedical image datasets | F1-score 85.6 | 14–301 ms/image | 0.36–512 MB | N/A      | N/A   | N/A    | PyTorch / FastAI | N/A      | None          | No            |
