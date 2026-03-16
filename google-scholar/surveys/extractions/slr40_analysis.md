# SLR40 Analysis

## 1. Basic Information

**Title:**  
A Machine Learning-Oriented Survey on Tiny Machine Learning

**Authors:**  
Luigi Capogrosso, Federico Cunico, Dong Seon Cheng, Franco Fummi, Marco Cristani

**Year:**  
2024

**Journal / Conference:**  
IEEE Access

**Type of Review:**  
Survey paper using a PRISMA-based systematic review methodology

---

## 2. Scope and Purpose of the Review

**Main Objective:**  
To provide a machine-learning–oriented overview of TinyML, focusing specifically on the learning algorithms, model optimization strategies, and model design techniques used for deploying machine learning models on resource-constrained embedded devices.

**Problem Addressed:**  
Existing surveys on TinyML largely focus on hardware architectures or application domains. The authors aim to fill a gap by analyzing TinyML from a machine learning perspective, particularly focusing on model training strategies, optimization techniques, and design approaches suitable for constrained hardware.

**Scope:**  

- TinyML
- Machine learning for embedded systems
- Edge AI
- Model optimization techniques
- Neural network design for microcontrollers
- Learning algorithms for resource-constrained environments

**Main Contributions Claimed by the Authors:**

- Provide an up-to-date overview of machine learning techniques applied in TinyML systems.
- Introduce three development workflows for TinyML systems:
  - ML-oriented workflow
  - Hardware-oriented workflow
  - Hardware–software co-design workflow.
- Propose a taxonomy of TinyML learning techniques.
- Analyze the hardware platforms and software frameworks used for TinyML.
- Identify open challenges and research directions in the TinyML field.

---

## 3. Search Methodology

### Databases Used

The literature search was conducted using the following databases:

- Web of Science
- Scopus
- IEEE Xplore
- ScienceDirect
- Google Scholar

### Search Strings

The search used the following keywords:

- "TinyML"
- "efficient machine deep learning"
- "neural network optimization"
- "iot machine deep learning"
- "embedded machine deep learning"
- "edge machine deep learning"
- "mcu machine deep learning"

Exact Boolean queries are **not reported**.

### Time Range

Publications considered:

2018 – January 2024

### Study Types Included

- Peer-reviewed journal articles
- Peer-reviewed conference papers
- English-language publications

---

## 4. Inclusion and Exclusion Criteria

### Inclusion Criteria

- Publications written in English
- Peer-reviewed conference or journal papers
- Studies related to TinyML or machine learning on embedded/edge devices
- Studies retrieved using the defined keyword combinations

### Exclusion Criteria

- Duplicate papers
- Papers automatically flagged as ineligible by filtering tools
- Papers that were not accessible
- Papers excluded after title and abstract screening

---

## 5. Deduplication and Screening Process

The study selection process followed multiple filtering stages.

1. **Initial records identified:** 1047 papers.
2. **Duplicate removal:** 739 duplicates removed.
3. **Automated filtering:** 71 records excluded by automation tools.
4. **Accessibility filtering:** 23 papers removed because they were not accessible.
5. **Title and abstract screening:** 117 papers excluded.
6. **Final included studies:** 86 papers.

The screening process was supported using the **Rayyan systematic review platform**.

---

## 6. PRISMA or Selection Flow

**PRISMA Used:** Yes

The paper follows the PRISMA systematic review methodology and presents a **PRISMA flow diagram** describing the paper selection process.

The filtering stages include:

- Records identified
- Duplicates removed
- Records screened
- Records excluded
- Full-text assessed for eligibility
- Studies included in the final review

Counts of papers are reported for each stage.

---

## 7. Data Extraction Method

The review extracts multiple types of information from the selected studies.

Examples of extracted information include:

**Machine Learning Techniques**

- pruning
- quantization
- knowledge distillation
- hyper-parameter optimization

**Model Design Techniques**

- neural architecture search
- rational activation functions
- depthwise separable convolutions
- attention mechanisms

**Learning Algorithms**

- supervised learning
- unsupervised learning
- self-supervised learning
- reinforcement learning
- weakly supervised learning
- meta-learning
- continual learning

**Hardware Platforms**

- CPUs
- GPUs
- FPGAs
- TPUs
- microcontrollers

**Performance Aspects**

- model size
- energy consumption
- inference latency
- hardware compatibility

**TinyML Frameworks**

- TensorFlow Lite Micro
- uTensor
- Edge Impulse
- Embedded Learning Library
- X-CUBE-AI
- uTVM
- MinUn

---

## 8. Quality Assessment / Risk of Bias

**Quality Assessment:** Not reported

The paper does not describe a formal quality assessment procedure for evaluating the methodological quality of the included studies.

No scoring rubric, checklist, or risk-of-bias assessment is presented.

---

## 9. Types of Analysis Used

The authors synthesize the literature using several analysis approaches.

**Narrative Synthesis**

Discussion of techniques and approaches used in TinyML research.

**Taxonomy Development**

A taxonomy of TinyML learning techniques is proposed.

**Comparative Analysis**

Comparison of:

- optimization techniques
- model design approaches
- learning paradigms

**Trend Analysis**

Analysis of the popularity of TinyML techniques over time.

**Hardware Analysis**

Comparative discussion of different hardware platforms used in TinyML.

**Application Domain Analysis**

Discussion of application domains such as:

- anomaly detection
- healthcare
- IoT monitoring
- environmental sensing

---

## 10. Figures and Tables Used in the Review

Typical figures and tables include:

**Figures**

- Hardware performance vs power consumption charts
- Number of TinyML publications over time
- PRISMA flow diagram
- TinyML development workflow diagrams
- Taxonomy diagrams of TinyML learning techniques

**Tables**

- Popularity of model optimization techniques
- Popularity of model design techniques
- Popularity of learning algorithms
- Hardware platform comparisons
- TinyML hardware platforms used in literature

---

## 11. Practical Recommendations

The authors provide several recommendations for future research.

Examples include:

- Increase research on hyper-parameter optimization techniques for TinyML.
- Explore rational activation functions and learned optimizers.
- Expand research on:
  - self-supervised learning
  - weakly supervised learning
- Develop more hardware–software co-design approaches.
- Improve benchmarking frameworks for TinyML systems.
- Develop standardized datasets and benchmarks for TinyML evaluation.

---

## 12. Limitations of the Review

The authors highlight several limitations related to the TinyML field:

- Lack of standardized benchmarks for TinyML models.
- Limited availability of public datasets for TinyML applications.
- Absence of widely accepted baseline models.
- Hardware heterogeneity across TinyML platforms.
- Memory and computational constraints that limit experimentation.

---

## 13. Methodological Strengths of This SLR

- Use of PRISMA systematic review methodology.
- Multi-database literature search.
- Clearly described paper selection process.
- Explicit reporting of paper counts at each filtering stage.
- Structured taxonomy of TinyML learning techniques.
- Combination of qualitative and quantitative analysis.

---

## 14. Potential Methodological Weaknesses

- Search queries are not reported as reproducible Boolean expressions.
- No formal quality assessment of the included studies.
- No risk-of-bias evaluation.
- Limited details about reviewer agreement during screening.
- No detailed description of database-specific queries.

---

## 15. Extracted SLR Methodology Checklist

SLR Methodology Checklist:

[x] Multiple databases used  
[x] Search strings reported  
[x] Time window defined  
[x] Inclusion/exclusion criteria defined  
[x] Deduplication described  
[x] Title/abstract screening described  
[x] Full-text screening described  
[x] PRISMA flow diagram used  
[x] Data extraction fields defined  
[ ] Quality assessment performed  
[x] Comparative tables included  
[x] Quantitative synthesis included  
[x] Taxonomy of literature included
