## Paper ID: RRNet-Repetition-Reduction-Network-for-Energy-Efficient-Depth-Estimation

TinyML classification: Near-TinyML — the work is edge/mobile-GPU relevant but does not provide explicit MCU-class deployment or microcontroller-level constraints.

### Basic Info

* Authors: Sangyun Oh; Hye-Jin S. Kim; Jongeun Lee; Junmo Kim
* Year: 2020
* Title: RRNet: Repetition-Reduction Network for Energy Efficient Depth Estimation
* Source: IEEE Access
* Type: Experimental / Methodological

### Problem & Context

* Task: Depth estimation
* Objective: Design an energy-efficient lightweight encoder-decoder model for resource-constrained depth estimation.
* Application domain: Mobile computer vision, augmented reality, virtual reality, robotics, autonomous vehicles, drones, and smart factories.
* Scenario: Mobile GPU / edge / resource-constrained mobile applications
* TinyML relevance: Partial
* TinyML justification: The paper targets lightweight and energy-efficient computer vision inference on mobile GPU hardware, but does not report MCU-class deployment or microcontroller-level constraints.

### Model / Method

* Model: RRNet
* Architecture family: CNN
* Techniques: Lightweight encoder-decoder design, depthwise convolution reduction, pointwise convolution, Repetition-Reduction block, Condensed Decoding Connection, hardware-aware GPU latency optimization
* Framework: TensorFlow 1.4.0 with CUDA 8.0 and cuDNN 7.0
* Training type: From scratch
* Inference type: On-device

### Hardware

* Device: NVIDIA TX2 Development Kit
* Hardware type: GPU / SoC / CPU
* Processor / microcontroller: ARM-A57 CPU with NVIDIA Pascal-based mobile GPU
* Clock frequency: Not reported
* SRAM / RAM: 8 GB main memory
* Flash / ROM / Storage: Not reported
* Power consumption: NVIDIA TX2 TDP reported as 15 W
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Memory usage, runtime, energy consumption, computation, GPU latency, model complexity

### Dataset

* Name: KITTI; Cityscapes
* Type: Public
* Dataset size: KITTI contains 42,382 rectified stereo pairs; Cityscapes contains 22,973 training stereo pairs
* Number of classes: Not applicable
* Input resolution: 256 × 512 × 3 during training
* Data modality: Stereo RGB image pairs

### Metrics

* Accuracy: Not reported
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: 0.135 s per image on NVIDIA TX2; 54 s runtime for 400 KITTI images
* FPS: Not reported
* Throughput: Not reported
* Model size: 1.1M parameters
* Parameters: 1.1M
* MACs / FLOPs: 3.26B MAdds
* RAM usage: 2181 MB memory usage on NVIDIA TX2
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: 128.84 J total energy consumption for 400 KITTI images on NVIDIA TX2

### Optimization

* Techniques used: Repetition-Reduction block, Condensed Decoding Connection, reduced depthwise convolution usage, pointwise channel reduction, lightweight encoder-decoder design, GPU latency-aware architecture design
* Quantization: None
* Pruning: No
* Knowledge distillation: No
* Compression method: Lightweight architectural compression through RR blocks and CDCs
* Hardware-specific optimization: Yes, optimized for mobile GPU latency and energy efficiency
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 1.1M parameters
* Energy per inference reported: Not reported
* Latency on target device reported: 0.135 s per image on NVIDIA TX2
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper evaluates an energy-efficient vision model on NVIDIA TX2 mobile GPU hardware with Linux and 8 GB memory, but provides no MCU-class deployment evidence.

### Benchmarking / Standardization

* Benchmark used: KITTI; Cityscapes
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: KITTI depth estimation benchmark-style evaluation; Cityscapes
* Comparison with baseline models: Monodepth, SqueezeNet, MobileNetv2, ShuffleNet, EfficientNet, PyDNet, DiCENet, DABNet
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: RRNet achieved 1.1M parameters, 3.26B MAdds, 2181 MB memory usage, 54 s runtime, and 128.84 J total energy on NVIDIA TX2 for 400 KITTI images. The paper reports 3.84× lower energy consumption, 3.06× lower memory usage, and 2.21× faster runtime than conventional schemes on a commercial mobile GPU.

### Limitations

* Not reported

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

* This paper proposes RRNet, an energy-efficient lightweight encoder-decoder network for depth estimation using Repetition-Reduction blocks and Condensed Decoding Connections to reduce computation, memory usage, runtime, and energy consumption on mobile GPU hardware.

| Paper     | Year | Task             | Model | Technique                                           | Device     | Dataset           | Main Metric   | Latency              | Model Size      | SRAM/RAM             | Flash | Energy                  | Framework        | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | ---------------- | ----- | --------------------------------------------------- | ---------- | ----------------- | ------------- | -------------------- | --------------- | -------------------- | ----- | ----------------------- | ---------------- | -------- | ------------- | ------------- |
| Oh et al. | 2020 | Depth estimation | RRNet | Lightweight encoder-decoder with RR blocks and CDCs | NVIDIA TX2 | KITTI; Cityscapes | Abs Rel 0.071 | 0.135 s/image on TX2 | 1.1M parameters | 2181 MB memory usage | N/A   | 128.84 J for 400 images | TensorFlow 1.4.0 | N/A      | None          | No            |
