## Paper ID: FastKAN-DDD-a-novel-fast-Kolmogorov-Arnold-network-based-approach-for-driver-drowsiness-detection-optimized-for-TinyML-deployment

TinyML classification: Strict TinyML — the paper explicitly targets microcontroller-based TinyML deployment with reported MCU-level memory footprint, latency, quantization, and embedded conversion evidence.

### Basic Info

* Authors: Siham Essahraui; Ismail Lamaakal; Yassine Maleh; Khalid El Makkaoui; Mouncef Filali Bouami; Ibrahim Ouahbi; Hela Elmannai; Ahmed A. Abd El-Latif
* Year: 2025
* Title: FastKAN-DDD: A novel fast Kolmogorov-Arnold network-based approach for driver drowsiness detection optimized for TinyML deployment
* Source: PLOS One 20(11): e0332577
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Develop an accurate, compact, interpretable, and efficient driver drowsiness detection model optimized for TinyML deployment.
* Application domain: Automotive driver monitoring and road safety
* Scenario: Embedded automotive system; TinyML; microcontroller-based deployment
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets TinyML and microcontroller-based deployment, reporting quantized model size, inference latency, and conversion to embedded `.cc` array format.

### Model / Method

* Model: FastKAN-DDD
* Architecture family: Other
* Techniques: Post-training quantization, dynamic range quantization, full integer quantization, float-16 quantization, weight-only quantization, TensorFlow Lite conversion, `.cc` array conversion
* Framework: TensorFlow Lite
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: Microcontroller-based systems targeted; specific target microcontroller not reported
* Hardware type: MCU target; GPU/CPU used for development
* Processor / microcontroller: Not reported for deployment; NVIDIA Tesla V100 and Intel Core i7-11800H reported for experimentation
* Clock frequency: Not reported for deployment; Intel Core i7-11800H at 2.30 GHz reported for local setup
* SRAM / RAM: Not reported for deployment; 16 GB RAM reported for local setup
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, latency, compute, power, energy, privacy, deployment on resource-constrained embedded systems

### Dataset

* Name: UTA-RLDD
* Type: Public
* Dataset size: 60 participants, 180 videos, approximately 30 hours of RGB video; 20,205 labeled frames after filtering
* Number of classes: 2
* Input resolution: 150×150, 128×128, 64×64, 32×32
* Data modality: RGB video frames

### Metrics

* Accuracy: Up to 99.94%
* mAP: Not reported
* Precision: Up to 99.94%
* Recall: Up to 99.94%
* F1-score: Up to 99.94%
* Latency: As low as 0.05 ms in Table 7; abstract reports as low as 0.04 ms
* FPS: Not reported
* Throughput: Not reported
* Model size: As low as 35 KB
* Parameters: 17,462 for 32×32; 69,686 for 64×64; 278,582 for 128×128; 382,554 for 150×150
* MACs / FLOPs: Not reported
* RAM usage: Not reported
* Flash usage: Not reported as device flash; `.cc` array size reported as 224 KB for 32×32 and 661 KB for 64×64
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Post-training quantization, TensorFlow Lite conversion, embedded `.cc` array conversion
* Quantization: PTQ; INT8 dynamic range; INT8 full integer; FP16; weight-only
* Pruning: No
* Knowledge distillation: No
* Compression method: Quantization
* Hardware-specific optimization: Conversion to `.cc` array for microcontroller firmware integration
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported as device flash; `.cc` array size reported
* Model size reported: 35 KB minimum; 104 KB for the 64×64 PTQ model
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported on a named target device; TensorFlow Lite inference latency reported
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: No
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly targets microcontroller-based TinyML deployment and reports very small quantized model sizes, low latency, and embedded `.cc` array conversion, although detailed target MCU SRAM and energy measurements are not reported.

### Benchmarking / Standardization

* Benchmark used: UTA-RLDD
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: Not reported
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Code

### Results

* Summary: FastKAN-DDD achieved up to 99.94% accuracy on the UTA-RLDD driver drowsiness dataset. Quantized models reached very small model sizes, with the 32×32 PTQ weight-only version reporting 35 KB size and 0.05 ms inference latency.

### Limitations

* The dataset was collected under semi-controlled conditions and may not fully represent real-world driving variability.
* The paper notes challenges such as lighting variation, occlusions, diverse driver behavior, and lack of multimodal input evaluation.
* Detailed deployment measurements on a named microcontroller, including SRAM, flash, and energy per inference, are not reported.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes FastKAN-DDD, a compact Fast Kolmogorov-Arnold Network-based driver drowsiness detection model optimized with post-training quantization for TinyML and microcontroller-oriented deployment.

| Paper            | Year | Task           | Model       | Technique        | Device                        | Dataset  | Main Metric     | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework       | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------------- | ---: | -------------- | ----------- | ---------------- | ----------------------------- | -------- | --------------- | ------- | ---------- | -------- | ----- | ------ | --------------- | -------- | ------------- | ------------- |
| Essahraui et al. | 2025 | Classification | FastKAN-DDD | PTQ quantization | Microcontroller-based systems | UTA-RLDD | Accuracy 99.94% | 0.05 ms | 35 KB      | N/A      | N/A   | N/A    | TensorFlow Lite | PTQ      | None          | Yes           |
