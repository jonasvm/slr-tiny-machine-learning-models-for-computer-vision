Paper ID: Preserving-differential-privacy-in-neural-networks-for-foreign-object-detection-with-heterogeneity-based-noising-among-distributed-devices

TinyML classification: Near-TinyML — It targets distributed IoT/edge vision devices and privacy-preserving on-device learning, but reports no explicit MCU, Cortex-M, TFLite Micro, or kilobyte-level deployment constraints.

Basic Info

Authors: Meng Wang; Qiong-Yun Wang; Ya-Hao Zhang; Zi-Xuan Zhang; Ya-Ning Feng; Yu-Feng Cao

Year: 2024

Title: Preserving differential privacy in neural networks for foreign object detection with heterogeneity-based noising among distributed devices

Source: The Journal of Supercomputing, 80:21447–21474. 

Type: Methodological

Problem & Context

Task: Classification and segmentation

Objective: Improve privacy-preserving federated learning for railway foreign object detection using nonzero-mean differential privacy noise and secure aggregation.

Application domain: Railway / rail-driving systems

Scenario: IoT, distributed devices, rail-driving system

TinyML relevance: Partial

TinyML justification: The paper targets IoT/distributed devices for rail-driving computer vision, but does not report MCU-class deployment, memory constraints, energy, latency, model size, or bare-metal/RTOS execution.

Model / Method

Model: VGG16 for CIFAR10, ResNet50 for CIFAR100, ResNet101 for RailSem19; pBNN used for pFedBayes baseline

Architecture family: CNN / Other

Techniques: Federated learning, differential privacy, nonzero-mean Gaussian noise addition, fully homomorphic encryption, CKKS, greedy average block Kaczmarz method, denoising weighted aggregation

Framework: Python; fastcore library for fully homomorphic encryption; CKKS

Training type: Not reported

Inference type: Not reported

Hardware

Device: Distributed rail-driving devices with cameras; server and third party described as high-performance computers

Hardware type: Other

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Privacy, communication security, data heterogeneity, noise variance, distributed learning

Dataset

Name: CIFAR10; CIFAR100; RailSem19

Type: CIFAR10/CIFAR100 public; RailSem19 not reported

Dataset size: CIFAR10: 50,000 training and 10,000 testing images; CIFAR100: 50,000 training and 10,000 testing images; RailSem19: 8,500 annotated short sequences, with 840 training and 360 testing samples selected

Number of classes: CIFAR10: 10; CIFAR100: 100; RailSem19: 19

Input resolution: Not reported

Data modality: RGB images and rail-scene image sequences

Metrics

Accuracy: Reported for CIFAR10 and CIFAR100; highest visible proposed-method max accuracy is 0.8640 on CIFAR10 IID and 0.4275 on CIFAR100 IID

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

Techniques used: Nonzero-mean differential privacy noise, fully homomorphic encryption, CKKS, greedy average block Kaczmarz method, denoising weighted aggregation in federated learning

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

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper does not report MCU-class hardware, memory limits, latency, energy, model size, TFLite Micro, CMSIS-NN, or bare-metal/RTOS deployment.

Benchmarking / Standardization

Benchmark used: CIFAR10; CIFAR100; RailSem19

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: CIFAR10; CIFAR100; RailSem19

Comparison with baseline models: FedAvg and pFedBayes for classification; FedAvg for segmentation

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset references for CIFAR10/CIFAR100; code and model not reported

Results

Summary: The proposed method achieved higher classification accuracy than FedAvg and pFedBayes on CIFAR10/CIFAR100 under tested IID and non-IID conditions. It also produced lower global testing loss than FedAvg on RailSem19 segmentation and improved privacy/security trends in most evaluated cases.

Limitations

Not reported.

Practical Reporting Checklist Evidence

Reports hardware clearly: No

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a privacy-preserving federated learning framework using nonzero-mean differential privacy noise, fully homomorphic encryption, and greedy average block Kaczmarz-based denoising aggregation for IoT rail-driving image classification and segmentation.

| Paper       | Year | Task                         | Model                      | Technique                                                                                             | Device                                                                           | Dataset                      | Main Metric                   | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework              | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------------------- | -------------------------- | ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ---------------------------- | ----------------------------- | ------- | ---------- | -------- | ----- | ------ | ---------------------- | -------- | ------------- | ------------- |
| Wang et al. | 2024 | Classification; Segmentation | VGG16; ResNet50; ResNet101 | Nonzero-mean differential privacy federated learning with CKKS/FHE and denoising weighted aggregation | Unspecified rail-driving IoT camera devices; high-performance server/third party | CIFAR10; CIFAR100; RailSem19 | Accuracy; global testing loss | N/A     | N/A        | N/A      | N/A   | N/A    | Python; fastcore; CKKS | N/A      | N/A           | No            |
