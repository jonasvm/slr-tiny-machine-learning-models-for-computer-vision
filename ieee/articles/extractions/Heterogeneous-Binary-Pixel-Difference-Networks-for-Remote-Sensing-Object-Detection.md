Paper ID: Heterogeneous-Binary-Pixel-Difference-Networks-for-Remote-Sensing-Object-Detection

TinyML classification: Near-TinyML — Uses binary neural networks and efficient object detection for edge-oriented remote sensing, but reports GPU-based experiments rather than MCU-class deployment.

Basic Info

Authors: Jialei Zhan, Liang Bai, Jiehua Zhang, Tianpeng Liu, Fan Shi, Yongxiang Liu, and Li Liu

Year: 2025

Title: Heterogeneous Binary Pixel Difference Networks for Remote Sensing Object Detection

Source: IEEE Transactions on Geoscience and Remote Sensing, Vol. 63, 2025 

Type: Experimental

Problem & Context

Task: Object Detection

Objective: Improve binarized remote sensing object detection by preserving local contrast and multiscale information for small objects while maintaining efficiency.

Application domain: Remote sensing

Scenario: Edge, embedded, drones, satellites, Raspberry Pi 4 deployment evaluation

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained edge deployment using binary neural networks, but evaluation is mainly on RTX 3090 GPU and Raspberry Pi 4 rather than MCU-class hardware.

Model / Method

Model: HBiPiDiNet

Architecture family: Hybrid CNN / Transformer / ViT

Techniques: Binarization, binary neural networks, local binary patterns, binary pixel difference convolution, heterogeneous kernel fusion convolution blocks

Framework: PyTorch, MMDetection

Training type: Fine-tuning

Inference type: On-device for Raspberry Pi 4 evaluation; GPU evaluation also reported

Hardware

Device: Raspberry Pi 4; NVIDIA RTX 3090 GPU; Senputing image sensor chip used for theoretical energy simulation

Hardware type: SoC / CPU; GPU; Other

Processor / microcontroller: Raspberry Pi 4 with four ARM Cortex-A72 cores

Clock frequency: Up to 1.5 GHz

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: 0.94 mJ theoretical energy for HBiPiDiNet on Senputing chip simulation

Execution without full OS: Not reported

Fully on-device inference: Yes, for Raspberry Pi 4 evaluation

Constraints mentioned: Computational cost, power consumption, storage cost, resource-constrained edge deployment, high-resolution remote sensing images

Dataset

Name: AI-TOD; VisDrone2019; DIOR

Type: Not reported

Dataset size: AI-TOD has 14,018 training images and 14,018 testing images; VisDrone2019 and DIOR sizes not reported

Number of classes: Not reported

Input resolution: 800 × 800 in Raspberry Pi 4 inference evaluation; otherwise not reported

Data modality: Optical remote sensing images

Metrics

Accuracy: Not reported

mAP: AI-TOD HBiPiDiNet* with Faster R-CNN ResNet-18: mAP 14.0, mAP50 36.5, mAP75 8.0; VisDrone2019 HBiPiDiNet*: mAP 14.7; DIOR HBiPiDiNet*: mAP 33.5

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 11.16 s/image for HBiPiDiNet with Faster R-CNN ResNet-18 on Raspberry Pi 4

FPS: Not reported

Throughput: Not reported

Model size: 14.88 MB parameter amount for HBiPiDiNet with Faster R-CNN ResNet-18

Parameters: 14.88 MB parameter amount

MACs / FLOPs: 16.34 × 10⁹ OPs for HBiPiDiNet with Faster R-CNN ResNet-18

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: 0.94 mJ theoretical energy for HBiPiDiNet on Senputing chip simulation

Power consumption: Not reported

Optimization

Techniques used: 1-bit binarization, BiPDC, LBP-based local contrast enhancement, HKFCB multiscale binary convolution

Quantization: 1-bit binary weights and activations

Pruning: No

Knowledge distillation: No, IDa-Det knowledge distillation steps were excluded

Compression method: Binary neural networks

Hardware-specific optimization: Theoretical evaluation on Senputing image sensor chip; no deployment-specific optimization framework reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 14.88 MB parameter amount

Energy per inference reported: 0.94 mJ theoretical energy

Latency on target device reported: 11.16 s/image on Raspberry Pi 4

Runs without full operating system: Not reported

Fully on-device inference: Yes, on Raspberry Pi 4

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports edge-oriented binarized detection and Raspberry Pi 4 deployment timing, but does not report MCU-class deployment, SRAM/Flash constraints, bare-metal/RTOS execution, CMSIS-NN, or TensorFlow Lite Micro.

Benchmarking / Standardization

Benchmark used: AI-TOD, VisDrone2019, DIOR

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: Yes, compared with real-valued models, BiDet, IDa-Det, LSQ, Adabin, ReBNN, ReCU, IRNet, and lightweight RSOD methods

Comparison with previous works: Yes

Reproducibility artifacts available: code / model

Results

Summary: HBiPiDiNet improves binary remote sensing object detection by adding BiPDC and HKFCB, reaching mAP 14.0 and mAP50 36.5 on AI-TOD with Faster R-CNN ResNet-18. Raspberry Pi 4 evaluation reports 11.16 s/image and 3.86× acceleration over the real-valued Faster R-CNN ResNet-18 model.

Limitations

BNN-capable chips are reported as limited, energy consumption is evaluated theoretically, and applying BiPDC to the backbone reduced detection accuracy.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes HBiPiDiNet, a binarized remote sensing object detector that combines binary pixel difference convolution with heterogeneous kernel fusion blocks to improve small-object detection efficiency and accuracy.

| Paper       | Year | Task             | Model      | Technique                 | Device         | Dataset                    | Main Metric       | Latency       | Model Size | SRAM/RAM | Flash | Energy              | Framework             | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---- | ---------------- | ---------- | ------------------------- | -------------- | -------------------------- | ----------------- | ------------- | ---------- | -------- | ----- | ------------------- | --------------------- | -------- | ------------- | ------------- |
| Zhan et al. | 2025 | Object Detection | HBiPiDiNet | 1-bit BNN + BiPDC + HKFCB | Raspberry Pi 4 | AI-TOD; VisDrone2019; DIOR | AI-TOD mAP50 36.5 | 11.16 s/image | 14.88 MB   | N/A      | N/A   | 0.94 mJ theoretical | PyTorch / MMDetection | N/A      | None          | No            |
