# SLR30 Analysis

## 1. Basic Information

**Title:**  
Edge AI in Practice: A Survey and Deployment Framework for Neural Networks on Embedded Systems

**Authors:**  
Ruth Cordova-Cardenas, Daniel Amor, Álvaro Gutiérrez

**Year:**  
2025

**Journal / Conference:**  
Electronics (MDPI)

**Type of Review:**  
Survey with systematic literature review methodology (PRISMA-aligned)

---

## 2. Scope and Purpose of the Review

**Main Objective:**  
To review the current landscape of Edge AI deployment techniques for neural networks on embedded systems and propose a structured framework for deploying optimized deep learning models on resource-constrained devices.

**Problem Addressed:**  
Deploying deep learning models on embedded and edge devices is challenging due to limited computational resources, strict memory constraints, and energy consumption limitations. The review seeks to organize existing research and provide practical guidance for developers implementing Edge AI systems.

**Scope:**  
- Edge AI  
- Embedded AI  
- Neural network deployment  
- Model compression techniques  
- Hardware acceleration for AI  
- TinyML and lightweight deep learning

**Main Contributions Claimed by the Authors:**

- Systematic review of Edge AI deployment strategies.
- Analysis of optimization techniques such as pruning, quantization, and knowledge distillation.
- Survey of hardware platforms used for Edge AI.
- Identification of current challenges and future research directions.
- Proposal of a five-stage deployment framework for Edge AI systems.

---

## 3. Search Methodology

### Databases Used

- IEEE Xplore  
- ACM Digital Library  
- MDPI  
- SpringerLink  
- ScienceDirect  
- arXiv  

### Search Strings

The study uses a structured Boolean search query combining Edge AI concepts with optimization and deployment techniques.

Concept Block A

```
"Edge AI"
OR
"embedded deep learning"
OR
"TinyML"
```

Concept Block B

```
"neural network optimization"
OR
"quantization"
OR
"pruning"
OR
"compact networks"
OR
"NPU acceleration"
OR
"Edge TPU"
OR
"FPGA inference"
OR
"YOLO optimization"
OR
"model compression"
OR
"hardware-software co-design"
```

Combined Query

```
("Edge AI" OR "embedded deep learning" OR "TinyML")
AND
("neural network optimization" OR "quantization" OR "pruning"
OR "compact networks" OR "NPU acceleration" OR "Edge TPU"
OR "FPGA inference" OR "YOLO optimization"
OR "model compression" OR "hardware-software co-design")
```

Exclusion Terms

```
"cloud computing"
OR
"cloud inference"
OR
"data center"
```

The search terms were applied to:

- title  
- abstract  
- keywords  

### Time Range

The review focuses primarily on studies published within the **last five years**, including publications up to **2025**.

### Study Types Included

- Journal articles  
- Conference papers  
- Preprints (e.g., arXiv)  
- Experimental studies involving Edge AI deployment

---

## 4. Inclusion and Exclusion Criteria

### Inclusion Criteria

- Studies proposing **model optimization techniques** (e.g., pruning, quantization, knowledge distillation).
- Studies presenting **efficient neural architectures** suitable for embedded systems.
- Studies with **experimental validation on edge hardware platforms**.
- Studies reporting measurable performance metrics such as:
  - latency
  - energy consumption
  - memory usage
  - frames per second (FPS)

### Exclusion Criteria

- Purely theoretical works without experimental validation.
- Review articles without quantitative evaluation results.
- Simulation-only studies without real hardware deployment.
- Papers lacking clear methodology or results sections.
- Duplicate publications (conference and journal versions).

---

## 5. Deduplication and Screening Process

The study follows a structured multi-stage screening process.

Initial records identified:  
1020

Duplicates removed:  
70

Records screened (title and abstract):  
950

Records excluded after screening:  
710

Full-text articles assessed for eligibility:  
240

Final studies included:  
60

Reasons for exclusion during full-text screening included:

- absence of hardware performance metrics
- simulation-only evaluations
- incomplete methodology descriptions

---

## 6. PRISMA or Selection Flow

The review follows **PRISMA 2020 guidelines**.

Features reported:

- PRISMA flow diagram describing the study selection process.
- Number of papers reported at each filtering stage.
- PRISMA checklist provided as supplementary material.
- Review protocol registered in the **Open Science Framework (OSF)**.

Filtering Stages

1. Identification  
2. Screening  
3. Eligibility  
4. Included  

---

## 7. Data Extraction Method

The authors extracted multiple categories of information from each study.

### Model Characteristics

- neural network architecture
- model size
- FLOPs
- quantization level

### Hardware Platform

- CPU
- GPU
- FPGA
- NPU
- Edge TPU
- microcontrollers

### Performance Metrics

- inference latency
- throughput (FPS)
- energy consumption
- memory usage

### Task Performance Metrics

- classification accuracy
- mean average precision (mAP)
- Rank-N accuracy
- Word Error Rate (WER)

### System-Level Metrics

- runtime memory footprint
- workload distribution
- thermal stability

---

## 8. Quality Assessment / Risk of Bias

Quality assessment performed:  
No.

The authors state that a formal risk-of-bias assessment was not conducted because the review focuses on technical performance studies rather than experimental or clinical evidence.

---

## 9. Types of Analysis Used

The review synthesizes the literature using multiple analytical approaches.

Narrative synthesis

Most studies are discussed through structured narrative analysis.

Taxonomy development

The literature is organized into taxonomies including:

- neural network architectures
- model compression techniques
- hardware platforms
- deployment strategies

Comparative tables

Tables compare models and deployment results across multiple studies.

Trend analysis

The paper identifies emerging trends such as:

- TinyML
- ultra-low precision inference
- neuromorphic computing
- on-device learning

Framework synthesis

The authors propose a **five-stage Edge AI deployment framework** derived from the literature.

---

## 10. Figures and Tables Used in the Review

Typical visual elements include:

Figures

- PRISMA flow diagram
- Edge AI inference pipeline diagrams
- deployment workflow diagrams

Tables

- model architecture comparisons
- hardware platform comparisons
- optimization technique comparisons
- benchmark performance tables
- case-study deployment results

---

## 11. Practical Recommendations

The authors propose a practical methodology for Edge AI deployment consisting of five stages:

1. Define system requirements and constraints (latency, memory, energy).
2. Select an appropriate neural architecture.
3. Apply model optimization techniques.
4. Select deployment frameworks and hardware platforms.
5. Benchmark and validate system performance.

These steps aim to guide developers in implementing efficient embedded AI systems.

---

## 12. Limitations of the Review

The authors mention several limitations:

- Lack of standardized benchmarks across Edge AI studies.
- Heterogeneity of hardware platforms and evaluation environments.
- Limited hardware support for ultra-low-precision inference.
- Fragmented software ecosystems for Edge AI deployment.
- Difficulty comparing results across studies due to inconsistent metrics.

---

## 13. Methodological Strengths of This SLR

- PRISMA-aligned systematic methodology.
- Explicit search strategy and Boolean queries.
- Multiple academic databases included.
- Transparent screening and selection process.
- Quantitative reporting of paper selection stages.
- Structured data extraction across multiple technical dimensions.
- Integration of literature review with a deployment framework.

---

## 14. Potential Methodological Weaknesses

- Absence of formal quality assessment of included studies.
- Inclusion of heterogeneous study types.
- Limited discussion of reviewer agreement or screening reliability.
- Variability of evaluation metrics across studies.

---

## 15. Extracted SLR Methodology Checklist

SLR Methodology Checklist:

- [x] Multiple databases used
- [x] Search strings reported
- [x] Time window defined
- [x] Inclusion/exclusion criteria defined
- [x] Deduplication described
- [x] Title/abstract screening described
- [x] Full-text screening described
- [x] PRISMA flow diagram used
- [x] Data extraction fields defined
- [ ] Quality assessment performed
- [x] Comparative tables included
- [x] Narrative synthesis included
- [x] Trend analysis included
- [x] Deployment framework proposed
