# SLR18 Analysis

## 1. Basic Information

**Title:**  
Lightweight Deep Learning for Resource-Constrained Environments: A Survey

**Authors:**  
Hou-I Liu; Marco Galindo; Hongxia Xie; Lai-Kuan Wong; Hong-Han Shuai; Yung-Hui Li; Wen-Huang Cheng

**Year:**  
2024

**Journal / Conference:**  
ACM Computing Surveys (ACM Comput. Surv.), Volume 56, Issue 10

**Type of Review:**  
Survey

---

# 2. Scope and Purpose of the Review

**Main objective of the review:**  
To provide a comprehensive overview of methods and techniques that enable deep learning models to operate efficiently on resource-constrained devices such as mobile phones, embedded systems, and microcontrollers.

**Problem the review claims to solve:**  
Modern deep learning models have grown significantly in size and computational complexity, making them difficult to deploy on devices with limited computational power, memory, and energy resources.

**Scope:**  
Lightweight deep learning for resource-constrained environments, including:

- edge AI
- embedded systems
- mobile devices
- TinyML environments
- computer vision and general AI workloads

The survey focuses on three main pillars:

- lightweight neural network architectures  
- model compression techniques  
- hardware acceleration for deep learning

**Main contributions claimed by the authors:**

- Organizing lightweight neural network architectures into architecture families (e.g., MobileNet series).
- Providing a historical overview of lightweight architectures.
- Reviewing compression techniques such as pruning, quantization, and knowledge distillation.
- Reviewing hardware acceleration and deployment techniques for constrained devices.
- Discussing future directions including TinyML and deployment challenges for large models on edge devices.

---

# 3. Search Methodology

**Databases Used:**  
Not reported.

**Search Strings:**  
Not reported.

**Time Range:**  
Not reported.

**Study Types Included:**

Not explicitly defined, but the references include:

- journal articles
- conference papers
- preprints (e.g., arXiv)

Major venues cited include CVPR, ICCV, ICLR, ICML, and ACL.

---

# 4. Inclusion and Exclusion Criteria

Not reported.

No explicit inclusion or exclusion criteria are defined in the paper.

---

# 5. Deduplication and Screening Process

**Duplicate removal described:**  
Not reported.

**Title/abstract screening described:**  
Not reported.

**Full-text screening described:**  
Not reported.

**Selection process explanation:**  
The paper does not describe a systematic literature selection process.  
Instead, the authors discuss representative works related to lightweight architectures, compression methods, and hardware acceleration.

---

# 6. PRISMA or Selection Flow

**PRISMA used:**  
No.

**Counts of papers reported at each stage:**  
Not reported.

**Stages of filtering:**  
Not reported.

The paper does not include a PRISMA diagram or any formal study selection workflow.

---

# 7. Data Extraction Method

A formal data extraction protocol is not described.

However, the survey analyzes and categorizes studies based on technical aspects such as:

- neural network architecture design
- lightweight architecture families
- convolution blocks and model structures
- pruning methods
- quantization techniques
- knowledge distillation
- neural architecture search (NAS)
- hardware accelerators (GPU, FPGA, TPU)
- deployment frameworks and libraries
- hardware–software co-design techniques
- TinyML deployment techniques

---

# 8. Quality Assessment / Risk of Bias

**Quality assessment performed:**  
No.

**Quality assessment method:**  
Not reported.

**Number of evaluation criteria:**  
Not reported.

The paper does not evaluate the methodological quality of the included studies.

---

# 9. Types of Analysis Used

The survey primarily uses qualitative and conceptual synthesis.

Main analysis approaches:

- narrative literature synthesis
- taxonomy of lightweight architectures
- categorization of compression techniques
- categorization of hardware acceleration methods
- conceptual framework of lightweight DL deployment
- trend and future research discussion

---

# 10. Figures and Tables Used in the Review

Typical figures and tables used in the paper include:

- taxonomy diagrams of lightweight neural networks
- architecture family diagrams (e.g., MobileNet series)
- conceptual diagrams of lightweight deep learning pipelines
- comparison tables of compression techniques
- diagrams of hardware accelerators
- tables summarizing model optimization strategies

---

# 11. Practical Recommendations

The authors provide several recommendations for researchers and practitioners:

- Design neural network architectures specifically for resource-constrained environments.
- Combine multiple model optimization strategies (e.g., pruning + quantization).
- Consider hardware-aware model design.
- Use neural architecture search to automatically design efficient models.
- Explore hardware–software co-design approaches.
- Investigate TinyML as a promising research direction.

---

# 12. Limitations of the Review

Explicit limitations are not clearly discussed in the paper.

However, implicit limitations include:

- lack of systematic search methodology
- absence of structured study selection
- absence of study quality assessment
- possible incompleteness of the literature coverage

---

# 13. Methodological Strengths of This SLR

- Broad coverage of lightweight deep learning techniques.
- Clear taxonomy of lightweight architectures.
- Integration of architecture design, compression, and hardware acceleration perspectives.
- Strong conceptual organization of the lightweight deep learning pipeline.
- Extensive reference coverage across multiple research areas.

---

# 14. Potential Methodological Weaknesses

- No systematic search strategy described.
- No database sources specified.
- Search strings are not reported.
- No inclusion or exclusion criteria.
- No screening or selection workflow.
- No PRISMA diagram.
- No study quality assessment.
- Reproducibility of the literature selection process is limited.

---

# 15. Extracted SLR Methodology Checklist

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
[ ] Quantitative synthesis included
