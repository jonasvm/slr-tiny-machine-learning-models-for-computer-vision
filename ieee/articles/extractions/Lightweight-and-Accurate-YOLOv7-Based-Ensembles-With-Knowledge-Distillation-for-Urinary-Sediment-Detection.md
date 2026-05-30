## Paper ID: Lightweight-and-Accurate-YOLOv7-Based-Ensembles-With-Knowledge-Distillation-for-Urinary-Sediment-Detection

TinyML classification: Near-TinyML — The paper targets lightweight edge/resource-constrained medical-device vision deployment, but does not explicitly report MCU-class hardware, Cortex-M/TFLM deployment, or MCU-level memory constraints.

### Basic Info
- Authors: Keita Sasaki; Hiroki Nishikawa; Ittetsu Taniguchi; Takao Onoye
- Year: 2025
- Title: Lightweight and Accurate YOLOv7-Based Ensembles With Knowledge Distillation for Urinary Sediment Detection
- Source: IEEE Access, Volume 13, 2025, DOI: 10.1109/ACCESS.2025.3574169
- Type: Experimental

### Problem & Context
- Task: Object detection
- Objective: Improve urinary sediment particle detection accuracy while reducing model size for resource-constrained deployment.
- Application domain: Medical image analysis / urinary sediment analysis
- Scenario: Resource-constrained clinical hardware / medical devices
- TinyML relevance: Partial
- TinyML justification: The paper targets lightweight object detection and model-size reduction for resource-constrained medical devices, but does not report MCU-class deployment or TinyML-specific runtime evidence.

### Model / Method
- Model: Ensemble of two distilled YOLOv7-tiny student models derived from YOLOv7-CBAM and YOLOv7-SE teachers, fused with Weighted Boxes Fusion.
- Architecture family: CNN
- Techniques: Ensemble learning, feature-based knowledge distillation, attention modules, Weighted Boxes Fusion, model-size reduction
- Framework: PyTorch
- Training type: Not reported
- Inference type: Not reported

### Hardware
- Device: Ubuntu workstation with NVIDIA RTX A2000 GPU; local PC with NVIDIA RTX A2000 GPU for ensemble-only experiments
- Hardware type: CPU / GPU
- Processor / microcontroller: AMD EPYC 7313; Intel Core i7-11700 for ensemble-only experiments
- Clock frequency: 2.50 GHz for Intel Core i7-11700; AMD EPYC clock frequency not reported
- SRAM / RAM: 12 GB GPU VRAM; system RAM not reported
- Flash / ROM / Storage: Not reported
- Power consumption: Not reported
- Energy per inference: Not reported
- Execution without full OS: No
- Fully on-device inference: Not reported
- Constraints mentioned: Model size, memory consumption, computational cost, resource-constrained clinical hardware

### Dataset
- Name: Urine Sediment Dataset (USD)
- Type: Not reported
- Dataset size: 5,376 images; 4,256 training, 852 validation, and 268 testing images
- Number of classes: 7
- Input resolution: Not reported
- Data modality: Microscopic urinary sediment images

### Metrics
- Accuracy: Not reported
- mAP: 0.920 mAP@0.5
- Precision: 84.6%
- Recall: 88.1%
- F1-score: Not reported
- Latency: Not reported
- FPS: Not reported
- Throughput: Not reported
- Model size: Approximately one-third of YOLOv7-CBAM; exact size not reported in text
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: Not reported
- Power consumption: Not reported

### Optimization
- Techniques used: Feature-based knowledge distillation, YOLOv7-tiny student models, ensemble learning, Weighted Boxes Fusion
- Quantization: None reported
- Pruning: No
- Knowledge distillation: Yes
- Compression method: Feature-based knowledge distillation from YOLOv7-CBAM and YOLOv7-SE teachers to YOLOv7-tiny students
- Hardware-specific optimization: Not reported
- Use of CMSIS-NN: Not reported
- Use of TensorFlow Lite Micro: Not reported
- Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Approximately one-third of YOLOv7-CBAM; exact size not reported in text
- Energy per inference reported: Not reported
- Latency on target device reported: Not reported
- Runs without full operating system: No
- Fully on-device inference: Not reported
- Communication required during inference: Not reported
- Candidate for Strict TinyML: No
- Reason: The paper targets lightweight and resource-constrained deployment but evaluates on Ubuntu GPU workstations and does not report MCU-class hardware, SRAM/Flash usage, energy, latency on embedded target, TFLM, or bare-metal/RTOS deployment.

### Benchmarking / Standardization
- Benchmark used: Urine Sediment Dataset (USD)
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: Not reported
- Comparison with baseline models: Yes; YOLOv7, YOLOv7-tiny, YOLOv7-CBAM, YOLOv7-SE, and distilled YOLOv7-tiny variants
- Comparison with previous works: Yes; Faster R-CNN, YOLOv5s-CBL, YOLOv8n, YOLOv8x, YOLO11n, YOLO11x, and YOLOv7-CBAM
- Reproducibility artifacts available: Not reported

### Results
- Summary: The proposed model achieved 84.6% precision, 88.1% recall, and 0.920 mAP@0.5 on the USD dataset. It outperformed YOLOv7-tiny and achieved accuracy comparable to or better than larger YOLO-based models while reducing model size to approximately one-third of YOLOv7-CBAM.

### Limitations
- The USD dataset was collected under specific conditions, and generalizability to other imaging settings or institutions was not verified.
- The limited number of rare abnormal samples may affect robustness.
- The effectiveness of the method on other lightweight architectures remains unexplored.
- Class-specific weaknesses remain for cryst, cast, epithn, epith, and leuko.
- Weighted Boxes Fusion may dampen the unique strengths of individual models.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: No
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: No

### Contribution
- This paper proposes a lightweight YOLOv7-based urinary sediment detection framework that distills attention-enhanced YOLOv7 teacher models into YOLOv7-tiny student models and fuses their predictions with Weighted Boxes Fusion.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Sasaki et al. | 2025 | Object Detection | Distilled YOLOv7-tiny ensemble | Feature-based knowledge distillation + ensemble/WBF | NVIDIA RTX A2000 GPU | USD | mAP@0.5 = 0.920 | N/A | ~1/3 of YOLOv7-CBAM | N/A | N/A | N/A | PyTorch | N/A | N/A | No |
