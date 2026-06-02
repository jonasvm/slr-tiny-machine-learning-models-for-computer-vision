## Paper ID: Optimized-YOLO-architectures-for-efficient-Kiwi-detection-in-precision-agriculture-on-embedded-systems

TinyML classification: Near-TinyML — the deployment target is Jetson TX2 edge hardware, not an explicitly MCU-class or TensorFlow Lite Micro platform.

### Basic Info
- Authors: Berat Karacaoglu; Muhammet Emin Sahin
- Year: 2025
- Title: Optimized YOLO architectures for efficient Kiwi detection in precision agriculture on embedded systems
- Source: Scientific Reports, 15:45113
- Type: Benchmark

### Problem & Context
- Task: Object detection
- Objective: Benchmark YOLOv8–YOLOv11 architectures and optimize lightweight YOLO models for kiwi fruit detection on embedded hardware.
- Application domain: Precision agriculture
- Scenario: Embedded edge AI
- TinyML relevance: Partial
- TinyML justification: The paper evaluates on-device object detection on NVIDIA Jetson TX2, but does not target MCU-class deployment or report TinyML-level SRAM/Flash constraints.

### Model / Method
- Model: YOLOv8, YOLOv9, YOLOv10, YOLOv11; best reported optimized model is YOLOv11s-HPO.
- Architecture family: CNN / Hybrid CNN-Transformer
- Techniques: Hyperparameter optimization using Ultralytics model.tune with Random Search, Bayesian Optimization, and Evolutionary search.
- Framework: Ultralytics YOLO; Python; CUDA-enabled GPU; JetPack SDK support reported for Jetson TX2.
- Training type: Not reported
- Inference type: On-device

### Hardware
- Device: NVIDIA Jetson TX2
- Hardware type: SoC / GPU / CPU
- Processor / microcontroller: 256-core NVIDIA Pascal GPU; 6-core CPU with 2× Denver 2 and 4× ARM Cortex-A57
- Clock frequency: Not reported
- SRAM / RAM: 8 GB LPDDR4
- Flash / ROM / Storage: 32 GB eMMC
- Power consumption: 7.5–15 W typical operation
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Yes
- Constraints mentioned: Latency, compute, resource constraints, hardware compatibility, embedded deployment suitability.

### Dataset
- Name: Kiwifruit dataset from orchards in Samsun, Turkey / GitHub kivi dataset
- Type: Public
- Dataset size: 66 training images with 2,925 annotations; 40 test images with 1,936 annotations
- Number of classes: 1
- Input resolution: Original 512×512; resized to 640×640
- Data modality: RGB image

### Metrics
- Accuracy: Not reported
- mAP: YOLOv11s-HPO mAP@0.5 = 0.956; mAP@0.5:0.95 = 0.644
- Precision: YOLOv11s-HPO = 0.883
- Recall: YOLOv11s-HPO = 0.899
- F1-score: YOLOv11s-HPO = 0.891
- Latency: YOLOv11s-HPO average inference time = 3.333 s/image on Jetson TX2
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: 7.5–15 W typical Jetson TX2 operation

### Optimization
- Techniques used: Hyperparameter optimization of YOLOv8s, YOLOv9s, YOLOv10s, and YOLOv11s.
- Quantization: None
- Pruning: No
- Knowledge distillation: No
- Compression method: Not reported
- Hardware-specific optimization: Not reported
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: Not reported
- Latency on target device reported: 3.333 s/image on Jetson TX2 for YOLOv11s-HPO
- Runs without full operating system: No
- Fully on-device inference: Yes
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The target device is NVIDIA Jetson TX2 running an Ubuntu-based Linux environment, with no MCU-class deployment, TensorFlow Lite Micro, CMSIS-NN, or SRAM/Flash-constrained execution reported.

### Benchmarking / Standardization
- Benchmark used: Custom kiwifruit detection benchmark using YOLOv8–YOLOv11 variants.
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes
- Comparison with previous works: Yes
- Reproducibility artifacts available: Dataset

### Results
- Summary: The optimized YOLOv11s model achieved the best accuracy-efficiency trade-off, reaching mAP@0.5 = 0.956 and 3.333 s/image on Jetson TX2. Larger YOLO variants achieved similar or slightly higher accuracy but were impractical for low-latency embedded deployment due to high inference time.

### Limitations
- The dataset is relatively small and limited in environmental diversity.
- Real-time embedded evaluation used pre-collected images rather than continuous video streams.
- The study focused mainly on YOLO architectures and did not benchmark alternative lightweight detectors.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a YOLOv8–YOLOv11 benchmarking and hyperparameter optimization pipeline for embedded kiwi fruit detection on NVIDIA Jetson TX2.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Karacaoglu et al. | 2025 | Object detection | YOLOv11s-HPO | Hyperparameter optimization | NVIDIA Jetson TX2 | Public kiwifruit dataset | mAP@0.5 = 0.956 | 3.333 s/image | N/A | 8 GB LPDDR4 | 32 GB eMMC | N/A | Ultralytics YOLO / JetPack SDK | N/A | None | No |
