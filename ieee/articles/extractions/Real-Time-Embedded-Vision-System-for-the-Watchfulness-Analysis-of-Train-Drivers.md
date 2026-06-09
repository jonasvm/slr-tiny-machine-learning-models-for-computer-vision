Paper ID: Real-Time-Embedded-Vision-System-for-the-Watchfulness-Analysis-of-Train-Drivers

TinyML classification: Near-TinyML — Edge/embedded vision deployment is explicit, but there is no MCU-class or ultra-low-power TinyML evidence.

Basic Info

Authors: Carlo Alberto Avizzano; Paolo Tripicchio; Emanuele Ruffaldi; Alessandro Filippeschi; Juan Manuel Jacinto-Villegas

Year: 2021

Title: Real-Time Embedded Vision System for the Watchfulness Analysis of Train Drivers

Source: IEEE Transactions on Intelligent Transportation Systems, Vol. 22, No. 1, January 2021. 

Type: Experimental

Problem & Context

Task: Driver watchfulness monitoring; face tracking; eye/blink detection

Objective: Monitor train driver watchfulness using a single cockpit camera and provide automated consensus to the train control logic.

Application domain: Railway safety and driver monitoring

Scenario: Embedded onboard train system

TinyML relevance: Partial

TinyML justification: The system performs real-time embedded computer vision fully on-device, but uses an Intel Atom Linux ECU with 4 GB RAM rather than MCU-class TinyML hardware.

Model / Method

Model: Computer vision pipeline using HAAR/HOG face detection, DLib facial landmarking, PERCLOS estimation, polynomial blink detection, and blink filtering

Architecture family: Classical ML / Other

Techniques: Low-computation algorithm design; optimized pupil localization; face detection scheduling; temporal filtering; conservative false-positive rejection

Framework: OpenCV; DLib; Linux Ubuntu 18.04

Training type: Not reported

Inference type: On-device

Hardware

Device: Watchfulness Monitoring System with camera, IR illuminator, embedded computing unit, and custom electronic board

Hardware type: CPU / Other

Processor / microcontroller: Intel Atom x5-Z8350

Clock frequency: 1.44 GHz

SRAM / RAM: 4 GB RAM

Flash / ROM / Storage: 32 GB Flash

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: No

Fully on-device inference: Yes

Constraints mentioned: Real-time processing, safety requirements, hardware selection limitations, illumination variability, false-positive avoidance, latency, and robustness to multiple faces and occlusions

Dataset

Name: Not reported

Type: Private

Dataset size: 353 minutes of preliminary train video recordings and 312 minutes of final real-operation recordings

Number of classes: Not reported

Input resolution: 1920 × 1080 camera resolution

Data modality: Video with RGB/IR image data

Metrics

Accuracy: Watchfulness always correctly recognized in final assessment; average face detection close to 96%

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: Image analysis thread T2 reported 11.0 ms minimum, 31.7 ms typical, and 108.6 ms maximum

FPS: 28 ± 1 FPS when the driver is seated and looking forward; 10 FPS when the driver face cannot be found

Throughput: Not reported

Model size: Not reported

Parameters: Not reported

MACs / FLOPs: Not reported

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Optimized pupil localization, low-computation classical vision pipeline, temporal filtering, face-detection scheduling, blink coherence checks

Quantization: None

Pruning: No

Knowledge distillation: No

Compression method: None

Hardware-specific optimization: Algorithmic choices were made to reduce computational load on the embedded CPU

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Not reported

Energy per inference reported: Not reported

Latency on target device reported: 11.0 ms minimum, 31.7 ms typical, and 108.6 ms maximum for image analysis thread

Runs without full operating system: No

Fully on-device inference: Yes

Communication required during inference: No

Candidate for Strict TinyML: No

Reason: The target hardware is an Intel Atom Linux embedded computer with 4 GB RAM, not an MCU-class or ultra-low-power TinyML platform.

Benchmarking / Standardization

Benchmark used: Real train operation videos; SMI Eye Tracking Glasses 2; manual BORIS annotation

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: Not reported

Comparison with baseline models: HAAR and HOG face detection were compared; WMS blink detection was compared with a commercial eye tracker and manual annotation

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: The embedded system processed camera images in real time and achieved 28 ± 1 FPS under normal seated-driver conditions. In real train operation tests, watchfulness was correctly recognized and blink detection produced no false positives.

Limitations

Higher blink miss rate was reported due to conservative false-positive rejection; other limitations were not explicitly stated.

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

This paper proposes a real-time embedded computer-vision system for train driver watchfulness monitoring using face tracking, eye analysis, PERCLOS-based blink detection, and onboard train-control integration.

| Avizzano et al. | 2021 | Driver monitoring / blink detection | HAAR + HOG + DLib + PERCLOS | Low-compute classical CV and filtering | Intel Atom x5-Z8350 ECU | Private train-operation videos | 0 false positives; watchfulness always correctly recognized | 11.0/31.7/108.6 ms | N/A | 4 GB RAM | 32 GB Flash | N/A | OpenCV / DLib | N/A | None | No |
