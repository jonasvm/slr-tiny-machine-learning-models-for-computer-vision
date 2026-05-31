## Paper ID: Efficient-Edge-AI-for-Next-Generation-Smart-Mirror-Applications

TinyML classification: Near-TinyML — The work uses embedded edge platforms such as NVIDIA AGX Orin/Orin NX, Hailo-8, Versal, and ROS2-based local inference, but does not explicitly target MCU-class deployment.

### Basic Info
- Authors: Nils Kucza, Florian Porrmann, Christian Stollenwerk, Jens Hagemeyer
- Year: 2025
- Title: Efficient Edge AI for Next Generation Smart Mirror Applications
- Source: IEEE Access, DOI: 10.1109/ACCESS.2025.3574492
- Type: Experimental

### Problem & Context
- Task: Object detection, gesture detection, face detection, face identification, emotion recognition
- Objective: Develop and evaluate a locally processed AI-based smart mirror with low-latency interaction, privacy-preserving inference, and energy-efficient embedded deployment.
- Application domain: Smart mirror, smart home, assisted living, human interaction interface
- Scenario: Edge, embedded AIoT, smart home
- TinyML relevance: Partial
- TinyML justification: The paper targets local edge inference on embedded GPUs and AI accelerators with power, latency, energy, pruning, and quantization evaluation, but the main computer vision pipeline is not deployed on MCU-class hardware.

### Model / Method
- Model: YOLOv7 for object and gesture detection; YOLOv4 on Versal; RetinaFace and FaceNet-based models for face detection and identification; emotion detection model from Savchenko et al.
- Architecture family: CNN
- Techniques: Structured pruning, INT8 quantization, FP16 quantization, layer fusion, hardware acceleration, model optimization
- Framework: ROS2, TensorRT, HailoRT, Hailo AI Software Suite, PyTorch, Darknet, TensorFlow, Eclipse Cyclone DDS
- Training type: Transfer learning reported for gesture detection; retraining after pruning reported; object detection training details partially reported
- Inference type: On-device

### Hardware
- Device: NVIDIA AGX Orin, NVIDIA AGX Xavier, NVIDIA Orin NX, Hailo-8 accelerator, AMD/Xilinx Versal AI Core/Edge, Intel RealSense D415, Arduino Nano RP2040 Connect for keyword spotting
- Hardware type: GPU, NPU, FPGA, SoC, MCU
- Processor / microcontroller: NVIDIA AGX Orin with Cortex-A78AE cores; Orin NX with Cortex-A78AE cores; Versal with Cortex-A72/R5F; Hailo-8 with Cortex-M4 for data-flow management; Arduino Nano RP2040 Connect for microphone keyword spotting
- Clock frequency: AGX Orin up to 2.2 GHz; Orin NX up to 2.0 GHz; Versal A72/R5F 1.7/0.75 GHz; Hailo-8 clock not reported
- SRAM / RAM: AGX Orin 32 GB or 64 GB RAM; Orin NX 16 GB RAM; AGX Xavier 32 GB RAM; Versal 8 GB RAM; Hailo-8 32 MB SRAM
- Flash / ROM / Storage: Not reported
- Power consumption: Optimized AGX Orin + Hailo-8 setup consumes around 38 W; Hailo-8 object detection benchmark reports 2.82 W for the 60%-sized object model; AGX Orin gesture benchmark reports 44.5 W for the 15%-sized gesture model
- Energy per inference: Optimized full application reports 1.3 mJ per frame; 60%-sized object detection on Hailo-8 reports 44.48 mJ per frame; 15%-sized gesture detection on AGX Orin reports 173.93 mJ per frame
- Execution without full OS: Not reported
- Fully on-device inference: Yes
- Constraints mentioned: Latency, FPS, power consumption, energy efficiency, GFLOPs, model size, communication, privacy, hardware utilization, cooling

### Dataset
- Name: COCO; self-created hand gesture dataset; Google Speech Commands for keyword spotting
- Type: COCO is public; hand gesture dataset is self-created; Google Speech Commands is public
- Dataset size: COCO has over 200,000 images; hand gesture dataset has around 2,800 images per gesture class and Figure 6 reports around 4,000 labeled images per class
- Number of classes: COCO has 80 classes; hand gesture dataset has 19 gestures for each hand and includes face-related labels, with the paper reporting 41/42 total trained classes
- Input resolution: 640 × 640 pixels for YOLO-based object and gesture detection; 40 × 49 spectrogram input for keyword spotting
- Data modality: RGB image, RGB-D image, depth image, audio spectrogram

### Metrics
- Accuracy: Not reported as a primary classification metric
- mAP: Object detection 60%-sized YOLOv7 reports 65.9% mAP@0.5 and 46.7% mAP@0.5:0.95; gesture detection 15%-sized YOLOv7 reports 93.6% mAP@0.5 and 72.9% mAP@0.5:0.95 in Table 4
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: 60%-sized object model on Hailo-8 reports 15.03 ms; 15%-sized gesture model on AGX Orin reports 4.41 ms; full detection pipeline reports 135.7 ms; image visualization reports around 206 ms
- FPS: Full optimized application achieves 30 FPS; 60%-sized object model on Hailo-8 reaches 63 FPS; 15%-sized gesture model on AGX Orin reaches 255 FPS
- Throughput: 30 FPS for the full application; 63 FPS for object detection on Hailo-8; 255 FPS for gesture detection on AGX Orin
- Model size: Object detection 60%-sized YOLOv7 has 22.6M parameters; gesture detection 15%-sized YOLOv7 has 5.5M parameters
- Parameters: Object detection 60%-sized YOLOv7 has 22.6M parameters; gesture detection 15%-sized YOLOv7 has 5.5M parameters
- MACs / FLOPs: Object detection 60%-sized YOLOv7 requires 63 GFLOPs; gesture detection 15%-sized YOLOv7 requires 15.9 GFLOPs
- RAM usage: Object detection 60%-sized YOLOv7 reports 354.0 MB VRAM; gesture detection 15%-sized YOLOv7 reports 202.12 MB VRAM
- Flash usage: Not reported
- Energy per inference: Full optimized application reports 1.3 mJ per frame; object detection on Hailo-8 reports 44.48 mJ per frame; gesture detection on AGX Orin reports 173.93 mJ per frame
- Power consumption: Full optimized AGX Orin + Hailo-8 setup reports 38 W; object detection on Hailo-8 reports 2.82 W; gesture detection on AGX Orin reports 44.5 W

### Optimization
- Techniques used: Structured pruning, INT8 quantization, FP16 quantization, TensorRT optimization, Hailo hardware optimization, layer fusion, heterogeneous hardware acceleration
- Quantization: INT8 for Hailo-8; FP16 for Jetson modules; 8-bit quantization for microcontroller keyword spotting
- Pruning: Yes
- Knowledge distillation: No
- Compression method: Structured pruning using Embedl Model Optimization SDK
- Hardware-specific optimization: TensorRT for NVIDIA Jetson systems; Hailo AI Software Suite and HailoRT for Hailo-8; Versal-specific deployment with YOLOv4
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported; Hailo-8 hardware SRAM is listed as 32 MB
- Flash usage reported: Not reported
- Model size reported: Object detection 60%-sized YOLOv7 has 22.6M parameters and 63 GFLOPs; gesture detection 15%-sized YOLOv7 has 5.5M parameters and 15.9 GFLOPs
- Energy per inference reported: Full optimized application reports 1.3 mJ per frame; object detection reports 44.48 mJ per frame; gesture detection reports 173.93 mJ per frame
- Latency on target device reported: Yes
- Runs without full operating system: Not reported
- Fully on-device inference: Yes
- Communication required during inference: No cloud communication is required; local ROS2 communication and local device-to-device data transfer are used
- Candidate for Strict TinyML: No
- Reason: The main computer vision inference pipeline runs on embedded GPU, accelerator, FPGA, and SoC platforms rather than MCU-class or OS-free TinyML hardware.

### Benchmarking / Standardization
- Benchmark used: COCO object detection benchmark; self-created hand gesture dataset; hardware latency/FPS/power benchmarks
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: COCO; Google Speech Commands for keyword spotting
- Comparison with baseline models: Yes, compared against unpruned YOLOv7, YOLOv7-Tiny, MobileNetV2/3 with SSD, and EfficientDet variants
- Comparison with previous works: Yes
- Reproducibility artifacts available: code

### Results
- Summary: The optimized smart mirror runs object, gesture, and face detection locally at 30 FPS using an AGX Orin coupled with a Hailo-8 accelerator. Structured pruning reduces object detection GFLOPs to 60% with limited mAP loss and improves gesture detection accuracy for relevant classes while maintaining efficient embedded inference.

### Limitations
- No formal limitations section is reported.
- Orin NX results are preliminary, and the paper reports that cooling improvements are needed because initial tests reached over 80 °C under full load.
- Future work includes evaluating newer YOLO versions, deeper pruning analysis, additional accelerators, RISC-V systems, and further u.RECS integration.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: Yes
- Reports latency: Yes
- Reports energy or power: Yes
- Reports model size: Yes
- Reports optimization method: Yes
- Reports deployment framework: Yes
- Reports dataset and preprocessing: Yes
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes an energy-efficient edge-AI smart mirror architecture that performs local object, gesture, face, and speech-related interaction using pruned neural networks deployed on heterogeneous embedded hardware and AI accelerators.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Kucza et al. | 2025 | Object, gesture, and face detection/recognition | YOLOv7, RetinaFace, FaceNet | Structured pruning + INT8/FP16 hardware optimization | NVIDIA AGX Orin + Hailo-8 | COCO + self-created gesture dataset | Object mAP@0.5 65.9%; gesture mAP@0.5 93.6% | Object 15.03 ms; gesture 4.41 ms; full detection 135.7 ms | Object 22.6M params; gesture 5.5M params | 32 GB RAM / Hailo-8 32 MB SRAM; model VRAM 354.0 MB and 202.12 MB | N/A | 1.3 mJ/frame full app; object 44.48 mJ/frame | ROS2 + TensorRT + HailoRT | INT8/FP16 | None | No |
