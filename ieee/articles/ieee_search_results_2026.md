# IEEE - Initial Screening Table

Database: IEEE Xplore

Search date: 28 April 2026

Search query:

("tinyml" OR "tiny machine learning" OR "edge ai" OR "embedded ai" OR "on-device ai" OR "low-power ai" OR "microcontroller" OR "mcu")  
AND  
("computer vision" OR "embedded vision" OR "edge vision")  
AND  
("image classification" OR "object detection" OR "small object detection" OR "image segmentation" OR "semantic segmentation" OR "object tracking" OR "visual recognition")

Filters applied:

- Content type: Journals
- Publication years: 2015–2025

Total results returned:

18 papers

Selection criteria applied during screening:

**Inclusion criteria:**

- Papers related to TinyML, Edge AI, Embedded AI, or embedded/on-device AI
- Papers focused on computer vision tasks
- Papers involving image classification, object detection, small object detection, segmentation, object tracking, or visual recognition
- Peer-reviewed journal publications

**Exclusion criteria:**

- Papers not related to computer vision
- Papers focused mainly on non-visual modalities, such as audio, glove sensors, or LiDAR-only data
- Papers with strong cloud, 5G, or edge-cloud dependence and no clear TinyML/on-device focus
- Papers not clearly related to embedded, constrained, low-power, or edge AI systems

**Notes**

Title-based screening was used for this initial classification.  
Papers marked as Keep should be checked in full text or abstract screening.  
Papers marked as Discard are considered outside the scope of TinyML / Edge AI for computer vision.

---

# IEEE - Initial Screening Table

| # | Title | Year | Type | Venue | Decision | Reason |
|---|---|---|---|---|---|---|
| 1 | DSORT-MCU: Detecting Small Objects in Real Time on Microcontroller Units | 2024 | Research article | IEEE Sensors Journal | Keep | Directly related to small object detection on microcontroller units |
| 2 | Real-Time Road Damage Detection and Infrastructure Evaluation Leveraging Unmanned Aerial Vehicles and Tiny Machine Learning | 2024 | Research article | IEEE Internet of Things Journal | Keep | Uses TinyML for a real-time computer vision detection task |
| 3 | Real-Time Object Detection Using Low-Resolution Thermal Camera for Smart Ventilation Systems | 2025 | Research article | IEEE Access | Keep | Object detection task with low-resolution visual input and likely constrained deployment context |
| 4 | Accelerating Image-based Pest Detection on a Heterogeneous Multicore Microcontroller | 2024 | Research article | IEEE Transactions on AgriFood Electronics | Keep | Image-based detection on microcontroller hardware |
| 5 | Lightweight AI Models in Mineral Processing: Classifying Hydrocyclone Underflow With ResNet-18 and MobileViT-V2 | 2025 | Research article | IEEE Access | Keep | Computer vision classification using lightweight AI models |
| 6 | Benchmark Analysis of Semantic Segmentation Algorithms for Safe Planetary Landing Site Selection | 2022 | Research article | IEEE Access | Discard | Semantic segmentation benchmark, but not clearly related to TinyML, embedded AI, or constrained edge deployment |
| 7 | Flexible and Fully Quantized Lightweight TinyissimoYOLO for Ultra-Low-Power Edge Systems | 2024 | Research article | IEEE Access | Keep | Strongly related to quantized lightweight object detection for ultra-low-power edge systems |
| 8 | A Reconfigurable Neural Architecture for Edge–Cloud Collaborative Real-Time Object Detection | 2022 | Research article | IEEE Internet of Things Journal | Discard | Edge-cloud collaborative system, not clearly TinyML or fully on-device constrained inference |
| 9 | Adaptive-Cloud: Dynamic Computation Control for 3D Object Detection From LIDAR Point Clouds | 2025 | Research article | IEEE Robotics and Automation Letters | Discard | Focuses on LiDAR point clouds and adaptive cloud computation rather than computer vision TinyML |
| 10 | Pruning vs XNOR-Net: A Comprehensive Study of Deep Learning for Audio Classification on Edge-Devices | 2022 | Research article | IEEE Access | Discard | Audio classification, not computer vision |
| 11 | Automated Overtake Assist System Using YOLOv4 and Mask R-CNN for Enhanced Autonomous Driving | 2025 | Research article | IEEE Access | Discard | Uses computer vision models, but no clear TinyML, embedded, low-power, or constrained edge focus |
| 12 | Design, Development and Evaluation of an Intelligent Animal Repelling System for Crop Protection Based on Embedded Edge-AI | 2021 | Research article | IEEE Access | Keep | Embedded Edge-AI system with likely visual detection component |
| 13 | Cluster Pruning: An Efficient Filter Pruning Method for Edge AI Vision Applications | 2020 | Research article | IEEE Journal of Selected Topics in Signal Processing | Keep | Directly related to pruning for Edge AI vision applications |
| 14 | Multimodal Fusion and Cutting-Edge AI-Based Smart Vending Machines for Electronic Component Management | 2025 | Research article | IEEE Access | Discard | Not focused on TinyML or computer vision as the main constrained AI problem |
| 15 | Hybrid Decision Making via Deep Learning for Integrated Visual Object Detection, Pose Estimation, and Energy Control in IoT Connected Multi-Robot Systems Using 5G Network | 2025 | Research article | IEEE Access | Discard | Strong 5G/multi-robot system focus, not clearly TinyML or constrained on-device vision |
| 16 | FAVbot: An Autonomous Target Tracking Micro-Robot With Frequency Actuation Control | 2025 | Research article | IEEE Transactions on Circuits and Systems for Artificial Intelligence | Keep | Target tracking in a micro-robot context, potentially relevant to embedded visual AI |
| 17 | A Lightweight Visual Font Style Recognition With Quantized Convolutional Autoencoder | 2024 | Research article | IEEE Open Journal of the Computer Society | Keep | Lightweight visual recognition with quantization |
| 18 | Utilizing Gramian Angular Fields and Convolution Neural Networks in Flex Sensors Glove for Human–Computer Interaction | 2024 | Research article | IEEE Transactions on Human-Machine Systems | Discard | Sensor-based human-computer interaction, not computer vision |

---

# Recommended Immediate Discard

The items below can be removed immediately from the initial screening table because they are clearly outside the scope or weakly related to TinyML / Edge AI for computer vision:

- Benchmark Analysis of Semantic Segmentation Algorithms for Safe Planetary Landing Site Selection
- A Reconfigurable Neural Architecture for Edge–Cloud Collaborative Real-Time Object Detection
- Adaptive-Cloud: Dynamic Computation Control for 3D Object Detection From LIDAR Point Clouds
- Pruning vs XNOR-Net: A Comprehensive Study of Deep Learning for Audio Classification on Edge-Devices
- Automated Overtake Assist System Using YOLOv4 and Mask R-CNN for Enhanced Autonomous Driving
- Multimodal Fusion and Cutting-Edge AI-Based Smart Vending Machines for Electronic Component Management
- Hybrid Decision Making via Deep Learning for Integrated Visual Object Detection, Pose Estimation, and Energy Control in IoT Connected Multi-Robot Systems Using 5G Network
- Utilizing Gramian Angular Fields and Convolution Neural Networks in Flex Sensors Glove for Human–Computer Interaction

---

# Strong Candidates to Keep

The strongest papers to retain at the initial screening stage are:

- DSORT-MCU: Detecting Small Objects in Real Time on Microcontroller Units
- Real-Time Road Damage Detection and Infrastructure Evaluation Leveraging Unmanned Aerial Vehicles and Tiny Machine Learning
- Accelerating Image-based Pest Detection on a Heterogeneous Multicore Microcontroller
- Flexible and Fully Quantized Lightweight TinyissimoYOLO for Ultra-Low-Power Edge Systems
- Design, Development and Evaluation of an Intelligent Animal Repelling System for Crop Protection Based on Embedded Edge-AI
- Cluster Pruning: An Efficient Filter Pruning Method for Edge AI Vision Applications

---

# Suggested Rule for IEEE Screening

For the initial screening of IEEE Xplore results, the following practical rule can be used.

## Keep

- TinyML
- Microcontroller / MCU
- Embedded AI
- Edge AI vision
- Ultra-low-power edge systems
- Quantized models for vision
- Lightweight computer vision models
- Pruning or compression for edge vision
- Object detection, image classification, segmentation, tracking, or visual recognition in constrained environments

## Discard

- Audio-only papers
- Sensor-only papers without visual input
- LiDAR-only papers
- Cloud-heavy or 5G-heavy systems without clear on-device inference
- Generic computer vision papers without edge, embedded, TinyML, or low-power constraints
- Broad AI systems without a clear computer vision and constrained-device focus
