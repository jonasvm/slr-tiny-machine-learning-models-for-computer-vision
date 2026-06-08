Paper ID: Real-Time-Detection-of-Hogweed-UAV-Platform-Empowered-by-Deep-Learning

TinyML classification: Near-TinyML — evaluated on Jetson Nano and other edge SBCs, but without explicit MCU-class deployment.

Basic Info

Authors: Alexander Menshchikov, Dmitrii Shadrin, Viktor Prutyanov, Daniil Lopatkin, Sergey Sosnin, Evgeny Tsykunov, Evgeny Iakovlev, Andrey Somov 

Year: 2021

Title: Real-Time Detection of Hogweed: UAV Platform Empowered by Deep Learning 

Source: IEEE Transactions on Computers, Vol. 70, No. 8, August 2021 

Type: Experimental

Problem & Context

Task: Segmentation

Objective: Real-time detection and localization of Sosnowsky’s hogweed from UAV imagery using onboard deep learning.

Application domain: Precision agriculture; harmful weed monitoring.

Scenario: UAV, embedded system, edge computing, onboard image processing.

TinyML relevance: Partial

TinyML justification: The paper targets low-power embedded edge inference on UAV-mounted single-board computers, mainly NVIDIA Jetson Nano, but does not deploy on MCU-class hardware. 

Model / Method

Model: Modified U-Net; SegNet; RefineNet with ResNet backbone.

Architecture family: CNN

Techniques: Width scaling, depth scaling, compound scaling, frame chunking/sliding-window processing; network slimming evaluated separately on Crop/weed dataset; INT8 quantization used for Google Coral experiment.

Framework: Not reported

Training type: Not reported for final U-Net; RefineNet uses pre-trained ResNet-50 backbone.

Inference type: On-device

Hardware

Device: NVIDIA Jetson Nano used as UAV payload; Raspberry Pi 3B, Raspberry Pi 3B + Intel NCS2, and Google Coral compared. 

Hardware type: SoC / embedded GPU

Processor / microcontroller: NVIDIA Jetson Nano

Clock frequency: Not reported

SRAM / RAM: 4 GB RAM shared between CPU and GPU on NVIDIA Jetson Nano.

Flash / ROM / Storage: Not reported

Power consumption: 5.5 W for U-Net (W=4, D=5); up to 7.5 W for larger models. 

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, power consumption, frame rate, area coverage, embedded compute limits.

Dataset

Name: Hogweed dataset / Heracleum dataset

Type: Public, author-collected

Dataset size: 263 annotated images: 92 DJI Phantom 3, 102 DJI Mavic Pro, 69 Xiaomi Yi action camera. 

Number of classes: 2

Input resolution: Original images include 4000x3000, 4000x2250, and 4608x3456; training crops are 512x512; inference uses 4000x2250 frames. 

Data modality: RGB image / aerial imagery

Metrics

Accuracy: Not reported

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 65 ms per 480x360 frame on NVIDIA Jetson Nano for U-Net (W=4, D=5) in the reported comparison scenario. 

FPS: 0.46 FPS on 4K frames for U-Net (W=4, D=5) on NVIDIA Jetson Nano; up to 0.70 FPS for U-Net (W=2, D=4). 

Throughput: Not reported

Model size: Not reported in MB

Parameters: 0.053M for U-Net (W=4, D=5); 29.4M for SegNet; 27.3M for RefineNet. 

MACs / FLOPs: Not reported

RAM usage: Each 4K input frame and temporal convolution memory of the same size take about 100 MB.

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 5.5 W for U-Net (W=4, D=5); 7.0 W for SegNet; 7.5 W for RefineNet. 

Optimization

Techniques used: Width scaling, depth scaling, compound scaling, input frame chunking, model comparison across embedded platforms.

Quantization: INT8 only for Google Coral experiment; not reported for Jetson Nano hogweed model.

Pruning: No for selected hogweed model; network slimming evaluated separately.

Knowledge distillation: No

Compression method: Model scaling by reducing convolutional channels and/or network depth.

Hardware-specific optimization: Frame chunking to fit large 4K frames into embedded memory; model scaling for NVIDIA Jetson Nano.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Parameters reported; MB size not reported.

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No cloud/offloaded inference reported; post-processed detection data are transmitted to the ground station.

Candidate for Strict TinyML: No

Reason: Deployment is on Jetson Nano and other edge SBC/accelerator platforms, not MCU-class hardware with SRAM/Flash-level constraints.

Benchmarking / Standardization

Benchmark used: Custom Hogweed dataset; embedded platform comparison using ResNet-50, MobileNet v2, MobileNet SSD v2, and U-Net; Crop/weed dataset used for model scaling versus network slimming comparison.

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ResNet-50, MobileNet v2, MobileNet SSD v2 used in embedded platform comparison.

Comparison with baseline models: Yes, SegNet, U-Net variants, RefineNet, and embedded platform baselines.

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset

Results

Summary: The best selected model, U-Net (W=4, D=5), achieved ROC AUC 0.958, 0.46 FPS on NVIDIA Jetson Nano, 0.053M parameters, 5.5 W power consumption, and 18.4 ha estimated coverage per 40-minute UAV mission. SegNet achieved the highest ROC AUC of 0.969 but only 0.020 FPS. 

Limitations

No explicit limitations section; the discussion notes RGB-only visual spectrum, potential benefits and cost issues of multispectral imaging, and an open issue around instance segmentation for two or more classes.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a UAV-based real-time hogweed segmentation platform using FCNN models optimized through model scaling for low-power embedded edge inference.

| Paper              | Year | Task         | Model          | Technique                 | Device             | Dataset         | Main Metric   | Latency                                        | Model Size        | SRAM/RAM                | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------------ | ---: | ------------ | -------------- | ------------------------- | ------------------ | --------------- | ------------- | ---------------------------------------------- | ----------------- | ----------------------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Menshchikov et al. | 2021 | Segmentation | Modified U-Net | Width/depth model scaling | NVIDIA Jetson Nano | Hogweed dataset | ROC AUC 0.958 | 65 ms per 480x360 frame; 0.46 FPS on 4K frames | 0.053M parameters | 4 GB RAM shared CPU/GPU | N/A   | N/A    | N/A       | N/A      | None          | No            |
