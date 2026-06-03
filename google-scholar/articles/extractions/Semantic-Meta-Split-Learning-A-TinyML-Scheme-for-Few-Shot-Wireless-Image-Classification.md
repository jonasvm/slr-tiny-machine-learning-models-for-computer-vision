## Paper ID: Semantic-Meta-Split-Learning-A-TinyML-Scheme-for-Few-Shot-Wireless-Image-Classification

TinyML classification: Near-TinyML — it is relevant to TinyML/Edge AI vision but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Eslam Eldeeb, Mohammad Shehab, Hirley Alves, Mohamed-Slim Alouini
* Year: 2025
* Title: Semantic Meta-Split Learning: A TinyML Scheme for Few-Shot Wireless Image Classification
* Source: IEEE Transactions on Machine Learning in Communications and Networking
* Type: Methodological

### Problem & Context

* Task: Classification
* Objective: Perform few-shot wireless image classification with reduced device-side computation, lower energy consumption, privacy preservation, and reduced data requirements.
* Application domain: Semantic and goal-oriented wireless communication
* Scenario: Edge / embedded wireless devices with aggregator-side processing
* TinyML relevance: Partial
* TinyML justification: The paper proposes a TinyML-oriented low-computation and energy-efficient framework for constrained end users, but does not report MCU-class deployment.

### Model / Method

* Model: Semantic-MSL
* Architecture family: CNN
* Techniques: Split learning, meta-learning, MAML, semantic communication, conformal prediction, cut-layer analysis
* Framework: PyTorch; ECO2AI for energy estimation
* Training type: Few-shot meta-learning
* Inference type: Hybrid

### Hardware

* Device: End-user wireless devices and aggregator; experiments implemented on a single NVIDIA Tesla V100 GPU
* Hardware type: GPU for experiments; target device hardware not specified
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: No
* Constraints mentioned: Computation, energy, communication overhead, privacy, data availability, wireless channel quality, latency, parameter count

### Dataset

* Name: Omniglot
* Type: Not reported
* Dataset size: 1623 classes from 50 languages, with 20 handwritten images per class
* Number of classes: 1623 total; 10 classes per task in experiments
* Input resolution: Not reported
* Data modality: Handwritten letter images

### Metrics

* Accuracy: Semantic-MSL reaches 95% accuracy after 20 SGD steps; more than 91% accuracy with 5 shots
* mAP: N/A
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Baseline 889.54 ms; 3-Conv 770.54 ms; 2-Conv 479.25 ms; 1-Conv 287.64 ms
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Device-side parameters are 74,496 for 3-Conv, 37,568 for 2-Conv, and 640 for 1-Conv
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Split learning, meta-learning, cut-layer placement, semantic message transmission, conformal prediction
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Semantic message transmission through split learning
* Hardware-specific optimization: Cut-layer placement to reduce device-side computation and parameters
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Device-side inference time reported, but target device hardware is not specified
* Runs without full operating system: Not reported
* Fully on-device inference: No
* Communication required during inference: Yes
* Candidate for Strict TinyML: No
* Reason: The paper does not report MCU-class deployment, SRAM/Flash usage, TensorFlow Lite Micro, CMSIS-NN, or fully on-device inference.

### Benchmarking / Standardization

* Benchmark used: Omniglot
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Omniglot
* Comparison with baseline models: Semantic-SL and baseline DNN
* Comparison with previous works: Not reported
* Reproducibility artifacts available: Not reported

### Results

* Summary: Semantic-MSL outperforms Semantic-SL and baseline DNN in classification accuracy, convergence speed, conformal prediction coverage, and energy consumption. Moving the cut layer closer to the device reduces device-side computation energy and inference time but increases communication overhead.

### Limitations

* Moving the cut layer closer to the device side increases communication overhead and may introduce privacy risks.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: No
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a Semantic Meta-Split Learning framework that combines split learning and meta-learning for energy-efficient few-shot wireless image classification.

| Paper         | Year | Task           | Model        | Technique                      | Device       | Dataset  | Main Metric  | Latency   | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | -------------- | ------------ | ------------------------------ | ------------ | -------- | ------------ | --------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Eldeeb et al. | 2025 | Classification | Semantic-MSL | Split learning + meta-learning | Not reported | Omniglot | 95% accuracy | 287.64 ms | N/A        | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
