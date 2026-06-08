Paper ID: A-Lightweight-Deep-Learning-Algorithm-for-Welding-Defect-Detection-in-New-Energy-Vehicle-Battery-Current-Collectors

TinyML classification: Near-TinyML — Deployment is on Jetson Nano embedded GPU/TensorRT, with no explicit MCU-class constraints.

Basic Info

Authors: Lei Yuan, Yanrong Chen, Hai Tang, Ren Gao, Wenhuan Wu

Year: 2024

Title: A Lightweight Deep-Learning Algorithm for Welding Defect Detection in New Energy Vehicle Battery Current Collectors

Source: IEEE Sensors Journal, Vol. 24, No. 13, 1 July 2024 

Type: Methodological

Problem & Context

Task: Object detection

Objective: Detect welding defects in new energy vehicle battery current collectors using a lightweight deep-learning detector deployable on embedded hardware.

Application domain: Industrial quality inspection; new energy vehicle battery current collectors.

Scenario: Embedded industrial visual inspection.

TinyML relevance: Partial

TinyML justification: The paper targets lightweight embedded on-device vision and deploys on NVIDIA Jetson Nano, but does not report MCU-class deployment or SRAM/Flash constraints.

Model / Method

Model: MGNet

Architecture family: CNN

Techniques: Lightweight MDM module, DOConv, DWConv, ODConv, MGD module, GDConv, GS_GFPN, GSConv, GhostConv, C3Ghost, TensorRT FP16 acceleration.

Framework: PyTorch 1.12.1; ONNX; TensorRT.

Training type: Transfer learning / pretrained model initialization.

Inference type: On-device.

Hardware

Device: NVIDIA Jetson Nano; training used Intel Core i5-12600KF, 16 GB RAM, NVIDIA RTX3080×2.

Hardware type: Embedded GPU / SoC.

Processor / microcontroller: NVIDIA Jetson Nano with onboard 128-core Maxwell GPU.

Clock frequency: Not reported.

SRAM / RAM: Deployment RAM not reported; training RAM 16G.

Flash / ROM / Storage: Not reported.

Power consumption: Not reported.

Energy per inference: Not reported.

Execution without full OS: No.

Fully on-device inference: Yes.

Constraints mentioned: Computational complexity, model weight, parameter redundancy, latency, FPS, limited embedded resources.

Dataset

Name: BCC Surface Defect Database; NEU-DET.

Type: BCC Surface Defect Database: private / self-constructed; NEU-DET: public.

Dataset size: BCC: 2000 defect images split 7:1:2; NEU-DET: 1800 jpg images split 8:2.

Number of classes: BCC: five defect types reported in text, while Table VII reports six objects; NEU-DET: six defect types.

Input resolution: Training image size 640; NEU-DET images 200 × 200; BCC original resolution not reported.

Data modality: Image.

Metrics

Accuracy: Not reported.

mAP: BCC: mAP50 93.9%, mAP50-95 69.1%; NEU-DET: mAP50 78.0%, mAP50-95 40.4%.

Precision: BCC: 94.7%; NEU-DET: 74.2%.

Recall: BCC: 91.0%; NEU-DET: 73.1%.

F1-score: Not reported.

Latency: Around 0.06 s/image on NVIDIA Jetson Nano after TensorRT acceleration.

FPS: BCC: 212.8 FPS; NEU-DET: 238.1 FPS.

Throughput: Not reported beyond FPS.

Model size: 3.1 M weights.

Parameters: 3.1 M.

MACs / FLOPs: 2.1 GFLOPs.

RAM usage: Not reported.

Flash usage: Not reported.

Energy per inference: Not reported.

Power consumption: Not reported.

Optimization

Techniques used: Lightweight network design, MDM module, GS_GFPN feature fusion, GhostConv, GSConv, C3Ghost, ONNX conversion, TensorRT acceleration, FP16 precision.

Quantization: FP16.

Pruning: No.

Knowledge distillation: No.

Compression method: Lightweight architecture and parameter reduction using depthwise/dynamic convolution, GhostConv, GSConv, and C3Ghost.

Hardware-specific optimization: TensorRT acceleration on NVIDIA Jetson Nano.

Use of CMSIS-NN: No.

Use of TensorFlow Lite Micro: No.

Use of MLPerf Tiny: No.

Strict TinyML Evidence

SRAM peak reported: Not reported.

Flash usage reported: Not reported.

Model size reported: 3.1 M weights.

Energy per inference reported: Not reported.

Latency on target device reported: Around 0.06 s/image on NVIDIA Jetson Nano.

Runs without full operating system: No.

Fully on-device inference: Yes.

Communication required during inference: Not reported.

Candidate for Strict TinyML: No.

Reason: Deployment uses NVIDIA Jetson Nano with Ubuntu and GPU acceleration, with no MCU-class platform, bare-metal execution, SRAM/Flash usage, or energy-per-inference evidence.

Benchmarking / Standardization

Benchmark used: BCC Surface Defect Database; NEU-DET.

MLPerf Tiny mentioned: No.

Visual Wake Words mentioned: No.

Other standard benchmark: NEU-DET.

Comparison with baseline models: Yes; compared with Inception-v4, EfficientViT, MobileNetv3, MobileViTv2, FasterNet, EfficientNet, Xception, Next-ViT, YOLOv5n, YOLOv5l, LF-YOLOx0.5, LF-YOLO, YOLOv7-tiny, YOLOv8n, and YOLOv4s.

Comparison with previous works: Yes.

Reproducibility artifacts available: Not reported.

Results

Summary: MGNet achieved 93.9% mAP50, 69.1% mAP50-95, 212.8 FPS, and 3.1 M weights on the BCC dataset. On NEU-DET, it achieved 78.0% mAP50, 40.4% mAP50-95, 238.1 FPS, and 3.1 M weights. TensorRT deployment on Jetson Nano reached around 0.06 s/image.

Limitations

Not explicitly reported; future work mentions developing efficient architectures for industrial defect detection across different detection objects and distances.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a lightweight MGNet object detection model combining MDM and GS_GFPN modules for real-time embedded welding defect detection in new energy vehicle battery current collectors.

| Paper       | Year | Task             | Model | Technique                                                         | Device             | Dataset                              | Main Metric                          | Latency                      | Model Size   | SRAM/RAM | Flash | Energy | Framework               | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ---------------- | ----- | ----------------------------------------------------------------- | ------------------ | ------------------------------------ | ------------------------------------ | ---------------------------- | ------------ | -------- | ----- | ------ | ----------------------- | -------- | ------------- | ------------- |
| Yuan et al. | 2024 | Object Detection | MGNet | Lightweight CNN with MDM + GS_GFPN and TensorRT FP16 acceleration | NVIDIA Jetson Nano | BCC Surface Defect Database; NEU-DET | mAP50 93.9% on BCC; 78.0% on NEU-DET | ~0.06 s/image on Jetson Nano | 3.1M weights | N/A      | N/A   | N/A    | PyTorch; ONNX; TensorRT | FP16     | None          | No            |
