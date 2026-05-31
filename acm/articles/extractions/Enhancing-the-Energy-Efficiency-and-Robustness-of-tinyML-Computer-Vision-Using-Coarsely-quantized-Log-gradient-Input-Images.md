## Paper ID: Enhancing-the-Energy-Efficiency-and-Robustness-of-tinyML-Computer-Vision-Using-Coarsely-quantized-Log-gradient-Input-Images

TinyML classification: Strict TinyML — The paper explicitly targets tinyML CV and microcontroller-constrained NAS with memory, model-size, and latency bounds.

### Basic Info

* Authors: Qianyun Lu; Boris Murmann
* Year: 2024
* Title: Enhancing the Energy Efficiency and Robustness of tinyML Computer Vision Using Coarsely-quantized Log-gradient Input Images
* Source: ACM Transactions on Embedded Computing Systems, Vol. 23, No. 3, Article 41, May 2024
* Type: Experimental

### Problem & Context

* Task: Classification
* Objective: Evaluate log-gradient input images for CNN-based tinyML computer vision to improve input quantization, CNN resource efficiency, illumination robustness, and adversarial robustness.
* Application domain: tinyML computer vision for near-sensor and battery-powered IoT systems.
* Scenario: Embedded, IoT, near-sensor tinyML vision pipeline.
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets tinyML computer vision, microcontroller-oriented CNN resource constraints, low-power image pipelines, input quantization, memory/model-size reduction, and energy-efficient preprocessing.

### Model / Method

* Model: μNAS-optimized CNNs; 2conv1fc toy CNN; MobileNetV2; ResNet-18 substitute model for adversarial attacks.
* Architecture family: CNN
* Techniques: Log-gradient preprocessing, 1-bit and 1.5-bit input quantization, soft binary quantizer threshold search, neural architecture search, structural pruning, filter-similarity analysis, adversarial training.
* Framework: TensorFlow; PyTorch; CleverHans.
* Training type: Models are trained experimentally; transfer learning is not reported.
* Inference type: Not reported as deployed on-device; evaluated experimentally.

### Hardware

* Device: Not reported for deployment; Nvidia GeForce RTX6000 @ 24GB GDDR6/module used for training.
* Hardware type: Not reported for deployment; GPU used for training.
* Processor / microcontroller: Not reported.
* Clock frequency: Not reported.
* SRAM / RAM: μNAS peak memory bound configured to 10,000 bytes; exact deployed SRAM/RAM not reported.
* Flash / ROM / Storage: μNAS model size bound configured to 20,000 bytes; exact deployed Flash/ROM/storage not reported.
* Power consumption: Not reported.
* Energy per inference: Not reported.
* Execution without full OS: Not reported.
* Fully on-device inference: Not reported.
* Constraints mentioned: Memory, persistent storage/model size, processor speed, MACs, energy, power, latency, ISP energy, image-sensor energy, CNN resource footprint.

### Dataset

* Name: PASCAL RAW 2014; Visual Wake Words with approximate RAW reconstruction using ExpandNet in ancillary experiments.
* Type: Public; reconstructed/simulated RAW for VWW ancillary experiments.
* Dataset size: PASCAL RAW subset includes 6,550 images.
* Number of classes: 3 for PASCAL RAW: bicycle, car, person.
* Input resolution: 96 × 96 × 1 for μNAS and threshold search; 224 × 224 × 1 for fixed CNN experiments; 96 × 96 × 3 for adversarial robustness experiments using duplicated grayscale channels.
* Data modality: 16-bit grayscale RAW images, generated 8-bit JPEG images, full-precision log-gradient images, 1.5-bit log-gradient images, and 1-bit log-gradient images.

### Metrics

* Accuracy: 1-bit log-gradient input achieves 96.2% accuracy with four first-layer Conv2D filters in the fixed CNN experiment; log-gradient models show 0.1% and 1.7% accuracy drops under dark and bright perturbations, compared with 10.9% and 4.3% for JPEG.
* mAP: Not reported.
* Precision: Not reported.
* Recall: Not reported.
* F1-score: Not reported.
* Latency: Not reported on target hardware; latency is approximated by MACs in μNAS.
* FPS: Not reported.
* Throughput: Not reported.
* Model size: μNAS model size bound configured to 20,000 bytes; at 2% error rate, FP log-gradient model size is reported as about 5× smaller than JPEG.
* Parameters: Not reported.
* MACs / FLOPs: μNAS MAC bound configured to 1,000,000 MACs; at 2% error rate, FP log-gradient MACs are reported as about 5× smaller than JPEG.
* RAM usage: μNAS peak memory bound configured to 10,000 bytes; at 2% error rate, FP log-gradient peak memory usage is reported as about 1.1× smaller than JPEG.
* Flash usage: Not directly reported; model size bound of 20,000 bytes is used as persistent storage constraint.
* Energy per inference: Not reported.
* Power consumption: Not reported.

### Optimization

* Techniques used: Log-gradient input representation, 1-bit and 1.5-bit input quantization, threshold search, NAS, structural pruning, reduced ISP pipeline, adversarial training.
* Quantization: 1-bit and 1.5-bit input quantization; CNN weights and activations are kept floating point.
* Pruning: Yes
* Knowledge distillation: No
* Compression method: Input representation compression through coarsely quantized log-gradient images combined with NAS and structural pruning.
* Hardware-specific optimization: Microcontroller-constrained μNAS resource bounds and analog image-sensor-oriented log-gradient / ratio-to-digital conversion discussion.
* Use of CMSIS-NN: Not reported.
* Use of TensorFlow Lite Micro: Not reported.
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: μNAS peak memory bound configured to 10,000 bytes; exact deployed SRAM not reported.
* Flash usage reported: Not directly reported; model size bound configured to 20,000 bytes.
* Model size reported: μNAS model size bound of 20,000 bytes and relative model-size reductions are reported.
* Energy per inference reported: Not reported.
* Latency on target device reported: Not reported.
* Runs without full operating system: Not reported.
* Fully on-device inference: Not reported.
* Communication required during inference: Not reported.
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly targets tinyML computer vision and microcontroller-constrained CNN design with memory, model-size, MAC, and energy-efficiency constraints, although no physical MCU deployment is reported.

### Benchmarking / Standardization

* Benchmark used: PASCAL RAW 2014; Visual Wake Words used in ancillary generalization experiments.
* MLPerf Tiny mentioned: Yes
* Visual Wake Words mentioned: Yes
* Other standard benchmark: PASCAL RAW 2014; ImageNet mentioned but not used.
* Comparison with baseline models: Yes, compares 8-bit JPEG, 16-bit RAW, full-precision log-gradient, 1.5-bit log-gradient, and 1-bit log-gradient inputs.
* Comparison with previous works: Yes, related work discusses prior ISP simplification, CNN compression, μNAS, MCUNet, MicroNets, and log-gradient image-sensor work.
* Reproducibility artifacts available: Dataset

### Results

* Summary: Log-gradient inputs enable aggressive 1-bit first-layer input quantization while maintaining classification performance comparable to or better than JPEG baselines. The method reduces CNN resource requirements in μNAS experiments and improves robustness to illumination changes and black-box adversarial attacks when using quantized log-gradient inputs.

### Limitations

* CNN weight and activation quantization are not considered and are left for future work.
* Actual hardware implementation is not performed, so real energy footprints and savings are not verified.
* RAW image datasets are limited, and the Visual Wake Words RAW data are only approximated from JPEG images.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: No
* Reports memory usage: Yes
* Reports latency: No
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a log-gradient tinyML computer vision pipeline that uses coarsely quantized sensor-level input images to improve CNN compressibility, illumination robustness, and adversarial robustness.

| Paper     | Year | Task           | Model                            | Technique                                                        | Device                                                         | Dataset                                  | Main Metric     | Latency | Model Size                                                    | SRAM/RAM                                                         | Flash | Energy | Framework          | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------- | ---: | -------------- | -------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------- | ---------------------------------------- | --------------- | ------- | ------------------------------------------------------------- | ---------------------------------------------------------------- | ----- | ------ | ------------------ | -------- | ------------- | ------------- |
| Lu et al. | 2024 | Classification | μNAS CNNs; 2conv1fc; MobileNetV2 | 1-bit log-gradient input quantization + NAS + structural pruning | Microcontroller-constrained search; no physical MCU deployment | PASCAL RAW 2014; VWW+ExpandNet ancillary | Accuracy: 96.2% | N/A     | 20,000-byte model-size bound; ~5× smaller vs JPEG at 2% error | 10,000-byte peak-memory bound; ~1.1× smaller vs JPEG at 2% error | N/A   | N/A    | TensorFlow/PyTorch | N/A      | None          | Yes           |
