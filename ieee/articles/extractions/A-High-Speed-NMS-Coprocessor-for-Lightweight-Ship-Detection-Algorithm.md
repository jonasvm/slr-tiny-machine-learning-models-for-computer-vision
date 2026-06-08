Paper ID: A-High-Speed-NMS-Coprocessor-for-Lightweight-Ship-Detection-Algorithm

TinyML classification: Near-TinyML — dedicated edge/ASIC-FPGA acceleration is reported, but there is no explicit MCU-class deployment evidence.

Basic Info

Authors: Ke Ning; Mingxin Zhao; Chunhe Yao; Xuemin Zheng; Mengmeng Xu; Nanjian Wu; Liyuan Liu; Shuangming Yu

Year: 2022

Title: A High-Speed NMS Coprocessor for Lightweight Ship Detection Algorithm

Source: IEEE Transactions on Circuits and Systems II: Express Briefs, Vol. 69, No. 3

Type: Experimental

Problem & Context

Task: Object detection

Objective: Accelerate NMS processing for lightweight ship detection in edge-computing scenarios using hardware/software co-design.

Application domain: Remote sensing ship detection

Scenario: Edge computing, embedded vision acceleration

TinyML relevance: Partial

TinyML justification: The paper targets low-power edge object detection with dedicated hardware acceleration and integer-only processing, but does not report MCU-class deployment.

Model / Method

Model: MobileNetV1-SSD

Architecture family: CNN

Techniques: Post-training quantization, integer-only processing, hardware/software co-design, NMS acceleration, approximate circuits, dynamic memory management

Framework: Not reported

Training type: Fine-tuning

Inference type: On-device

Hardware

Device: Vision Processor with NMS coprocessor; FPGA board used for verification

Hardware type: FPGA / SoC / Other

Processor / microcontroller: Independently designed Vision Processor with NMS coprocessor

Clock frequency: 800 MHz

SRAM / RAM: 256 KB memory for dynamic address allocation

Flash / ROM / Storage: Quantized MobileNetV1-SSD and parameters stored on-chip

Power consumption: 25.864 mW for the NMS coprocessor

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Power consumption, processing speed, hardware resources, storage, floating-point operation avoidance, NMS latency

Dataset

Name: Airbus Ship Detection Challenge dataset

Type: Public

Dataset size: Not reported

Number of classes: Not reported

Input resolution: Not reported

Data modality: RGB image

Metrics

Accuracy: 88.6%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 166 FPS

Throughput: 100 GOPS peak performance

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: 256 KB memory for dynamic address allocation

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 25.864 mW

Optimization

Techniques used: Post-training INT8 quantization, fine-tuning-based decoding conversion, integer-only NMS processing, approximate exponential arithmetic, approximate IoU, sorting simplification, data and space compression, hardware/software co-design

Quantization: INT8 / PTQ

Pruning: No

Knowledge distillation: No

Compression method: Data compression by confidence thresholding and space compression with dynamic linked-list memory allocation

Hardware-specific optimization: NMS coprocessor with 16 parallel processing units, approximate Softmax/IoU circuits, dynamic memory management, integer-only operations

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The work targets low-power edge/embedded detection hardware but does not explicitly report MCU-class deployment, Cortex-M/TFLM use, or SRAM/Flash-constrained execution.

Benchmarking / Standardization

Benchmark used: Airbus Ship Detection Challenge dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: MobileNetV1-SSD on Intel i9-9900K and NVIDIA 2080Ti

Comparison with previous works: Compared with another NMS processor in 28 nm technology

Reproducibility artifacts available: Not reported

Results

Summary: The proposed NMS coprocessor runs MobileNetV1-SSD at 166 FPS with 88.6% accuracy on the Airbus dataset. The NMS coprocessor operates at 800 MHz, consumes 25.864 mW, reaches 100 GOPS peak performance, and achieves 3.866 TOPS/W peak energy efficiency. 

Limitations

Not explicitly reported.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: No

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a hardware/software co-designed NMS coprocessor with integer quantization and approximate circuits to accelerate lightweight MobileNetV1-SSD ship detection for edge-computing hardware.

| Paper       | Year | Task             | Model           | Technique                                                | Device                                                    | Dataset                         | Main Metric    | Latency | Model Size | SRAM/RAM                                 | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------- | --------------- | -------------------------------------------------------- | --------------------------------------------------------- | ------------------------------- | -------------- | ------- | ---------- | ---------------------------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Ning et al. | 2022 | Object detection | MobileNetV1-SSD | INT8 PTQ and NMS coprocessor hardware/software co-design | Vision Processor with NMS coprocessor / FPGA verification | Airbus Ship Detection Challenge | 88.6% accuracy | N/A     | N/A        | 256 KB dynamic address allocation memory | N/A   | N/A    | N/A       | INT8/PTQ | None          | No            |
