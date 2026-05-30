## Paper ID: Real-Time-Multilingual-Video-Subtitle-Spotting-on-Resource-Constrained-Devices

TinyML classification: Near-TinyML — The work targets edge/on-device TV hardware with CPU/NPU acceleration, but does not provide explicit MCU-class deployment evidence.

### Basic Info

* Authors: Illya Degtyarenko, Olga Radyvonenko, Nazarii Tkach, Valerii Sielikhov, Kostiantyn Seliuk, Oleksandr Ivanov
* Year: 2025
* Title: Real-Time Multilingual Video Subtitle Spotting on Resource-Constrained Devices
* Source: IEEE Access
* Type: Experimental

### Problem & Context

* Task: Video text spotting, subtitle detection, subtitle tracking, and OCR/text recognition
* Objective: Enable accurate real-time on-device multilingual subtitle spotting, recognition, translation support, and text-to-speech voicing for burned-in subtitles in video content.
* Application domain: Video accessibility, subtitle translation, text-to-speech conversion, video content comprehension, smart TV services
* Scenario: Edge, on-device, resource-constrained TV device, consumer multimedia device
* TinyML relevance: Partial
* TinyML justification: The paper targets on-device inference on resource-constrained TV edge hardware with latency, memory, model-size, pruning, and quantization concerns, but does not report MCU-class, bare-metal, RTOS, or TensorFlow Lite Micro deployment.

### Model / Method

* Model: Multi-stage subtitle spotting pipeline with content classifier, subtitle tracker, SSD subtitle detector, CRNN-CTC text recognizer, language model decoder, and TTS module
* Architecture family: Hybrid CNN / RNN
* Techniques: Pruning, Quantization-Aware Training, asymmetric affine quantization, dynamic fixed-point quantization, NPU porting, subtitle tracking, text-line coordinate adjustment, chunk-based CRNN recognition, language-model decoding
* Framework: Not reported; TTS engine embedded into Tizen 9.0
* Training type: Not reported
* Inference type: On-device

### Hardware

* Device: Commodity visual display device / TV set using Samsung NQ8 AI Gen3 chipset
* Hardware type: SoC / CPU / NPU
* Processor / microcontroller: Samsung NQ8 AI Gen3 chipset
* Clock frequency: Not reported
* SRAM / RAM: Average memory consumption below 24 MB; peak memory consumption below 36.5 MB
* Flash / ROM / Storage: Total database with all solution components for one language below 7.5 MB
* Power consumption: Not reported
* Energy per inference: Not reported
* Execution without full OS: No
* Fully on-device inference: Yes
* Constraints mentioned: Memory, CPU consumption, computational resources, latency, storage/model size, real-time processing

### Dataset

* Name: Custom synthetic subtitle datasets; BOVText subset for independent evaluation
* Type: Synthetic / public
* Dataset size: Content classifier dataset has about 2.0M target frames and 0.6M non-target frames; tracker dataset has 1.1M images; detector dataset has 2.1M images; recognition datasets range from 1.4M to 2.3M images per language; independent BOVText subset has 26 videos
* Number of classes: Binary content classification; binary subtitle tracking; text-line detection; multilingual OCR recognition
* Input resolution: Content classifier uses 300 × 300 frames; tracker uses two 300 × 300 consecutive frames; detector uses 256 × 256 frames; recognition uses text lines normalized to 48 px height and 48 × 192 chunks
* Data modality: Video frames, screen images, subtitle text-line images

### Metrics

* Accuracy: Average CRR 99.48%, WRR 98.37%, E2E CRR* 97.29%, E2E WRR* 96.17% across seven languages
* mAP: Subtitle detector mAP 0.91 at IoU=0.5, 0.62 at IoU=0.75, and 0.58 at IoU=[0.5:0.95]
* Precision: Not reported
* Recall: Not reported
* F1-score: Not reported
* Latency: Average E2E latency below 150 ms per screen
* FPS: Screen sampling rate of 0.5 FPS for subtitle tracking
* Throughput: Not reported
* Model size: Content classifier 0.27 MB; tracker 0.23 MB; detector 3.2 MB; recognition model per language uses 0.66–0.69 MB on NPU and 2.6–3.6 MB on CPU; total solution database below 7.5 MB per language
* Parameters: Not reported
* MACs / FLOPs: Not reported
* RAM usage: Average below 24 MB; peak below 36.5 MB
* Flash usage: Not reported
* Energy per inference: Not reported
* Power consumption: Not reported

### Optimization

* Techniques used: Pruning, Quantization-Aware Training, asymmetric affine quantization, dynamic fixed-point quantization, MobileNet-based lightweight architectures, NPU porting, subtitle-specific post-processing, text chunking
* Quantization: QAT
* Pruning: Yes
* Knowledge distillation: Not reported
* Compression method: Pruning and quantization
* Hardware-specific optimization: Models except the RNN and recognition decoder were quantized and ported to the NPU
* Use of CMSIS-NN: No
* Use of TensorFlow Lite Micro: No
* Use of MLPerf Tiny: No

### Strict TinyML Evidence

* SRAM peak reported: Not reported; runtime memory peak below 36.5 MB is reported
* Flash usage reported: Not reported; total database below 7.5 MB per language is reported
* Model size reported: Yes
* Energy per inference reported: Not reported
* Latency on target device reported: Yes, below 150 ms per screen
* Runs without full operating system: No
* Fully on-device inference: Yes
* Communication required during inference: Not reported
* Candidate for Strict TinyML: No
* Reason: The paper targets TV-class edge hardware with CPU/NPU acceleration and Tizen-based deployment, not MCU-class, bare-metal, RTOS, Cortex-M, or TensorFlow Lite Micro deployment.

### Benchmarking / Standardization

* Benchmark used: BOVText subset for independent evaluation
* MLPerf Tiny mentioned: No
* Visual Wake Words mentioned: No
* Other standard benchmark: BOVText
* Comparison with baseline models: Yes, previous tracker/detector from [17], PaddleOCR mobile, and EasyOCR
* Comparison with previous works: Yes
* Reproducibility artifacts available: Not reported

### Results

* Summary: The proposed on-device subtitle spotting system achieved average E2E WRR* of 96.17% across seven languages with average latency below 150 ms per screen. The subtitle detector improved mAP@[0.5:0.95] from 0.44 to 0.58 over the previous detector, and the recognition model achieved 98.58% WRR with a 3.2 MiB model.

### Limitations

* Rolling subtitles are not supported because they require higher sampling frequency and special tracking.
* Multi-color subtitles can be processed incorrectly because the adjustment method assumes constant text-line color.
* Atypical subtitle locations, small subtitles, low-contrast subtitles, overlapping text, and non-subtitle text elements can cause detection or recognition errors.

### Practical Reporting Checklist Evidence

* Reports hardware clearly: Yes
* Reports memory usage: Yes
* Reports latency: Yes
* Reports energy or power: No
* Reports model size: Yes
* Reports optimization method: Yes
* Reports deployment framework: No
* Reports dataset and preprocessing: Yes
* Reports evaluation metric clearly: Yes
* Reports reproducibility artifacts: No

### Contribution

* This paper proposes a real-time multilingual on-device video subtitle spotting pipeline combining lightweight content classification, subtitle tracking, SSD-based text-line detection, CRNN-CTC recognition, quantization, pruning, and NPU deployment for resource-constrained TV devices.

| Paper              | Year | Task                               | Model                                                                      | Technique                   | Device                        | Dataset                                    | Main Metric     | Latency        | Model Size                                               | SRAM/RAM                  | Flash | Energy | Framework                                | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------------ | ---- | ---------------------------------- | -------------------------------------------------------------------------- | --------------------------- | ----------------------------- | ------------------------------------------ | --------------- | -------------- | -------------------------------------------------------- | ------------------------- | ----- | ------ | ---------------------------------------- | -------- | ------------- | ------------- |
| Degtyarenko et al. | 2025 | Video subtitle text spotting / OCR | Content classifier + subtitle tracker + SSD detector + CRNN-CTC recognizer | Pruning + QAT + NPU porting | Samsung NQ8 AI Gen3 TV device | Custom synthetic datasets + BOVText subset | E2E WRR* 96.17% | <150 ms/screen | <7.5 MB total DB per language; recognition model 3.2 MiB | Avg <24 MB; peak <36.5 MB | N/A   | N/A    | Tizen 9.0 TTS; ML framework not reported | QAT      | None          | No            |
