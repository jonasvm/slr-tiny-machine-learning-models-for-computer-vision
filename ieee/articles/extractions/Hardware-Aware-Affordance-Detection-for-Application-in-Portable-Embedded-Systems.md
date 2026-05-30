## Paper ID: Hardware-Aware-Affordance-Detection-for-Application-in-Portable-Embedded-Systems

TinyML classification: Near-TinyML — evaluated on Jetson TX2, Jetson Nano, and smartphones, with no successful MCU-class deployment reported.

### Basic Info

* Authors: Edoardo Ragusa; Christian Gianoglio; Strahinja Dosen; Paolo Gastaldo
* Year: 2021
* Title: Hardware-Aware Affordance Detection for Application in Portable Embedded Systems
* Source: IEEE Access
* Type: Experimental

### Problem & Context

* Task: Segmentation
* Objective: Develop and deploy hardware-aware affordance detection models for portable embedded systems with limited computational resources.
* Application domain: Smart prosthetic limbs and resource-constrained robotic systems
* Scenario: Edge, embedded, wearable, portable
* TinyML relevance: Partial
* TinyML justification: The paper targets embedded and portable on-device inference with memory, latency, power, and model-size constraints, but deployment is performed on Jetson devices and smartphones rather than MCU-class hardware.

### Model / Method

* Model: V1_Se, V1_U, and V3_LR
* Architecture family: CNN
* Techniques: Hardware-aware CNN design, MobileNet backbones, depthwise convolutions, image segmentation meta-architectures, FP16 deployment, INT8 post-training quantization, TensorRT optimization, TensorFlow Lite deployment
* Framework: Keras, TensorFlow, TensorRT, TensorFlow Lite
* Training type: Fine-tuning
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson TX2, NVIDIA Jetson Nano, Honor 10, Samsung Galaxy S8, Samsung Galaxy A40
* Hardware type: SoC / GPU / Mobile
* Processor / microcontroller: Jetson TX2 uses dual-core NVIDIA Denver2, quad-core ARM Cortex-A57, and 256-core Pascal GPU; Jetson Nano uses quad-core ARM A57 and 128-core Maxwell GPU; smartphone processors not reported
* Clock frequency: Jetson TX2 GPU modes from 0.85 GHz to 1.30 GHz; Jetson Nano CPU/GPU configurations include 1.5 GHz / 0.92 GHz and 0.9 GHz / 0.64 GHz
* SRAM / RAM: Jetson TX2 has 8 GB LPDDR4; Jetson Nano has 4 GB RAM; smartphones not reported
* Flash / ROM / Storage: Not reported
* Power consumption: Jetson TX2 SOM ranges from 5 W to 11 W; Jetson Nano reports 5.2 W in Max-N mode and 3.6 W in 5W mode; smartphone power consumption reported in the order of mWatts
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, latency, computational cost, model parameters, FLOPs, size, battery lifetime, heating, communication dependence

### Dataset

* Name: UMD Dataset; ADE20K; IIT dataset
* Type: Public
* Dataset size: UMD contains around 30,000 images
* Number of classes: UMD has 7 affordance classes; prosthetics setup uses 3 classes
* Input resolution: 224 × 224 × 3 for MobileNetV3 LR-ASPP model
* Data modality: RGB image

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 21 ms for V3_LR on Jetson TX2 configuration 0; 68 ms and 104 ms for V3_LR on Jetson Nano; 225 ms, 278 ms, and 285 ms on smartphones
* FPS: 48 FPS for V3_LR on Jetson TX2; 10 FPS for Jetson Nano 5W configuration; up to 3 FPS on smartphones
* Throughput: Not reported
* Model size: V3_LR has 238 KB with INT8, 421 KB with FP16, and 954 KB with FP32
* Parameters: V1_Se has 5,344,840 parameters; V1_U has 6,318,984 parameters; V3_LR has 195,768 parameters
* MACs / FLOPs: V1_Se has 7,584,227,590 FLOPs; V1_U has 10,358,759,686 FLOPs; V3_LR has 642,135,722 FLOPs
* RAM usage: Jetson Nano reports 1782 MB in Max-N mode and 1870 MB in 5W mode
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Jetson TX2 SOM ranges from 5 W to 11 W; Jetson Nano reports 5.2 W and 3.6 W

### Optimization

* Techniques used: Hardware-aware CNN architecture selection, MobileNet backbones, TensorRT optimization, TensorFlow Lite deployment, FP16 deployment, INT8 post-training quantization
* Quantization: INT8 / FP16 / FP32
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Compact MobileNet-based segmentation architectures and post-training quantization
* Hardware-specific optimization: TensorRT optimization for Jetson devices and TensorFlow Lite deployment for smartphones
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 238 KB INT8, 421 KB FP16, and 954 KB FP32 for V3_LR
* Energy per inference reported: Not reported
* Latency on target device reported: 21 ms on Jetson TX2, 68 ms and 104 ms on Jetson Nano, and 225–285 ms on smartphones
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: No
* Reason: The paper deploys on Linux-based Jetson devices and Android smartphones, while STM32 and GAP-8 deployment is only discussed as future work and was not successfully demonstrated.

### Benchmarking / Standardization

* Benchmark used: UMD affordance detection dataset
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: ADE20K for pre-training
* Comparison with baseline models: AffordanceNet, EfficientNet-B0 + UNet, BiSeNet, VGG + SegNet, VGG + UNet
* Comparison with previous works: Yes
* Reproducibility artifacts available: Code

### Results

* Summary: The proposed MobileNet-based hardware-aware segmentation models achieved competitive affordance detection results with substantially fewer parameters than AffordanceNet. V3_LR achieved the smallest model size and fastest inference, while V1_U showed strong performance in the simplified prosthetics setup.

### Limitations

* The hardware-aware models perform worse than AffordanceNet for fine-grained affordance classes with underrepresented categories.
* Dark illumination with black background was the most challenging realistic condition.
* Deployment on STM32 and GAP-8 was not successfully achieved due to unsupported operations and excessive computational cost.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a hardware-aware affordance detection framework using compact MobileNet-based segmentation models deployed and evaluated on portable embedded edge devices for real-time prosthetic and robotic applications.

| Paper         | Year | Task         | Model                                                     | Technique                                         | Device                               | Dataset | Main Metric                                             | Latency                       | Model Size                              | SRAM/RAM                    | Flash | Energy | Framework                                   | INT8/QAT          | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---: | ------------ | --------------------------------------------------------- | ------------------------------------------------- | ------------------------------------ | ------- | ------------------------------------------------------- | ----------------------------- | --------------------------------------- | --------------------------- | ----- | ------ | ------------------------------------------- | ----------------- | ------------- | ------------- |
| Ragusa et al. | 2021 | Segmentation | MobileNetV1+SegNet; MobileNetV1+UNet; MobileNetV3+LR-ASPP | Hardware-aware CNN + TensorRT/TFLite quantization | Jetson TX2; Jetson Nano; smartphones | UMD     | F^Wβ = 0.90 grasp for V1_U in 3-class prosthetics setup | 21 ms on Jetson TX2 for V3_LR | 238 KB INT8 / 421 KB FP16 / 954 KB FP32 | 1782–1870 MB on Jetson Nano | N/A   | N/A    | TensorFlow/Keras; TensorRT; TensorFlow Lite | INT8/PTQ and FP16 | None          | No            |
