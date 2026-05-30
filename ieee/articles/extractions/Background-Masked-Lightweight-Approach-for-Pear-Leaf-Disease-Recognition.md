## Paper ID: Background-Masked-Lightweight-Approach-for-Pear-Leaf-Disease-Recognition

TinyML classification: Near-TinyML — it uses lightweight CNN backbones for edge/resource-constrained plant disease recognition, but the paper does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Romiyal George; Selvarajah Thuseethan; Roshan G. Ragel; Sutharshan Rajasegarar; Mamoun Alazab; Hamish Campbell; John Yearwood
* Year: 2025
* Title: Background-Masked Lightweight Approach for Pear Leaf Disease Recognition
* Source: IEEE Access, Volume 13, 2025
* Type: Experimental

### Problem & Context

* Task: Classification, with segmentation-based background masking as preprocessing
* Objective: Improve pear leaf disease recognition from in-field images with complex backgrounds using background masking, object cropping, and lightweight neural networks.
* Application domain: Precision agriculture / plant disease recognition
* Scenario: Resource-constrained edge/end-device classification with cloud-offloaded preprocessing
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained devices and lightweight computer vision, but preprocessing is executed in the cloud and no MCU-class deployment is reported.

### Model / Method

* Model: DeepLabV3 with ResNet101 for background masking; MobileNet-v2, EfficientNet-b0, SqueezeNet-1.1, and ShuffleNet-v2 for disease classification
* Architecture family: CNN
* Techniques: Background masking, object cropping, lightweight CNN backbones, data augmentation, transfer learning, Grad-CAM explainability
* Framework: PyTorch 1.13.1
* Training type: Transfer learning / fine-tuning
* Inference type: Hybrid

### Hardware

* Device: Laptop as end device; Google Colab as cloud server; NVIDIA RTX A6000 GPU for experiments
* Hardware type: CPU / GPU / cloud simulation
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: No
* Constraints mentioned: Resource constraints, computational complexity, training time, inference time, memory, energy, cloud communication

### Dataset

* Name: Pear leaf disease sub-dataset from DiaMOS Plant dataset; OWB, OWoB, AWB, and AWoB derived datasets
* Type: Public
* Dataset size: OWB/OWoB: 3,006 images; background masking training/validation subset: 1,179 images; AWB/AWoB after augmentation: 4,073 images
* Number of classes: 4
* Input resolution: 256 × 256 for background masking; 224 × 224 for classification
* Data modality: Pear leaf images; RGB not explicitly reported

### Metrics

* Accuracy: Best proposed accuracy was 90.84% using SqueezeNet-1.1; best baseline accuracy was 89.22% using SqueezeNet-1.1
* mAP: Not reported
* Precision: Proposed SqueezeNet-1.1 average precision was 91.43%
* Recall: Proposed SqueezeNet-1.1 average recall was 93.06%
* F1-score: Proposed SqueezeNet-1.1 average F1-score was 92.15%
* Latency: Proposed SqueezeNet-1.1 total inference time was 14.74 ms; preprocessing time was 2.96 ms and classification time was 11.78 ms
* FPS: Not reported
* Throughput: Not reported
* Model size: Proposed SqueezeNet-1.1 estimated total size was 212.35 MB; DeepLabV3 estimated total size was 8338.53 MB
* Parameters: Proposed SqueezeNet-1.1 classification model had 0.72M parameters; DeepLabV3 had 60.99M parameters
* MACs / FLOPs: Proposed SqueezeNet-1.1 classification model had 0.35G FLOPs; DeepLabV3 had 125.59G FLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Background masking, object cropping, lightweight CNN backbones, data augmentation, transfer learning
* Quantization: None
* Pruning: No
* Knowledge distillation: No
* Compression method: Lightweight backbone selection and object-cropped input
* Hardware-specific optimization: No
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Proposed SqueezeNet-1.1 estimated total size was 212.35 MB; DeepLabV3 estimated total size was 8338.53 MB
* Energy per inference reported: Not reported
* Latency on target device reported: Proposed SqueezeNet-1.1 total inference time was 14.74 ms in the simulated laptop/cloud setup
* Runs without full operating system: No
* Fully on-device inference: No
* Communication required during inference: Yes
* Candidate for Strict TinyML: No
* Reason: The pipeline requires cloud communication for preprocessing, uses a laptop/Google Colab simulation, and does not report MCU-class deployment, SRAM, Flash, TensorFlow Lite Micro, CMSIS-NN, or energy measurements.

### Benchmarking / Standardization

* Benchmark used: DiaMOS Plant pear leaf disease dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed background masking model achieved 93.93% validation IoU. The best disease recognition result was obtained with SqueezeNet-1.1, reaching 90.84% accuracy, 91.43% precision, 93.06% recall, and 92.15% F1-score. The proposed approach improved accuracy and reduced classification time compared with the baseline lightweight models.

### Limitations

* The full pipeline was not deployed entirely on the resource-constrained end device.
* The background masking module was offloaded to the cloud.
* Energy consumption was not experimentally evaluated on real edge devices.
* Future evaluation on Raspberry Pi or NVIDIA Jetson Nano was proposed but not reported.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Partial
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Partial
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a background-masked lightweight pipeline for pear leaf disease recognition that removes complex image backgrounds in the cloud and performs disease classification using lightweight CNN backbones on a resource-constrained end device.

| Paper         | Year | Task           | Model                      | Technique                                              | Device                                 | Dataset                                | Main Metric      | Latency  | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---: | -------------- | -------------------------- | ------------------------------------------------------ | -------------------------------------- | -------------------------------------- | ---------------- | -------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| George et al. | 2025 | Classification | DeepLabV3 + SqueezeNet-1.1 | Background masking + object cropping + lightweight CNN | Laptop end device + Google Colab cloud | DiaMOS Plant pear leaf disease dataset | Accuracy: 90.84% | 14.74 ms | 212.35 MB  | N/A      | N/A   | N/A    | PyTorch   | FP32     | None          | No            |
