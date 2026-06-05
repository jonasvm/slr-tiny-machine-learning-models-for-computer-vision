Paper ID: Enhancing-Neural-Architecture-Search-With-Multiple-Hardware-Constraints-for-Deep-Learning-Model-Deployment-on-Tiny-IoT-Devices

TinyML classification: Strict TinyML — targets ultra-low-power TinyML deployment with kB-level memory constraints and GAP8 RISC-V embedded SoC evaluation.

Basic Info

Authors: Alessio Burrello; Matteo Risso; Beatrice Alessandra Motetti; Enrico Macii; Luca Benini; Daniele Jahier Pagliari

Year: 2024

Title: Enhancing Neural Architecture Search With Multiple Hardware Constraints for Deep Learning Model Deployment on Tiny IoT Devices 

Source: IEEE Transactions on Emerging Topics in Computing, Vol. 12, No. 3, July-September 2024

Type: Methodological

Problem & Context

Task: Image classification; visual wake words; also keyword spotting and anomaly detection benchmarks

Objective: Generate deep neural networks in one-shot that satisfy multiple hardware constraints such as memory and latency while maintaining accuracy.

Application domain: TinyML and IoT deep learning deployment

Scenario: Embedded, low-power IoT, on-device inference

TinyML relevance: Yes

TinyML justification: The paper targets TinyML deployment on low-power IoT devices, uses MLPerf Tiny benchmarks, considers kB/MB-level memory constraints, and deploys models on the GAP8 ultra-low-power RISC-V SoC.

Model / Method

Model: DUCCIO, applied to mask-based and path-based differentiable NAS using seed/reference networks such as ResNet-like CNN, MobileNetV1 0.25, DS-CNN, fully connected autoencoder, and ResNet18

Architecture family: CNN

Techniques: Neural Architecture Search, hardware-aware optimization, multi-constraint optimization, model size reduction, latency/OPs constraints, layer-wise memory constraints, channel pruning, INT8 deployment quantization

Framework: Python 3.10.9, PyTorch 1.13.1, PLiNIO, ONNX, DORY C-code deployment toolchain

Training type: From scratch with warmup, search, and fine-tuning phases

Inference type: On-device

Hardware

Device: GreenWaves Technologies GAP8 IoT multi-core System-on-Chip

Hardware type: SoC

Processor / microcontroller: Single 32-bit RISC-V fabric controller plus 8-core RISC-V computational cluster

Clock frequency: Not reported

SRAM / RAM: 512 kB L2 memory; 64 kB shared cluster L1 memory; 16 kB fabric-controller L1 memory

Flash / ROM / Storage: Larger off-chip L3 memory reachable through HyperBus or quad-SPI; exact Flash/ROM capacity not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, model size, latency, OPs, layer-wise memory hierarchy, compute, real-time constraints

Dataset

Name: CIFAR-10; Visual Wake Words based on MSCOCO 2014; Speech Commands v2; DCASE2020 Toy-car; Tiny ImageNet

Type: Public

Dataset size: CIFAR-10: 60,000 images; Visual Wake Words/MSCOCO 2014: more than 100k images; Speech Commands v2: 105,829 utterances; Tiny ImageNet: 100k images; DCASE2020 Toy-car size not reported

Number of classes: CIFAR-10: 10; Visual Wake Words: 2; Speech Commands v2: 12; Tiny ImageNet: 200; DCASE2020 Toy-car: Not reported

Input resolution: CIFAR-10: 32x32x3; Visual Wake Words: 96x96x3; Tiny ImageNet: 64x64x3; other benchmarks not reported

Data modality: RGB image; audio for keyword spotting and anomaly detection benchmarks

Metrics

Accuracy: ICL best reported accuracy 85.7%; VWW best reported accuracy 85.83%; KWS best reported accuracy 92.82%; Tiny ImageNet seed top-1 accuracy 71.97%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: GAP8 ICL deployment latency ranges from 9.40 ms to 27.86 ms; reference latency 21.42 ms

FPS: Not reported

Throughput: ICL deployment throughput ranges from 0.20 to 0.57 GOPs/s; Tiny ImageNet deployment throughput ranges from 0.19 to 0.47 GOPs/s

Model size: ICL deployed memory ranges from 14.6 kB to 75.5 kB; Tiny ImageNet deployed memory ranges from 2264 kB to 7770 kB

Parameters: Tiny ImageNet seed has 11.28M parameters; one ICL model has 33.3k parameters; KWS examples report 9.4k and 9.96k parameters

MACs / FLOPs: ICL mask-based OPs span 1.07M to 10.0M; GAP8 ICL deployment reports 2.48 to 12.50 MOPs; Tiny ImageNet deployment reports 731.0 to 1956.8 MOPs

RAM usage: Hardware memory hierarchy reported; model memory and L2 violation reported, but peak runtime RAM usage not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: DUCCIO multi-constraint differentiable NAS, mask-based channel reduction, path-based layer selection, discretized Gumbel-Softmax sampling, layer-wise memory-aware refinement, INT8 deployment quantization

Quantization: INT8

Pruning: Yes

Knowledge distillation: Not reported

Compression method: NAS-based model size reduction and channel pruning

Hardware-specific optimization: Yes, GAP8 memory hierarchy-aware layer-wise constraints and DORY deployment

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: Yes

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes, deployed model memory is reported for GAP8 experiments

Energy per inference reported: Not reported

Latency on target device reported: Yes, GAP8 latency is reported for ICL models

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: Yes

Reason: The paper targets ultra-low-power TinyML deployment, uses MLPerf Tiny benchmarks, considers kB-level memory hierarchy constraints, and deploys INT8 models on the GAP8 RISC-V IoT SoC.

Benchmarking / Standardization

Benchmark used: MLPerf Tiny suite; Tiny ImageNet

MLPerf Tiny mentioned: Yes

Visual Wake Words mentioned: Yes

Other standard benchmark: CIFAR-10; Speech Commands v2; DCASE2020 Toy-car; Tiny ImageNet

Comparison with baseline models: Yes, compared against reference DNNs for each benchmark

Comparison with previous works: Yes, compares with standard DNAS formulations and ablation variants; related NAS methods are summarized

Reproducibility artifacts available: code

Results

Summary: DUCCIO finds models that match or improve baseline accuracy while reducing memory and OPs, including 87.4% memory reduction and 54.2% OPs reduction on VWW. GAP8 deployment shows ICL latency as low as 9.40 ms and model memory as low as 14.6 kB. Layer-wise Tiny ImageNet refinement reduces cycles by up to 61% with small accuracy drops.

Limitations

Path-based DNAS was less effective for some benchmarks due to limited search-space flexibility, and OPs were not always a perfect latency proxy for architectures with depthwise layers.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes DUCCIO, a one-shot differentiable neural architecture search method that incorporates multiple hardware constraints to generate TinyML-oriented deep neural networks satisfying memory and latency targets.

| Paper           | Year | Task                                     | Model                      | Technique          | Device   | Dataset                                   | Main Metric                              | Latency       | Model Size                                   | SRAM/RAM                                 | Flash | Energy | Framework           | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---: | ---------------------------------------- | -------------------------- | ------------------ | -------- | ----------------------------------------- | ---------------------------------------- | ------------- | -------------------------------------------- | ---------------------------------------- | ----- | ------ | ------------------- | -------- | ------------- | ------------- |
| Burrello et al. | 2024 | Image classification / Visual Wake Words | DUCCIO with CNN-based DNAS | Hardware-aware NAS | GAP8 SoC | MLPerf Tiny; Tiny ImageNet; CIFAR-10; VWW | Accuracy: up to 85.7% ICL and 85.83% VWW | 9.40-27.86 ms | 14.6-75.5 kB ICL; 2264-7770 kB Tiny ImageNet | 512 kB L2; 64 kB cluster L1; 16 kB FC L1 | N/A   | N/A    | PyTorch/PLiNIO/DORY | INT8     | None          | Yes           |
