Paper ID: Efficient-Attention-Lightweight-Deep-Learning-Architecture-Integration-for-Plant-Pest-Recognition

TinyML classification: Near-TinyML — lightweight edge-oriented computer vision model, but no explicit microcontroller-class deployment or MCU memory/energy constraints.

Basic Info

Authors: Sivasubramaniam Janarthan; Selvarajah Thuseethan; Charles Joseph; Vigneshwaran Palanisamy; Sutharshan Rajasegarar; John Yearwood

Year: 2025

Title: Efficient Attention-Lightweight Deep Learning Architecture Integration for Plant Pest Recognition

Source: IEEE Transactions on Agrifood Electronics, Vol. 3, No. 2, September/October 2025 

Type: Experimental

Problem & Context

Task: Classification

Objective: Determine the optimal integration configuration of attention mechanisms with MobileNetV2 for plant pest recognition.

Application domain: Agriculture; plant pest recognition.

Scenario: In-field agricultural recognition; mobile/resource-constrained deployment is discussed, but no real deployment hardware is evaluated.

TinyML relevance: Partial

TinyML justification: The paper targets lightweight deep learning for resource-constrained and mobile devices, but does not report MCU-class deployment, SRAM/Flash constraints, energy, or embedded inference measurements.

Model / Method

Model: MobileNetV2 with attention mechanisms; evaluated variants include SE-MobileNetV2, ECA-Net, BAM4, BAM12, ULSAM, CA-Net, and MobileViT-XSS.

Architecture family: CNN

Techniques: Attention mechanism integration; empirical attention-location selection; lightweight architecture design; ImageNet pretraining; fine-tuning.

Framework: PyTorch

Training type: Fine-tuning

Inference type: Not reported

Hardware

Device: Deployment device not reported; training/pretraining used a Windows server with Dual Intel E5-2630 v4 CPU, 128 GB RAM, and 8× NVIDIA GeForce GTX 1080 Ti GPUs; pest fine-tuning used Google Colab.

Hardware type: CPU / GPU

Processor / microcontroller: Dual Intel E5-2630 v4 @ 2.20 GHz; microcontroller not reported.

Clock frequency: 2.20 GHz

SRAM / RAM: 128 GB RAM for training server; SRAM not reported.

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Computational complexity, memory consumption, model parameters, FLOPs, resource-constrained devices, mobile phones, and tablets.

Dataset

Name: D15869, D1500, D21599, D2545; CIFAR100 used for tuning; ImageNet used for pretraining.

Type: Public

Dataset size: D15869: 5,869 images; D1500: 500 images; D21599: 1,599 images; D2545: 545 images.

Number of classes: D15869 and D1500: 10 classes; D21599: 24 classes; D2545: 10 classes.

Input resolution: 224 × 224

Data modality: Plant pest images

Metrics

Accuracy: Best reported results: BAM12 achieved 96.70% on D15869, 92.40% on D1500, and 99.08% on D2545; BAM4 achieved 96.69% on D21599.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Best reported results: BAM12 achieved 96.45% on D15869, 92.37% on D1500, and 99.06% on D2545; BAM4 achieved 96.48% on D21599.

Latency: Not reported

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: BAM12: 3.88M parameters; BAM4: 3.51M; SE: 4.07M; MobileNetV2 baseline: 3.50M.

MACs / FLOPs: BAM12: 0.3920 GMAC; BAM4: 0.3359 GMAC; SE: 0.3371 GMAC; MobileNetV2 baseline: 0.3342 GMAC.

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Attention integration with MobileNetV2; empirical selection of attention placement; tuning of attention hyperparameters.

Quantization: Not reported

Pruning: No

Knowledge distillation: No

Compression method: Not reported

Hardware-specific optimization: Not reported

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

Reason: The paper evaluates lightweight CNN-attention models but does not report MCU deployment, TensorFlow Lite Micro, SRAM/Flash usage, energy, latency on embedded hardware, or OS-less execution.

Benchmarking / Standardization

Benchmark used: CIFAR100; ImageNet; D15869; D1500; D21599; D2545.

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet; CIFAR100

Comparison with baseline models: Yes; compared with MobileNetV2 baseline.

Comparison with previous works: Yes; compared with SE, ECA-Net, BAM, ULSAM, CA-Net, and MobileViT variants.

Reproducibility artifacts available: Dataset; code/model not reported.

Results

Summary: BAM12 achieved the best performance on D15869, D1500, and D2545, while BAM4 achieved the best performance on D21599. The study reports that careful attention integration improves MobileNetV2 performance without drastically increasing computational complexity.

Limitations

The paper does not evaluate deployment on actual resource-constrained hardware. Future work includes comparison with YOLO-based, APNet, and Transformer-based lightweight models, testing under diverse environmental conditions, and evaluating compatibility with resource-constrained devices.

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

Reports reproducibility artifacts: No

Contribution

This paper proposes a systematic attention-lightweight architecture integration method to identify effective attention configurations for MobileNetV2-based plant pest image classification.

| Janarthan et al. | 2025 | Classification | MobileNetV2+BAM12 | Attention integration | N/A | D15869/D1500/D21599/D2545 | Accuracy 99.08% | N/A | N/A | N/A | N/A | N/A | PyTorch | N/A | None | No |
