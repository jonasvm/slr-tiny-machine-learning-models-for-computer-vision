## Paper ID: An-integrated-tiny-YOLO-v3-and-Q-iteration-framework-for-stable-energy-efficient-autonomous-navigation-of-quadruped-robots-on-AMB82-mini-microcontrollers

TinyML classification: Strict TinyML — The paper explicitly reports MCU-class deployment on AMB82-Mini and Teensy 4.0 microcontrollers with TFLite Micro, INT8 quantization, constrained memory, latency, and low-power embedded operation.

### Basic Info

* Authors: Falah Hasan Salih; Amir Hooshang Mazinan; Seyed Mahmoud Modaresi
* Year: 2026
* Title: An integrated tiny-YOLO v3 and Q-iteration framework for stable, energy-efficient autonomous navigation of quadruped robots on AMB82-mini microcontrollers
* Source: Scientific Reports, 16:1021
* Type: Experimental

### Problem & Context

* Task: Object detection, pose estimation, autonomous navigation, obstacle avoidance
* Objective: Deploy an integrated Tiny-YOLOv3 perception and Q-iteration control framework for stable, energy-efficient autonomous quadruped navigation on low-power microcontrollers.
* Application domain: Autonomous quadruped robotics
* Scenario: Embedded microcontroller-based autonomous system
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets ultra-low-power microcontrollers, on-device inference, INT8 quantization, TensorFlow Lite Micro deployment, and memory-constrained embedded operation.

### Model / Method

* Model: Tiny-YOLOv3 for visual perception and Q-iteration for adaptive locomotion control
* Architecture family: CNN + Other
* Techniques: INT8 quantization, lightweight object detection, TensorFlow Lite Micro deployment, static tensor arena, optimized C/C++ implementation, compact UART communication
* Framework: TensorFlow Lite Micro; Arduino IDE with C/C++; Amoeba IoT conversion platform
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: AMB82-Mini microcontroller for perception; Teensy 4.0 microcontroller for control; custom TMUBot quadruped robot
* Hardware type: MCU
* Processor / microcontroller: AMB82-Mini with ARM Cortex-M processor; Teensy 4.0 with ARM Cortex-M7
* Clock frequency: Teensy 4.0 reported as 480 MHz, equivalent to 600 MHz; AMB82-Mini clock not reported
* SRAM / RAM: 512 KB SRAM and 2 MB PSRAM on AMB82-Mini
* Flash / ROM / Storage: MicroSD card for data logging; Flash/ROM not reported
* Power consumption: 20.66 W on flat terrain and 23.15 W on 20° incline
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, latency, compute, real-time inference, communication overhead

### Dataset

* Name: Custom dataset for the quadruped robot operational environment
* Type: Private
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: Not reported
* Data modality: RGB image from onboard camera; LiDAR explored in simulation

### Metrics

* Accuracy: 100% static object detection accuracy; 83% average accuracy during locomotion
* mAP: 0.8554
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 128.32 ms per frame for object detection; approximately 1.66 ms communication latency
* FPS: Approximately 7.8 FPS
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Designed to fit within 512 KB SRAM and 2 MB PSRAM; peak RAM usage not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 20.66 W on flat terrain and 23.15 W on 20° incline

### Optimization

* Techniques used: INT8 quantization, lightweight Tiny-YOLOv3 architecture, TensorFlow Lite Micro graph optimization, static tensor arena, optimized C/C++ code, compact binary UART protocol
* Quantization: INT8
* Pruning: No
* Knowledge distillation: No
* Compression method: INT8 quantization
* Hardware-specific optimization: TensorFlow Lite Micro conversion for AMB82-Mini, integer arithmetic optimization, static memory allocation, optimized embedded C/C++ implementation
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Yes
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: 128.32 ms per frame on AMB82-Mini
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Local UART communication between AMB82-Mini and Teensy 4.0; no cloud or external high-performance computing reported
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly deploys INT8 Tiny-YOLOv3 using TensorFlow Lite Micro on MCU-class AMB82-Mini hardware with reported SRAM/PSRAM constraints and on-device latency.

### Benchmarking / Standardization

* Benchmark used: Custom robot experiments and simulation scenarios
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Q-iteration compared with PPO and SAC
* Comparison with previous works: Yes
* Reproducibility artifacts available: code / dataset

### Results

* Summary: The system achieved 0.8554 mAP with 128.32 ms inference latency, approximately 7.8 FPS, and real-time on-device perception on AMB82-Mini. The robot demonstrated obstacle avoidance, stable navigation on slopes up to 35°, and reported power consumption of 20.66 W to 23.15 W.

### Limitations

* Tiny-YOLOv3 may have lower absolute detection accuracy than larger models on high-end hardware.
* Q-iteration may produce less smooth trajectories than more complex DRL algorithms such as PPO and SAC.
* Precise energy-per-inference, peak memory usage, and systematic ZMP logging were not reported.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes an integrated Tiny-YOLOv3 and Q-iteration framework for real-time perception, adaptive control, and energy-efficient autonomous navigation of a quadruped robot on AMB82-Mini and Teensy 4.0 microcontrollers.

| Paper        | Year | Task                                     | Model                     | Technique                           | Device                  | Dataset                          | Main Metric | Latency   | Model Size | SRAM/RAM                 | Flash | Energy | Framework             | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | ---------------------------------------- | ------------------------- | ----------------------------------- | ----------------------- | -------------------------------- | ----------- | --------- | ---------- | ------------------------ | ----- | ------ | --------------------- | -------- | ------------- | ------------- |
| Salih et al. | 2026 | Object detection / autonomous navigation | Tiny-YOLOv3 + Q-iteration | INT8 quantization + TFLM deployment | AMB82-Mini + Teensy 4.0 | Custom robot-environment dataset | mAP 0.8554  | 128.32 ms | N/A        | 512 KB SRAM + 2 MB PSRAM | N/A   | N/A    | TensorFlow Lite Micro | INT8     | TFLM          | Yes           |
