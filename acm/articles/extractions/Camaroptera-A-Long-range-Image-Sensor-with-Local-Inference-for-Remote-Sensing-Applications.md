## Paper ID: Camaroptera-A-Long-range-Image-Sensor-with-Local-Inference-for-Remote-Sensing-Applications

TinyML classification: Strict TinyML — Explicit MSP430FR5994 MCU deployment with 8 kB SRAM, 256 kB FRAM, optimized 20 kB DNN weights, and measured energy/latency constraints.

### Basic Info

* Authors: Harsh Desai, Matteo Nardello, Davide Brunelli, Brandon Lucia
* Year: 2022
* Title: Camaroptera: A Long-range Image Sensor with Local Inference for Remote Sensing Applications
* Source: ACM Transactions on Embedded Computing Systems, Vol. 21, No. 3, Article 32
* Type: Experimental

### Problem & Context

* Task: Visual Wake Words / image classification for person presence detection
* Objective: Reduce costly long-range image transmission by performing local inference on a batteryless image-sensing platform.
* Application domain: Remote visual sensing
* Scenario: Batteryless embedded IoT sensor node with energy harvesting and long-range LoRa communication
* TinyML relevance: Yes
* TinyML justification: The paper deploys local DNN inference on an ultra-low-power MSP430 MCU with explicit memory, energy, latency, and communication constraints.

### Model / Method

* Model: LeNet-derived DNN for person detection combined with image differencing and JPEG compression
* Architecture family: CNN
* Techniques: Input downsampling, fixed-point arithmetic, sparse weight storage, pruning, layer separation, CSR encoding, image differencing, JPEG compression
* Framework: Genesis network minimization tool; deployment framework not reported
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: Camaroptera / CamHW prototype
* Hardware type: MCU
* Processor / microcontroller: Texas Instruments MSP430FR5994
* Clock frequency: 16 MHz
* SRAM / RAM: 8 kB SRAM
* Flash / ROM / Storage: 256 kB embedded non-volatile FRAM
* Power consumption: LoRa transmission reported as the highest-power operation; radio TX power reported as 17 dBm; system-level power consumption not fully reported
* Energy per inference: Around 65 mJ for DNN image classification
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, energy harvesting, latency, compute capability, LoRa communication energy, bandwidth, and recharge time

### Dataset

* Name: Custom Camaroptera image dataset
* Type: Private
* Dataset size: 4,000 images
* Number of classes: 2 for model output; images were labeled as person, no person, or invalid
* Input resolution: 160 × 120 grayscale images downsampled to 30 × 40 before the CNN
* Data modality: Grayscale image

### Metrics

* Accuracy: 78%
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: DNN inference around 12 s; JPEG compression 7 s; transmitted frame latency 36–114 s depending on light level
* FPS: Not reported
* Throughput: Not reported
* Model size: 20 kB weights after optimization; initial weights were 3.6 MB
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Around 80 kB for intermediate activations
* Flash usage: Not reported
* Energy per inference: Around 65 mJ
* Power consumption: Radio transmission reported as highest-power operation; exact full-system power not reported

### Optimization

* Techniques used: 4 × 4 average pooling, Genesis network minimization, aggressive near-zero pruning, layer separation, sparse CSR encoding, 16-bit fixed-point arithmetic, fixed-point JPEG, image differencing, JPEG header omission
* Quantization: 16-bit fixed-point arithmetic; INT8 not reported
* Pruning: Yes
* Knowledge distillation: Not reported
* Compression method: Sparse CSR weight representation and JPEG image compression
* Hardware-specific optimization: Fixed-point arithmetic and sparse matrix kernels for MSP430 MCU without native floating-point support
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: 8 kB SRAM available; peak SRAM usage not reported
* Flash usage reported: 256 kB FRAM available; Flash usage not reported
* Model size reported: 20 kB DNN weights after optimization
* Energy per inference reported: Around 65 mJ
* Latency on target device reported: DNN inference around 12 s; JPEG compression 7 s; transmitted frame latency 36–114 s depending on light level
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No; LoRa communication is used after local inference selects images for transmission
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly deploys local DNN inference on a resource-constrained MSP430 MCU with kB-scale memory, batteryless energy harvesting, and measured latency and energy constraints.

### Benchmarking / Standardization

* Benchmark used: Custom hardware evaluation with multi-week experiments
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes; Sense-and-Send and Basic Thresholding operating modes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: Local Inference enabled Camaroptera to send up to 12× more interesting images, transmit up to 6.5× fewer uninteresting images, and capture up to 14.7× more total images than Sense-and-Send. The prototype demonstrates batteryless, long-range visual sensing with local DNN inference on an MCU-class platform.

### Limitations

* DNN inference and JPEG compression are latency-intensive on the MSP430 MCU.
* The device can miss interesting events while processing images or recharging energy for transmission.
* Classifier performance is limited, with 78% accuracy, 40% false positives, and 1% false negatives.
* The best classifier configuration depends on input power and deployment conditions.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes Camaroptera, a batteryless solar energy-harvesting long-range image sensor that performs on-device local DNN inference to reduce LoRa image transmission and improve remote visual sensing availability.

| Paper        | Year | Task                                     | Model             | Technique                                                                                       | Device                        | Dataset                          | Main Metric                                          | Latency                              | Model Size    | SRAM/RAM                      | Flash       | Energy           | Framework       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---: | ---------------------------------------- | ----------------- | ----------------------------------------------------------------------------------------------- | ----------------------------- | -------------------------------- | ---------------------------------------------------- | ------------------------------------ | ------------- | ----------------------------- | ----------- | ---------------- | --------------- | -------- | ------------- | ------------- |
| Desai et al. | 2022 | Visual Wake Words / image classification | LeNet-derived DNN | Fixed-point sparse CNN with pruning, layer separation, image differencing, and JPEG compression | Camaroptera with MSP430FR5994 | Custom Camaroptera image dataset | 78% accuracy; up to 12× more interesting images sent | DNN 12 s; transmitted frame 36–114 s | 20 kB weights | 8 kB SRAM; ~80 kB activations | 256 kB FRAM | ~65 mJ/inference | CamSW / Genesis | N/A      | None          | Yes           |
