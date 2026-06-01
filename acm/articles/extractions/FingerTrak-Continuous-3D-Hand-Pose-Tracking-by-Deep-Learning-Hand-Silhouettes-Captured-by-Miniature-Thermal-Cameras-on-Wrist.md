## Paper ID: FingerTrak-Continuous-3D-Hand-Pose-Tracking-by-Deep-Learning-Hand-Silhouettes-Captured-by-Miniature-Thermal-Cameras-on-Wrist

TinyML classification: Near-TinyML — relevant wearable/edge vision system, but no clear evidence of MCU-class inference or microcontroller-level deployment.

### Basic Info

* Authors: Fang Hu, Peng He, Songlin Xu, Yin Li, Cheng Zhang
* Year: 2020
* Title: FingerTrak: Continuous 3D Hand Pose Tracking by Deep Learning Hand Silhouettes Captured by Miniature Thermal Cameras on Wrist
* Source: Proceedings of the ACM on Interactive, Mobile, Wearable and Ubiquitous Technologies, Vol. 4, No. 2, Article 71
* Type: Experimental

### Problem & Context

* Task: 3D hand pose estimation / hand pose tracking
* Objective: Estimate continuous 3D finger joint positions from hand silhouettes captured by wrist-mounted miniature thermal cameras.
* Application domain: Wearable interaction, human-computer interaction, VR/AR, robotic control, daily activity recognition
* Scenario: Wearable / mobile / edge-like sensing prototype
* TinyML relevance: Partial
* TinyML justification: The paper targets a wearable low-power sensing system using miniature thermal cameras, but inference is performed through Raspberry Pi/laptop/workstation infrastructure rather than explicit MCU-class deployment.

### Model / Method

* Model: Multi-view CNN with a ResNet-34-style backbone and regression network
* Architecture family: CNN
* Techniques: Multi-view feature fusion, hand silhouette-based pose estimation, synthetic data generation, camera-position design search
* Framework: Not reported
* Training type: From scratch
* Inference type: Offloaded / hybrid

### Hardware

* Device: Wristband with four MLX90640 thermal cameras, four Raspberry Pi 3B+ boards, Wi-Fi router, ThinkPad X1 laptop
* Hardware type: CPU / SoC / Other
* Processor / microcontroller: Raspberry Pi 3B+ and Intel Hexa-Core i7-8750H CPU laptop
* Clock frequency: Not reported
* SRAM / RAM: Not reported
* Flash / ROM / Storage: Not reported
* Power consumption: On-band camera section below 0.44 W; each camera current below 23 mA; Raspberry Pi 3B+ idle at 435 mA with Wi-Fi and 610 mA under CPU stress; expected Raspberry Pi power below 3.1 W
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: No
* Constraints mentioned: Wearable form factor, camera size, power consumption, camera resolution, frame synchronization, communication, camera-position shifts, background robustness

### Dataset

* Name: Synthetic MANO-based hand silhouette dataset and private FingerTrak user-study dataset
* Type: Synthetic / private
* Dataset size: Synthetic dataset uses 600,000 training images and 10,000 test images per camera setting; real user study includes 132K samples from 11 participants
* Number of classes: Not applicable
* Input resolution: 32 × 24 per thermal image
* Data modality: Multi-view low-resolution thermal images / hand silhouettes

### Metrics

* Accuracy: RGB pilot study for 12 micro-finger pose classification reports 92.62% average accuracy
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: 16 Hz frame rate
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: On-band camera section below 0.44 W; Raspberry Pi expected below 3.1 W

### Optimization

* Techniques used: Multi-view feature fusion, synthetic data generation, camera configuration search
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: Camera placement and wearable hardware prototype design
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
* Fully on-device inference: No
* Communication required during inference: Yes
* Candidate for Strict TinyML: No
* Reason: The prototype uses Raspberry Pi boards, Wi-Fi transmission, and laptop/workstation inference, with no reported MCU-class deployment, memory footprint, model size, or energy-per-inference evidence.

### Benchmarking / Standardization

* Benchmark used: Private user study and synthetic MANO-based data
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Comparison with prior hand pose estimation systems and sensing modalities
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: FingerTrak achieved 1.20 cm joint-position MAE and 6.46° angular MAE under the same background, and 2.09 cm / 8.06° under a different background. After re-mounting, it achieved 2.72 cm / 9.44°, and with objects in hand it achieved 2.68 cm / 10.37°.

### Limitations

* User-independent models perform substantially worse than user-dependent models.
* The system requires user-specific training data in its current form.
* Leap Motion ground truth is limited for complex hand poses and object-holding scenarios.
* Low-resolution thermal cameras may fail to capture subtle finger-pose differences.
* Backgrounds with similar or higher temperature than the human body may reduce robustness.
* Camera-position shifts after re-mounting increase estimation error.
* Object-holding evaluation is preliminary and uses only four objects in an indoor setting.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: No
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a wrist-mounted thermal-camera system and multi-view CNN for continuous 3D hand pose estimation from hand silhouettes.

| Paper     | Year | Task                    | Model                                        | Technique                                                          | Device                                                                            | Dataset                                       | Main Metric                           | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | ----------------------- | -------------------------------------------- | ------------------------------------------------------------------ | --------------------------------------------------------------------------------- | --------------------------------------------- | ------------------------------------- | ------- | ---------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Hu et al. | 2020 | 3D hand pose estimation | Multi-view CNN with ResNet-34-style backbone | Multi-view silhouette fusion / synthetic data-guided camera design | Wristband with 4 MLX90640 thermal cameras, 4 Raspberry Pi 3B+, ThinkPad X1 laptop | Synthetic MANO data + private user-study data | 1.20 cm joint MAE / 6.46° angular MAE | N/A     | N/A        | N/A      | N/A   | N/A    | N/A       | N/A      | None          | No            |
