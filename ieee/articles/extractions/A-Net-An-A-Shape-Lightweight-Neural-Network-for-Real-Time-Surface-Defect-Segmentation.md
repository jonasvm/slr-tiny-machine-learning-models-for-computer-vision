Paper ID: A-Net-An-A-Shape-Lightweight-Neural-Network-for-Real-Time-Surface-Defect-Segmentation

TinyML classification: Near-TinyML — Edge/CPU-oriented lightweight vision deployment is reported, but no explicit MCU-class deployment evidence is provided.

Basic Info

Authors: Biao Chen, Tongzhi Niu, Wenyong Yu, Ruoqi Zhang, Zhenrong Wang, and Bin Li

Year: 2024

Title: A-Net: An A-Shape Lightweight Neural Network for Real-Time Surface Defect Segmentation

Source: IEEE Transactions on Instrumentation and Measurement, Vol. 73, Article 5001314, DOI: 10.1109/TIM.2023.3341115 

Type: Methodological

Problem & Context

Task: Segmentation

Objective: Real-time surface defect segmentation with high accuracy and low computational cost for resource-constrained industrial settings.

Application domain: Industrial quality control / surface defect detection

Scenario: Industrial edge devices, CPU-based edge inference, resource-constrained deployment

TinyML relevance: Partial

TinyML justification: The paper targets lightweight real-time edge segmentation and evaluates CPU inference without GPU acceleration, but it does not report MCU-class deployment, SRAM/Flash constraints, TFLM/CMSIS-NN, energy, or bare-metal/RTOS execution. 

Model / Method

Model: A-Net

Architecture family: CNN

Techniques: A-shaped lightweight encoder-decoder architecture, lightweight feature extraction blocks, depthwise separable convolution, point-wise convolution, factorized convolution, residual connections, dropout, single skip connection.

Framework: PyTorch 1.9.0; OpenVINO Benchmark Python Tool; CUDA 11.7, CUDNN 8.5, TensorRT 8.5.3 used in experimental setup.

Training type: from scratch

Inference type: on-device

Hardware

Device: Intel Core i7-10750H CPU @ 2.60 GHz on Windows; Intel Xeon CPU E5-2650 v4 @ 2.20 GHz on Ubuntu 18.04; NVIDIA GeForce GTX 1080Ti used for model evaluation setup.

Hardware type: CPU; GPU used in experimental evaluation setup.

Processor / microcontroller: Intel Core i7-10750H; Intel Xeon E5-2650 v4; no microcontroller reported.

Clock frequency: 2.60 GHz; 2.20 GHz

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Computational cost, FLOPs, parameter count, latency/inference speed, edge deployment, resource-constrained industrial settings.

Dataset

Name: NEU-seg, DAGM-seg, MCSD, MT

Type: NEU-seg: public/standard; DAGM-seg: synthetic/manual; MCSD: Not reported; MT: Not reported

Dataset size: NEU-seg: three selected defect types with 250 training and 50 test images per type; DAGM-seg: categories 7-10 with 250 training and 50 test images per category; MCSD: 886 training and 222 test images; MT: 341 training and 51 test images. 

Number of classes: NEU-seg: 3 selected defect subsets; DAGM-seg: 4 selected category subsets; MCSD: Not reported; MT: Not reported

Input resolution: NEU-seg original 200 × 200 resized to 224 × 224; DAGM-seg, MCSD, and MT images 512 × 512; CPU inference-speed test input 3 × 224 × 224.

Data modality: Image

Metrics

Accuracy: Not reported; IoU reported instead.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 190.6 FPS on Intel Core i7-10750H Windows CPU; 284.6 FPS on Intel Xeon E5-2650 v4 Linux CPU.

Throughput: 190.6 FPS on Windows CPU; 284.6 FPS on Linux CPU.

Model size: Not reported in MB

Parameters: 0.39M

MACs / FLOPs: 0.44G FLOPs on NEU-seg / 224 × 224 setting; 2.30G FLOPs on DAGM-seg, MCSD, and MT / 512 × 512 setting.

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Lightweight CNN architecture, depthwise separable convolution, point-wise convolution, factorized convolution, residual connections, dropout, single skip connection, reduced FLOPs and parameter count.

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Architectural lightweighting through lightweight convolution blocks.

Hardware-specific optimization: OpenVINO Benchmark Python Tool used for CPU inference-speed testing; no hardware-specific model optimization reported.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 0.39M parameters; MB file size not reported.

Energy per inference reported: Not reported

Latency on target device reported: No; FPS reported instead.

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper evaluates lightweight edge/CPU inference but does not provide MCU-class deployment, SRAM/Flash usage, energy per inference, TFLM/CMSIS-NN use, or execution without a full operating system.

Benchmarking / Standardization

Benchmark used: NEU-seg, DAGM-seg, MCSD, MT; OpenVINO CPU inference-speed benchmark.

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: NEU-seg; DAGM-seg

Comparison with baseline models: Yes; FCN, SegNet, PSPNet, DeepLabV3+, RefineNet, U-Net, Swin-Unet, CCNet, PGA-Net, LSA-Net, BiSeNet, BiSeNetV2, STDC, ERFNet, ESNet, ENet, and TopFormer.

Comparison with previous works: Yes

Reproducibility artifacts available: code

Results

Summary: A-Net reports 0.39M parameters and 0.44G FLOPs on the 224 × 224 NEU-seg setting, with IoU results of 60.53, 78.76, and 59.51 on NEU-seg subsets. It reports IoU values of 82.86, 75.99, 88.03, and 77.01 on DAGM-seg, 78.68 on MCSD, and 69.18 on MT, with CPU inference speeds of 190.6 FPS on Windows and 284.6 FPS on Linux. 

Limitations

A-Net does not achieve the highest performance among all models on all defect categories, and the authors state that further improvement of lightweight neural network performance for surface defect detection is needed. 

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes A-Net, an A-shaped lightweight CNN for real-time industrial surface defect segmentation using lightweight feature extraction and fusion blocks to reduce parameters and FLOPs while maintaining competitive IoU performance.

| Paper       | Year | Task         | Model | Technique                                                                   | Device                                              | Dataset                     | Main Metric                       | Latency | Model Size       | SRAM/RAM | Flash | Energy | Framework         | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ------------ | ----- | --------------------------------------------------------------------------- | --------------------------------------------------- | --------------------------- | --------------------------------- | ------- | ---------------- | -------- | ----- | ------ | ----------------- | -------- | ------------- | ------------- |
| Chen et al. | 2024 | Segmentation | A-Net | Lightweight CNN blocks with depthwise separable and factorized convolutions | Intel Core i7-10750H CPU; Intel Xeon E5-2650 v4 CPU | NEU-seg; DAGM-seg; MCSD; MT | IoU: 78.68% on MCSD; 69.18% on MT | N/A     | 0.39M parameters | N/A      | N/A   | N/A    | PyTorch; OpenVINO | N/A      | None          | No            |
