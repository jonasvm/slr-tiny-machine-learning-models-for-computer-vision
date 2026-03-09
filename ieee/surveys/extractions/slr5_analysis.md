# SLR3 Analysis

## 1. Basic Information

**Title:**
Tiny Machine Learning: Progress and Futures

**Authors:**
Ji Lin; Ligeng Zhu; Wei-Ming Chen; Wei-Chen Wang; Song Han

**Year:**
2023

**Journal / Conference:**
IEEE Circuits and Systems Magazine

**Type of Review:**
Narrative survey / perspective review (not a formal systematic literature review)

---

## 2. Scope and Purpose of the Review

**Main Objective of the Review**

To review the progress of Tiny Machine Learning (TinyML) and present techniques that enable deep learning on extremely resource-constrained devices such as microcontrollers.

**Problem the Review Claims to Solve**

Running and training deep learning models on microcontrollers is difficult due to severe constraints such as:

* extremely limited SRAM
* limited flash storage
* low computational capacity
* lack of traditional OS/runtime environments

**Scope**

* TinyML
* Edge AI
* Efficient deep learning for microcontrollers
* On-device training
* Algorithm–system co-design for embedded ML

**Main Contributions Claimed by the Authors**

* Overview of the TinyML research landscape
* Discussion of algorithmic and system techniques enabling TinyML
* Presentation of the MCUNet framework
* Description of methods for TinyML inference and training
* Identification of future research challenges in TinyML

---

## 3. Search Methodology

**Databases Used**

Not reported.

**Search Strings**

Not reported.

**Time Range**

Not reported.

**Study Types Included**

Not explicitly defined.

The paper references:

* journal articles
* conference papers
* arXiv preprints
* system frameworks

but does not formally define study types.

---

## 4. Inclusion and Exclusion Criteria

Not reported.

The paper does not define explicit inclusion or exclusion criteria.

---

## 5. Deduplication and Screening Process

**Duplicate Removal**

Not reported.

**Title / Abstract Screening**

Not reported.

**Full-text Screening**

Not reported.

**Selection Process**

The paper does not describe a formal study selection process.
Papers appear to have been selected manually based on relevance to TinyML.

---

## 6. PRISMA or Selection Flow

**PRISMA Used**

No.

**Counts of Papers at Each Stage**

Not reported.

**Stages of Filtering**

Not reported.

---

## 7. Data Extraction Method

The paper does not explicitly describe a data extraction protocol.

However, comparison tables extract technical attributes such as:

* model architecture
* dataset used
* input resolution
* inference latency
* peak memory usage
* flash storage usage
* energy consumption
* accuracy metrics

These attributes appear in benchmark comparison tables.

---

## 8. Quality Assessment / Risk of Bias

**Quality Assessment Performed**

No.

**Assessment Method**

Not reported.

**Number of Criteria**

Not reported.

---

## 9. Types of Analysis Used

The paper synthesizes the literature using:

* narrative synthesis of TinyML research progress
* taxonomy of techniques and system approaches
* comparative benchmarking tables
* experimental evaluation of proposed methods
* trend discussion and future research directions

---

## 10. Figures and Tables Used in the Review

Typical figures and tables include:

* comparison tables of TinyML frameworks
* performance benchmarking tables (latency, memory, accuracy)
* architecture diagrams
* workflow diagrams
* performance trade-off graphs (accuracy vs memory or latency)

---

## 11. Practical Recommendations

The authors highlight several recommendations for TinyML research:

* design neural networks jointly with system constraints
* develop memory-aware neural architectures
* optimize inference engines for microcontrollers
* enable lightweight on-device training techniques
* adopt algorithm–system co-design approaches

---

## 12. Limitations of the Review

The paper does not explicitly list methodological limitations.

However, implicit limitations include:

* absence of systematic literature search
* lack of reproducible methodology
* no study selection protocol
* no quality assessment of studies
* strong focus on the authors’ own framework (MCUNet)

---

## 13. Methodological Strengths of This Review

Although not a formal SLR, the paper provides:

* a comprehensive overview of TinyML techniques
* detailed benchmark comparisons
* clear taxonomy of system and algorithm approaches
* extensive experimental validation
* insights into future research challenges

---

## 14. Potential Methodological Weaknesses

From an SLR perspective, the following limitations exist:

* no database search strategy
* no search strings reported
* no inclusion/exclusion criteria
* no PRISMA flow diagram
* no systematic screening process
* no quality assessment
* potential selection bias

---

## 15. Extracted SLR Methodology Checklist

SLR Methodology Checklist:

* [ ] Multiple databases used
* [ ] Search strings reported
* [ ] Time window defined
* [ ] Inclusion/exclusion criteria defined
* [ ] Deduplication described
* [ ] PRISMA flow diagram used
* [ ] Data extraction fields defined
* [ ] Quality assessment performed
* [x] Comparative tables included
* [x] Quantitative benchmarking included
* [x] Narrative synthesis
* [x] Taxonomy of techniques
