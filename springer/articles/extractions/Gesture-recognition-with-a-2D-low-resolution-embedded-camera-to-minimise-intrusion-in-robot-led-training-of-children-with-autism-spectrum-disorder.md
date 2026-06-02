## Paper ID: Gesture-recognition-with-a-2D-low-resolution-embedded-camera-to-minimise-intrusion-in-robot-led-training-of-children-with-autism-spectrum-disorder

TinyML classification: Near-TinyML — The work is edge/embedded vision on NAO/Jetson TX2, but it does not provide MCU-class deployment evidence.

### Basic Info
- Authors: Giovanni Ercolano; Silvia Rossi; Daniela Conti; Alessandro Di Nuovo
- Year: 2024
- Title: Gesture recognition with a 2D low-resolution embedded camera to minimise intrusion in robot-led training of children with autism spectrum disorder
- Source: Applied Intelligence, 54:6579–6591
- Type: Experimental

### Problem & Context
- Task: Gesture recognition / action classification
- Objective: Automatically recognize children’s imitation gestures using only the NAO robot embedded camera during robot-assisted therapy.
- Application domain: Robot-assisted therapy for children with Autism Spectrum Disorder and Intellectual Disability.
- Scenario: Embedded robotics / edge AI
- TinyML relevance: Partial
- TinyML justification: The paper targets low-resource embedded robotic vision and evaluates Jetson TX2 edge inference, but does not target MCU-class TinyML deployment.

### Model / Method
- Model: OpenPose-based skeleton extraction followed by a two-layer LSTM gesture classifier.
- Architecture family: Hybrid CNN / RNN
- Techniques: 2D pose extraction, skeleton normalization, sliding window inference, LSTM tuning, MobileNet-based OpenPose for reduced computation.
- Framework: OpenPose 1.7.0; Weka for classical ML baselines.
- Training type: From scratch for the LSTM classifier; OpenPose used for feature extraction.
- Inference type: On-device proof-of-concept on embedded edge hardware.

### Hardware
- Device: NAO robot embedded camera; NVIDIA Jetson TX2 for edge-AI inference evaluation.
- Hardware type: GPU / SoC / embedded robot platform
- Processor / microcontroller: NVIDIA Jetson TX2; NAO onboard processor not reported.
- Clock frequency: Not reported
- SRAM / RAM: Not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Average 4.77 W for gesture recognition on Jetson TX2; peak 10.14 W including baseline.
- Energy per inference: Not reported
- Execution without full OS: Not reported
- Fully on-device inference: Yes, for the Jetson TX2 proof-of-concept evaluation.
- Constraints mentioned: Limited onboard CPU and memory, low camera resolution, low frame rate, battery, power consumption, heat, latency, privacy, and avoidance of cloud communication.

### Dataset
- Name: Not reported
- Type: Private clinical dataset
- Dataset size: 207 videos from six children.
- Number of classes: 5
- Input resolution: 320 × 240 pixels at about 10 fps.
- Data modality: Low-resolution 2D RGB video from embedded robot camera.

### Metrics
- Accuracy: Best table result of 95.09 ± 2.48%; conclusion reports average accuracy of 93.01% with timestep 5 and step 1.
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: OpenPose averaged 0.13 ± 0.01 s per frame; LSTM model averaged 0.03 ± 0.00 s per 25-frame sequence on Jetson TX2.
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Average 4.77 W for gesture recognition; peak 10.14 W including baseline.

### Optimization
- Techniques used: MobileNet-based OpenPose to reduce computation, sliding-window processing, step-2 inference to reduce OpenPose computation, LSTM hyperparameter tuning.
- Quantization: Not reported
- Pruning: Not reported
- Knowledge distillation: Not reported
- Compression method: Not reported
- Hardware-specific optimization: Evaluation on NVIDIA Jetson TX2 embedded AI board.
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: Yes
- Runs without full operating system: Not reported
- Fully on-device inference: Yes, for Jetson TX2 proof-of-concept evaluation.
- Communication required during inference: No cloud communication is proposed for inference.
- Candidate for Strict TinyML: No
- Reason: The paper evaluates embedded edge inference on Jetson TX2 and NAO robot sensing, but does not report MCU-class deployment, RTOS/bare-metal execution, TFLite Micro, SRAM, or Flash constraints.

### Benchmarking / Standardization
- Benchmark used: Private clinical dataset collected during robot-assisted therapy.
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes, compared with SVM, Bayesian Network, HMM, Naive Bayes, J48, Random Forest, and Random Tree.
- Comparison with previous works: Yes, discussed related gesture-recognition methods and accuracy levels.
- Reproducibility artifacts available: Dataset available upon reasonable request; code and model not reported.

### Results
- Summary: The proposed OpenPose + LSTM method achieved high gesture-recognition accuracy from low-resolution NAO robot camera videos. The Jetson TX2 evaluation showed feasible embedded edge execution with reported latency and power consumption.

### Limitations
- Low-resolution 320 × 240 video and 10 fps acquisition due to onboard resource limits.
- No depth information from the embedded robot camera.
- Robot movement and arm occlusions sometimes obstructed the child.
- Dataset is private and limited to six children.
- MCU-class memory, energy, model size, and deployment framework details were not reported.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes an embedded-camera-based gesture recognition approach using OpenPose and LSTM models to assess children’s imitation performance during robot-assisted therapy with a low-power Jetson TX2 proof-of-concept evaluation.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Ercolano et al. | 2024 | Gesture recognition / classification | OpenPose + 2-layer LSTM | Pose extraction + sliding-window LSTM | NVIDIA Jetson TX2; NAO embedded camera | Private clinical video dataset | Accuracy 95.09 ± 2.48% | OpenPose 0.13 ± 0.01 s/frame; LSTM 0.03 ± 0.00 s/25-frame sequence | N/A | N/A | N/A | N/A | OpenPose 1.7.0; Weka | N/A | N/A | No |
