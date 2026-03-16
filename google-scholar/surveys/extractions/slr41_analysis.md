# slr41_analysis

## 1. Basic Information

**Title:** Tiny Machine Learning and On-Device Inference: A Survey of Applications, Challenges, and Future Directions  
**Authors:** Soroush Heydari; Qusay H. Mahmoud  
**Year:** 2025  
**Journal / Conference:** Sensors  
**Type of Review:** Systematic literature review / survey (PRISMA-based)

---

## 2. Scope and Purpose of the Review

**Main Objective of the Review**

To analyze TinyML and on-device inference as alternatives to cloud-based AI processing by examining experimental studies and synthesizing research findings about machine learning models, hardware platforms, and performance metrics used in TinyML implementations.

**Problem the Review Claims to Solve**

Traditional IoT architectures rely heavily on cloud-based inference, which introduces latency, bandwidth dependency, and potential privacy risks. The review investigates whether TinyML on-device inference can mitigate these limitations in applications requiring low latency and reliable operation.

**Scope**

- TinyML  
- On-device inference  
- Edge AI  
- Embedded machine learning  
- IoT and edge computing  
- Resource-constrained devices  

**Main Contributions Claimed by the Authors**

- Synthesis of experimental studies implementing TinyML  
- Analysis of ML algorithms and hardware used in TinyML deployments  
- Identification of research gaps in TinyML experimentation  
- Evaluation of real-world applications where TinyML outperforms cloud inference  
- Discussion of future research directions for TinyML systems  

---

## 3. Search Methodology

**Databases Used**

- Google Scholar  
- IEEE Xplore  
- ACM Digital Library  

**Search Strategy**

The review uses two main approaches:

1. Identification of recent TinyML surveys using database searches  
2. Identification of experimental studies through citations in those surveys and additional keyword searches  

**Search Strings**

Survey identification query:

TinyML Survey

Experimental studies search query:

("instantaneous inference" OR "real-time") (TinyML OR "Edge AI") "implement" —review


**Time Range**

Experimental search results were filtered to include studies published since **2021**, though included experiments span approximately **2020–2024**.

**Study Types Included**

- Peer-reviewed journal articles  
- Peer-reviewed conference papers  
- Experimental studies implementing TinyML  
- Studies cited within selected surveys  

---

## 4. Inclusion and Exclusion Criteria

### Inclusion Criteria

Studies were included if they:

- Addressed at least one research question  
- Presented experimental implementations of TinyML  
- Reported the ML frameworks and hardware used  
- Performed inference locally on embedded devices  
- Were written in English  
- Were published in peer-reviewed journals or conferences  

### Exclusion Criteria

Studies were excluded if they:

- Used cloud-based inference instead of on-device inference  
- Proposed models or frameworks without experimental use cases  
- Were older surveys covered by newer reviews  
- Were not peer-reviewed publications  
- Did not provide sufficient experimental detail  

---

## 5. Deduplication and Screening Process

**Duplicate Removal**

Not reported.

**Screening Process**

The selection process followed these steps:

1. Search for TinyML surveys using database queries  
2. Select six comprehensive and recent surveys  
3. Extract experimental studies cited in those surveys  
4. Perform additional search for low-latency TinyML experiments  
5. Apply eligibility criteria to screen studies  
6. Select final experimental studies for analysis  

**Final Dataset**

26 experimental studies were included in the review.

---

## 6. PRISMA or Selection Flow

**PRISMA Used**

Yes.

The study explicitly follows **PRISMA guidelines** and presents a **PRISMA flow diagram** describing the study selection process.

**Stages of Filtering**

- Identified  
- Screened  
- Eligible  
- Included  

**Counts Reported**

The PRISMA flow diagram reports:

- 1880 records identified after filtering search results  
- 100 records screened  
- 26 studies included in the final review  

---

## 7. Data Extraction Method

The review extracted the following information from each experimental study:

- Proposed use case of the experiment  
- Reason TinyML inference was chosen over cloud or IoT inference  
- Hardware platform used  
- Neural network software or ML framework used  
- Results of the TinyML experiment  

Additional contextual analysis considered:

- Machine learning algorithms used  
- Hardware platforms  
- Performance metrics  
- Application domain  

---

## 8. Quality Assessment / Risk of Bias

Quality assessment methodology:

Not reported.

The study does not apply a formal quality scoring framework or methodological rubric to assess included studies.

---

## 9. Types of Analysis Used

The literature is synthesized using:

**Narrative synthesis**

Detailed qualitative description of experiments and findings.

**Domain-based classification**

Experiments categorized into application domains:

- Healthcare  
- Ecology  
- Vehicular detection  
- Industrial and miscellaneous applications  

**Comparative tables**

Tables summarize experimental studies, results, and implications.

**Trend and gap analysis**

Discussion identifies patterns in TinyML usage and research gaps.

---

## 10. Figures and Tables Used in the Review

Typical figures and tables include:

**Figures**

- TinyML architecture diagram  
- PRISMA selection flow diagram  

**Tables**

- Table of existing TinyML surveys  
- Tables listing rejected surveys  
- Tables listing rejected experiments  
- Tables listing selected experimental studies  
- Healthcare experiment summary table  
- Ecology experiment summary table  
- Vehicular detection experiment summary table  
- Other application experiment table  

---

## 11. Practical Recommendations

The authors suggest several research directions:

- Development of standardized TinyML hardware and software frameworks  
- Improved benchmarking methods for TinyML systems  
- Creation of scalable deployment pipelines for TinyML models  
- Exploration of new training approaches such as:
  - federated learning  
  - transfer learning  
  - continuous learning  
- Improved integration of TinyML with IoT ecosystems  

---

## 12. Limitations of the Review

The authors identify several limitations:

- Focus on studies cited in surveys may exclude relevant work  
- Exclusion of cloud-inference studies may remove useful comparisons  
- Evaluation metrics across experiments are not standardized  
- Possible publication bias toward successful experiments  
- Potential overestimation of TinyML performance due to limited negative results  

---

## 13. Methodological Strengths of This SLR

Methodological strengths include:

- Use of PRISMA guidelines  
- Clearly defined research questions  
- Explicit inclusion and exclusion criteria  
- Structured study selection process  
- Categorization of experiments by application domain  
- Structured extraction of experimental information  
- Identification of research gaps and future research directions  

---

## 14. Potential Methodological Weaknesses

Potential weaknesses include:

- No formal quality assessment of included studies  
- Limited number of databases used  
- Search strategy not fully comprehensive  
- Heavy reliance on experiments cited within surveys  
- Possible selection bias toward successful implementations  
- Lack of standardized evaluation metrics across studies  

---

## 15. Extracted SLR Methodology Checklist

- [x] Multiple databases used  
- [x] Search strings reported  
- [x] Time window defined  
- [x] Inclusion/exclusion criteria defined  
- [ ] Deduplication described  
- [x] PRISMA flow diagram used  
- [x] Data extraction fields defined  
- [ ] Quality assessment performed  
- [x] Comparative tables included  
- [x] Quantitative synthesis included  
- [x] Domain-based classification of studies  
