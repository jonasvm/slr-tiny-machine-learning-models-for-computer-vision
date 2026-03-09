# SLR9 Analysis

## 1. Basic Information

**Title:**  
Small-Object Detection at the Edge: A Pareto-Efficient Benchmark of Lightweight YOLO Models on UAV and Overhead Datasets

**Authors:**  
Bijay Shakya, Omar El-Gayar, Jihene Kaabi, Khandaker Mamun Ahmed

**Year:**  
2026

**Journal / Conference:**  
IEEE Access

**Type of review:**  
Experimental benchmarking study (Not a Systematic Literature Review)

---

## 2. Scope and Purpose of the Review

**Main objective of the review**

To benchmark lightweight YOLO models for small-object detection in UAV and overhead imagery, focusing on performance trade-offs between accuracy, latency, and resource usage on edge devices.

**Problem the review claims to solve**

Existing literature lacks consistent cross-platform benchmarking of lightweight object detection models considering accuracy, inference speed, and energy efficiency for edge deployment scenarios.

**Scope**

- Computer Vision  
- Object Detection  
- Lightweight YOLO models  
- Edge AI  
- UAV and overhead imagery  
- Small-object detection

**Main contributions claimed by the authors**

- Comprehensive benchmark of lightweight YOLO models for edge deployment.
- Evaluation of models across UAV and overhead image datasets.
- Multi-objective analysis considering accuracy, latency, memory, and energy consumption.
- Pareto frontier analysis to identify optimal trade-offs between performance metrics.
- Practical recommendations for deploying object detection models on edge devices.

---

## 3. Search Methodology

**Databases Used**

Not reported.

**Search Strings**

Not reported.

**Time Range**

Not reported.

**Study Types Included**

Not reported.

This study does not perform a literature search; instead it evaluates machine learning models experimentally.

---

## 4. Inclusion and Exclusion Criteria

Not reported.

No study selection criteria are defined because the paper is not a systematic literature review.

---

## 5. Deduplication and Screening Process

**Duplicate removal described**

Not reported.

**Title/abstract screening**

Not reported.

**Full-text screening**

Not reported.

**Selection process explanation**

Not applicable.  
The study evaluates a predefined set of lightweight YOLO architectures rather than selecting papers from the literature.

---

## 6. PRISMA or Selection Flow

**PRISMA used**

No.

**Counts of papers reported at each stage**

Not reported.

**Stages of filtering**

Not reported.

---

## 7. Data Extraction Method

The study extracts experimental performance metrics from the evaluated models.

**Extracted fields include**

- mAP@0.5
- mAP@0.5:0.95
- Precision
- Recall
- F1-score
- inference latency
- FPS
- model size
- parameter count
- GFLOPs
- RAM usage
- GPU utilization
- energy consumption

These metrics are used to compare models across datasets and hardware platforms.

---

## 8. Quality Assessment / Risk of Bias

**Quality assessment exists**

No.

**Method used**

Not reported.

**Number of criteria**

Not reported.

---

## 9. Types of Analysis Used

The literature and experimental results are synthesized using:

- Narrative discussion of model performance
- Quantitative statistical comparison of performance metrics
- Comparative benchmark tables
- Pareto frontier analysis for multi-objective optimization
- Cross-platform performance comparison
- Trend analysis of trade-offs between accuracy and efficiency

---

## 10. Figures and Tables Used in the Review

Typical figures and tables include:

- Model comparison tables
- Benchmark performance tables
- Accuracy vs latency charts
- Pareto frontier plots
- Detection output visualizations
- Dataset description tables
- Hardware resource usage comparisons

---

## 11. Practical Recommendations

The authors provide guidance for deploying object detection models on edge devices.

Examples include:

- Selecting models depending on latency or accuracy constraints.
- Using TensorRT FP16 optimizations for improved performance.
- Choosing lightweight YOLO variants for real-time UAV applications.
- Selecting models based on device memory and energy limitations.

---

## 12. Limitations of the Review

The authors acknowledge several limitations:

- Results depend on specific hardware configurations.
- Some models lack optimized TensorRT implementations.
- Dataset annotation differences may affect evaluation.
- Fixed training configurations may benefit certain architectures.
- Benchmark limited to YOLO-based models.

---

## 13. Methodological Strengths of This SLR

Even though the paper is not an SLR, it presents strong experimental methodology:

- standardized benchmarking pipeline
- evaluation across multiple datasets
- cross-platform edge-device testing
- multi-objective performance evaluation
- energy consumption measurements
- Pareto frontier analysis

---

## 14. Potential Methodological Weaknesses

- Not a systematic literature review
- No literature search strategy
- No database search
- No inclusion/exclusion criteria
- No PRISMA flow diagram
- No study quality assessment
- Limited scope to YOLO-based architectures

---

## 15. Extracted SLR Methodology Checklist

SLR Methodology Checklist:

[ ] Multiple databases used  
[ ] Search strings reported  
[ ] Time window defined  
[ ] Inclusion/exclusion criteria defined  
[ ] Deduplication described  
[ ] PRISMA flow diagram used  
[ ] Data extraction fields defined  
[ ] Quality assessment performed  
[x] Comparative tables included  
[x] Quantitative synthesis included  
[x] Experimental benchmarking  
[x] Pareto frontier analysis  
[x] Hardware-aware evaluation
