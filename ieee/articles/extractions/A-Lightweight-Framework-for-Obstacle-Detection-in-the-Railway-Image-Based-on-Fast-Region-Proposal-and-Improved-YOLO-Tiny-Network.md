Paper ID: A-Lightweight-Framework-for-Obstacle-Detection-in-the-Railway-Image-Based-on-Fast-Region-Proposal-and-Improved-YOLO-Tiny-Network

TinyML classification: Near-TinyML — edge-relevant lightweight computer vision with CPU/low-power GPU latency and model efficiency results, but no explicit MCU-class constraints.

Basic Info

Authors: Ling Guan; Limin Jia; Zhengyu Xie; Chaoying Yin

Year: 2022

Title: A Lightweight Framework for Obstacle Detection in the Railway Image Based on Fast Region Proposal and Improved YOLO-Tiny Network

Source: IEEE Transactions on Instrumentation and Measurement, vol. 71, 2022, Article 5009116. 

Type: Methodological

Problem & Context

Task: Object detection

Objective: Detect railway obstacles in single railway images using a lightweight framework with reduced parameters, FLOPs, and inference latency.

Application domain: Railway safety and railway obstacle detection

Scenario: Edge / railway monitoring / limited computational resources

TinyML relevance: Partial

TinyML justification: The paper targets lightweight CPU and low-power GPU inference for vision-based obstacle detection, but does not report MCU-class deployment, SRAM/Flash constraints, or TensorFlow Lite Micro execution.

Model / Method

Model: Three-stage framework with CRP module, RODNet, and postprocessing; RODNet is based on an improved YOLOv4-tiny network.

Architecture family: Hybrid CNN + Classical ML

Techniques: Fast region proposal, BING detector, IoM-based region filtering, lightweight CNN redesign, MOSA block, coordinate attention, residual blocks, tiny FPN, postprocessing fusion/removal/suppression.

Framework: PyTorch; OpenCV BING detector

Training type: Transfer learning / fine-tuning

Inference type: On-device

Hardware

Device: Laptop Intel i7-9750H CPU and laptop GTX1660Ti 6-GB GPU for inference; Intel Core i7-7820 CPU, 8-GB memory, and NVIDIA TITAN XP 12-GB GPU for training.

Hardware type: CPU / GPU

Processor / microcontroller: Intel i7-9750H@2.60 GHz CPU; GTX1660Ti 6-GB GPU; training used Intel Core i7-7820 CPU and NVIDIA TITAN XP GPU.

Clock frequency: 2.60 GHz for inference CPU; 3.6 GHz for training CPU.

SRAM / RAM: 6-GB GPU memory for inference GPU; 8-GB system memory for training hardware.

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Model size, parameters, FLOPs, CPU/GPU latency, limited computational resources, training cost, deployment cost.

Dataset

Name: RAILOD; Pascal VOC2007/2012; MSCOCO; CIFAR-10

Type: Private/custom for RAILOD; public for Pascal VOC, MSCOCO, and CIFAR-10.

Dataset size: RAILOD train set: 819 samples; RAILOD test set: 3832 samples; fused training dataset: 83,664 images.

Number of classes: RAILOD: 2 classes; Pascal VOC comparison: 5 classes; CIFAR-10: 10 classes.

Input resolution: Source images/videos: 1280 × 720 and 1920 × 1080; evaluated network input sizes: 416, 512, 608, and 800.

Data modality: RGB railway images / video frames

Metrics

Accuracy: Not reported for target railway obstacle detection.

mAP: Proposed framework: 80.3 mAP at input size 800 on RAILOD; RODNet: 89.98 mAP on Pascal VOC2007 5-class evaluation.

Precision: Proposed framework-800: car 82.6%, person 51.1%.

Recall: Proposed framework-800: car 80.7%, person 76.8%.

F1-score: Not reported

Latency: Proposed framework-800: 1916.6 ms CPU and 65.9 ms GPU; RODNet: 116.8 ms CPU and 11.7 ms GPU.

FPS: RODNet: 10.6 FPS CPU and 94.1 FPS GPU.

Throughput: Not reported

Model size: RODNet: 11.7 MB.

Parameters: RODNet: 2.91M parameters; 48% reduction compared with YOLOv4-tiny.

MACs / FLOPs: RODNet: 2.43 GFLOPs; 29% reduction compared with YOLOv4-tiny.

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Lightweight network redesign, fast BING-based coarse region proposal, MOSA block, coordinate attention, residual-like blocks, reduced output dimensions, IoU/IoM-based postprocessing.

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: Architecture-level model size and FLOP reduction.

Hardware-specific optimization: CPU-oriented lightweight inference evaluation; no hardware-specific embedded optimization reported.

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: 11.7 MB

Energy per inference reported: Not reported

Latency on target device reported: 65.9 ms/pic on low-power GPU; 1916.6 ms/pic on CPU for proposed framework-800.

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper evaluates lightweight computer vision on CPU/GPU hardware but does not report MCU-class deployment, SRAM/Flash limits, bare-metal/RTOS execution, or TFLM/CMSIS-NN usage.

Benchmarking / Standardization

Benchmark used: RAILOD; Pascal VOC2007/2012; MSCOCO; CIFAR-10

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Pascal VOC2007, Pascal VOC2012, MSCOCO, CIFAR-10

Comparison with baseline models: SSD, YOLOv3, YOLOv4, YOLOv4-tiny, Faster R-CNN, method from Li et al. [20], SSDlite, YOLOv3-tiny, YOLOv3-tiny-CIoU.

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: The proposed framework achieved 80.3 mAP on RAILOD at 65.9 ms/pic on the low-power GPU. RODNet reduced parameters by 48% and FLOPs by 29% compared with YOLOv4-tiny and improved CPU inference speed.

Limitations: The authors state that future work should expand the railway dataset, enrich railway scenes, label distance parameters, and further improve precision and recall for small and distant pedestrian detection.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a lightweight three-stage railway obstacle detection framework combining BING-based coarse region proposal, an improved YOLOv4-tiny RODNet detector, and postprocessing strategies for efficient railway image object detection.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| Guan et al. | 2022 | Object Detection | RODNet / improved YOLOv4-tiny | Lightweight CNN redesign + fast region proposal | Intel i7-9750H CPU / GTX1660Ti GPU | RAILOD | 80.3 mAP | 65.9 ms/pic GPU | 11.7 MB | N/A | N/A | N/A | PyTorch | N/A | None | No |
