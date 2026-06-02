## Paper ID: Leveraging-fundus-images-for-on-device-eye-disease-diagnosis-with-AI-powered-lightweight-software-hardware-framework

TinyML classification: Near-TinyML — The paper uses Raspberry Pi 5/ARM Cortex-A76 edge deployment, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Prajwal Thaware, A. A. Khurshid, Chetan Sonkusare, Yash Agrawal
* Year: 2025
* Title: Leveraging fundus images for on device eye disease diagnosis with AI powered lightweight software hardware framework
* Source: Scientific Reports
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Develop a low-cost on-device AI framework for multi-disease eye diagnosis from fundus images.
* Application domain: Ophthalmology / retinal disease screening
* Scenario: Edge, embedded, portable medical diagnostic device
* TinyML relevance: Partial
* TinyML justification: The paper deploys TensorFlow Lite inference on Raspberry Pi 5 for fully on-device edge diagnosis, but does not report MCU-class deployment or kilobyte-scale memory constraints.

### Model / Method

* Model: EfficientNet-B0 with spatial CNN block
* Architecture family: CNN
* Techniques: Transfer learning, spatial attention CNN block, Grad-CAM heatmap generation, CLAHE preprocessing, pixel pitch calibration, TensorFlow Lite edge optimization
* Framework: TensorFlow Lite
* Training type: Transfer learning / fine-tuning
* Inference type: On-device

### Hardware

* Device: Raspberry Pi 5-based portable fundus imaging prototype
* Hardware type: SoC / CPU
* Processor / microcontroller: Arm Cortex-A76 processor
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, processing power, battery life, latency, model compression trade-offs, and network connectivity

### Dataset

* Name: EyePACS, Messidor-2, IDRID, REFUGE Challenge, custom hospital datasets
* Type: Public / private
* Dataset size: 13,300 images, 15,400 labels, 6,650 subjects
* Number of classes: 9
* Input resolution: 256×256
* Data modality: Fundus images

### Metrics

* Accuracy: 96.2%
* mAP: Not reported
* Precision: 0.91–0.99 per class
* Recall: 0.89–0.985 per class
* F1-score: 0.958 overall/weighted
* Latency: 5 s per image on Raspberry Pi 5; 8 s for batch processing of 10 images
* FPS: Not reported
* Throughput: 10 images per batch in approximately 8 s
* Model size: Not reported
* Parameters: 5.6 million
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Lightweight EfficientNet-B0 architecture, spatial CNN attention block, TensorFlow Lite optimized inference, preprocessing pipeline with CLAHE and resizing
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: TensorFlow Lite inference optimized for Raspberry Pi 5 / Arm Cortex-A76
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 5 s per image on Raspberry Pi 5
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: No
* Reason: The deployment target is Raspberry Pi 5 with Arm Cortex-A76, and the paper does not report MCU-class execution, SRAM/Flash usage, or ultra-low-power deployment evidence.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: EyePACS, Messidor-2, IDRID, REFUGE Challenge
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset

### Results

* Summary: The proposed EfficientNet-B0 with spatial CNN block achieved 96.2% accuracy and 0.958 overall/weighted F1-score for fundus image disease classification. The TensorFlow Lite model achieved on-device inference on Raspberry Pi 5 with an average latency of 5 s per image.

### Limitations

* Pharmaceutical pupil dilation may cause discomfort and increase clinical workflow time.
* The limited field of view may miss peripheral retinal lesions important for diagnosis.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a low-cost integrated fundus imaging and on-device AI diagnostic framework using an optimized EfficientNet-B0 model with TensorFlow Lite deployment on Raspberry Pi 5.

| Paper          | Year | Task           | Model                                  | Technique                                             | Device         | Dataset                                                           | Main Metric    | Latency   | Model Size | SRAM/RAM | Flash | Energy | Framework       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---: | -------------- | -------------------------------------- | ----------------------------------------------------- | -------------- | ----------------------------------------------------------------- | -------------- | --------- | ---------- | -------- | ----- | ------ | --------------- | -------- | ------------- | ------------- |
| Thaware et al. | 2025 | Classification | EfficientNet-B0 with spatial CNN block | TensorFlow Lite edge optimization + spatial attention | Raspberry Pi 5 | EyePACS, Messidor-2, IDRID, REFUGE, custom hospital fundus images | Accuracy 96.2% | 5 s/image | N/A        | N/A      | N/A   | N/A    | TensorFlow Lite | N/A      | None          | No            |
