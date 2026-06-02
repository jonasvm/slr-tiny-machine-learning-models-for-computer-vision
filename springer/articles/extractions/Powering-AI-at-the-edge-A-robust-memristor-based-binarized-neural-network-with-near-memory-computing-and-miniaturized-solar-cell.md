## Paper ID: Powering-AI-at-the-edge-A-robust-memristor-based-binarized-neural-network-with-near-memory-computing-and-miniaturized-solar-cell

TinyML classification: Strict TinyML — it explicitly targets extreme-edge ultra-low-power embedded AI with fabricated near-memory hardware, solar-cell operation, and measured low-energy inference constraints.

### Basic Info
- Authors: Fadi Jebali; Atreya Majumdar; Clément Turck; Kamel-Eddine Harabi; Mathieu-Coumba Faye; Eloi Muhr; Jean-Pierre Walder; Oleksandr Bilousov; Amadéo Michaud; Elisa Vianello; Tifenn Hirtzlin; François Andrieu; Marc Bocquet; Stéphane Collin; Damien Querlioz; Jean-Michel Portal
- Year: 2024
- Title: Powering AI at the edge: A robust, memristor-based binarized neural network with near-memory computing and miniaturized solar cell
- Source: Nature Communications, 15:741
- Type: Experimental

### Problem & Context
- Task: Classification
- Objective: Demonstrate a robust self-powered edge AI binarized neural network using memristor-based near-memory computing powered by a miniaturized solar cell.
- Application domain: Intelligent sensing for health, safety, and environmental monitoring.
- Scenario: Extreme-edge, embedded, self-powered IoT sensing.
- TinyML relevance: Yes
- TinyML justification: The paper targets ultra-low-power edge AI with a fabricated low-power integrated circuit, non-volatile memristor storage, solar energy harvesting, and measured inference energy constraints.

### Model / Method
- Model: Binarized neural network
- Architecture family: CNN / Other
- Techniques: Binarization, near-memory computing, logic-in-sense-amplifier XNOR, complementary memristor programming, majority-vote mapping to memristor arrays.
- Framework: PyTorch for neural-network simulations; custom CMOS/memristor hardware for inference experiments.
- Training type: Not reported
- Inference type: Hybrid; single-layer computation is on-chip, while multilayer operation in the experimental setup requires off-chip transfer through a microcontroller/Python script.

### Hardware
- Device: Custom hybrid CMOS/memristor binarized neural network integrated circuit powered by a miniaturized AlGaAs/GaInP solar cell.
- Hardware type: Other
- Processor / microcontroller: Custom low-power 130-nm CMOS/memristor integrated circuit; STM32F746ZGT6 microcontroller used in the measurement setup.
- Clock frequency: 10 MHz to 66 MHz
- SRAM / RAM: Not reported
- Flash / ROM / Storage: 32,768 memristors for non-volatile storage of synaptic weights and neuron thresholds; Flash/ROM not reported.
- Power consumption: Not reported
- Energy per inference: Lowest measured whole-chip inference energy of 45 nJ at 0.7 V and 10 MHz.
- Execution without full OS: Not reported
- Fully on-device inference: No
- Constraints mentioned: Unreliable harvested power, supply voltage, energy, memristor variability, calibration avoidance, communication/data transfer, and low-illumination operation.

### Dataset
- Name: MNIST; CIFAR-10
- Type: Public
- Dataset size: Not reported
- Number of classes: 10 for MNIST; 10 for CIFAR-10
- Input resolution: Not reported
- Data modality: Image

### Metrics
- Accuracy: MNIST: 97.2% baseline, 97.1% at 8 suns, 96.9% at 0.8 suns, 96.9% at 0.36 suns, 96.5% at 0.08 suns; CIFAR-10: 86.6% baseline, 83.6% at 8 suns, 78.2% at 0.8 suns, 78.3% at 0.36 suns, 73.4% at 0.08 suns.
- mAP: Not reported
- Precision: Not reported
- Recall: Not reported
- F1-score: Not reported
- Latency: Not reported
- FPS: Not reported
- Throughput: Not reported
- Model size: Not reported
- Parameters: Not reported
- MACs / FLOPs: Not reported
- RAM usage: Not reported
- Flash usage: Not reported
- Energy per inference: 45 nJ minimum measured whole-chip inference energy.
- Power consumption: Not reported

### Optimization
- Techniques used: Binarized neural networks, memristor-based non-volatile storage, digital near-memory computing, XNOR logic-in-sense-amplifier, complementary memristor programming, and majority-vote hardware mapping.
- Quantization: Binary weights and activations
- Pruning: No
- Knowledge distillation: No
- Compression method: Binarization
- Hardware-specific optimization: Custom CMOS/memristor near-memory computing circuit optimized for unreliable harvested power and low-energy inference.
- Use of CMSIS-NN: No
- Use of TensorFlow Lite Micro: No
- Use of MLPerf Tiny: No

### Strict TinyML Evidence
- SRAM peak reported: Not reported
- Flash usage reported: Not reported
- Model size reported: Not reported
- Energy per inference reported: 45 nJ minimum measured whole-chip inference energy.
- Latency on target device reported: Not reported
- Runs without full operating system: Not reported
- Fully on-device inference: No
- Communication required during inference: Yes
- Candidate for Strict TinyML: Yes
- Reason: The work explicitly targets extreme-edge ultra-low-power embedded AI with a fabricated self-powered circuit and measured nJ-level inference energy, although it is a custom integrated circuit rather than an MCU deployment and full multilayer inference still requires off-chip orchestration in the current setup.

### Benchmarking / Standardization
- Benchmark used: MNIST; CIFAR-10
- MLPerf Tiny mentioned: No
- Visual Wake Words mentioned: No
- Other standard benchmark: MNIST; CIFAR-10
- Comparison with baseline models: Yes; comparison with software baseline without bit errors.
- Comparison with previous works: Yes
- Reproducibility artifacts available: code / dataset

### Results
- Summary: The fabricated memristor-based BNN remained functional under solar-cell power down to 0.08 suns and achieved a minimum measured inference energy of 45 nJ. Simulated neural-network accuracy under measured hardware error rates remained high for MNIST and degraded more substantially for CIFAR-10 under low illumination.

### Limitations
- The current setup requires off-chip communication through a microcontroller/Python script for multilayer computation, does not include an input buffer or dedicated convolution handling, and experiences significant inaccuracies below 0.7 V due to transistor threshold limitations.

### Practical Reporting Checklist Evidence
- Reports hardware clearly: Yes
- Reports memory usage: No
- Reports latency: No
- Reports energy or power: Yes
- Reports model size: No
- Reports optimization method: Yes
- Reports deployment framework: No
- Reports dataset and preprocessing: No
- Reports evaluation metric clearly: Yes
- Reports reproducibility artifacts: Yes

### Contribution
- This paper proposes a robust self-powered memristor-based binarized neural network integrated circuit that uses digital near-memory computing and a miniaturized solar cell to enable ultra-low-power edge AI inference under unstable harvested energy.

| Paper | Year | Task | Model | Technique | Device | Dataset | Main Metric | Latency | Model Size | SRAM/RAM | Flash | Energy | Framework | INT8/QAT | CMSIS-NN/TFLM | Strict TinyML |
|---|---:|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Jebali et al. | 2024 | Classification | Binarized neural network | Binarization + memristor near-memory computing | Custom CMOS/memristor IC + miniaturized solar cell | MNIST; CIFAR-10 | Accuracy: 97.1% MNIST and 83.6% CIFAR-10 at 8 suns | N/A | N/A | N/A | N/A | 45 nJ/inference | PyTorch + custom hardware | N/A | None | Yes |
