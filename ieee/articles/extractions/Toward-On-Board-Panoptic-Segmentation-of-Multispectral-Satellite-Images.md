Paper ID: Toward-On-Board-Panoptic-Segmentation-of-Multispectral-Satellite-Images

TinyML classification: Near-TinyML — evaluated for resource-constrained on-board edge processing on Jetson Nano, with no explicit MCU-class deployment.

Basic Info

Authors: Tharindu Fernando; Clinton Fookes; Harshala Gammulle; Simon Denman; Sridha Sridharan

Year: 2023

Title: Toward On-Board Panoptic Segmentation of Multispectral Satellite Images

Source: IEEE Transactions on Geoscience and Remote Sensing, Vol. 61, 2023 

Type: Experimental / Methodological / Benchmark

Problem & Context

Task: Panoptic segmentation

Objective: Evaluate and improve on-board panoptic segmentation of multispectral satellite images using a lightweight single-frame student model guided by a multimodal teacher.

Application domain: Remote sensing / satellite image analysis / agricultural land monitoring

Scenario: On-board satellite processing / edge embedded GPU

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained on-board inference and evaluates deployment on NVIDIA Jetson Nano, but does not target MCU-class TinyML hardware.

Model / Method

Model: U-TAE + PAPS student network with Cross Attention Fusion teacher

Architecture family: Hybrid CNN

Techniques: Online knowledge distillation; cross-modality attention fusion; lightweight unimodal student network

Framework: PyTorch

Training type: From scratch

Inference type: On-device

Hardware

Device: NVIDIA Jetson Nano GPU

Hardware type: GPU / SoC

Processor / microcontroller: NVIDIA Jetson Nano GPU

Clock frequency: Not reported

SRAM / RAM: 4 GB 64-bit LPDDR4 memory

Flash / ROM / Storage: 32 GB microSD card

Power consumption: 5–10 W

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Limited on-board resources; compute; power; latency; communication bandwidth; loss of temporal observations

Dataset

Name: PASTIS; PASTIS-R

Type: Public

Dataset size: 2433 multispectral image patches

Number of classes: 20 semantic classes

Input resolution: 128 × 128 pixels

Data modality: Multispectral satellite image time series; radar + multispectral for PASTIS-R; single multispectral frame for student inference

Metrics

Accuracy: Not reported

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 15.90 s/image on NVIDIA Jetson Nano; 0.37 s run time for U-TAE + PAPS student with Cross Attention Fusion teacher in reported experiments

FPS: Not reported

Throughput: Not reported

Model size: Not reported

Parameters: 1.2M for U-TAE + PAPS student; 2.4M for Cross Attention Fusion teacher

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: 5–10 W on NVIDIA Jetson Nano

Optimization

Techniques used: Online knowledge distillation; cross-modality attention fusion; lightweight student model

Quantization: None

Pruning: No

Knowledge distillation: Yes

Compression method: Knowledge distillation from multimodal time-series teacher to unimodal single-frame student

Hardware-specific optimization: Batch size set to one for Jetson Nano evaluation

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 15.90 s/image on NVIDIA Jetson Nano

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The deployment target is a Linux-based NVIDIA Jetson Nano with 4 GB RAM, not an MCU-class or bare-metal/RTOS TinyML device.

Benchmarking / Standardization

Benchmark used: PASTIS; PASTIS-R

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: PASTIS; PASTIS-R

Comparison with baseline models: Yes

Comparison with previous works: Yes

Reproducibility artifacts available: Dataset

Results

Summary: The proposed online knowledge distillation framework improved SQ, RQ, and PQ by 10.7%, 11.9%, and 10.6% compared with the baseline U-TAE + PAPS single-frame unimodal model. On Jetson Nano, the student model generated panoptic outputs in 15.90 s/image.

Limitations

The authors state that the work is not a complete solution for on-board panoptic segmentation. Deployment on Intel Movidius Myriad 2 VPU was not completed because custom layers caused model translation problems.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: Yes

Reports model size: No

Reports optimization method: Yes

Reports deployment framework: Yes

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: Yes

Contribution

This paper proposes an online cross-modality knowledge distillation framework for on-board panoptic segmentation of multispectral satellite images using a lightweight unimodal student guided by a multimodal time-series teacher.

| Fernando et al. | 2023 | Panoptic segmentation | U-TAE + PAPS student | Online knowledge distillation | NVIDIA Jetson Nano | PASTIS-R | PQ 24.4 | 15.90 s/image | N/A | 4 GB LPDDR4 | N/A | N/A | PyTorch | N/A | None | No |
