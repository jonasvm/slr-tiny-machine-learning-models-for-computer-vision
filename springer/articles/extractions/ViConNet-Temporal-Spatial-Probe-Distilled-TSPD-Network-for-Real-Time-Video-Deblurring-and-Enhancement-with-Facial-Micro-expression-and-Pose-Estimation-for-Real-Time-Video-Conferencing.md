Paper ID: ViConNet-Temporal-Spatial-Probe-Distilled-TSPD-Network-for-Real-Time-Video-Deblurring-and-Enhancement-with-Facial-Micro-expression-and-Pose-Estimation-for-Real-Time-Video-Conferencing

TinyML classification: Near-TinyML — targets mobile and edge deployment with reduced model size and computation, but lacks explicit MCU-class hardware or memory constraints.

Basic Info

Authors: Arti Ranjan; M. Ravinder

Year: 2026

Title: ViConNet: Temporal-Spatial Probe Distilled (TSPD) Network for Real-Time Video Deblurring and Enhancement with Facial Micro-expression and Pose Estimation for Real-Time Video Conferencing

Source: Circuits, Systems, and Signal Processing, 45, 1486–1528

Type: Experimental / Methodological

Problem & Context

Task: Video deblurring and enhancement with facial micro-expression preservation and pose estimation

Objective: Restore blur-free real-time facial video while preserving facial identity, micro-expressions, head pose, and temporal coherence.

Application domain: Video conferencing, telemedicine, facial recognition, remote collaboration, telepresence

Scenario: Mobile, edge, embedded, real-time video conferencing

TinyML relevance: Partial

TinyML justification: The paper targets lightweight real-time deployment on mobile and edge devices, but does not report MCU-class deployment, TensorFlow Lite Micro, bare-metal/RTOS execution, or SRAM/Flash-constrained evaluation.

Model / Method

Model: ViConNet with DINO-ViT, ViTPose, Restormer+, and TSPD student model

Architecture family: Transformer / ViT

Techniques: Knowledge distillation, model compression, temporal-spatial probe distillation, dynamic attention, pose-guided restoration, self-supervised feature extraction

Framework: PyTorch; TensorFlow; Hugging Face Transformers; OpenCV; MediaPipe

Training type: Not reported

Inference type: Not reported

Hardware

Device: NVIDIA RTX 3090 GPU + Intel Xeon 16-core CPU experimental platform

Hardware type: GPU / CPU

Processor / microcontroller: Intel Xeon 16-core CPU

Clock frequency: Not reported

SRAM / RAM: 128 GB RAM

Flash / ROM / Storage: 2 TB NVMe SSD

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Not reported

Constraints mentioned: Model size, computational cost, inference speed, real-time processing, resource-constrained mobile and edge deployment

Dataset

Name: 2MF2; YouTube Faces Dataset (YTF); TalkingHead-1KH

Type: Not reported

Dataset size: 2MF2: 11,590 videos, 850 identities, 19,202,440 sequential frames; YTF: 3,425 videos, 1,595 identities; TalkingHead-1KH: not reported

Number of classes: Not reported

Input resolution: Not reported

Data modality: RGB video / facial video frames

Metrics

Accuracy: Not reported

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: 37 FPS after TSPD distillation on 2MF2; 36 FPS after distillation on YTF; 38 FPS in 2MF2→YTF cross-dataset test; 36 FPS in YTF→2MF2 cross-dataset test

Throughput: Not reported

Model size: 17 MB after TSPD distillation on 2MF2; 18 MB after distillation on YTF and cross-dataset experiments; 33 MB before distillation on 2MF2

Parameters: Restormer+ full model approximately 27M; TSPD-student approximately 6M

MACs / FLOPs: Not reported; 40% lower computational cost reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Temporal-Spatial Probe Distillation, teacher-student knowledge transfer, probe-based feature selection, motion consistency loss, dynamic transposed attention, Gated-DConv Feed-Forward Network

Quantization: None

Pruning: No

Knowledge distillation: Yes

Compression method: TSPD teacher-student distillation reducing model size and computational complexity

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 17 MB after TSPD distillation on 2MF2; 18 MB after distillation on YTF

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: No

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports lightweight edge/mobile-oriented compression but evaluates on desktop-class GPU/CPU hardware and does not provide MCU-class deployment, SRAM/Flash usage, energy per inference, or bare-metal/RTOS evidence.

Benchmarking / Standardization

Benchmark used: 2MF2; YouTube Faces Dataset; TalkingHead-1KH

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: PSNR; SSIM; LPIPS; temporal consistency score; flicker rate; identity consistency; CED plot

Comparison with baseline models: DeblurGAN, SRN, DID-MDN, DMPHN, DBGAN, MPRNet, NAFNet, Uformer, Restormer

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: ViConNet after TSPD distillation reports 32.1 PSNR, 0.92 SSIM, 0.082 LPIPS, 37 FPS, and 17 MB model size on 2MF2. On YTF, the distilled model reports 30.1 PSNR, 0.91 SSIM, 36 FPS, and 18 MB model size. The paper reports 45% model size reduction and 40% lower computational cost after distillation.

Limitations

Explicit limitations are not reported; future work includes adaptive distillation, multi-modal video enhancement, quantization, hardware-aware optimization, embedded/mobile deployment, adversarial robustness, and domain adaptation.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: No

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: No

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes ViConNet, a transformer-based real-time facial video deblurring and enhancement framework using DINO-ViT, ViTPose, Restormer+, and Temporal-Spatial Probe Distillation to reduce model size and computation while preserving video restoration quality.

| Paper         | Year | Task                             | Model                   | Technique              | Device                               | Dataset                    | Main Metric                              | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework            | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---- | -------------------------------- | ----------------------- | ---------------------- | ------------------------------------ | -------------------------- | ---------------------------------------- | ------- | ---------- | -------- | ----- | ------ | -------------------- | -------- | ------------- | ------------- |
| Ranjan et al. | 2026 | Video deblurring and enhancement | ViConNet / TSPD-student | Knowledge distillation | NVIDIA RTX 3090 GPU + Intel Xeon CPU | 2MF2; YTF; TalkingHead-1KH | PSNR 32.1 / SSIM 0.92 on 2MF2 after TSPD | N/A     | 17 MB      | N/A      | N/A   | N/A    | PyTorch / TensorFlow | N/A      | None          | No            |
