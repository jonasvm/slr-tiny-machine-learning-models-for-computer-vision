Paper ID: IGM-MELv2-Infrared-Guiding-Modal-Multiuser-Eye-Localization-System-on-ARM-CPU-for-Autostereoscopic-Displays

TinyML classification: Near-TinyML — evaluated on Raspberry Pi 4B ARM CPU, not on MCU-class hardware.

Basic Info

Authors: Jiahe Zhu, Jinji Zheng, Xinyi Xia, Yifan Li, Zhiru Li, Xicai Li

Year: 2024

Title: IGM-MELv2: Infrared Guiding Modal Multiuser Eye Localization System on ARM CPU for Autostereoscopic Displays

Source: IEEE Transactions on Circuits and Systems for Video Technology, Vol. 34, No. 9, September 2024 

Type: Experimental / Methodological

Problem & Context

Task: Object detection / eye localization / face detection

Objective: Real-time multiuser eye localization on a single ARM CPU for binocular autostereoscopic displays.

Application domain: Autostereoscopic displays

Scenario: Embedded edge device / on-device inference / ARM CPU

TinyML relevance: Partial

TinyML justification: The paper targets real-time embedded computer vision on Raspberry Pi 4B ARM CPU using tiny-lightweight CNNs, but does not report MCU-class deployment.

Model / Method

Model: IGM-MELv2 with Yolo-Fastest-TF for TIR face detection and Yolo-Fastest-VE for RGB eye localization

Architecture family: CNN

Techniques: Compound downscaling, low-resolution dual-band task decomposition, bottom-up pathway, fine output grid, low-threshold-and-sort strategy

Framework: Darknet for training; NCNN for inference

Training type: From scratch

Inference type: On-device

Hardware

Device: Raspberry Pi 4B

Hardware type: CPU / SoC

Processor / microcontroller: ARMv7 BCM2711 CPU

Clock frequency: 1.5 GHz

SRAM / RAM: 4 GB RAM

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Computational budget, latency, real-time operation, low-cost embedded deployment, low-resolution processing

Dataset

Name: RGBT-MLEL; BioID; 300W

Type: Private/custom for RGBT-MLEL; public for BioID and 300W

Dataset size: RGBT-MLEL has 4000 RGB-TIR image pairs split into 3000 training, 500 validation, and 500 test pairs; BioID has 1521 images

Number of classes: 1 class for TIR face detection; 1 class for eye detection

Input resolution: TIR images 160 × 120; RGB images 640 × 480; Yolo-Fastest-TF input 160 × 128; Yolo-Fastest-VE input 160 × 160

Data modality: RGB-TIR image pairs

Metrics

Accuracy: IGM-MELv2 locates 97.4% of eyes on RGBT-MLEL test set; Yolo-Fastest-VE achieves 99.5% success rate at e ≤ 0.1 and 100% at e ≤ 0.15 on BioID

mAP: Yolo-Fastest-TF achieves 57.41 mAP and 91.46 AP50 on TIR face detection

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: IGM-MELv2 total latency 22.29 ms; Yolo-Fastest-VE latency 12.66 ms

FPS: IGM-MELv2 44.86 FPS; Yolo-Fastest-TF 103.84 FPS

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Yolo-Fastest-TF 21 MFLOPs; Yolo-Fastest-VE 37 MFLOPs

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Compound downscaling, network width/depth compression, low-resolution processing, task decomposition, NCNN deployment

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Compound downscaling of CNN resolution, width, and depth

Hardware-specific optimization: Accuracy-latency tradeoff searched and evaluated on Raspberry Pi 4B ARM CPU

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Yes

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: No off-device inference communication reported

Candidate for Strict TinyML: No

Reason: The deployment target is Raspberry Pi 4B with 4 GB RAM, not MCU-class hardware, and no SRAM/Flash/energy/RTOS/TFLM evidence is reported.

Benchmarking / Standardization

Benchmark used: RGBT-MLEL; BioID

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: BioID

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: IGM-MELv2 achieves 44.86 FPS and 97.4% eye localization success on Raspberry Pi 4B. Yolo-Fastest-TF achieves 91.46 AP50 with 21 MFLOPs, while Yolo-Fastest-VE achieves 100% success at e ≤ 0.15 with 37 MFLOPs.

Limitations: The paper reports limitations in the tiny-lightweight CNN design, notes that newer detectors can improve TIR face detection accuracy, and states that the eye localization model predicts eye bounding boxes instead of eye centers.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes an infrared-guiding modal multiuser eye localization system that decomposes the task into TIR face detection and RGB face-region eye localization using tiny-lightweight CNNs for real-time ARM CPU deployment.

| Paper      | Year | Task                                | Model                                        | Technique                                 | Device                            | Dataset          | Main Metric        | Latency  | Model Size | SRAM/RAM | Flash | Energy | Framework      | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---: | ----------------------------------- | -------------------------------------------- | ----------------------------------------- | --------------------------------- | ---------------- | ------------------ | -------- | ---------- | -------- | ----- | ------ | -------------- | -------- | ------------- | ------------- |
| Zhu et al. | 2024 | Object detection / eye localization | IGM-MELv2: Yolo-Fastest-TF + Yolo-Fastest-VE | Compound downscaling + task decomposition | Raspberry Pi 4B ARMv7 BCM2711 CPU | RGBT-MLEL; BioID | 97.4% success rate | 22.29 ms | N/A        | 4 GB RAM | N/A   | N/A    | Darknet / NCNN | N/A      | None          | No            |
