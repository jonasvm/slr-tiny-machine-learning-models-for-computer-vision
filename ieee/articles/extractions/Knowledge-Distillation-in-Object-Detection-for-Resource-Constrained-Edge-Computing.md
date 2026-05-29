## Paper ID: Knowledge-Distillation-in-Object-Detection-for-Resource-Constrained-Edge-Computing

TinyML classification: Near-TinyML — evaluated on edge platforms such as Jetson Nano, Orin Nano, and Raspberry Pi 4B, with no explicit MCU-class deployment evidence.

### Basic Info

* Authors: Arief Setyanto; Theopilus Bayu Sasongko; Muhammad Ainul Fikri; Dhani Ariatmanto; I. Made Artha Agastya; Rakandhiya Daanii Rachmanto; Affan Ardana; In Kee Kim
* Year: 2025
* Title: Knowledge Distillation in Object Detection for Resource-Constrained Edge Computing
* Source: IEEE Access, Volume 13, DOI: 10.1109/ACCESS.2025.3534020
* Type: Experimental

### Problem & Context

* Task: Object detection
* Objective: Compress YOLOv4 for resource-constrained edge devices by replacing the CSPDarkNet53 backbone with smaller MobileNetV2 or RepViT backbones trained through knowledge distillation.
* Application domain: Edge object detection, road sign detection, license plate detection, and Mini COCO object detection.
* Scenario: Edge computing, resource-constrained edge devices, on-device inference.
* TinyML relevance: Partial
* TinyML justification: The paper targets compressed on-device object detection on Jetson Nano, Jetson Orin Nano, and Raspberry Pi 4B, but does not report MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, or kilobyte-scale SRAM/Flash deployment.

### Model / Method

* Model: M-YOLO-CRD and RV-YOLO-CRD
* Architecture family: CNN / Hybrid CNN-ViT
* Techniques: Knowledge distillation, contrastive representation distillation, model compression, lightweight backbone replacement.
* Framework: Python 3.10.12, PyTorch 2.0.1, CUDA 11.6
* Training type: Fine-tuning through knowledge distillation
* Inference type: On-device

### Hardware

* Device: NVIDIA Jetson Nano, NVIDIA Jetson Orin Nano, Raspberry Pi 4B
* Hardware type: CPU / GPU / SoC
* Processor / microcontroller: Jetson Nano: 4-core ARM Cortex-A57; Jetson Orin Nano: 6-core ARM Cortex-A78AE v8.2; Raspberry Pi 4B: 4-core ARM Cortex-A72
* Clock frequency: Jetson Nano CPU @ 1.43 GHz and GPU max 921 MHz; Jetson Orin Nano CPU @ 1.5 GHz and GPU max 625 MHz; Raspberry Pi 4B CPU @ 1.5 GHz
* SRAM / RAM: Jetson Nano: 4GB LPDDR4; Jetson Orin Nano: 8GB LPDDR5; Raspberry Pi 4B: 8GB LPDDR4
* Flash / ROM / Storage: Not reported
* Power consumption: Jetson Nano device power range 5W-10W; Jetson Orin Nano device power range 7W-15W; M-YOLO-CRD power usage per frame reported as 1099.34-1141.21 mW on Jetson Nano and 304.93-305.21 mW on Jetson Orin Nano
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Model size, parameters, GFLOPs, latency, memory, CPU usage, GPU usage, and power consumption

### Dataset

* Name: CIFAR-100; Road Sign; Car License Plate; Mini COCO
* Type: Public
* Dataset size: CIFAR-100: 50,000 train and 10,000 test; Road Sign: 702 train and 175 test; Car License Plate: 347 train and 86 test; Mini COCO: 7,000 train and 3,000 test
* Number of classes: CIFAR-100: 100; Road Sign: 4; Car License Plate: 1; Mini COCO: 10
* Input resolution: CIFAR-100: 32 x 32; Road Sign: 245 x 400; Car License Plate: 400 x 300; Mini COCO: vary
* Data modality: Color images / images

### Metrics

* Accuracy: CIFAR-100 CRD accuracy: MobileNetV2 T=6 W=0.5 = 68.33%; MobileNetV2 T=6 W=0.25 = 59.35%; RepViT-M0.6 = 65.71%; ResNet14 = 66.34%; ResNet8 = 58.67%
* mAP: Road Sign mAP@0.5: M-YOLO-CRD = 78.39 ± 0.59, RV-YOLO-CRD = 82.5 ± 0.57; License Plate mAP@0.5: M-YOLO-CRD = 86.08 ± 1.54, RV-YOLO-CRD = 85.13 ± 1.67; Mini COCO mAP@0.5: M-YOLO-CRD = 29.36, RV-YOLO-CRD = 30.46
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: M-YOLO-CRD: 167.118 ms on Jetson Nano for license plate, 168.452 ms on Jetson Nano for road sign, 37.634 ms on Orin Nano for license plate, 37.652 ms on Orin Nano for road sign, 1310.94 ms on Raspberry Pi 4B for license plate, and 1317.24 ms on Raspberry Pi 4B for road sign
* FPS: Around 25 FPS on Orin Nano for M-YOLO-CRD
* Throughput: Not reported
* Model size: YOLOv4-CSPDarkNet53 = 245.53 MB; M-YOLO-CRD = 35.76 MB; RV-YOLO-CRD = 154.03 MB
* Parameters: YOLOv4-CSPDarkNet53 = 64,363,101; M-YOLO-CRD = 9,373,501; RV-YOLO-CRD = 40,377,973
* MACs / FLOPs: YOLOv4-CSPDarkNet53 = 60.527 GFLOPs; M-YOLO-CRD = 6.811 GFLOPs; RV-YOLO-CRD = 28.789 GFLOPs
* RAM usage: Not reported
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: M-YOLO-CRD power usage per frame: 1099.34-1141.21 mW on Jetson Nano and 304.93-305.21 mW on Orin Nano

### Optimization

* Techniques used: Knowledge distillation, contrastive representation distillation, lightweight backbone replacement, model compression
* Quantization: None
* Pruning: No
* Knowledge distillation: Yes
* Compression method: Replacing CSPDarkNet53 with MobileNetV2 or RepViT and transferring knowledge using CRD
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: 35.76 MB for M-YOLO-CRD and 154.03 MB for RV-YOLO-CRD
* Energy per inference reported: Not reported
* Latency on target device reported: Yes
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The deployment uses Linux-based edge devices and embedded GPU/CPU platforms rather than MCU-class, bare-metal, RTOS, TensorFlow Lite Micro, or kilobyte-scale memory-constrained hardware.

### Benchmarking / Standardization

* Benchmark used: CIFAR-100, Road Sign, Car License Plate, Mini COCO
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: CIFAR-100 and Mini COCO
* Comparison with baseline models: Yes, compared against YOLOv4-CSPDarkNet53, YOLOv4-MobileNetV2, YOLOv4-RepViT, M-YOLO-CrossKD, and RV-YOLO-CrossKD
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: M-YOLO-CRD reduced YOLOv4 model size from 245.53 MB to 35.76 MB and reduced GFLOPs from 60.527 to 6.811 with limited mAP loss. On edge devices, M-YOLO-CRD reached 37.6 ms per frame on Orin Nano, about 167-168 ms on Jetson Nano, and about 1310-1317 ms on Raspberry Pi 4B.

### Limitations

* RV-YOLO-CRD achieved higher mAP on some datasets but remained much larger than M-YOLO-CRD and suffered from higher latency.
* Raspberry Pi 4B required more than one second per frame, limiting real-time object detection performance.
* Compressing the entire object detection model is left as future work.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: Yes
* Reports energy or power: Yes
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a YOLOv4 object detection compression method that replaces CSPDarkNet53 with MobileNetV2 or RepViT backbones trained using contrastive representation distillation for resource-constrained edge deployment.

| Paper           | Year | Task             | Model                    | Technique                                                      | Device                                         | Dataset                                            | Main Metric                                                                      | Latency                                                                                                 | Model Size                                         | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| --------------- | ---: | ---------------- | ------------------------ | -------------------------------------------------------------- | ---------------------------------------------- | -------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | -------------------------------------------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Setyanto et al. | 2025 | Object Detection | M-YOLO-CRD / RV-YOLO-CRD | Contrastive representation distillation + backbone replacement | Jetson Nano; Jetson Orin Nano; Raspberry Pi 4B | Road Sign; Car License Plate; Mini COCO; CIFAR-100 | mAP@0.5: 78.39% road sign; 86.08% license plate; 29.36% Mini COCO for M-YOLO-CRD | 37.634-37.652 ms on Orin Nano; 167.118-168.452 ms on Jetson Nano; 1310.94-1317.24 ms on Raspberry Pi 4B | 35.76 MB for M-YOLO-CRD; 154.03 MB for RV-YOLO-CRD | N/A      | N/A   | N/A    | PyTorch   | N/A      | None          | No            |
