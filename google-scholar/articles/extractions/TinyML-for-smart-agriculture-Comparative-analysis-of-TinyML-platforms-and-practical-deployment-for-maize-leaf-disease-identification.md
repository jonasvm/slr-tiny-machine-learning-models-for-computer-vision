## Paper ID: TinyML-for-smart-agriculture-Comparative-analysis-of-TinyML-platforms-and-practical-deployment-for-maize-leaf-disease-identification

TinyML classification: Strict TinyML — targets MCU-class deployment on Arduino Nano 33 BLE Sense with reported RAM, Flash, latency, and INT8 quantization constraints.

### Basic Info

* Authors: Dennis Agyemanh Nana Gookyi; Fortunatus Aabangbio Wulnye; Ewura Abena Essanoah Arthur; Roger Kwao Ahiadormey; Justice Owusu Agyemang; Kwame Opuni-Boachie Obour Agyekum; Raymond Gyaang
* Year: 2024
* Title: TinyML for smart agriculture: Comparative analysis of TinyML platforms and practical deployment for maize leaf disease identification
* Source: Smart Agricultural Technology, 8, 100490
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Develop and deploy a TinyML-based maize leaf disease identification system and compare TensorFlow and Edge Impulse workflows.
* Application domain: Smart agriculture / crop disease detection
* Scenario: Embedded edge / IoT / MCU-based agricultural device
* TinyML relevance: Yes
* TinyML justification: The paper targets MCU deployment on Arduino Nano 33 BLE Sense with reported latency, RAM, Flash, quantization, and offline edge inference.

### Model / Method

* Model: Custom CNN maize disease detection model
* Architecture family: CNN
* Techniques: Data augmentation, hyperparameter optimization, TensorFlow Lite conversion, INT8 quantization, Edge Impulse deployment
* Framework: TensorFlow, TensorFlow Lite, Edge Impulse
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: Arduino Nano 33 BLE Sense with camera module and TinyML shield
* Hardware type: MCU
* Processor / microcontroller: Not reported
* Clock frequency: 64 MHz
* SRAM / RAM: 256 KB SRAM device specification; 726.6 KB reported model RAM usage
* Flash / ROM / Storage: 1 MB CPU Flash device specification; 344.7 KB reported classifier Flash usage
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, latency, power, compute, cost, and resource-constrained deployment

### Dataset

* Name: Maize leaf disease dataset from Kaggle, Harvard Dataverse, and Mendeley
* Type: Public
* Dataset size: 12,344 raw images and 7,454 augmented images
* Number of classes: 5
* Input resolution: 96 × 96 pixels
* Data modality: RGB leaf images

### Metrics

* Accuracy: 94.84% testing accuracy for Edge Impulse / hybrid deployment; 96.38% TensorFlow testing accuracy
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Blight 0.99; Common Rust 0.98; Gray Leaf Spot 0.92; Healthy 0.99; Streak Virus 0.93
* Latency: 7.60 ms reported in abstract; 7,648 ms total INT8 latency reported in deployment table
* FPS: Not reported
* Throughput: Not reported
* Model size: 344.7 KB classifier Flash for INT8; 1.2 MB classifier Flash for float32
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: 726.6 KB INT8 total RAM; 2.8 MB float32 total RAM
* Flash usage: 344.7 KB INT8 classifier Flash; 1.2 MB float32 classifier Flash
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Data augmentation, model hyperparameter tuning, TensorFlow Lite conversion, INT8 quantization, MCU-oriented deployment optimization
* Quantization: INT8
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: INT8 quantization
* Hardware-specific optimization: Optimization for Arduino Nano 33 BLE Sense RAM, Flash, and latency constraints
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: 726.6 KB RAM usage
* Flash usage reported: 344.7 KB classifier Flash usage
* Model size reported: 344.7 KB INT8 classifier Flash; 1.2 MB float32 classifier Flash
* Energy per inference reported: Not reported
* Latency on target device reported: 7.60 ms in abstract; 7,648 ms total INT8 latency in deployment table
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly targets MCU-class TinyML deployment on Arduino Nano 33 BLE Sense with reported RAM, Flash, latency, and INT8 quantization results.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: TensorFlow, Edge Impulse, and hybrid workflow compared; INT8 and float32 deployment compared
* Comparison with previous works: Related work discussed, but no standardized quantitative benchmark comparison reported
* Reproducibility artifacts available: Dataset available on request

### Results

* Summary: The hybrid TensorFlow and Edge Impulse workflow achieved 94.84% testing accuracy with 344.7 KB Flash and 726.6 KB RAM usage. The INT8 model reduced memory requirements compared with float32 while maintaining comparable accuracy for maize leaf disease classification.

### Limitations

* Gray Leaf Spot classification had lower performance than other classes.
* Broader datasets, additional architectures, advanced augmentation, and sensor integration are suggested as future improvements.
* Energy per inference and power consumption were not quantitatively reported.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a TinyML-based maize leaf disease classification system using a custom CNN optimized and deployed on an Arduino Nano 33 BLE Sense through TensorFlow, TensorFlow Lite, and Edge Impulse workflows.

| Paper         | Year | Task           | Model      | Technique                                     | Device                    | Dataset                    | Main Metric     | Latency                     | Model Size | SRAM/RAM | Flash    | Energy | Framework                                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | -------------- | ---------- | --------------------------------------------- | ------------------------- | -------------------------- | --------------- | --------------------------- | ---------- | -------- | -------- | ------ | ----------------------------------------- | -------- | ------------- | ------------- |
| Gookyi et al. | 2024 | Classification | Custom CNN | INT8 quantization and Edge Impulse deployment | Arduino Nano 33 BLE Sense | Maize leaf disease dataset | Accuracy 94.84% | 7.60 ms / 7,648 ms reported | 344.7 KB   | 726.6 KB | 344.7 KB | N/A    | TensorFlow, TensorFlow Lite, Edge Impulse | INT8     | N/A           | Yes           |
