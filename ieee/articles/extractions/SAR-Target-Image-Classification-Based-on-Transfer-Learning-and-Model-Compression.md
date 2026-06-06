Paper ID: SAR-Target-Image-Classification-Based-on-Transfer-Learning-and-Model-Compression

TinyML classification: Near-TinyML — It targets resource-constrained embedded use but reports GPU-based evaluation and does not provide explicit MCU-class deployment evidence.

Basic Info

Authors: Chengliang Zhong, Xiaodong Mu, Xiangchen He, Jiaxin Wang, and Ming Zhu

Year: 2019

Title: SAR Target Image Classification Based on Transfer Learning and Model Compression

Source: IEEE Geoscience and Remote Sensing Letters, Vol. 16, No. 3, March 2019. 

Type: Methodological

Problem & Context

Task: Classification

Objective: Obtain a compact and light CNN for SAR target image classification using transfer learning and model compression.

Application domain: Synthetic aperture radar target recognition

Scenario: Embedded airborne SAR processing devices / resource-constrained systems

TinyML relevance: Partial

TinyML justification: The paper targets resource-constrained embedded SAR systems with storage, computation, power, and latency constraints, but evaluation is performed on a GTX1070 GPU and no MCU-class deployment is reported.

Model / Method

Model: Transferred CaffeNet, VGG-F, and VGG-M; pruning experiments focus on transferred CaffeNet.

Architecture family: CNN

Techniques: Transfer learning, fine-tuning, removal of fully connected layers, global mean pooling, filter-based pruning, retraining

Framework: Caffe

Training type: Transfer learning / fine-tuning

Inference type: Not reported

Hardware

Device: GTX1070 GPU accelerated by cuDNN v5.0 for speed evaluation; embedded airborne SAR processing device mentioned as target scenario but not specified.

Hardware type: GPU

Processor / microcontroller: Not reported

Clock frequency: Not reported

SRAM / RAM: Not reported

Flash / ROM / Storage: Not reported

Power consumption: Not reported

Energy per inference: Not reported

Execution without full OS: Not reported

Fully on-device inference: Not reported

Constraints mentioned: Storage, computation, power, latency, model parameters, FLOPs, limited SAR data

Dataset

Name: MSTAR

Type: Public

Dataset size: Training samples increased to 2700 per class by augmentation; test set class counts are reported in the confusion matrix.

Number of classes: 10

Input resolution: 88 × 88

Data modality: Single-channel SAR image

Metrics

Accuracy: 98.39% for transferred CaffeNet pruned 70% with l1-norm; 97.71% for transferred CaffeNet pruned 80% with l1-norm; 98.56% for unpruned transferred VGG-F.

mAP: Not reported

Precision: Not reported

Recall: Not reported

F1-score: Not reported

Latency: 1.08 ms forward propagation for pruned-70 and 0.79 ms forward propagation for pruned-80 on GTX1070 GPU with batch size 64.

FPS: Not reported

Throughput: Not reported

Model size: Transferred CaffeNet 9.3 MB, VGG-F 8.8 MB, VGG-M 26.3 MB before pruning.

Parameters: 0.22M for pruned-70; 0.10M for pruned-80.

MACs / FLOPs: 8.68M FLOPs for pruned-70; 4.37M FLOPs for pruned-80.

RAM usage: Not reported

Flash usage: Not reported

Energy per inference: Not reported

Power consumption: Not reported

Optimization

Techniques used: Removal of FC layers, added convolutional layer, global mean pooling, fine-tuning, filter pruning, retraining/recovery strategy

Quantization: None

Pruning: Yes

Knowledge distillation: No

Compression method: Filter-based pruning using l1-norm and mean activation criteria

Hardware-specific optimization: Not reported

Use of CMSIS-NN: No

Use of TensorFlow Lite Micro: No

Use of MLPerf Tiny: No

Strict TinyML Evidence

SRAM peak reported: Not reported

Flash usage reported: Not reported

Model size reported: Yes; transferred model storage is reported in MB.

Energy per inference reported: Not reported

Latency on target device reported: Not reported

Runs without full operating system: Not reported

Fully on-device inference: Not reported

Communication required during inference: Not reported

Candidate for Strict TinyML: No

Reason: The paper reports compression and GPU-based latency but does not report MCU deployment, Cortex-M-class hardware, TFLite Micro, SRAM/Flash usage, or energy measurements.

Benchmarking / Standardization

Benchmark used: MSTAR

MLPerf Tiny mentioned: No

Visual Wake Words mentioned: No

Other standard benchmark: ImageNet used for pretrained models

Comparison with baseline models: Yes; compared with A-ConvNets, highway unit network, 2-VDCNN, CNN with simulated data, and CNN baseline.

Comparison with previous works: Yes

Reproducibility artifacts available: Not reported

Results

Summary: The pruned-80 transferred CaffeNet achieves 97.71% accuracy with 0.10M parameters, 4.37M FLOPs, and 0.79 ms forward time on GTX1070 GPU. Compared with A-ConvNets, it achieves about 3.6× speedup and 3.7× parameter compression with a 1.42% accuracy decrease.

Limitations: A 90% pruning ratio cannot restore the original classification performance, and multiple pruning shows large variance in final classification results.

Practical Reporting Checklist Evidence

Reports hardware clearly: Yes

Reports memory usage: No

Reports latency: Yes

Reports energy or power: No

Reports model size: Yes

Reports optimization method: Yes

Reports deployment framework: No

Reports dataset and preprocessing: Yes

Reports evaluation metric clearly: Yes

Reports reproducibility artifacts: No

Contribution

This paper proposes a transfer-learning and filter-pruning approach to obtain compact CNNs for SAR target image classification under resource-constrained embedded application requirements.

| Paper        | Year | Task           | Model                | Technique                          | Device      | Dataset | Main Metric     | Latency         | Model Size       | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
| ------------ | ---- | -------------- | -------------------- | ---------------------------------- | ----------- | ------- | --------------- | --------------- | ---------------- | -------- | ----- | ------ | --------- | -------- | ------------- | ------------- |
| Zhong et al. | 2019 | Classification | Transferred CaffeNet | Transfer learning + filter pruning | GTX1070 GPU | MSTAR   | 97.71% accuracy | 0.79 ms forward | 0.10M parameters | N/A      | N/A   | N/A    | Caffe     | N/A      | None          | No            |
