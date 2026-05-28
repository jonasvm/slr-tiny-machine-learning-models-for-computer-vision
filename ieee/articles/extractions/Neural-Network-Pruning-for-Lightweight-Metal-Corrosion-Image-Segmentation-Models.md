## Paper ID: Neural-Network-Pruning-for-Lightweight-Metal-Corrosion-Image-Segmentation-Models

### Basic Info

* Authors: Vincent F. Yu; Gemilang Santiyuda; Shih-Wei Lin; Udjianna S. Pasaribu; Yuli Sri Afrianti
* Year: 2025
* Title: Neural Network Pruning for Lightweight Metal Corrosion Image Segmentation Models
* Source: IEEE Access, Volume 13, 2025. DOI: 10.1109/ACCESS.2025.3562435
* Type: Experimental

### Problem & Context

* Task: Segmentation
* Objective: Reduce model size and computational cost of metal corrosion image segmentation models using structured pruning while maintaining segmentation performance.
* Application domain: Metal corrosion detection and structural health monitoring.
* Scenario: Edge, IoT-based monitoring, UAV-based inspection, resource-constrained edge systems.
* TinyML relevance: Partial
* TinyML justification: The paper targets efficient deployment on resource-constrained edge devices and discusses local inference, model size, MAC reduction, memory footprint, and communication constraints. However, it does not report MCU-class deployment, SRAM/Flash usage, latency, energy, or execution without a full operating system.

### Model / Method

* Model: FPN, U-Net, U-Net++, LinkNet, MA-Net with ResNet-101 encoder pretrained on ImageNet.
* Architecture family: CNN
* Techniques: Structured pruning, linear pruning, automated gradual pruning, movement pruning, Taylor pruning, model compression, fine-tuning.
* Framework: PyTorch; NNI Python library.
* Training type: Transfer learning and fine-tuning.
* Inference type: Not reported.

### Hardware

* Device: NVIDIA GeForce GTX 2080 Ti and Intel i9-7900X with 20 cores.
* Hardware type: GPU / CPU
* Processor / microcontroller: Intel i9-7900X; NVIDIA GeForce GTX 2080 Ti.
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Computational cost, model size, memory footprint, latency-sensitive applications, network connectivity, bandwidth, communication dependency, privacy, energy efficiency.

### Dataset

* Name: SSCS dataset; NEA dataset.
* Type: SSCS: public; NEA: not reported.
* Dataset size: SSCS: 440 annotated images, split into 396 training images and 44 testing images; NEA: 292 images.
* Number of classes: SSCS: 4 classes; NEA: 3 classes.
* Input resolution: SSCS images resized to 512 × 512; NEA images originally 1280 × 720.
* Data modality: Image.

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Reported. Original models range from 344.9 MB to 1270.6 MB; pruned models reach as low as 19.4 MB for FPN, 21 MB for U-Net, 27.5 MB for U-Net++, 39.6 MB for LinkNet, and 65 MB for MA-Net.
* Parameters: Not reported
* MACs / FLOPs: MACs reported. For example, on NEA, FPN is reduced from 1.83 × 10¹¹ MAC to approximately 1.97 × 10¹⁰ MAC at 90% sparsity; MA-Net is reduced from 3.41 × 10¹¹ MAC to approximately 3.42 × 10¹⁰ MAC at 90% sparsity.
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Structured pruning, linear pruning, automated gradual pruning, movement pruning, Taylor pruning, model compression, fine-tuning.
* Quantization: None
* Pruning: Yes
* Knowledge distillation: No
* Compression method: Structured pruning of segmentation models to target sparsity levels of 0.2, 0.5, and 0.9.
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Yes
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper focuses on lightweight segmentation for edge deployment and reports model size and MAC reductions, but it does not evaluate deployment on MCU-class hardware, does not report SRAM/Flash usage, does not report latency or energy on a target device, and does not demonstrate execution without a full operating system.

### Benchmarking / Standardization

* Benchmark used: SSCS dataset and NEA dataset.
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: ImageNet used for encoder pretraining.
* Comparison with baseline models: Yes. Pruned models are compared with their original unpruned versions.
* Comparison with previous works: Not reported
* Reproducibility artifacts available: Code.

### Results

* Summary: Structured pruning substantially reduces model size and MACs while preserving segmentation performance at moderate sparsity levels. LP and AGP are generally more stable than MP. At 90% sparsity, performance often deteriorates, although some models retain useful IoU depending on architecture, dataset, and pruning method.

### Limitations

* Energy efficiency is not measured directly.
* Pruned models are not evaluated on real edge devices.
* SRAM, Flash, latency, power, and energy per inference are not reported.
* Dataset class imbalance affects IoU interpretation.
* Further work is needed on energy-aware pruning, hyperparameter tuning, finer sparsity levels, dataset quality, and practical edge-device evaluation.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a structured pruning-based framework for producing lightweight metal corrosion image segmentation models and analyzing the trade-off between segmentation quality, model size, and computational cost across multiple architectures and pruning strategies.

| Paper     | Year | Task         | Model                                | Technique          | Device                                      | Dataset   | Main Metric | Latency | Model Size           | SRAM/RAM | Flash | Energy | Framework    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | ------------ | ------------------------------------ | ------------------ | ------------------------------------------- | --------- | ----------- | ------- | -------------------- | -------- | ----- | ------ | ------------ | -------- | ------------- | ------------- |
| Yu et al. | 2025 | Segmentation | FPN, U-Net, U-Net++, LinkNet, MA-Net | Structured pruning | NVIDIA GeForce GTX 2080 Ti + Intel i9-7900X | SSCS; NEA | IoU         | N/A     | 19.4 MB to 1270.6 MB | N/A      | N/A   | N/A    | PyTorch; NNI | N/A      | None          | No            |
