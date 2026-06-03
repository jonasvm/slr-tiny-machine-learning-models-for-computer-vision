## Paper ID: Tiny-Machine-Learning-Based-Supply-Canal-Surface-Condition-Monitoring

TinyML classification: Strict TinyML — The paper explicitly targets MCU-class deployment on Arduino Nano 33 BLE Sense / nRF52840 with TFLite Micro and kilobyte-scale model constraints.

### Basic Info

* Authors: Chengjie Huang; Xinjuan Sun; Yuxuan Zhang
* Year: 2024
* Title: Tiny-Machine-Learning-Based Supply Canal Surface Condition Monitoring
* Source: Sensors, 24, 4124
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Classify supply canal surface conditions into normal, cracks, and holes using a lightweight CNN deployed on an MCU.
* Application domain: Structural health monitoring of hydraulic infrastructure
* Scenario: TinyML, embedded, low-power, MCU-based monitoring
* TinyML relevance: Yes
* TinyML justification: The paper explicitly deploys a quantized CNN model on a low-power Arduino Nano 33 BLE Sense MCU using TensorFlow Lite Micro.

### Model / Method

* Model: Custom lightweight CNN
* Architecture family: CNN
* Techniques: Data augmentation, depthwise separable convolution, lightweight architecture design, post-training quantization, full-integer quantization
* Framework: TensorFlow, TensorFlow Lite, TensorFlow Lite Micro, Arduino IDE, MLTK
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: Arduino Nano 33 BLE Sense
* Hardware type: MCU
* Processor / microcontroller: nRF52840 ARM Cortex-M4F 32-bit processor
* Clock frequency: 64 MHz
* SRAM / RAM: 256 KB available; 96.0 KB used by proposed model
* Flash / ROM / Storage: 1 MB CPU flash; 0.35 MB flash used by proposed model
* Power consumption: Approximately 18.9 mW during operation; 7.05 µW in sleep mode
* Energy per inference: 5610.18 µJ
* Execution without full OS: Yes
* Fully on-device inference: Yes
* Constraints mentioned: Memory, flash, RAM, power, latency, energy, compute, deployment feasibility

### Dataset

* Name: Supply canal damage image dataset
* Type: Private
* Dataset size: 270 original images; augmented training/validation dataset with 720 training images, 180 validation images, and 120 test images
* Number of classes: 3
* Input resolution: 64 × 64 pixels
* Data modality: RGB image

### Metrics

* Accuracy: 94.17 ± 1.67%
* mAP: Not reported
* Precision: 94.47 ± 1.46%
* Recall: 94.27 ± 1.57%
* F1-score: 94.26 ± 1.94% before deployment; 94.34 ± 1.64% after deployment
* Latency: 296.94 ms
* FPS: Not reported
* Throughput: Not reported
* Model size: 7.54 KB / 7.57 KB
* Parameters: 803
* MACs / FLOPs: 905,618 FLOPs
* RAM usage: 96.0 KB
* Flash usage: 0.35 MB / 354.48 KB
* Energy per inference: 5610.18 µJ
* Power consumption: Approximately 18.9 mW during inference

### Optimization

* Techniques used: Lightweight CNN design, depthwise separable convolution, global average pooling, data augmentation, post-training quantization, full-integer quantization
* Quantization: INT8 / PTQ
* Pruning: No
* Knowledge distillation: No
* Compression method: Full-integer post-training quantization and lightweight architecture design
* Hardware-specific optimization: Model converted to TensorFlow Lite Micro C source for MCU deployment
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Yes
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: 96.0 KB RAM usage
* Flash usage reported: 0.35 MB / 354.48 KB
* Model size reported: 7.54 KB / 7.57 KB
* Energy per inference reported: 5610.18 µJ
* Latency on target device reported: 296.94 ms
* Runs without full operating system: Yes
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Yes
* Reason: The model is deployed on an ARM Cortex-M4F MCU using TensorFlow Lite Micro with reported RAM, flash, model size, latency, and energy metrics.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: ShuffleNetV2, ResNet-50, MobileNetV2, EfficientNet-B0, MnasNet
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed CNN achieved 94.17 ± 1.67% accuracy with only 803 parameters and 905,618 FLOPs. After MCU deployment, it achieved 94.34 ± 1.64% F1-score, 7.54 KB model size, 96.0 KB RAM usage, 0.35 MB flash usage, 296.94 ms latency, and 5610.18 µJ per inference.

### Limitations

* The dataset is small and limited to specific supply canal surface conditions.
* The authors state that further validation in additional scenarios, such as downstream slopes of supply canals, is needed.
* Future work should integrate additional sensor data such as temperature and humidity.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a lightweight TinyML CNN for supply canal surface damage classification and deploys it on a low-power MCU for structural health monitoring.

| Paper        | Year | Task           | Model                  | Technique                                       | Device                    | Dataset                                   | Main Metric            | Latency   | Model Size | SRAM/RAM | Flash   | Energy     | Framework             | INT8/QAT   | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | -------------- | ---------------------- | ----------------------------------------------- | ------------------------- | ----------------------------------------- | ---------------------- | --------- | ---------- | -------- | ------- | ---------- | --------------------- | ---------- | ------------- | ------------- |
| Huang et al. | 2024 | Classification | Custom lightweight CNN | Lightweight CNN + PTQ full-integer quantization | Arduino Nano 33 BLE Sense | Private supply canal damage image dataset | Accuracy 94.17 ± 1.67% | 296.94 ms | 7.54 KB    | 96.0 KB  | 0.35 MB | 5610.18 µJ | TensorFlow Lite Micro | INT8 / PTQ | TFLM          | Yes           |
