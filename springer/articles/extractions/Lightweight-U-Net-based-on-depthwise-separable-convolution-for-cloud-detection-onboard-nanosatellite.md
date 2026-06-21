Paper ID: Lightweight-U-Net-based-on-depthwise-separable-convolution-for-cloud-detection-onboard-nanosatellite

Basic Info

Authors: Imane Khalil; Mohammed Alae Chanoui; Zine El Abidine Alaoui Ismaili; Zouhair Guennoun; Adnane Addaim; Mohammed Sbihi

Year: 2024

Title: Lightweight U-Net based on depthwise separable convolution for cloud detection onboard nanosatellite

Source: The Journal of Supercomputing, 80:26308–26332 

Type: Experimental

Problem & Context

Task: Segmentation

Objective: Detect and quantify cloud coverage onboard a 3U university nanosatellite to reduce transmission of cloudy Earth-observation images.

Application domain: Earth observation / nanosatellite onboard cloud detection

Scenario: Embedded, onboard nanosatellite, MCU-based payload controller

TinyML relevance: Yes

TinyML justification: The paper explicitly proposes a tiny machine learning U-Net model deployed on an STM32H7 microcontroller under memory, energy, computation, and communication constraints.

Model / Method

Model: Lightweight U-Net; Depthwise U-Net; Quantized U-Net

Architecture family: CNN

Techniques: Depthwise separable convolution; reduced kernels and filters; post-training quantization; full integer quantization; image downscaling and tiling

Framework: TensorFlow; Keras; TensorFlow Lite post-training quantization; X-CUBE-AI

Training type: Not reported

Inference type: On-device

Hardware

Device: Payload controller STM32H7A3ZI

Hardware type: MCU

Processor / microcontroller: STM32H7A3ZI with ARM Cortex-M7 core

Clock frequency: Not reported

SRAM / RAM: 1 MB RAM

Flash / ROM / Storage: 2 MB Flash

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Memory, energy, computation, inference time, communication bandwidth, onboard storage

Dataset

Name: Sentinel-2B-based cloud dataset from Park [9]; Gecko imager dataset

Type: Public training/testing dataset; private Gecko imager evaluation dataset

Dataset size: 666 RGB images; 466 training images; 200 validation images; 100 test images used for cloud-coverage comparison; Gecko dataset size not reported

Number of classes: Not reported

Input resolution: 48 × 64 pixels / 64 × 48 pixels; Gecko images originally 1266 × 672 pixels

Data modality: RGB satellite images

Metrics

Accuracy: U-Net 90.83%; Depthwise U-Net 89.64%

mAP: N/A

Precision: U-Net 89.62%; Depthwise U-Net 89.70%

Recall: U-Net 82.70%; Depthwise U-Net 78.64%

F1-score: U-Net 85.92%; Depthwise U-Net 83.56%

Latency: U-Net 1043 ms; Depthwise U-Net 399 ms; Quantized U-Net 256 ms

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: U-Net 47,025; Depthwise U-Net 9,910; Quantized U-Net 47,025

MACs / FLOPs: Not reported

RAM usage: U-Net 776.32 KB; Depthwise U-Net 775.42 KB; Quantized U-Net 524.95 KB

Flash usage: U-Net 203.08 KB; Depthwise U-Net 61.89 KB; Quantized U-Net 111.96 KB

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Depthwise separable convolution; reduced network layers/channels; post-training full integer quantization; image resizing and tiling

Quantization: INT8 PTQ

Pruning: No

Knowledge distillation: No

Compression method: Depthwise separable convolution and post-training quantization

Hardware-specific optimization: Deployment using X-CUBE-AI on STM32H7A3ZI microcontroller

Use of CMSIS-NN: Not reported

Use of TensorFlow Lite Micro: Not reported

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: RAM usage reported, but peak SRAM not explicitly reported

Flash usage reported: Yes; 61.89 KB for Depthwise U-Net and 111.96 KB for Quantized U-Net

Model size reported: Parameters reported; standalone model file size not reported

Energy per inference reported: No

Latency on target device reported: Yes; 1043 ms, 399 ms, and 256 ms depending on model variant

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No cloud/offloaded inference reported; UART is used to display/transmit results

Candidate for Strict TinyML: Yes

Reason: The model is deployed for fully on-device inference on an STM32H7 MCU with explicit Flash, RAM, latency, quantization, and embedded deployment evidence.

Benchmarking / Standardization

Benchmark used: Not reported

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: None

Comparison with baseline models: Yes; U-Net, Depthwise U-Net, and Quantized U-Net are compared

Comparison with previous works: Yes; memory comparison includes Jeppesen (2019) and Park (2020)

Reproducibility artifacts available: Dataset

Results

Summary: Depthwise U-Net reduces parameters to 9,910 and uses 61.89 KB Flash while maintaining 89.64% accuracy on the validation dataset. On STM32H7A3ZI, inference time decreases from 1043 ms for standard U-Net to 399 ms for Depthwise U-Net and 256 ms for Quantized U-Net.

Limitations

The Gecko imager evaluation dataset lacks labels and is assessed visually. The model struggles with thin/cirrus clouds, bright regions, and desert scenes due to RGB-only input and sensor/domain differences. Energy consumption analysis is not reported and is left for future work.

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

This paper proposes a lightweight U-Net-based cloud segmentation framework using depthwise separable convolution and post-training quantization for real-time onboard cloud-coverage prediction on an STM32H7 nanosatellite payload controller.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Khalil et al. | 2024 | Segmentation | Depthwise U-Net | Depthwise separable convolution + PTQ quantization | STM32H7A3ZI | Sentinel-2B cloud dataset + Gecko imager images | Accuracy 89.64% | 399 ms; 256 ms quantized | 9,910 params | 775.42 KB; 524.95 KB quantized | 61.89 KB; 111.96 KB quantized | N/A | TensorFlow/Keras; TensorFlow Lite PTQ; X-CUBE-AI | PTQ | None | Yes |
