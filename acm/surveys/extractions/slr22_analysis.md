# SLR22 Analysis

## 1. Basic Information

**Title:**  
Hardware Approximate Techniques for Deep Neural Network Accelerators: A Survey

**Authors:**  
Giorgos Armeniakos; Georgios Zervakis; Dimitrios Soudris; Jörg Henkel

**Year:**  
2022

**Journal / Conference:**  
ACM Computing Surveys

**Type of Review:**  
Survey

---

## 2. Scope and Purpose of the Review

**Main Objective:**  
To provide a comprehensive survey and analysis of hardware approximation techniques used in deep neural network (DNN) accelerators, focusing on their impact on efficiency, accuracy, and energy consumption.

**Problem Addressed:**  
Deep neural networks require high computational power and energy consumption, particularly due to the large number of multiply–accumulate (MAC) operations. Approximate computing techniques can exploit the inherent error resilience of DNNs to improve energy efficiency and hardware performance in accelerators.

**Scope:**  
- Approximate computing  
- Hardware-level approximation techniques  
- Deep neural network accelerators  
- Energy-efficient DNN inference  
- Edge and embedded AI hardware

**Main Contributions Claimed by the Authors:**

- Identification and classification of hardware approximation techniques for DNN accelerators.  
- Clustering of the literature based on approximation technique families.  
- Analysis of the complexity of evaluations used in prior research (datasets and DNN size).  
- Discussion of error metrics suitable for approximate DNN hardware design.  
- Review of accuracy recovery techniques used in approximate DNN systems.  
- Discussion of reliability and security implications of approximate computing in DNN accelerators.

---

## 3. Search Methodology

**Databases Used:**  
Not reported

**Search Strings:**  
Not reported

**Time Range:**  
Not reported

**Study Types Included:**  
Not reported

The paper does not describe a systematic literature search process. Instead, it presents a narrative survey of relevant works.

---

## 4. Inclusion and Exclusion Criteria

Not reported

The authors do not specify explicit inclusion or exclusion criteria for selecting the reviewed studies.

---

## 5. Deduplication and Screening Process

**Duplicate Removal:**  
Not reported

**Title and Abstract Screening:**  
Not reported

**Full-Text Screening:**  
Not reported

**Selection Process Description:**  
The paper does not describe a formal screening or study selection workflow. The reviewed literature is organized and discussed based on approximation techniques and hardware design categories.

---

## 6. PRISMA or Selection Flow

**PRISMA Used:**  
No

**Counts of Papers Reported at Each Stage:**  
No

**Stages of Filtering:**  
Not reported

The paper does not include a PRISMA diagram or a systematic study selection flow.

---

## 7. Data Extraction Method

The authors extract and analyze information about prior work related to approximate computing techniques applied to DNN accelerators.

Extracted aspects include:

- Type of hardware approximation technique  
- Approximate arithmetic units (e.g., adders, multipliers)  
- Hardware architecture modifications  
- Error metrics used for evaluation  
- Dataset complexity used in experiments  
- DNN model size  
- Energy efficiency improvements  
- Accuracy impact of approximations  
- Accuracy recovery techniques  
- Reliability and security implications

---

## 8. Quality Assessment / Risk of Bias

**Quality Assessment Performed:**  
No

**Method Used:**  
Not reported

**Number of Criteria:**  
Not reported

The paper does not include a formal methodological quality assessment of the included studies.

---

## 9. Types of Analysis Used

The literature is synthesized using:

- Narrative synthesis  
- Taxonomy of hardware approximation techniques  
- Comparative analysis of accelerator designs  
- Trend analysis of publications  
- Categorization of approximation families  
- Comparative discussion of error metrics and evaluation strategies

---

## 10. Figures and Tables Used in the Review

Typical figures and tables include:

**Figures**

- Publication trend showing the number of works applying approximation techniques to DNN inference  
- Conceptual diagrams of neural network computation  
- Architectural diagrams of approximate DNN accelerators  
- Classification diagrams of approximation techniques

**Tables**

- Table comparing related surveys in the literature  
- Tables categorizing approximation techniques  
- Tables summarizing hardware implementations  
- Tables comparing approximate computing methods

---

## 11. Practical Recommendations

The authors suggest:

- Designing approximate arithmetic circuits specifically tailored to DNN workloads.  
- Selecting error metrics that better reflect neural network robustness to approximation errors.  
- Integrating accuracy recovery mechanisms into approximate DNN accelerator design.  
- Exploring approximate computing not only for energy efficiency but also for improving reliability and security in hardware accelerators.

---

## 12. Limitations of the Review

Not explicitly reported.

However, the review implicitly limits its scope to **compute-based approximation techniques**, excluding approximate memory approaches.

---

## 13. Methodological Strengths of This SLR

- Comprehensive taxonomy of hardware approximation techniques.  
- Structured categorization of approximation families.  
- Comparative discussion of multiple accelerator design strategies.  
- Analysis of evaluation complexity in prior studies.  
- Broad literature coverage within the approximate DNN accelerator domain.

---

## 14. Potential Methodological Weaknesses

- No systematic search strategy reported.  
- Databases used for literature search are not reported.  
- Search strings are not provided.  
- No time window for literature inclusion is defined.  
- No inclusion or exclusion criteria are specified.  
- No PRISMA diagram or study selection workflow.  
- No duplicate removal process described.  
- No study quality assessment or risk-of-bias analysis.

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
