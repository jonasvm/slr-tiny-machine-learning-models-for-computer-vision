Paper ID: Generalized-self-cueing-real-time-attention-scheduling-with-intermittent-inspection-and-image-resizing

TinyML classification: Near-TinyML — evaluated on Jetson Xavier embedded GPU hardware, with no explicit MCU-class deployment or Cortex-M/TFLite Micro constraints.

Basic Info

Authors: Shengzhong Liu; Xinzhe Fu; Yigong Hu; Maggie Wigness; Philip David; Shuochao Yao; Lui Sha; Tarek Abdelzaher

Year: 2023

Title: Generalized self-cueing real-time attention scheduling with intermittent inspection and image resizing

Source: Real-Time Systems, 59, 302-343, Springer, DOI: 10.1007/s11241-023-09396-z 

Type: Methodological

Problem & Context

Task: Object Detection

Objective: Optimize real-time DNN-based visual machine perception on resource-limited embedded platforms using self-cueing, intermittent inspection, image resizing, and task batching.

Application domain: Autonomous driving

Scenario: Edge, embedded, autonomous system

TinyML relevance: Partial

TinyML justification: The paper targets resource-limited embedded visual perception and evaluates on NVIDIA Jetson Xavier, but does not report MCU-class deployment or MCU-level memory constraints.

Model / Method

Model: YOLOv5l object detector with optical-flow-based object tracking and GBPB scheduling

Architecture family: CNN

Techniques: Image resizing, intermittent inspection, task batching, frame slicing, optical-flow tracking, region merge, bounding box filtering, FP16 inference

Framework: PyTorch

Training type: Pretrained on COCO; training or fine-tuning not reported

Inference type: on-device

Hardware

Device: NVIDIA Jetson Xavier

Hardware type: SoC / CPU / GPU

Processor / microcontroller: 8-core Carmel Arm v8.2 64-bit CPU and 512-core Volta GPU

Clock frequency: Not reported

SRAM / RAM: 32 GB memory

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Yes

Constraints mentioned: Latency, compute, resource constraints, scheduling load, limited GPU processing time

Dataset

Name: Waymo Open Dataset; COCO used for pretraining

Type: public

Dataset size: Waymo driving video segments of 20 s each; number of segments used not reported

Number of classes: Not reported

Input resolution: 1920 x 1280 front-camera video frames

Data modality: Camera video / image frames

Metrics

Accuracy: Overall classification accuracy 99.88%; critical-object classification accuracy 99.96%

mAP: Overall mAP 62.76%; critical-object mAP 78.14% for YOLOv5l full-frame ceiling; GBPB improves BPB by 5.42% overall mAP and 6.33% critical mAP in busy traffic at 70 ms frame interval

Precision: Overall detection precision 87.54%; critical-object detection precision 92.05%

Recall: Overall detection recall 70.09%; critical-object detection recall 82.29%

F1-score: Not reported

Latency: YOLOv5l Xavier latency 239 ms; scheduling overhead generally below 30 ms; BPB per-frame policy overhead < 2 ms; GBPB per-frame policy overhead < 9 ms

FPS: Workload frame rates approximately 6.67 Hz, 10 Hz, and 14 Hz; achieved FPS not reported

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Generalized batched proportional balancing, intermittent inspection, image resizing, task batching, frame slicing, optical-flow-based tracking, region merging, bounding box filtering

Quantization: FP16

Pruning: Not reported

Knowledge distillation: Not reported

Compression method: Image resizing / input downscaling

Hardware-specific optimization: GPU task batching on Jetson Xavier and profiled YOLO inference latencies for different target sizes

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: YOLOv5l latency 239 ms on NVIDIA Jetson Xavier; scheduling overhead generally below 30 ms

Runs without full operating system: Not reported

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is an NVIDIA Jetson Xavier SoC with GPU and 32 GB memory, with no evidence of MCU-class deployment, TFLite Micro, bare-metal execution, or SRAM/Flash constraints.

Benchmarking / Standardization

Benchmark used: Waymo Open Dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO used for YOLOv5 pretraining

Comparison with baseline models: Yes; DS, HUF, BHUF, BPB, and GBPB are compared

Comparison with previous works: Yes; compares against the prior BPB policy

Reproducibility artifacts available: Not reported

Results

Summary: The proposed GBPB scheduling approach improves mAP over baseline scheduling methods and the prior BPB approach, especially under short frame intervals and busy traffic. In busy traffic at 70 ms frame interval, GBPB improves over BPB by 5.42% overall mAP and 6.33% critical-object mAP.

Limitations

GBPB shows slightly worse recall on physically close objects than BPB because resizing decisions are based on object size and do not consider object criticality. The authors also note that GBPB has higher policy overhead than BPB and could be improved by parallel execution across CPUs.

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

This paper proposes a generalized self-cueing attention scheduling framework that combines intermittent inspection, image resizing, and task batching to improve real-time DNN-based visual perception on resource-constrained embedded platforms.

| Paper      | Year | Task             | Model   | Technique                                                | Device               | Dataset            | Main Metric                                                                            | Latency                                    | Model Size | SRAM/RAM  | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ---------- | ---- | ---------------- | ------- | -------------------------------------------------------- | -------------------- | ------------------ | -------------------------------------------------------------------------------------- | ------------------------------------------ | ---------- | --------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Liu et al. | 2023 | Object Detection | YOLOv5l | Image resizing + intermittent inspection + task batching | NVIDIA Jetson Xavier | Waymo Open Dataset | mAP 62.76% overall / 78.14% critical; GBPB +5.42% overall mAP in busy traffic at 70 ms | 239 ms YOLOv5l; <30 ms scheduling overhead | N/A        | 32 GB RAM | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
