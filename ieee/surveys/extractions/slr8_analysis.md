# SLR8 Analysis

## 1. Basic Information

**Title:** A Survey on Approximate Edge AI for Energy Efficient Autonomous Driving Services  

**Authors:** Dewant Katare, Diego Perino, Jari Nurmi, Martijn Warnier, Marijn Janssen, Aaron Yi Ding  

**Year:** 2023  

**Journal / Conference:** IEEE Communications Surveys & Tutorials  

**Type of Review:** Survey with an SLR-inspired methodology (based on Kitchenham and Charters guidelines)

---

# 2. Scope and Purpose of the Review

**Main Objective**

The paper aims to review research on approximate computing and Edge AI techniques that enable energy-efficient autonomous driving systems.

The survey investigates how AI models, communication technologies, and edge computing infrastructures can be optimized to reduce power consumption while maintaining acceptable performance for autonomous vehicles.

**Problem the Review Claims to Solve**

Autonomous driving systems produce extremely large volumes of data from multiple sensors and communication channels. Processing this data requires significant computational resources and energy.

The review addresses the challenge of enabling **energy-efficient autonomous driving services** through the integration of:

- approximate AI methods
- Edge AI architectures
- communication optimization
- energy-aware frameworks

**Scope**

The review covers multiple technical areas related to autonomous driving systems:

- Edge AI for vehicular systems
- approximate computing techniques
- machine learning and deep learning models
- perception and object detection
- SLAM and localization
- vehicular communication systems (V2X)
- autonomous driving datasets
- AI frameworks for edge deployment

**Main Contributions Claimed by the Authors**

The authors claim the following contributions:

1. A comprehensive survey of approximate Edge AI techniques for energy-efficient autonomous driving.
2. A taxonomy of key technologies including perception, communication, SLAM, and AI frameworks.
3. A review of datasets and benchmark models used in autonomous driving research.
4. An analysis of research trends in autonomous driving.
5. The proposal of an Edge AI processing pipeline based on identified research gaps.

---

# 3. Search Methodology

**Databases Used**

The paper explicitly reports the use of:

- Scopus (for publication trend analysis)

Other databases are not explicitly reported for the literature search.

**Search Strings**

Exact Boolean search strings are **not reported**.

However, groups of keywords used for topic refinement include:

Energy-efficient computing keywords:
- Energy-efficient Edge & Vehicles
- AI model compression & approximation
- TinyML
- Energy-efficient Edge Framework
- Vehicular communication compression
- Low-power Vehicular-Edge

Edge AI keywords:
- Vehicle-Edge-Cloud computing
- Tiny Edge
- Embedded intelligence
- Edge artificial intelligence

SLAM keywords:
- SLAM
- EKF
- KF
- visual SLAM
- deep SLAM
- pose estimation
- graph SLAM
- vehicular localization
- vehicular mapping

Vehicular communication keywords:
- V2X
- V2V
- V2I
- C-V2X
- 5G-V2X
- DSRC
- RSU
- Vehicular communication
- Inter-vehicular communication

Object detection keywords:
- perception
- object detection
- edge analytics
- traffic monitoring
- classification
- collaborative perception
- cooperative perception
- lane detection

**Time Range**

For the trend analysis, publications from **2011 to May 2023** are considered.

A strict review time window for included studies is **not explicitly defined**.

**Study Types Included**

For the Scopus analysis, the search includes:

- journal articles
- conference papers
- books
- book chapters

The study types used for the actual literature review are **not explicitly defined**.

---

# 4. Inclusion and Exclusion Criteria

The paper states that inclusion and exclusion criteria were applied to refine the literature based on the survey’s scope and objectives.

However, the criteria are **not explicitly listed**.

Reported at a high level:

Included studies:
- research related to approximate AI
- energy-efficient AI techniques
- Edge AI architectures
- autonomous driving applications
- vehicular communication systems

Excluded studies:
- not explicitly reported

---

# 5. Deduplication and Screening Process

**Duplicate Removal**

Not reported.

**Title / Abstract Screening**

Not reported.

**Full-Text Screening**

Not reported.

**Selection Process**

The review follows an SLR-inspired methodology adapted from Kitchenham and Charters.

The general process includes:

1. defining research questions and objectives
2. identifying relevant keywords and topics
3. applying inclusion and exclusion criteria
4. collecting relevant papers
5. categorizing the papers according to their technical contributions
6. synthesizing results through comparisons and taxonomies

However, detailed screening stages are not described.

---

# 6. PRISMA or Selection Flow

**PRISMA Flow Diagram**

Not used.

Instead, the paper includes a **review process diagram** based on the SLR guidelines proposed by Kitchenham and Charters.

**Paper Counts at Each Stage**

Not reported.

**Filtering Stages**

The conceptual stages include:

- defining research questions
- identifying keywords and topics
- applying scope and criteria
- collecting articles
- categorizing research contributions
- synthesizing findings

---

# 7. Data Extraction Method

The paper does not describe a formal data extraction protocol.

However, based on the analysis performed, the following types of information were extracted from the literature:

Extracted study attributes include:

- AI task category
- application domain
- model architecture
- machine learning or deep learning method
- compression or approximation technique
- dataset used
- hardware platform
- inference speed
- accuracy performance
- communication technologies
- Edge AI frameworks
- system architecture
- deployment environment (vehicle, edge server, cloud)

Approximation techniques analyzed include:

- parameter reduction
- layer reduction
- node reduction
- neural architecture search
- quantization
- sparsification
- low-rank approximation
- knowledge distillation

---

# 8. Quality Assessment / Risk of Bias

**Quality Assessment Present:** No

The review does not perform a formal quality assessment of the included studies.

No quality rubric, scoring system, or risk-of-bias evaluation is reported.

The authors discuss challenges such as dataset bias and model generalization, but this is not part of a formal evaluation methodology.

---

# 9. Types of Analysis Used

The survey uses several synthesis methods:

**Narrative synthesis**

The majority of the review uses narrative discussion to summarize research across different areas of autonomous driving.

**Taxonomy analysis**

The literature is organized into a structured taxonomy including:

- perception
- SLAM
- communication
- AI frameworks
- datasets

**Trend analysis**

Publication trends in autonomous driving research are analyzed using Scopus data.

**Comparative analysis**

The paper includes multiple comparison tables across:

- AI models
- datasets
- communication technologies
- Edge AI frameworks

**Quantitative categorization**

Research works are categorized according to their techniques and application areas.

---

# 10. Figures and Tables Used in the Review

Typical figures and tables include:

Figures:

- publication trend graphs
- taxonomy diagrams
- system architecture diagrams
- review methodology diagram
- Edge AI pipeline diagram

Tables:

- comparison of previous surveys
- communication technologies comparison
- datasets for autonomous driving
- SLAM benchmarks
- deep learning models used in autonomous driving
- frameworks for Edge AI deployment

---

# 11. Practical Recommendations

The authors provide recommendations for future research directions.

Key recommendations include:

Develop unified Edge AI frameworks  
to integrate vehicle, edge, and cloud resources.

Improve data processing pipelines  
to enable real-time data compression and efficient offloading.

Increase use of collaborative Edge intelligence  
through federated learning and distributed training.

Optimize DNN models for resource-constrained devices  
by using model compression and approximate computing techniques.

Enhance energy efficiency  
through hardware acceleration and energy-aware AI design.

---

# 12. Limitations of the Review

The paper does not explicitly include a dedicated limitations section for the review methodology.

However, the following methodological limitations can be inferred:

- search strings are not fully reported
- databases used for the review are not clearly specified
- inclusion and exclusion criteria are not detailed
- no screening procedure is described
- no PRISMA flow diagram is provided
- no study quality assessment is conducted

---

# 13. Methodological Strengths of This SLR

The review demonstrates several methodological strengths:

- use of an SLR-inspired methodology
- clearly defined research questions
- structured taxonomy of the research field
- large coverage of autonomous driving technologies
- extensive comparison tables
- inclusion of datasets and frameworks
- integration of systems-level and algorithm-level analysis

---

# 14. Potential Methodological Weaknesses

The review also has several methodological limitations:

- lack of explicit search strings
- unclear database coverage
- missing inclusion and exclusion criteria
- no deduplication process described
- no screening procedure
- no PRISMA flow diagram
- absence of quality assessment of included studies
- limited reproducibility of the literature search process

---

# 15. Extracted SLR Methodology Checklist

SLR Methodology Checklist:

[ ] Multiple databases used  
[ ] Search strings reported  
[ ] Time window defined  
[x] Inclusion/exclusion criteria mentioned  
[ ] Deduplication described  
[ ] PRISMA flow diagram used  
[x] Research questions defined  
[x] SLR process diagram included  
[ ] Quality assessment performed  
[x] Comparative tables included  
[x] Quantitative analysis included  
[x] Taxonomy or classification provided

```
