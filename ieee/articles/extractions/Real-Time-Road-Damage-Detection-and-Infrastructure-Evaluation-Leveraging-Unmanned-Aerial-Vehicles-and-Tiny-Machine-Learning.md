## Paper ID: Real-Time-Road-Damage-Detection-and-Infrastructure-Evaluation-Leveraging-Unmanned-Aerial-Vehicles-and-Tiny-Machine-Learning

TinyML classification: Near-TinyML — The paper discusses TinyML and resource-constrained UAV/edge devices, but does not report explicit MCU-class deployment, SRAM/Flash constraints, TFLM/CMSIS-NN use, or on-device embedded inference.

### Basic Info

* Authors: Muhammad Waseem Khan, Mohammad S. Obaidat, Khalid Mahmood, Dania Batool, Hafiz Muhammad Sanaullah Badar, Muhammad Aamir, Wu Gao
* Year: 2024
* Title: Real-Time Road Damage Detection and Infrastructure Evaluation Leveraging Unmanned Aerial Vehicles and Tiny Machine Learning
* Source: IEEE Internet of Things Journal, Vol. 11, No. 12, 15 June 2024
* Type: Experimental

### Problem & Context

* Task: Object detection
* Objective: Detect and monitor road damages and support infrastructure evaluation using UAV and dashboard-camera imagery.
* Application domain: Road damage detection and infrastructure evaluation
* Scenario: UAV, edge/IoT, autonomous system
* TinyML relevance: Partial
* TinyML justification: The paper frames the problem around TinyML for low-power, resource-constrained UAVs and edge/IoT devices, but the experiments are performed on Google Colab Pro-Plus with an NVIDIA A100 GPU, and no MCU-level deployment, memory footprint, or on-device inference evidence is reported.

### Model / Method

* Model: Faster R-CNN ResNet101, YOLOv5, SSD MobileNet V1 FPN, EfficientDet D1
* Architecture family: CNN
* Techniques: Data augmentation, L2 regularization, fine-tuning, one-stage and two-stage object detection
* Framework: Not reported
* Training type: Fine-tuning
* Inference type: Not reported

### Hardware

* Device: Google Collaboratory Pro-Plus
* Hardware type: GPU / CPU
* Processor / microcontroller: NVIDIA A100-SXM GPU; Intel Xeon @ 2.20 GHz CPU
* Clock frequency: 2.20 GHz
* SRAM / RAM: 54.8 GB RAM
* Flash / ROM / Storage: Not reported
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Not reported
* Constraints mentioned: Resource constraints, low power, computational cost, class imbalance, latency/real-time monitoring

### Dataset

* Name: RDD2022
* Type: Public
* Dataset size: About 47,000 images in the full dataset; subset used contains images from China, Japan, and the United States, with 2,000 images per country subset and one mixed set
* Number of classes: 5 classes used: D00, D10, D20, D40, Repair
* Input resolution: 640 × 640
* Data modality: RGB images from UAVs and dashboard cameras

### Metrics

* Accuracy: Not reported
* mAP: Faster R-CNN ResNet101: 88.49% on mixed dataset; EfficientDet D1: 86.47% overall on mixed dataset and 95.12% for focused classes; YOLOv5: 84.41%; SSD MobileNet V1 FPN: 81.35%
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Not reported
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: 54.8 GB system RAM reported for experimental setup, not model inference RAM
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Data augmentation, L2 regularization, focal loss in EfficientDet D1, BiFPN feature fusion, compound scaling
* Quantization: Not reported
* Pruning: Not reported
* Knowledge distillation: Not reported
* Compression method: Not reported
* Hardware-specific optimization: Not reported
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: Not reported
* Use of MLPerf Tiny: Not reported

### Strict TinyML Evidence

* SRAM peak reported: Not reported
* Flash usage reported: Not reported
* Model size reported: Not reported
* Energy per inference reported: Not reported
* Latency on target device reported: Not reported
* Runs without full operating system: Not reported
* Fully on-device inference: Not reported
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: Although the paper uses TinyML terminology and discusses UAVs as low-power/resource-constrained devices, it does not report deployment on MCU-class hardware, TensorFlow Lite Micro/CMSIS-NN usage, on-device inference, SRAM/Flash usage, energy, power, or latency on a target embedded device.

### Benchmarking / Standardization

* Benchmark used: RDD2022
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: COCO, VOC, and KITTI are mentioned as benchmark datasets in the background for Faster R-CNN, but they are not used as the experimental benchmark in this paper.
* Comparison with baseline models: Yes
* Comparison with previous works: Yes
* Reproducibility artifacts available: Dataset

### Results

* Summary: Faster R-CNN ResNet101 achieved the highest overall mAP of 88.49% on the mixed dataset. EfficientDet D1 achieved 86.47% overall mAP and 95.12% mAP for focused classes, with the paper emphasizing its lower computational cost and better efficiency among one-stage detectors.

### Limitations

* No MCU-level or embedded-device deployment is reported.
* No latency, FPS, model size, SRAM/Flash usage, power, or energy-per-inference metrics are reported.
* The paper reports GPU-based experimental setup rather than deployment on a low-power target device.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: No
* Reports latency: No
* Reports energy or power: No
* Reports model size: No
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes an experimental comparison of Faster R-CNN ResNet101, YOLOv5, SSD MobileNet V1 FPN, and EfficientDet D1 for road damage detection and infrastructure evaluation using the RDD2022 dataset, with data augmentation to address class imbalance.

| Paper       | Year | Task             | Model                                                                 | Technique                                                    | Device                                     | Dataset | Main Metric                                                | Latency | Model Size | SRAM/RAM                       | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ----------- | ---: | ---------------- | --------------------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------ | ------- | ---------------------------------------------------------- | ------- | ---------- | ------------------------------ | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Khan et al. | 2024 | Object detection | Faster R-CNN ResNet101; YOLOv5; SSD MobileNet V1 FPN; EfficientDet D1 | Data augmentation; L2 regularization; BiFPN/compound scaling | Google Colab Pro-Plus, NVIDIA A100-SXM GPU | RDD2022 | mAP 88.49% overall; EfficientDet D1 95.12% focused classes | N/A     | N/A        | 54.8 GB RAM experimental setup | N/A   | N/A    | N/A       | N/A      | N/A           | No            |
