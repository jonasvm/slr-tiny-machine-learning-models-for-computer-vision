## Paper ID: Embedded-AI-for-Wheat-Yellow-Rust-Infection-Type-Classification

TinyML classification: Near-TinyML — The deployment uses Jetson Nano/TensorFlow Lite edge hardware rather than explicit MCU-class constraints.

### Basic Info

* Authors: Uferah Shafi; Rafia Mumtaz; Muhammad Deedahwar Mazhar Qureshi; Zahid Mahmood; Sikander Khan Tanveer; Ihsan Ul Haq; Syed Mohammad Hassan Zaidi
* Year: 2023
* Title: Embedded AI for Wheat Yellow Rust Infection Type Classification
* Source: IEEE Access, Volume 11, DOI: 10.1109/ACCESS.2023.3254430
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Classify wheat yellow rust infection type into healthy, resistant, moderate, and susceptible classes.
* Application domain: Precision agriculture / plant disease detection
* Scenario: Edge / embedded agricultural monitoring device
* TinyML relevance: Partial
* TinyML justification: The paper deploys a trained model on an embedded edge device for on-device inference, but the target hardware is Nvidia Jetson Nano rather than MCU-class hardware.

### Model / Method

* Model: U2-Net for segmentation; ResNet-50 and Xception for classification; ResNet-50 deployed on the edge device
* Architecture family: CNN
* Techniques: Transfer learning, foreground segmentation, dropout, TensorFlow Lite deployment
* Framework: TensorFlow Lite; Ailia SDK for U2-Net segmentation
* Training type: Transfer learning
* Inference type: On-device

### Hardware

* Device: Nvidia Jetson Nano-based wheat rust detection device with 7-inch touchscreen, Logitech Webcam C930e, and power bank
* Hardware type: SoC / GPU / CPU
* Processor / microcontroller: 128-core NVIDIA Maxwell GPU; quad-core ARM A57 CPU
* Clock frequency: Not reported
* SRAM / RAM: 4 GB LPDDR4
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Memory utilization, model size, prediction time, portability, and power-bank-based field operation

### Dataset

* Name: Collected wheat stripe rust dataset and publicly available Yellow-Rust-19 dataset
* Type: Mixed collected/public
* Dataset size: 1,640 collected images and 10,000 selected public images used for the four target classes
* Number of classes: 4
* Input resolution: 250 × 250 for Xception; ResNet-50 input resolution not reported
* Data modality: RGB image

### Metrics

* Accuracy: ResNet-50: 96% on public test split, 95.4% on combined test split, 91.87% on collected test split; Xception: 95.7% on public test split; field device accuracy: 93%
* mAP: Not reported
* Precision: ResNet-50 per-class precision: Healthy 0.99, Moderate 0.96, Resistant 0.97, Susceptible 0.92
* Recall: ResNet-50 per-class recall: Healthy 0.98, Moderate 0.91, Resistant 0.98, Susceptible 0.97
* F1-score: ResNet-50 per-class F1-score: Healthy 0.99, Moderate 0.94, Resistant 0.97, Susceptible 0.94
* Latency: ResNet-50 prediction time: 6 ms; Xception prediction time: 5 ms
* FPS: Not reported
* Throughput: Not reported
* Model size: ResNet-50: 100 MB; Xception: 95 MB
* Parameters: ResNet-50: 158,860,164; Xception: 156,133,932
* MACs / FLOPs: Not reported
* RAM usage: Not reported beyond Jetson Nano 4 GB RAM
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: TensorFlow Lite deployment, U2-Net segmentation, transfer learning, dropout
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: TensorFlow Lite deployment for embedded/mobile/end devices
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: ResNet-50: 100 MB; Xception: 95 MB
* Energy per inference reported: Not reported
* Latency on target device reported: 6 ms prediction time for ResNet-50
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The deployment uses Jetson Nano with Linux-based embedded edge hardware and large CNN models, without MCU-class memory, flash, or bare-metal/RTOS evidence.

### Benchmarking / Standardization

* Benchmark used: Public wheat yellow rust dataset used for external validation
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: ImageNet mentioned as the pretraining benchmark for selected models
* Comparison with baseline models: ResNet-50 compared with Xception
* Comparison with previous works: Compared with an existing wheat yellow rust CNN approach reporting 91% accuracy
* Reproducibility artifacts available: Dataset

### Results

* Summary: ResNet-50 achieved the best reported classification accuracy of 96% on the public test split and 95.4% on the combined test split. The trained ResNet-50 model was deployed on a Jetson Nano-based edge device and tested in field conditions, where the system achieved 93% accuracy.

### Limitations

* The collected dataset is smaller and lower-resolution than the public dataset.
* Resistant and moderate classes are more frequently misclassified due to visual similarity and fewer collected samples.
* Data collection used controlled backgrounds, and future work is needed for more flexible field image capture and robust segmentation.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes an embedded AI system for wheat yellow rust infection type classification using U2-Net segmentation, CNN-based classification, and on-device deployment on a Jetson Nano edge device.

---

| Paper        | Year | Task           | Model                       | Technique                                                     | Device             | Dataset                                              | Main Metric   | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | -------------- | --------------------------- | ------------------------------------------------------------- | ------------------ | ---------------------------------------------------- | ------------- | ------- | ---------- | -------- | ----- | ------ | --------------- | -------- | ------------- | ------------- |
| Shafi et al. | 2023 | Classification | ResNet-50; Xception; U2-Net | Transfer learning + segmentation + TensorFlow Lite deployment | Nvidia Jetson Nano | Collected wheat stripe rust dataset + Yellow-Rust-19 | Accuracy: 96% | 6 ms    | 100 MB     | 4 GB RAM | N/A   | N/A    | TensorFlow Lite | N/A      | None          | No            |
