# SLR31 Analysis

## 1. Basic Information

**Title:**  
A Review on Resource-Constrained Embedded Vision Systems-Based Tiny Machine Learning for Robotic Applications

**Authors:**  
Miguel Beltrán-Escobar  
Teresa E. Alarcón  
Jesse Y. Rumbo-Morales  
Sonia López  
Gerardo Ortiz-Torres  
Felipe D. J. Sorcia-Vázquez

**Year:**  
2024

**Journal / Conference:**  
Algorithms (MDPI)

**Type of Review:**  
State-of-the-art review / Narrative survey

---

# 2. Scope and Purpose of the Review

**Main Objective**

Provide a state-of-the-art overview of TinyML implementations for embedded vision systems in resource-constrained hardware platforms used in robotics.

**Problem the Review Claims to Solve**

Robotic systems using computer vision typically require high computational power, which leads to:

- high energy consumption  
- high hardware costs  
- complex system architectures  

The review explores how **TinyML and hardware-constrained embedded systems** can enable efficient machine learning implementations under these constraints.

**Scope**

- TinyML  
- Embedded vision systems  
- Robotics applications  
- Hardware-constrained embedded systems  
- Computer vision on microcontrollers

**Main Contributions Claimed by the Authors**

- Overview of TinyML implementations in embedded vision systems
- Analysis of hardware and software characteristics required for embedded vision
- Classification of embedded systems for TinyML robotics applications
- Demonstration of a TinyML implementation on low-cost hardware platforms

The review proposes a classification based on four analysis criteria:

1. System-on-Chip (SoC) CPU architecture  
2. Vision system implementation  
3. Power consumption rate  
4. Programming language and development platform support

---

# 3. Search Methodology

## Databases Used

Not reported.

The paper does not specify which academic databases were used for the literature search.

## Search Strings

Not reported.

No search query or keyword combinations are described.

## Time Range

Not reported.

No publication year filtering is specified.

## Study Types Included

Not reported.

Based on the references cited, the review appears to include:

- journal articles  
- conference papers  
- technical publications

However, this is not explicitly defined.

---

# 4. Inclusion and Exclusion Criteria

Not reported.

The paper does not specify any formal criteria for including or excluding studies.

---

# 5. Deduplication and Screening Process

Not reported.

The review does not describe:

- duplicate removal
- title/abstract screening
- full-text screening

The literature is presented through a narrative overview of related work.

---

# 6. PRISMA or Selection Flow

**PRISMA Used:**  
No.

**Selection Flow Diagram:**  
Not reported.

**Counts of Papers at Each Stage:**  
Not reported.

No systematic filtering pipeline is presented.

---

# 7. Data Extraction Method

The paper does not formally describe a structured data extraction protocol.

However, information extracted from studies includes characteristics of embedded systems and TinyML implementations.

Extracted fields include:

- CPU architecture
- embedded hardware platforms
- vision sensors
- power consumption characteristics
- electrical operating parameters
- programming languages
- development environments
- operating system support
- energy consumption
- battery compatibility
- hardware capabilities for image processing

The review organizes the literature using four classification dimensions:

1. CPU architecture
2. Vision system implementation
3. Power consumption rate
4. Programming language and platform support

---

# 8. Quality Assessment / Risk of Bias

**Quality Assessment Performed:**  
No.

**Quality Assessment Method:**  
Not reported.

**Number of Quality Criteria:**  
Not reported.

The paper does not evaluate the methodological quality of the included studies.

---

# 9. Types of Analysis Used

The literature is synthesized using several approaches:

**Narrative synthesis**

Discussion of embedded vision systems and TinyML implementations.

**Taxonomy / Classification**

Studies are organized into categories based on:

- CPU architecture
- vision systems
- power consumption
- programming platforms

**Comparative tables**

Hardware characteristics of embedded systems are compared.

**Trend discussion**

The review discusses future directions for TinyML and embedded robotics.

---

# 10. Figures and Tables Used in the Review

Typical figures and tables include:

- Tables comparing embedded system hardware specifications
- Power consumption comparison tables
- Electrical parameter tables
- Classification tables for embedded vision platforms
- Hardware architecture comparisons

Tables summarize characteristics such as:

- supply voltage
- operating current
- deep sleep current
- power consumption
- battery compatibility

---

# 11. Practical Recommendations

The review suggests several practices for implementing TinyML in robotics:

- use low-cost microcontrollers for embedded AI
- optimize machine learning models to fit hardware constraints
- minimize power consumption for mobile robotics
- use open-source platforms for development
- select hardware platforms compatible with TinyML frameworks

The authors demonstrate TinyML deployment using:

- Raspberry Pi Pico
- ESP32
- Arduino Nano 33 BLE Sense

---

# 12. Limitations of the Review

The paper mainly discusses limitations of embedded systems rather than limitations of the review methodology.

Examples mentioned include:

- limited RAM in microcontrollers
- hardware processing constraints
- power consumption limitations
- challenges running complex ML models on embedded devices

Methodological limitations of the review itself are not explicitly discussed.

---

# 13. Methodological Strengths of This SLR

Although not a systematic review, the paper has several strengths:

- structured classification framework
- multi-dimensional taxonomy of embedded systems
- extensive hardware comparison tables
- integration of practical TinyML implementation
- clear organization of embedded vision technologies

---

# 14. Potential Methodological Weaknesses

The main methodological limitations include:

- no description of literature search strategy
- databases not reported
- search strings not reported
- no inclusion or exclusion criteria
- no screening process
- no PRISMA flow diagram
- no quality assessment of studies
- limited reproducibility of the review process

---

# 15. Extracted SLR Methodology Checklist

SLR Methodology Checklist:

- [ ] Multiple databases used
- [ ] Search strings reported
- [ ] Time window defined
- [ ] Inclusion/exclusion criteria defined
- [ ] Deduplication described
- [ ] PRISMA flow diagram used
- [ ] Data extraction fields defined
- [ ] Quality assessment performed
- [x] Comparative tables included
- [x] Quantitative synthesis included
- [x] Taxonomy / classification framework
- [x] Narrative synthesis

---

**Overall Classification**

This paper is best categorized as a **Narrative Survey / State-of-the-Art Review**, rather than a formal **Systematic Literature Review (SLR)**.
