Paper ID: Real-time-person-re-identification-and-tracking-on-edge-devices-with-distributed-optimization

TinyML classification: Near-TinyML — Uses resource-constrained edge hardware, but deployment is on Jetson Nano/Linux-class devices rather than explicit MCU-class platforms.

Basic Info

Authors: Tuan Linh Dang; Minh Hoang Hoang; Viet Anh Ngo; Minh Quan Duong; Hoang Hiep Ha; The An Nguyen; Hoang Le

Year: 2025

Title: Real-time person re-identification and tracking on edge devices with distributed optimization

Source: Pattern Analysis and Applications, 28:117. 

Type: Experimental

Problem & Context

Task: Person re-identification, pedestrian tracking, object detection

Objective: Develop an efficient real-time person ReID and pedestrian tracking system for resource-constrained edge devices in multi-camera surveillance.

Application domain: Intelligent surveillance

Scenario: Edge devices with centralized server, multi-camera surveillance, distributed edge-server processing

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained edge devices such as Jetson Nano and 2-vCPU/4GB devices, but does not target MCU-class TinyML deployment.

Model / Method

Model: YOLOv10n for edge detection; OSNet for feature extraction; ByteTrack for tracking; Redis embedding storage; Apache Kafka message queue

Architecture family: CNN / Other

Techniques: Adaptive frame skipping, parallel batch processing, semantic-enhanced embeddings, memory-based retrieval, Kafka load balancing, TensorRT/ONNX deployment optimization

Framework: PyTorch, ONNX, TensorRT, Apache Kafka, Redis

Training type: Fine-tuning

Inference type: Hybrid

Hardware

Device: Jetson Nano; lightweight 2-core vCPU edge device; centralized server

Hardware type: CPU / GPU / SoC / Other

Processor / microcontroller: Jetson Nano ARM Cortex-A57; lightweight device 2-core vCPU; server Intel i5-12600K

Clock frequency: Jetson Nano 1.43 GHz; lightweight device 3.5 GHz; server not reported

SRAM / RAM: Jetson Nano 4GB LPDDR4; lightweight device 4GB RAM; server 32GB RAM

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: No

Constraints mentioned: Memory, compute, latency, network bandwidth, communication, scalability, real-time processing

Dataset

Name: CUHK03; COCO; Penn-Fudan; internal video dataset

Type: Public / private

Dataset size: CUHK03: 14,097 images and 1,467 individuals; COCO: over 200,000 images; Penn-Fudan: 170 images, 345 labeled persons, 423 bounding boxes; internal video: 865 frames

Number of classes: COCO: 80 object categories; CUHK03: 1,467 identities; Penn-Fudan: pedestrian/person detection; internal video: 6 individuals

Input resolution: Internal video: 1920 × 1080; other input resolutions not reported

Data modality: RGB image, video

Metrics

Accuracy: OSNet Rank-1 accuracy: 65.2% on CUHK03-D

mAP: YOLOv10n detection mAP: 0.8157; YOLOv10n AP@0.5: 0.9477; OSNet ReID mAP: 63.4%

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Not reported

FPS: YOLOv10n: 7/22 FPS on Jetson Nano; 17/None FPS on lightweight device

Throughput: Kafka reid_input topic maintained approximately 100 messages/s, maximum 110 messages/s

Model size: Not reported

Parameters: YOLOv10n: 2.7M; OSNet: 2.2M

MACs / FLOPs: YOLOv10n: 8.7B FLOPs

RAM usage: Batch processing 10/10 configuration ended with 51.57% RAM usage on server

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Adaptive frame skipping, ONNX conversion, TensorRT optimization, multithreaded batch processing, Kafka-based distributed buffering, Redis TTL embedding storage

Quantization: Not reported

Pruning: Not reported

Knowledge distillation: No

Compression method: HLS video compression; model compression not reported

Hardware-specific optimization: ONNX model on CPU-based devices; TensorRT model on Jetson Nano

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: No

Communication required during inference: Yes

Candidate for Strict TinyML: No

Reason: The system uses Jetson Nano, CPU-based edge devices, Kafka communication, and a centralized server, without MCU-class deployment or bare-metal/RTOS execution.

Benchmarking / Standardization

Benchmark used: CUHK03-D, Penn-Fudan, COCO, internal video dataset

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: COCO, CUHK03-D, Penn-Fudan

Comparison with baseline models: YOLOv10n compared with YOLOv8n; OSNet compared with LightMBN, HACNN, ResNet50, SCSN, Relation-Net, RGA-SC, HPM, ProNet++, and NFormer; ReID pipeline compared with and without tracking

Comparison with previous works: Yes

Reproducibility artifacts available: code / dataset

Results

Summary: YOLOv10n achieved 0.9477 AP@0.5 and 0.8157 mAP with 2.7M parameters and 8.7B FLOPs. Integrating ByteTrack reduced ID switching from 140 to 3 and wrong ReID instances from 63 to 3 compared with feature matching only. Kafka sustained approximately 100 messages/s in the distributed ReID pipeline.

Limitations

Low-light conditions, long occlusions, and changes in pose, clothing, outfits, or accessories may reduce re-identification performance.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: Yes

Reports latency: No

Reports energy or power: No

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes a hybrid distributed real-time person re-identification and pedestrian tracking system that performs lightweight YOLOv10n detection on edge devices while offloading feature extraction, tracking, identity management, and stream processing to a centralized server.

| Dang et al. | 2025 | Person ReID / tracking / object detection | YOLOv10n + OSNet + ByteTrack | Adaptive frame skipping + batch processing + ONNX/TensorRT | Jetson Nano; 2-core vCPU edge device | CUHK03; COCO; Penn-Fudan; internal video | YOLOv10n mAP 0.8157; OSNet mAP 63.4% | N/A | N/A | 4GB RAM edge; 51.57% server RAM usage | N/A | N/A | PyTorch / ONNX / TensorRT | N/A | None | No |
