## Paper ID: Neural-Network-Pruning-for-Lightweight-Metal-Corrosion-Image-Segmentation-Models

TinyML classification: Near-TinyML — The work targets edge/resource-constrained deployment but evaluates pruning on GPU hardware and does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Vincent F. Yu; Gemilang Santiyuda; Shih-Wei Lin; Udjianna S. Pasaribu; Yuli Sri Afrianti
* Year: 2025
* Title: Neural Network Pruning for Lightweight Metal Corrosion Image Segmentation Models
* Source: IEEE Access
* Type: Experimental

### Problem & Context

* Task: Segmentation
* Objective: Reduce computational cost and model size of deep learning corrosion image segmentation models while maintaining segmentation performance.
* Application domain: Metal corrosion detection and structural health monitoring.
* Scenario: Edge-based monitoring systems, IoT-based systems, UAV-assisted inspection.
* TinyML relevance: Partial
* TinyML justification: The paper targets lightweight models for resource-constrained edge deployment, but does not report MCU-class deployment or microcontroller-level memory, latency, or energy measurements.

### Model / Method

* Model: U-Net, U-Net++, FPN, LinkNet, MA-Net with ResNet-101 encoder.
* Architecture family: CNN
* Techniques: Structured pruning, linear pruning, automated gradual pruning, movement pruning, model compression, fine-tuning.
* Framework: PyTorch; NNI Python library.
* Training type: Transfer learning and fine-tuning.
* Inference type: Not reported

### Hardware

* Device: NVIDIA GeForce GTX 2080 Ti and Intel i9-7900X used for experiments.
* Hardware type: GPU / CPU
* Processor / microcontroller: Intel i9-7900X with 20 cores; NVIDIA GeForce GTX 2080 Ti.
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Computational cost, model size, edge resource constraints, latency-sensitive applications, bandwidth constraints, network connectivity, memory footprint, energy efficiency.

### Dataset

* Name: SSCS; NEA
* Type: SSCS public; NEA not reported
* Dataset size: SSCS has 440 annotated images split into 396 training images and 44 testing images; NEA has 292 images.
* Number of classes: SSCS has 4 classes; NEA is used with 3 classes.
* Input resolution: SSCS images resized to 512 × 512; NEA images are 1280 × 720.
* Data modality: Metal corrosion images.

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Reported; original models range from 344.9 MB to 1270.6 MB, and pruned models include sizes down to 19.4 MB, 21 MB, 27.5 MB, 39.6 MB, and 65 MB depending on architecture and sparsity.
* Parameters: Not reported
* MACs / FLOPs: Reported as MACs; pruning reduces MACs substantially, with examples such as FPN reduced from around 1.83 × 10¹¹ to 1.97 × 10¹⁰ MACs at 90% sparsity on NEA.
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Structured pruning, linear pruning, automated gradual pruning, movement pruning, fine-tuning.
* Quantization: None
* Pruning: Yes
* Knowledge distillation: No
* Compression method: Structured pruning of convolutional filters using LP, AGP, and MP with target sparsities of 0.2, 0.5, and 0.9.
* Hardware-specific optimization: No
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
* Reason: The paper targets edge-oriented lightweight segmentation through pruning, but experiments are conducted on GPU/CPU hardware and no MCU-class deployment, SRAM, Flash, latency, or energy evidence is reported.

### Benchmarking / Standardization

* Benchmark used: SSCS and NEA corrosion image segmentation datasets.
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: ImageNet used for encoder pre-training.
* Comparison with baseline models: Yes
* Comparison with previous works: Not reported
* Reproducibility artifacts available: code

### Results

* Summary: Structured pruning reduced model size and MACs while retaining segmentation quality up to 50% sparsity for several model-pruner combinations. Performance deteriorated substantially at 90% sparsity for many cases, and pruning effectiveness varied by architecture and pruning method.

### Limitations

* Energy efficiency was not evaluated.
* Pruned models were not evaluated on practical edge devices.
* Performance deteriorated significantly at 90% sparsity.
* Movement pruning showed instability and poor results for some architectures.
* Dataset class imbalance and label quality issues may affect evaluation.

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

* This paper proposes a structured pruning and fine-tuning framework for producing lightweight metal corrosion image segmentation models and analyzing the trade-off between segmentation quality, model size, and computational cost.

| Paper     | Year | Task         | Model                                | Technique          | Device                                      | Dataset   | Main Metric | Latency | Model Size           | SRAM/RAM | Flash | Energy | Framework    | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | ------------ | ------------------------------------ | ------------------ | ------------------------------------------- | --------- | ----------- | ------- | -------------------- | -------- | ----- | ------ | ------------ | -------- | ------------- | ------------- |
| Yu et al. | 2025 | Segmentation | U-Net; U-Net++; FPN; LinkNet; MA-Net | Structured pruning | NVIDIA GeForce GTX 2080 Ti / Intel i9-7900X | SSCS; NEA | IoU         | N/A     | 19.4 MB to 1270.6 MB | N/A      | N/A   | N/A    | PyTorch; NNI | N/A      | None          | No            |
