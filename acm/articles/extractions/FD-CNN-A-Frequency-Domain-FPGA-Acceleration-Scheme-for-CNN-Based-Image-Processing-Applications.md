## Paper ID: FD-CNN-A-Frequency-Domain-FPGA-Acceleration-Scheme-for-CNN-Based-Image-Processing-Applications

TinyML classification: Near-TinyML — the work targets ZYNQ FPGA/SoC edge platforms rather than explicit MCU-class deployment.

### Basic Info

* Authors: Xiaoyang Wang, Zhe Zhou, Zhihang Yuan, Jingchen Zhu, Yulong Cao, Yao Zhang, Kangrui Sun, Guangyu Sun
* Year: 2023
* Title: FD-CNN: A Frequency-Domain FPGA Acceleration Scheme for CNN-Based Image-Processing Applications
* Source: ACM Transactions on Embedded Computing Systems, Vol. 22, No. 6, Article 91
* Type: Experimental

### Problem & Context

* Task: Image classification and object detection
* Objective: Reduce image decoding and CNN inference bottlenecks in FPGA-based edge image-processing pipelines by using partial JPEG decoding and frequency-domain CNN acceleration.
* Application domain: Edge-AI image-processing applications
* Scenario: Edge, embedded FPGA/SoC, IoT
* TinyML relevance: Partial
* TinyML justification: The paper targets resource-constrained Edge-AI on ZYNQ FPGA/SoC platforms with latency, energy, quantization, and hardware-resource constraints, but it does not target MCU-class TinyML deployment.

### Model / Method

* Model: FD-CNN with Tiny-YOLO-v3-Freq, ResNet-18-Freq, and SqueezeNet-1.1-Freq
* Architecture family: CNN
* Techniques: Partial JPEG decoding, frequency-domain CNN inference, image-decoding-aware design-space exploration, pipelined execution, early stopping for progressive JPEG, INT-4 quantization, FPGA accelerator design
* Framework: PyTorch 1.10.1, MMDetection, Verilog, Vivado 2019.2, Xilinx SDK
* Training type: Not reported
* Inference type: On-device FPGA/SoC inference

### Hardware

* Device: ZC-706 and ZCU-102 FPGA platforms
* Hardware type: FPGA / SoC
* Processor / microcontroller: ZC-706 with Kintex-7 FPGA and dual ARM Cortex-A9 processors; ZCU-102 with UltraScale+ FPGA and quad ARM Cortex-A53 processors
* Clock frequency: 150 MHz
* SRAM / RAM: ZC-706 has 19.1 Mb BRAM, 1 GB PL_DDR, and 1 GB PS_DDR; ZCU-102 has 32.1 Mb BRAM, 500 MB PL_DDR, and 4 GB PS_DDR
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Absolute energy per inference not reported; average energy reduction of 2.55× on ZC-706 and 2.54× on ZCU-102
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Limited hardware resources, energy budget, latency, image-decoding overhead, CNN inference time, DSP usage, BRAM usage, LUT usage, FPGA resource utilization, communication bandwidth

### Dataset

* Name: ImageNet; VOC 2007
* Type: Public
* Dataset size: Not reported
* Number of classes: Not reported
* Input resolution: RGB inputs use 224 × 224 for ResNet-18 and SqueezeNet-1.1, 416 × 416 for Tiny-YOLO-v3; frequency-domain inputs use 192 × 28 × 28 for ResNet-18-Freq and SqueezeNet-1.1-Freq, and 192 × 52 × 52 for Tiny-YOLO-v3-Freq
* Data modality: RGB image, JPEG-compressed image, DCT frequency-domain image representation

### Metrics

* Accuracy: ResNet-18-Freq Top-1 68.54% and Top-5 88.37%; SqueezeNet-1.1-Freq Top-1 56.55% and Top-5 78.57%
* mAP: Tiny-YOLO-v3-Freq mAP 0.480
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: FD-CNN end-to-end latency on ZC-706 is 5.81 ms for SqueezeNet, 11.01 ms for ResNet-18, and 16.90 ms for Tiny-YOLO-v3; on ZCU-102 it is 5.13 ms, 8.00 ms, and 12.24 ms respectively
* FPS: Not reported
* Throughput: Average throughput improvement of 3.24× on ZC-706 and 4.29× on ZCU-102
* Model size: Not reported
* Parameters: Tiny-YOLO-v3-Freq 8.9M; ResNet-18-Freq 11.8M; SqueezeNet-1.1-Freq 1.27M
* MACs / FLOPs: Tiny-YOLO-v3-Freq 5.02 Bn FLOPs; ResNet-18-Freq 2.84 Bn FLOPs; SqueezeNet-1.1-Freq 0.67 Bn FLOPs
* RAM usage: FPGA BRAM usage reported as 435 / 545 on ZC-706 and 438 / 912 on ZCU-102 for evaluated configurations
* Flash usage: Not reported
* Energy per inference: Absolute energy per inference not reported; average energy reduction of 2.55× on ZC-706 and 2.54× on ZCU-102
* Power consumption: Not reported

### Optimization

* Techniques used: Frequency-domain input processing, partial JPEG decoding, removal of IDCT from decoding pipeline, FPGA command-driven accelerator, image-decoding-aware DSE, pipelined decoding and inference, early stopping for progressive JPEG, INT-4 quantization
* Quantization: QAT / INT-4
* Pruning: No
* Knowledge distillation: No
* Compression method: JPEG partial decoding; no neural-network compression method reported
* Hardware-specific optimization: FPGA-specific accelerator architecture, partial decoder, Conv/FC module, command set, DSE over Tn, Tm, and number of partial decoders
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Relative energy reduction reported, but absolute energy per inference not reported
* Latency on target device reported: Yes
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Compressed images are assumed to be sent from IoT devices to edge nodes; cloud communication during inference is not reported
* Candidate for Strict TinyML: No
* Reason: The paper targets ZYNQ FPGA/SoC edge platforms with DDR memory and ARM processors rather than MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, or kilobyte-scale SRAM/Flash deployment.

### Benchmarking / Standardization

* Benchmark used: ImageNet, VOC 2007, ZC-706, ZCU-102
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: ImageNet, Pascal VOC 2007
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: FD-CNN reduces image-decoding latency by using partial JPEG decoding and improves CNN accelerator utilization by feeding DCT frequency data into CNNs. It achieves average throughput improvements of 3.24× on ZC-706 and 4.29× on ZCU-102, with average energy reductions of 2.55× and 2.54× respectively.

### Limitations

* Frequency-domain models still show accuracy gaps compared with RGB-based counterparts.
* The authors indicate that hyperparameter tuning and higher-resolution frequency-domain channel selection may improve accuracy.

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

* This paper proposes FD-CNN, a frequency-domain FPGA acceleration pipeline that uses partial JPEG decoding and DCT-domain CNN inference to reduce decoding overhead, improve hardware utilization, and increase throughput and energy efficiency for Edge-AI image-processing applications.

| Paper       | Year | Task                                   | Model                                                              | Technique                                                   | Device                        | Dataset            | Main Metric                                              | Latency                  | Model Size | SRAM/RAM                                   | Flash | Energy                         | Framework                                         | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | -------------------------------------- | ------------------------------------------------------------------ | ----------------------------------------------------------- | ----------------------------- | ------------------ | -------------------------------------------------------- | ------------------------ | ---------- | ------------------------------------------ | ----- | ------------------------------ | ------------------------------------------------- | -------- | ------------- | ------------- |
| Wang et al. | 2023 | Image classification; object detection | FD-CNN with ResNet-18-Freq, SqueezeNet-1.1-Freq, Tiny-YOLO-v3-Freq | Frequency-domain partial JPEG decoding, FPGA DSE, INT-4 QAT | ZC-706; ZCU-102 ZYNQ FPGA/SoC | ImageNet; VOC 2007 | ResNet-18-Freq Top-1 68.54%; Tiny-YOLO-v3-Freq mAP 0.480 | 5.13–16.90 ms end-to-end | N/A        | BRAM 435/545 on ZC-706; 438/912 on ZCU-102 | N/A   | 2.55× / 2.54× energy reduction | PyTorch; MMDetection; Verilog; Vivado; Xilinx SDK | QAT      | None          | No            |
