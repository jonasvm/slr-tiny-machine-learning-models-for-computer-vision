Paper ID: Resource-Efficient-Visual-Multiobject-Tracking-on-Embedded-Device

TinyML classification: Near-TinyML — Uses edge embedded GPU hardware, not explicit MCU-class or Cortex-M/TFLite Micro deployment.

Basic Info

Authors: Jingzheng Tu, Cailian Chen, Qimin Xu, Bo Yang, Xinping Guan 

Year: 2022

Title: Resource-Efficient Visual Multiobject Tracking on Embedded Device

Source: IEEE Internet of Things Journal, Vol. 9, No. 11, June 1, 2022

Type: Methodological

Problem & Context

Task: Multiobject tracking

Objective: Design a resource-efficient MOT method with low latency and fast inference for edge embedded devices in IoT surveillance.

Application domain: Security surveillance

Scenario: Edge, embedded, IoT

TinyML relevance: Partial

TinyML justification: The paper targets on-device edge embedded inference on NVIDIA Jetson Xavier NX, but does not report MCU-class deployment, Cortex-M execution, TFLite Micro, or kilobyte-scale SRAM/Flash constraints.

Model / Method

Model: REMOT with appearance model, motion association, SSD MobileNet-V1 detector, and Tiny YOLO V3 detector

Architecture family: CNN

Techniques: Angular triplet loss, batch-efficient triplet sampling, motion association, low-rank model compression, Tucker-2 decomposition, parallel processing of FC and convolutional layers

Framework: PyTorch

Training type: Not reported

Inference type: On-device

Hardware

Device: NVIDIA Jetson Xavier NX embedded device

Hardware type: SoC / CPU / GPU

Processor / microcontroller: 6-core NVIDIA Carmel ARM v8.2 64-bit CPU and 384-core NVIDIA Volta GPU 

Clock frequency: 1900 MHz, 1500 MHz, 1400 MHz, or 1200 MHz depending on power mode

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: 10 W and 15 W power modes reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Latency, model size, limited computation resources, communication bandwidth, cloud offloading, and resource-constrained edge devices

Dataset

Name: MOT Challenge benchmark, MOT16, MOT17

Type: Public

Dataset size: MOT16 and MOT17 contain 14 real-world video sequences each

Number of classes: Not reported

Input resolution: Not reported

Data modality: Video

Metrics

Accuracy: MOTA 55.3% on MOT16; MOTA 53.4% on MOT17

mAP: Not reported

Precision: MOTP 78.3% on MOT16; MOTP 78.5% on MOT17

Recall: Not reported

F1-score: IDF1 54.4% on MOT16; IDF1 54.1% on MOT17

Latency: Average latency 12.40 ms in 15W 6Core mode; average latency range 12.40–13.91 ms across reported power modes

FPS: 81 fps with SSD MobileNet-V1; 58 fps with Tiny YOLO V3

Throughput: 81 fps with SSD MobileNet-V1; 58 fps with Tiny YOLO V3

Model size: REMOT 211 MB original; 188 MB with compression

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 10 W and 15 W power modes reported

Optimization

Techniques used: Low-rank model compression, Tucker-2 decomposition, parallel processing of FC and convolutional layers, motion association, angular triplet loss

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Low-rank matrix factorization using Tucker-2 decomposition

Hardware-specific optimization: Parallel processing of FC-layer loading and convolutional-layer execution on the embedded device

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 211 MB original; 188 MB compressed

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: No

Reason: The target platform is NVIDIA Jetson Xavier NX, an embedded GPU/SoC device, with no explicit MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, SRAM, or Flash evidence.

Benchmarking / Standardization

Benchmark used: MOT Challenge benchmark

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: MOT16 and MOT17

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: REMOT achieves 81 fps with SSD MobileNet-V1 and 58 fps with Tiny YOLO V3 on NVIDIA Jetson Xavier NX. It reduces latency by 2.4× compared with the original implementation and reports about 6% marginal accuracy loss.

Limitations

The paper evaluates the method on multiobject tracking and only discusses applicability to other vision tasks as future potential. It also notes that accuracy may be improved with fine-tuning or other training strategies.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes REMOT, a resource-efficient visual multiobject tracking framework for edge embedded devices that combines angular-triplet-loss appearance modeling, motion association, model compression, and parallel layer processing.

| Paper     | Year | Task                 | Model | Technique                                        | Device                  | Dataset       | Main Metric                   | Latency              | Model Size        | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---- | -------------------- | ----- | ------------------------------------------------ | ----------------------- | ------------- | ----------------------------- | -------------------- | ----------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Tu et al. | 2022 | Multiobject tracking | REMOT | Tucker-2 compression + parallel layer processing | NVIDIA Jetson Xavier NX | MOT16 / MOT17 | MOTA 55.3% MOT16; 53.4% MOT17 | 12.40 ms avg; 81 fps | 188 MB compressed | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
