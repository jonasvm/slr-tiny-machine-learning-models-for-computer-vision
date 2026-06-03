## Paper ID: TinyML-enabled-fuzzy-logic-for-enhanced-road-anomaly-detection-in-remote-sensing

TinyML classification: Near-TinyML — The work is relevant to edge/TinyML computer vision, but the available evidence reports general edge/resource-constrained framing rather than explicit MCU-class deployment or constraints.

### Basic Info

* Authors: Amna Khatoon; Weixing Wang; Mengfei Wang; Limin Li; Asad Ullah
* Year: 2025
* Title: TinyML-enabled fuzzy logic for enhanced road anomaly detection in remote sensing
* Source: Scientific Reports, 15:20659
* Type: Experimental

### Problem & Context

* Task: Segmentation / anomaly detection
* Objective: Detect and classify road network anomalies in remote sensing imagery using a TinyML-enabled U-Net and fuzzy logic framework.
* Application domain: Intelligent transportation systems, road infrastructure monitoring, remote sensing.
* Scenario: Edge / resource-constrained road anomaly detection.
* TinyML relevance: Yes
* TinyML justification: The paper explicitly frames the method as TinyML for resource-constrained edge devices and discusses compression, quantization, pruning, low-power operation, and microcontroller-oriented deployment, but does not report a concrete MCU deployment.

### Model / Method

* Model: TinyML-U-Net-FL
* Architecture family: Hybrid CNN
* Techniques: U-Net, fuzzy inference system, Gabor filtering, tensor voting, model compression, quantization, pruning.
* Framework: TensorFlow, Keras, PyTorch 1.7.0
* Training type: Transfer learning reported; details not reported
* Inference type: Hybrid / claimed edge; real deployment not reported

### Hardware

* Device: Deployment device not reported; experiments used Windows 11 Professional with Intel Core i9 CPU and NVIDIA GeForce RTX 4060 GPU with 16G video memory.
* Hardware type: CPU / GPU
* Processor / microcontroller: Intel Core i9; microcontroller not specified
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Memory, power, latency, computation, communication/cloud dependence.

### Dataset

* Name: DeepGlobe Road Extraction Dataset; Dubai aerial imagery / Semantic Segmentation of Aerial Imagery Dataset
* Type: Public
* Dataset size: DeepGlobe: 6226 aerial images; Dubai dataset size not reported
* Number of classes: Dubai dataset: 6 classes
* Input resolution: DeepGlobe: 1024×1024 pixels
* Data modality: Aerial/satellite RGB imagery

### Metrics

* Accuracy: 73.91%
* mAP: Not reported
* Precision: 78.2%
* Recall: 92.4%
* F1-score: 84.7%
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Model compression, quantization, pruning, fuzzy logic, Gabor filtering, tensor voting.
* Quantization: INT8 mentioned; QAT/PTQ not reported
* Pruning: Yes
* Knowledge distillation: Not reported
* Compression method: Compression, quantization, and pruning; details not reported
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Unclear
* Reason: The paper claims TinyML and microcontroller-oriented deployment, but does not report a specific MCU, SRAM/Flash usage, model size, latency, energy, or verified bare-metal/TFLM deployment.

### Benchmarking / Standardization

* Benchmark used: DeepGlobe Road Extraction Dataset; Semantic Segmentation of Aerial Imagery Dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: DeepGlobe Road Extraction Dataset
* Comparison with baseline models: DCS-TransUperNet, GOALF, GCB-Net, DiResNet, ScRoadExtractor
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset; code/model not reported

### Results

* Summary: TinyML-U-Net-FL achieved 73.91% accuracy, 78.2% precision, 92.4% recall, and 84.7% F1-score. The proposed method reported higher recall and F1-score than the compared road extraction/anomaly detection methods, but IoU was not reported for the proposed method.

### Limitations

* IoU was not reported for the proposed method, limiting localization assessment.
* Misclassifications remain for visually ambiguous road conditions.
* Computational resources, processing capacity, and training data availability remain challenges.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes, dataset only

### Contribution

* This paper proposes a TinyML-U-Net-FL framework that integrates TinyML, remote sensing, U-Net-based vision processing, and fuzzy logic for road network anomaly detection in resource-constrained edge scenarios.

| Paper          | Year | Task                             | Model           | Technique                                       | Device                                            | Dataset                         | Main Metric                  | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework                  | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | -------------------------------- | --------------- | ----------------------------------------------- | ------------------------------------------------- | ------------------------------- | ---------------------------- | ------- | ---------- | -------- | ----- | ------ | -------------------------- | -------- | ------------- | ------------- |
| Khatoon et al. | 2025 | Segmentation / anomaly detection | TinyML-U-Net-FL | Compression, quantization, pruning, fuzzy logic | Windows 11 PC, Intel Core i9, NVIDIA RTX 4060 16G | DeepGlobe; Dubai aerial imagery | F1-score 84.7%; Recall 92.4% | N/A     | N/A        | N/A      | N/A   | N/A    | TensorFlow, Keras, PyTorch | INT8     | None          | Unclear       |
