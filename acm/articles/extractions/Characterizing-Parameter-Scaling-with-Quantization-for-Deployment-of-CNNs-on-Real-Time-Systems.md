## Paper ID: Characterizing-Parameter-Scaling-with-Quantization-for-Deployment-of-CNNs-on-Real-Time-Systems

TinyML classification: Near-TinyML — The paper targets embedded/edge platforms such as Raspberry Pi 4, Jetson AGX Xavier, and Xilinx ZCU104, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Calvin B. Gealy; Alan D. George
* Year: 2024
* Title: Characterizing Parameter Scaling with Quantization for Deployment of CNNs on Real-Time Systems
* Source: ACM Transactions on Embedded Computing Systems, Vol. 23, No. 3, Article 38
* Type: Benchmark

### Problem & Context

* Task: Classification
* Objective: Compare uniform scaling and NeuralScale with quantization for CNN deployment on real-time embedded systems, analyzing inference latency, memory utilization, power, accuracy, and training tradeoffs.
* Application domain: Real-time computer vision on embedded systems
* Scenario: Embedded CPU, embedded GPU, and FPGA-based edge systems
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained embedded/edge deployment with latency, memory, power, and quantization analysis, but uses Raspberry Pi 4, Jetson AGX Xavier, and Xilinx ZCU104 rather than MCU-class TinyML hardware.

### Model / Method

* Model: VGG-11, MobileNetV2, ResNet-50
* Architecture family: CNN
* Techniques: Uniform scaling, NeuralScale, post-training quantization, parameter scaling, NAS-based scaling
* Framework: PyTorch, ONNX Runtime, NVIDIA TensorRT, Vitis AI, Xilinx DPU
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: Raspberry Pi 4; NVIDIA Jetson AGX Xavier; Xilinx ZCU104 FPGA SoC
* Hardware type: CPU / GPU / FPGA / SoC
* Processor / microcontroller: ARM Cortex-A72 CPU; NVIDIA Jetson AGX Xavier GPU; Xilinx Zynq UltraScale+ MPSoC with ARM Cortex-A53 CPU and FPGA fabric
* Clock frequency: Raspberry Pi 4 CPU 1.5 GHz; Jetson AGX Xavier CPU 2,100 MHz, GPU 900 MHz, memory 1,600 MHz; ZCU104 clock frequency not reported
* SRAM / RAM: Raspberry Pi 4 has 4.0 GB RAM; Jetson AGX Xavier has 16 GB shared memory; ZCU104 SRAM/RAM not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Raspberry Pi idle power 3.1 W; Jetson AGX Xavier idle power 8.1 W; Xilinx ZCU104 idle power 16.6 W; dynamic and peak load power measured externally
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Latency, runtime memory, power, throughput per watt, parameter count, FLOPs, real-time 60 FPS constraint

### Dataset

* Name: CIFAR-10; tinyImageNet
* Type: Public
* Dataset size: CIFAR-10 has 10,000 test images and uses 50,000 training images for calibration in one experiment; tinyImageNet size not reported
* Number of classes: CIFAR-10 has 10 classes; tinyImageNet has 200 classes
* Input resolution: CIFAR-10 32 × 32 RGB images; tinyImageNet 64 × 64 RGB images
* Data modality: RGB image

### Metrics

* Accuracy: Reported for all evaluated models, scaling ratios, datasets, and quantization settings
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Reported on ARM Cortex-A72, Jetson AGX Xavier, and Xilinx ZCU104; real-time threshold defined as 16.67 ms for 60 FPS
* FPS: 60 FPS target used as real-time constraint
* Throughput: Throughput per watt reported
* Model size: Not reported
* Parameters: Reported and analyzed across scaling ratios
* MACs / FLOPs: FLOPs reported and analyzed; MACs measured and multiplied by two to estimate FLOPs
* RAM usage: Runtime memory usage reported for CPU and GPU platforms
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Dynamic power and throughput per watt reported

### Optimization

* Techniques used: Uniform parameter scaling, NeuralScale NAS-based scaling, post-training INT8 quantization
* Quantization: INT8 / PTQ / mixed float32-int8
* Pruning: No
* Knowledge distillation: No
* Compression method: Parameter scaling and quantization
* Hardware-specific optimization: ONNX Runtime for ARM CPU, TensorRT for NVIDIA GPU, Vitis AI and Xilinx DPU for FPGA
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Yes
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper reports embedded CPU/GPU/FPGA deployment results but does not target MCU-class hardware, bare-metal/RTOS execution, TensorFlow Lite Micro, or kilobyte-scale SRAM/Flash constraints.

### Benchmarking / Standardization

* Benchmark used: CIFAR-10; tinyImageNet
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: CIFAR-10; tinyImageNet
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Code repositories and tools are referenced, but paper-specific artifacts are not reported

### Results

* Summary: Quantization was found to be the best first optimization step, reducing CPU latency by 3.1× and GPU latency by 2.7× over original float32 models. Uniform scaling generally improved latency, memory, and power efficiency more consistently than NeuralScale, while NeuralScale sometimes improved accuracy but often increased FLOPs and latency.

### Limitations

* Hyperparameters were not exhaustively optimized for each model and dataset.
* NeuralScale showed sensitivity to hyperparameter selection and sometimes failed to outperform uniform scaling.
* Some quantization tools struggled with NeuralScale ResNet-50 models, indicating that QAT may be needed for improved accuracy.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a comparative benchmarking study of CNN parameter scaling and quantization methods for real-time embedded deployment across CPU, GPU, and FPGA platforms.

| Paper        | Year | Task           | Model                          | Technique                        | Device                                           | Dataset                | Main Metric | Latency                             | Model Size | SRAM/RAM                                                                         | Flash | Energy | Framework                                             | INT8/QAT           | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | -------------- | ------------------------------ | -------------------------------- | ------------------------------------------------ | ---------------------- | ----------- | ----------------------------------- | ---------- | -------------------------------------------------------------------------------- | ----- | ------ | ----------------------------------------------------- | ------------------ | ------------- | ------------- |
| Gealy et al. | 2024 | Classification | VGG-11; MobileNetV2; ResNet-50 | Parameter scaling + quantization | Raspberry Pi 4; Jetson AGX Xavier; Xilinx ZCU104 | CIFAR-10; tinyImageNet | Accuracy    | Reported; 16.67 ms real-time target | N/A        | Runtime memory reported; Raspberry Pi 4 4 GB RAM; Jetson AGX Xavier 16 GB memory | N/A   | N/A    | PyTorch; ONNX Runtime; TensorRT; Vitis AI; Xilinx DPU | INT8 / PTQ / Mixed | None          | No            |
