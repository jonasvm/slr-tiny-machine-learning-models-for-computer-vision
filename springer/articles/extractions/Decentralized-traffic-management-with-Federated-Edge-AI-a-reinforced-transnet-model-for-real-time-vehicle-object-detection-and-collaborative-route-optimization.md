## Paper ID: Decentralized-traffic-management-with-Federated-Edge-AI-a-reinforced-transnet-model-for-real-time-vehicle-object-detection-and-collaborative-route-optimization

TinyML classification: Near-TinyML — The work is relevant to edge computer vision, but it does not provide explicit evidence of MCU-class deployment or microcontroller-level memory/energy constraints.

### Basic Info

* Authors: C. E. Mohankumar; A. Manikandan
* Year: 2025
* Title: Decentralized traffic management with Federated Edge AI: a reinforced transnet model for real-time vehicle object detection and collaborative route optimization
* Source: Discover Applied Sciences, 7:729
* Type: Experimental

### Problem & Context

* Task: Object detection and traffic route optimization
* Objective: To perform real-time vehicle detection, optimize traffic routes, reduce congestion, and preserve data privacy using decentralized Federated Edge AI.
* Application domain: Intelligent traffic management / smart cities
* Scenario: Edge AI, IoT, decentralized traffic monitoring
* TinyML relevance: Partial
* TinyML justification: The paper targets Edge AI and local processing on edge devices, but does not report MCU-class deployment, microcontroller hardware, or strict memory/energy constraints.

### Model / Method

* Model: DST-FedRL
* Architecture family: Transformer / Hybrid
* Techniques: Federated learning, Deep Spatial-Temporal Transformer Network, reinforcement learning, FedAvg aggregation, edge-local data processing
* Framework: Python-based tools, TensorFlow, reinforcement learning libraries
* Training type: Not reported
* Inference type: On-device edge processing / collaborative edge inference

### Hardware

* Device: Edge devices such as traffic cameras and IoT sensors
* Hardware type: Other
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes, at edge-device level
* Constraints mentioned: Latency, scalability, privacy, communication overhead, computational overhead

### Dataset

* Name: Road Traffic Video Monitoring Dataset
* Type: Public
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: 640 × 480 pixels
* Data modality: Traffic video frames

### Metrics

* Accuracy: 97.8% vehicle detection accuracy; 97.0% in comparative evaluation
* mAP: 98.2% mAP@0.5
* Precision: 97.8%
* Recall: 96.5%
* F1-score: 97.1%
* Latency: 2.5 ms/frame
* FPS: 67 FPS
* Throughput: 67 FPS
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Federated learning, FedAvg aggregation, reinforcement learning-based route optimization, edge-local processing
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 2.5 ms/frame
* Runs without full operating system: Not reported
* Fully on-device inference: Yes, at edge-device level
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper targets edge-device traffic processing but does not provide MCU-class deployment evidence, memory footprint, energy per inference, TensorFlow Lite Micro use, or microcontroller-level constraints.

### Benchmarking / Standardization

* Benchmark used: Road Traffic Video Monitoring Dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: YOLO, RCNN, SSD, DQN, DDQN
* Comparison with previous works: FedEdge AI-TC, YOLOv5 + Federated Learning, VINO_EffiFedAV, FedPylot
* Reproducibility artifacts available: Dataset

### Results

* Summary: DST-FedRL achieved 97.8% precision, 96.5% recall, 97.1% F1-score, 98.2% mAP@0.5, 2.5 ms/frame latency, and 67 FPS for vehicle detection. The system also reported 30.0% reduction in average travel time, 27.9% reduction in fuel consumption, 40.9% increase in vehicle speed, and 50.0% reduction in idle time at signals.

### Limitations

* Dependency on consistent edge device infrastructure.
* Latency under high-load scenarios.
* Computational capacity of edge devices may limit scalability and efficiency in resource-constrained environments.
* Real-world deployment was identified as future work.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes DST-FedRL, a decentralized Federated Edge AI framework combining DST-net and reinforcement learning for real-time vehicle detection and collaborative traffic route optimization.

| Paper             | Year | Task             | Model     | Technique                        | Device                                       | Dataset                               | Main Metric   | Latency      | Model Size | SRAM/RAM | Flash | Energy | Framework  | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------------- | ---: | ---------------- | --------- | -------------------------------- | -------------------------------------------- | ------------------------------------- | ------------- | ------------ | ---------- | -------- | ----- | ------ | ---------- | -------- | ------------- | ------------- |
| Mohankumar et al. | 2025 | Object detection | DST-FedRL | Federated Edge AI + DST-net + RL | Edge devices / traffic cameras / IoT sensors | Road Traffic Video Monitoring Dataset | mAP@0.5 98.2% | 2.5 ms/frame | N/A        | N/A      | N/A   | N/A    | TensorFlow | N/A      | None          | No            |
