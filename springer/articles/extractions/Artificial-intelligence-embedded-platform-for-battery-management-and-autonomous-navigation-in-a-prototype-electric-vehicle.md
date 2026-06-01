## Paper ID: Artificial-intelligence-embedded-platform-for-battery-management-and-autonomous-navigation-in-a-prototype-electric-vehicle

TinyML classification: Near-TinyML — the vision inference is deployed on Raspberry Pi rather than an explicitly MCU-class TinyML platform.

### Basic Info

* Authors: Kiran Keshyagol; Sandeep Kulkarni
* Year: 2025
* Title: Artificial intelligence embedded platform for battery management and autonomous navigation in a prototype electric vehicle
* Source: Discover Sustainability, 6:1474
* Type: Experimental

### Problem & Context

* Task: Object detection, traffic-sign classification, lane detection
* Objective: Integrate a microcontroller-based battery management system with embedded vision-based perception and actuation for a prototype autonomous electric vehicle.
* Application domain: Autonomous electric vehicles
* Scenario: Embedded, edge, autonomous system
* TinyML relevance: Partial
* TinyML justification: The system uses embedded hardware and on-device perception on Raspberry Pi, but the vision inference is not reported on MCU-class hardware or TensorFlow Lite Micro.

### Model / Method

* Model: Lightweight CNN with Haar cascade proposals; classical lane detection pipeline
* Architecture family: Hybrid CNN
* Techniques: CNN-Haar hybrid detection/classification, Canny edge detection, Hough transform, RLS-based SoC estimation, passive cell balancing
* Framework: OpenCV; CNN framework not reported
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: Raspberry Pi 4 Model B, ATmega328P, ESP32 gateway, 5 MP Raspberry Pi camera, IR proximity sensors
* Hardware type: CPU / MCU / SoC / Other
* Processor / microcontroller: Raspberry Pi 4 Model B; ATmega328P; ESP32
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Power profile peaks near 13 W; Raspberry Pi design load approximately 3 A at 5 V
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Latency, cost, power supply stability, battery safety, thermal limits, real-time perception, embedded deployment

### Dataset

* Name: Not reported
* Type: Public + private
* Dataset size: Base dataset of approximately 800 images; augmented to approximately 2400 samples
* Number of classes: 4
* Input resolution: 128×128 RGB
* Data modality: RGB image / live camera frames

### Metrics

* Accuracy: Object-detection/classification accuracy approximately 95%; lane detection accuracy 92.3% in daytime and 85.6% in low-light conditions
* mAP: Not reported
* Precision: Speed breaker 1.0; Stop sign 1.0; Traffic light 1.0; Zebra crossing 0.833
* Recall: Speed breaker 1.0; Stop sign 1.0; Traffic light 0.8; Zebra crossing 1.0
* F1-score: Speed breaker 1.0; Stop sign 1.0; Traffic light 0.888; Zebra crossing 0.909
* Latency: Typical end-to-end inference latency 40–60 ms; mean latency below 80 ms/frame
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Power profile peaks near 13 W

### Optimization

* Techniques used: Lightweight CNN-Haar hybrid pipeline for real-time embedded perception
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: Real-time pipeline designed for Raspberry Pi execution
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 40–60 ms typical; below 80 ms/frame on Raspberry Pi
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: No
* Reason: The perception model runs on Raspberry Pi rather than explicitly on MCU-class hardware, and no MCU-level memory, flash, or energy constraints are reported.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Ablated comparison with CNN module disabled
* Comparison with previous works: Not reported
* Reproducibility artifacts available: Not reported

### Results

* Summary: The integrated prototype achieved SoC estimation error below ±2%, reduced cell-voltage dispersion to within 0.05 V, achieved approximately 95% CNN-based traffic-sign classification accuracy, and maintained typical perception latency of 40–60 ms on Raspberry Pi.

### Limitations

* The perception module was evaluated on a small dataset with limited lighting and occlusion variation.
* Passive balancing introduces energy losses and may not scale well to large EV battery packs.
* Braking logic was tested only under controlled low-speed indoor conditions.
* The indoor test environment does not represent real outdoor driving variability.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: No
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an embedded AI-driven autonomous electric vehicle prototype that integrates a microcontroller-based battery management system with Raspberry Pi-based CNN-Haar perception and closed-loop actuation.

| Paper            | Year | Task                                                            | Model                       | Technique                                         | Device                                      | Dataset                                                                   | Main Metric                  | Latency                        | Model Size | SRAM/RAM | Flash | Energy | Framework                 | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---- | --------------------------------------------------------------- | --------------------------- | ------------------------------------------------- | ------------------------------------------- | ------------------------------------------------------------------------- | ---------------------------- | ------------------------------ | ---------- | -------- | ----- | ------ | ------------------------- | -------- | ------------- | ------------- |
| Keshyagol et al. | 2025 | Object detection / traffic-sign classification / lane detection | Lightweight CNN-Haar hybrid | Lightweight embedded CNN-Haar perception pipeline | Raspberry Pi 4 Model B + ATmega328P + ESP32 | Custom/public road-sign images, 800 base images augmented to 2400 samples | ~95% classification accuracy | 40–60 ms typical; <80 ms/frame | N/A        | N/A      | N/A   | N/A    | OpenCV; CNN framework N/A | N/A      | None          | No            |
