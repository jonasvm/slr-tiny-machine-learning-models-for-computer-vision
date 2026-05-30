## Paper ID: Affordance-Segmentation-Using-Tiny-Networks-for-Sensing-Systems-in-Wearable-Robotic-Devices

TinyML classification: Strict TinyML — It explicitly targets microcontrollers, reports STM32F746G-DISCO deployment, and constrains inference time and model complexity for embedded operation.

### Basic Info

* Authors: Edoardo Ragusa; Strahinja Dosen; Rodolfo Zunino; Paolo Gastaldo
* Year: 2023
* Title: Affordance Segmentation Using Tiny Networks for Sensing Systems in Wearable Robotic Devices
* Source: IEEE Sensors Journal, Vol. 23, No. 19, pp. 23916–23926, 1 October 2023. DOI: 10.1109/JSEN.2023.3308615.
* Type: Methodological

### Problem & Context

* Task: Segmentation
* Objective: Design tiny deep neural networks for affordance segmentation that can run effectively on microcontroller-like processing units in wearable robotic devices.
* Application domain: Wearable robotics, prostheses, exoskeletons, supernumerary limbs, semiautomatic grasping assistance.
* Scenario: Embedded, wearable, microcontroller-based teleceptive sensing system.
* TinyML relevance: Yes
* TinyML justification: The paper explicitly targets microcontroller-class deployment, tiny CNNs, hardware-aware NAS, limited processing power, latency constraints, and STM32F746G-DISCO deployment.

### Model / Method

* Model: HW-NAS-generated tiny CNNs for affordance segmentation.
* Architecture family: CNN
* Techniques: Hardware-aware neural architecture search, evolutionary NAS, hardware-friendly search space, empirical FLOPs-latency modeling, tiny CNN design.
* Framework: TensorFlow Lite; STM32 X-Cube-AI
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: stm32f746g-disco board
* Hardware type: MCU
* Processor / microcontroller: STM32F746NG microcontroller with Cortex-M7 32-bit RISC core and single-precision floating-point unit.
* Clock frequency: Not reported
* SRAM / RAM: Exact capacity not reported; RAM occupation is reported graphically in KiB.
* Flash / ROM / Storage: Exact capacity not reported; flash occupation is reported graphically in KiB.
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: Not reported
* Fully on-device inference: Yes
* Constraints mentioned: Memory, latency, FLOPs, limited processing power, network complexity, wearable device constraints.

### Dataset

* Name: UMD; Multi-View (MV); IIT
* Type: Benchmark datasets
* Dataset size: UMD: 28,843 RGB-D images; MV: 23,605 RGB-D images; IIT: 8,835 images.
* Number of classes: Three pixelwise classes for learning: grasp, do not grasp, and background; UMD has seven object categories; MV has 37 object classes; IIT object-class count not reported.
* Input resolution: NAS selected input sizes between 36 and 48 pixels; original input resolution not reported.
* Data modality: RGB images; UMD and MV datasets contain RGB-D images, but the study uses RGB inputs.

### Metrics

* Accuracy: Pixelwise accuracy reported for background / grasp / do-not-grasp. UMD Prop1S: 0.980 / 0.827 / 0.863; UMD Prop0.5S: 0.989 / 0.820 / 0.880. MV Prop1S: 0.970 / 0.804 / 0.618; MV Prop0.5S: 0.967 / 0.813 / 0.563. IIT Prop1S: 0.970 / 0.459 / 0.686; IIT Prop0.5S: 0.970 / 0.421 / 0.654.
* mAP: Not reported
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Smaller than 0.25 s reported for the generated networks on stm32f746g-disco; smallest generated network achieved 0.21 s.
* FPS: Not reported
* Throughput: Not reported
* Model size: Not reported as file size.
* Parameters: Prop1S / Prop0.5S parameters reported as 10.8K / 18.9K on UMD, 50.8K / 15.5K on MV, and 55.3K / 27.4K on IIT.
* MACs / FLOPs: Prop1S / Prop0.5S FLOPs reported as 12.46M / 7.02M on UMD, 13.65M / 5.91M on MV, and 12.63M / 6.66M on IIT.
* RAM usage: Reported graphically in KiB; exact values not tabulated.
* Flash usage: Reported graphically in KiB; exact values not tabulated.
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Hardware-aware NAS, empirical FLOPs/inference-time constraint, hardware-friendly search space, evolutionary architecture search, TensorFlow Lite conversion, STM32 X-Cube-AI optimization, memory indexing for external memory when necessary.
* Quantization: FP32
* Pruning: No
* Knowledge distillation: No
* Compression method: Tiny architecture design through hardware-aware NAS.
* Hardware-specific optimization: Yes
* Use of CMSIS-NN: Not reported
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Reported graphically as RAM occupation in KiB; exact values not tabulated.
* Flash usage reported: Reported graphically as flash occupation in KiB; exact values not tabulated.
* Model size reported: Parameters reported in Table I; file size not reported.
* Energy per inference reported: Not reported
* Latency on target device reported: Yes; smaller than 0.25 s, with the smallest generated network achieving 0.21 s.
* Runs without full operating system: Not reported
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: Yes
* Reason: The paper explicitly deploys tiny CNNs on an STM32F746G-DISCO microcontroller board and reports MCU-level latency, FLOPs, parameters, RAM, and flash constraints.

### Benchmarking / Standardization

* Benchmark used: UMD; MV; IIT affordance segmentation datasets.
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: UMD; MV; IIT
* Comparison with baseline models: Yes; MobileNetV3, TinySeg, EfficientNetB0 with UNet head, VGG16 with UNet head, and SegFormer.
* Comparison with previous works: Yes
* Reproducibility artifacts available: Code / model artifacts; generated architectures are reported as available on GitHub.

### Results

* Summary: The proposed HW-NAS tiny CNNs achieved affordance segmentation on foreground object images with accuracy comparable to larger baselines for the grasp and background classes while substantially reducing FLOPs, parameters, and latency. The generated networks were deployed on stm32f746g-disco and completed inference in less than 250 ms.

### Limitations

* The work only considered RGB inputs, although RGB-D inputs may improve segmentation at higher computational cost.
* The analysis did not fully address framing, occlusion, and illumination issues.
* The generated tiny networks are useful as modules in a larger control pipeline but are not presented as a stand-alone complete grasping solution.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: Yes
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: Yes

### Contribution

* This paper proposes a hardware-aware NAS strategy for designing tiny CNNs that perform affordance segmentation on microcontroller-based wearable robotic sensing systems.

| Paper         | Year | Task         | Model            | Technique          | Device           | Dataset      | Main Metric                                                 | Latency                  | Model Size             | SRAM/RAM                    | Flash                       | Energy | Framework               | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------- | ---: | ------------ | ---------------- | ------------------ | ---------------- | ------------ | ----------------------------------------------------------- | ------------------------ | ---------------------- | --------------------------- | --------------------------- | ------ | ----------------------- | -------- | ------------- | ------------- |
| Ragusa et al. | 2023 | Segmentation | HW-NAS tiny CNNs | Hardware-aware NAS | stm32f746g-disco | UMD; MV; IIT | Pixelwise accuracy: UMD grasp 0.827 Prop1S / 0.820 Prop0.5S | <250 ms; smallest 0.21 s | 10.8K–55.3K parameters | Reported graphically in KiB | Reported graphically in KiB | N/A    | TFLite; STM32 X-Cube-AI | FP32     | None          | Yes           |
