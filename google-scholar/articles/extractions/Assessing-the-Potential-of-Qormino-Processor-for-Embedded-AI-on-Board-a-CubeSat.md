# Paper ID: Assessing-the-Potential-of-Qormino-Processor-for-Embedded-AI-on-Board-a-CubeSat

TinyML classification: Near-TinyML — Uses embedded/on-board AI for satellite image segmentation on a Linux-based Cortex-A72 processor with GB-scale DDR4 memory, without explicit MCU-class constraints.

## Basic Info

**Authors:** Paul Vandame, Alexis Noé, Jiří Cech, Lian Apostol, Colin Prieur, Kieran McNamara, Frédéric Martin, Thierry Sequies, Tania McNamara, Mathieu Barthélémy, Jocelyn Chanussot

**Year:** 2022

**Title:** Assessing the Potential of Qormino Processor for Embedded AI on Board a CubeSat

**Source:** IEEE Journal on Miniaturization for Air and Space Systems, Vol. 3, No. 3, September 2022

**Type:** Benchmark

## Problem & Context

**Task:** Segmentation

**Objective:** Assess the Teledyne Qormino QLS1046-Space processor for embedded AI on board a CubeSat and demonstrate forest/nonforest and cloud/noncloud binary segmentation maps for deforestation monitoring.

**Application domain:** Earth observation and space-based environmental monitoring.

**Scenario:** Embedded on-board CubeSat inference.

**TinyML relevance:** Partial

**TinyML justification:** The paper targets embedded, on-board, memory- and power-constrained AI inference, but the deployment uses a Linux-based quad-core Cortex-A72 processor with GB-scale DDR4 memory rather than MCU-class hardware.

## Model / Method

**Model:** Specifically designed convolutional-layers-based pixel-wise classification algorithm for forest/nonforest and cloud/noncloud binary maps.

**Architecture family:** CNN

**Techniques:** Lightweight CNN, efficient memory management, FP16 use in benchmark inference, no additional compression.

**Framework:** Arm Compute Library, TensorFlow, PyTorch; specific deployment framework for the custom segmentation algorithm not reported.

**Training type:** Not reported

**Inference type:** On-device

## Hardware

**Device:** Teledyne Qormino QLS1046-Space development kit / Qormino QLS1046-Space processor module.

**Hardware type:** CPU / SoC

**Processor / microcontroller:** Quad-Core Arm Cortex-A72

**Clock frequency:** Up to 1.8 GHz; benchmarked at 1.6 GHz.

**SRAM / RAM:** 4 GB integrated DDR4 in the tested device; 8 GB version targeted.

**Flash / ROM / Storage:** Minimum required nonvolatile memory between 2 and 4 GB for mission software, OS, and stored raw images.

**Power consumption:** Payload power budget reported as 20 W with 30% margin; QLS1046-Space thermal power characteristic used for comparison is 14.6 W at 105 °C.

**Energy per inference:** Not reported

**Execution without full OS:** No

**Fully on-device inference:** Yes

**Constraints mentioned:** Memory, power, computing capability, power dissipation, size, energy supply, and downlink bandwidth.

## Dataset

**Name:** Sentinel-2 training data and Emerald 16M sensor test dataset.

**Type:** Public + private

**Dataset size:** Training size not reported; 17 labeled Emerald 300-mm-lens images used for quantitative testing.

**Number of classes:** 2 per binary task: forest/nonforest and cloud/noncloud.

**Input resolution:** Emerald images are 16 Mpix / 4096 × 4096; benchmark classifiers use 224 × 224 × 3 and other reported benchmark image sizes.

**Data modality:** RGB image and Raw Bayer image.

## Metrics

**Accuracy:** 0.89 overall accuracy for forest/nonforest classification on the labeled Emerald test images.

**mAP:** Not reported

**Precision:** Not reported

**Recall:** True Positive Rate 0.80 for forest pixels at threshold 0.509.

**F1-score:** Not reported

**Latency:** 4 min 42 s per 16-Mpix image for the custom AI algorithm on QLS1046-Space; benchmark inference examples include MobileNet 44 ms, ResNet50 206 ms, VGG16 418 ms, and YOLOv3 2500 ms in quad-core Arm Compute Library tests.

**FPS:** Not reported

**Throughput:** Not reported

**Model size:** Not reported

**Parameters:** Less than 1000 parameters for each trained binary model.

**MACs / FLOPs:** Not reported for the custom model; benchmark GFLOPS reported for standard neural networks.

**RAM usage:** Peak RAM usage not reported; 4 GB DDR4 identified as the main limitation.

**Flash usage:** Not reported

**Energy per inference:** Not reported

**Power consumption:** Not reported as measured inference power; 14.6 W thermal power characteristic used in power-efficiency comparison.

## Optimization

**Techniques used:** Lightweight CNN design, optimized memory management, FP16 type in benchmark inference, and no additional model compression.

**Quantization:** FP16 in benchmark inference; not reported for the custom segmentation algorithm.

**Pruning:** No

**Knowledge distillation:** No

**Compression method:** None; no additional compression applied because the models have less than 1000 parameters.

**Hardware-specific optimization:** Memory management for Qormino; Arm Compute Library used in benchmarks.

**Use of CMSIS-NN:** No

**Use of TensorFlow Lite Micro:** No

**Use of MLPerf Tiny:** No

## Strict TinyML Evidence

**SRAM peak reported:** Not reported

**Flash usage reported:** Not reported

**Model size reported:** Parameters reported; byte size not reported.

**Energy per inference reported:** Not reported

**Latency on target device reported:** Yes

**Runs without full operating system:** No

**Fully on-device inference:** Yes

**Communication required during inference:** No

**Candidate for Strict TinyML:** No

**Reason:** The target platform is a Linux-based quad-core Cortex-A72 processor module with 4 GB DDR4 memory, not an MCU-class, bare-metal, RTOS, or kilobyte-scale TinyML deployment.

## Benchmarking / Standardization

**Benchmark used:** BenchUtil, Arm Compute Library benchmark, AI-Benchmark, ConvNet benchmark, and custom 16-Mpix inference benchmark.

**MLPerf Tiny mentioned:** No

**Visual Wake Words mentioned:** No

**Other standard benchmark:** Not reported

**Comparison with baseline models:** AlexNet, GoogleNet, InceptionV3, InceptionV4, MobileNet, ResNet50, SqueezeNet, VGG16, YOLOv3, VGG19, ResNet-V2-50, ResNet-V2-152, VGG11, DenseNet121, MobileNetV2, ShuffleNet, and U-Net benchmarks.

**Comparison with previous works:** Intel Core i7-9750H used as hardware comparison.

**Reproducibility artifacts available:** Not reported

## Results

**Summary:** QLS1046-Space achieved acceptable embedded AI performance for space image processing, with the custom algorithm processing 16-Mpix images in 4 min 42 s on the target processor. The forest/nonforest test reached 0.89 overall accuracy, with True Positive Rate 0.80 and False Positive Rate 0.25 at threshold 0.509.

**Limitations:** The tested QLS1046-Space version has only 4 GB DDR4 memory, no real space images from the Emerald sensor were available, the test dataset differs from raw images expected in space, labels are imperfect, and additional tests are needed for raw space-image processing.

## Practical Reporting Checklist Evidence

**Reports hardware clearly:** Yes

**Reports memory usage:** Yes

**Reports latency:** Yes

**Reports energy or power:** Yes

**Reports model size:** Yes

**Reports optimization method:** Yes

**Reports deployment framework:** Yes

**Reports dataset and preprocessing:** Yes

**Reports evaluation metric clearly:** Yes

**Reports reproducibility artifacts:** No

## Contribution

This paper proposes a benchmark and feasibility assessment of the Teledyne Qormino QLS1046-Space processor for embedded on-board CubeSat AI, including a lightweight CNN-based binary segmentation algorithm for forest/cloud mapping in Earth observation images.

## Comparative Table

| Paper          | Year | Task         | Model                                 | Technique                             | Device                                           | Dataset                              | Main Metric   | Latency                      | Model Size       | SRAM/RAM  | Flash                              | Energy | Framework                                  | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| -------------- | ---- | ------------ | ------------------------------------- | ------------------------------------- | ------------------------------------------------ | ------------------------------------ | ------------- | ---------------------------- | ---------------- | --------- | ---------------------------------- | ------ | ------------------------------------------ | -------- | ------------- | ------------- |
| Vandame et al. | 2022 | Segmentation | Lightweight CNN pixel-wise classifier | Lightweight model + memory management | Qormino QLS1046-Space / Quad-Core Arm Cortex-A72 | Sentinel-2 + Emerald 16M test images | Accuracy 0.89 | 4 min 42 s per 16-Mpix image | <1000 parameters | 4 GB DDR4 | 2–4 GB nonvolatile memory required | N/A    | Arm Compute Library / TensorFlow / PyTorch | FP16     | None          | No            |
