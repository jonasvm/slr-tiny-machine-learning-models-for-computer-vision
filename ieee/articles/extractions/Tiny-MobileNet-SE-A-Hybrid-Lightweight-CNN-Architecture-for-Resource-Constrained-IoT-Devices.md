## Paper ID: Tiny-MobileNet-SE-A-Hybrid-Lightweight-CNN-Architecture-for-Resource-Constrained-IoT-Devices

TinyML classification: Strict TinyML — It explicitly reports deployment-related metrics on Arduino Nano 33 BLE Sense with a quantized TensorFlow Lite model and low memory/power constraints.

### Basic Info

* Authors: Jean Pierre Nyakuri; Celestin Nkundineza; Omar Gatera; Kizito Nkurikiyeyzu
* Year: 2025
* Title: Tiny-MobileNet-SE: A Hybrid Lightweight CNN Architecture for Resource-Constrained IoT Devices
* Source: IEEE Access, Volume 13, DOI: 10.1109/ACCESS.2025.3582055
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Develop a lightweight CNN architecture for image classification in resource-constrained environments while maintaining high accuracy and low model size.
* Application domain: Precision agriculture, human face analysis, and domestic animal classification.
* Scenario: Edge, embedded, IoT, mobile, and resource-constrained devices.
* TinyML relevance: Yes
* TinyML justification: The paper targets resource-constrained IoT and embedded deployment and reports quantized TensorFlow Lite model size, latency, memory utilization, and power consumption on Raspberry Pi 5, Raspberry Pi 4, and Arduino Nano 33 BLE Sense.

### Model / Method

* Model: Tiny-MobileNet-SE
* Architecture family: Hybrid CNN
* Techniques: Squeeze-and-Excitation blocks, depthwise separable convolutions, batch normalization, knowledge distillation, post-training quantization.
* Framework: TensorFlow; TensorFlow Lite
* Training type: Knowledge-distillation training using MobileNetV2 as teacher model; exact student initialization not reported.
* Inference type: On-device

### Hardware

* Device: Raspberry Pi 5; Raspberry Pi 4; Arduino Nano 33 BLE Sense
* Hardware type: MCU / CPU / Other
* Processor / microcontroller: Not reported
* Clock frequency: Not reported
* SRAM / RAM: Memory utilization reported as 527 MB on Raspberry Pi 5, 478 MB on Raspberry Pi 4, and 19 KB on Arduino Nano 33 BLE Sense.
* Flash / ROM / Storage: Not reported
* Power consumption: 3.2 W on Raspberry Pi 5, 3.5 W on Raspberry Pi 4, and 1.7 W on Arduino Nano 33 BLE Sense.
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, power, latency, computational cost, model size, number of parameters, and resource-constrained deployment.

### Dataset

* Name: PlantVillage crop disease dataset; PlantVillage crop pest dataset; PlantVillage crop fruits dataset; Kaggle human face emotions dataset; Kaggle human face ages dataset; Kaggle domestic animals dataset.
* Type: Public
* Dataset size: Crop diseases: 3,080 images; crop pests: 7,100 images; crop fruits: 12,000 images; human face emotions: 6,700 images; human face ages: 10,488 images; domestic animals: 27,187 images.
* Number of classes: Crop diseases: 4; crop pests: 5; crop fruits: 12; human face emotions: 4; human face ages: 110; domestic animals: 10.
* Input resolution: 224 × 224 × 3
* Data modality: RGB image

### Metrics

* Accuracy: Crop pest: 98.0%; crop disease: 98.6%; crop fruits: 98.6%; human face emotions: 90.1%; human face ages: 90.1%; domestic animals: 90.6%.
* mAP: Not reported
* Precision: Not reported
* Recall: Crop pest: 97.8%; crop disease: 98.0%; crop fruits: 97.5%; human face emotions: 90.0%; human face ages: 89.0%; domestic animals: 89.0%.
* F1-score: Crop pest: 97.5%; crop disease: 98.2%; crop fruits: 97.0%; human face emotions: 90.0%; human face ages: 89.3%; domestic animals: 89.5%.
* Latency: 80 ms on Raspberry Pi 5; 112 ms on Raspberry Pi 4; 750 ms on Arduino Nano 33 BLE Sense.
* FPS: Not reported
* Throughput: Not reported
* Model size: 0.72 MB; 260 KB in TensorFlow Lite format; text also states 26 MB after quantization.
* Parameters: 0.48 million / 482 K
* MACs / FLOPs: 240 million FLOPs
* RAM usage: 527 MB on Raspberry Pi 5; 478 MB on Raspberry Pi 4; 19 KB on Arduino Nano 33 BLE Sense.
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 3.2 W on Raspberry Pi 5; 3.5 W on Raspberry Pi 4; 1.7 W on Arduino Nano 33 BLE Sense.

### Optimization

* Techniques used: Lightweight CNN design, Squeeze-and-Excitation blocks, depthwise separable convolutions, knowledge distillation, and post-training quantization.
* Quantization: INT8 / PTQ
* Pruning: Not reported
* Knowledge distillation: Yes
* Compression method: Post-training quantization from 32-bit floating-point weights to 8-bit integers.
* Hardware-specific optimization: TensorFlow Lite conversion for edge deployment.
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported; memory utilization on Arduino Nano 33 BLE Sense reported as 19 KB.
* Flash usage reported: Not reported
* Model size reported: 0.72 MB; 260 KB in TensorFlow Lite format; text also states 26 MB after quantization.
* Energy per inference reported: Not reported
* Latency on target device reported: 80 ms on Raspberry Pi 5; 112 ms on Raspberry Pi 4; 750 ms on Arduino Nano 33 BLE Sense.
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Yes
* Reason: The paper reports deployment-related metrics on Arduino Nano 33 BLE Sense, including 19 KB memory utilization, 750 ms inference time, 1.7 W power consumption, and a 260 KB TensorFlow Lite model.

### Benchmarking / Standardization

* Benchmark used: Not reported
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes, compared with EfficientNetB0, SqueezeNet, MobileNet_v3, MobileNet_v2, ShuffleNet, GhostNet, and MobileViT.
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: Tiny-MobileNet-SE achieved up to 98.6% accuracy with a 0.72 MB model and 0.48 million parameters. The model was converted to TensorFlow Lite and evaluated on Raspberry Pi 5, Raspberry Pi 4, and Arduino Nano 33 BLE Sense, with the Arduino deployment reporting 750 ms latency, 19 KB memory utilization, and 1.7 W power consumption.

### Limitations

* The model achieved lower accuracy on human face emotions, human face ages, and domestic animal datasets than on crop pest, crop disease, and crop fruits datasets.
* Arduino Nano 33 BLE Sense showed higher inference time than Raspberry Pi 5 and Raspberry Pi 4, and peak training memory was not applicable due to limited capability for training.

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
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes Tiny-MobileNet-SE, a hybrid lightweight CNN architecture using SE blocks, depthwise separable convolutions, batch normalization, knowledge distillation, and post-training quantization for image classification on resource-constrained IoT and edge devices.

| Paper          | Year | Task           | Model             | Technique                                                                | Device                                                    | Dataset                                | Main Metric    | Latency                                                                                | Model Size             | SRAM/RAM                                                                               | Flash | Energy | Framework       | INT8/QAT   | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---: | -------------- | ----------------- | ------------------------------------------------------------------------ | --------------------------------------------------------- | -------------------------------------- | -------------- | -------------------------------------------------------------------------------------- | ---------------------- | -------------------------------------------------------------------------------------- | ----- | ------ | --------------- | ---------- | ------------- | ------------- |
| Nyakuri et al. | 2025 | Classification | Tiny-MobileNet-SE | SE blocks, depthwise separable convolutions, knowledge distillation, PTQ | Arduino Nano 33 BLE Sense; Raspberry Pi 5; Raspberry Pi 4 | PlantVillage and Kaggle image datasets | 98.6% accuracy | 750 ms on Arduino Nano 33 BLE Sense; 80 ms on Raspberry Pi 5; 112 ms on Raspberry Pi 4 | 0.72 MB; 260 KB TFLite | 19 KB on Arduino Nano 33 BLE Sense; 527 MB on Raspberry Pi 5; 478 MB on Raspberry Pi 4 | N/A   | N/A    | TensorFlow Lite | INT8 / PTQ | N/A           | Yes           |
