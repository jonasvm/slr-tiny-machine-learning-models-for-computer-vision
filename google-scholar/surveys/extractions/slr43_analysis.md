# SLR43 Analysis

## 1. Basic Information

**Title:**  
From Tiny Machine Learning to Tiny Deep Learning: A Survey

**Authors:**  
Shriyank Somvanshi, Md Monzurul Islam, Gaurab Chhetri, Rohit Chakraborty, Mahmuda Sultana Mimi, Sawgat Ahmed Shuvo, Kazi Sifatul Islam, Syed Javed, Sharif Ahmed Rafat, Anandi Dutta, Subasish Das

**Year:**  
2025

**Journal / Conference:**  
ACM Computing Surveys (ACM Comput. Surv.), Volume 58, Issue 7

**Type of Review:**  
Survey (Narrative Review)

---

## 2. Scope and Purpose of the Review

**Main objective of the review:**  
Provide a comprehensive overview of the evolution from Tiny Machine Learning (TinyML) to Tiny Deep Learning (TinyDL), covering architectures, optimization techniques, hardware platforms, deployment frameworks, and application domains for resource-constrained edge devices.

**Problem the review claims to solve:**  
Existing surveys primarily focus on traditional TinyML techniques and do not clearly distinguish the emerging paradigm of Tiny Deep Learning (TinyDL). The review aims to clarify this transition and consolidate research on deep learning models optimized for extremely resource-constrained environments.

**Scope:**  
- TinyML  
- Tiny Deep Learning (TinyDL)  
- Edge AI  
- Embedded deep learning  
- Resource-constrained devices (microcontrollers and edge hardware)

**Main contributions claimed by the authors:**  
- Introduces a conceptual distinction between TinyML and TinyDL.  
- Presents a taxonomy of TinyML/TinyDL architectures, frameworks, and hardware platforms.  
- Reviews optimization techniques such as quantization, pruning, and neural architecture search.  
- Analyzes hardware ecosystems and deployment toolchains.  
- Identifies research challenges and future directions for TinyDL systems.

---

## 3. Search Methodology

**Databases Used:**  
Not reported.

**Search Strings:**  
Not reported.

**Time Range:**  
Not explicitly defined. The paper reviews research developments up to approximately 2025.

**Study Types Included:**  
Not explicitly defined, but references indicate inclusion of:
- Journal articles  
- Conference papers  
- Preprints (e.g., arXiv)  
- Technical reports  
- Benchmark studies  
- Industry documentation

---

## 4. Inclusion and Exclusion Criteria

Not reported.

The paper does not explicitly describe inclusion or exclusion criteria for selecting studies.

---

## 5. Deduplication and Screening Process

**Duplicate removal described:**  
Not reported.

**Title/abstract screening described:**  
Not reported.

**Full-text screening described:**  
Not reported.

**Selection process description:**  
The authors synthesize findings from a large body of literature (over 200 references), but the paper does not describe a systematic selection workflow.

---

## 6. PRISMA or Selection Flow

**PRISMA used:**  
No.

**Counts of papers reported at each stage:**  
Not reported.

**Stages of filtering:**  
Not reported.

The paper does not present a PRISMA diagram or any structured study selection flow.

---

## 7. Data Extraction Method

The paper synthesizes information across multiple technical dimensions rather than defining a formal extraction protocol.

**Information extracted from studies includes:**

**Model architectures**
- CNN architectures (e.g., MobileNet, SqueezeNet)
- Lightweight transformers (e.g., TinyBERT, DistilBERT)

**Optimization techniques**
- Quantization
- Pruning
- Knowledge distillation
- Neural architecture search (NAS)

**Hardware platforms**
- Microcontrollers
- Neural accelerators
- Edge AI processors

**Deployment frameworks**
- TensorFlow Lite Micro
- CMSIS-NN
- MicroTVM
- Edge Impulse

**Evaluation metrics**
- Model size
- Inference latency
- Memory footprint
- Energy consumption
- Number of MAC operations

**Benchmarks and datasets**
- MLPerf Tiny
- Visual Wake Words
- Google Speech Commands
- CIFAR
- Tiny ImageNet

**Application domains**
- Computer vision
- Audio processing
- Natural language processing
- Healthcare
- Industrial IoT

---

## 8. Quality Assessment / Risk of Bias

**Quality assessment performed:**  
No.

**Quality assessment method:**  
Not reported.

**Number of criteria:**  
Not reported.

The paper does not evaluate the methodological quality or risk of bias of the included studies.

---

## 9. Types of Analysis Used

The review primarily uses qualitative and taxonomy-based synthesis.

**Narrative synthesis:**  
Yes — extensive discussion of architectures, frameworks, hardware, and optimization techniques.

**Taxonomy development:**  
Yes — classification of TinyML and TinyDL systems, tools, and architectures.

**Comparative tables:**  
Yes — multiple tables comparing hardware platforms, models, frameworks, and datasets.

**Trend analysis:**  
Yes — discussion of the evolution of TinyML/TinyDL technologies and research directions.

**Benchmark analysis:**  
Yes — discussion of benchmarking initiatives such as MLPerf Tiny.

---

## 10. Figures and Tables Used in the Review

Typical figures and tables include:

**Conceptual diagrams**
- TinyML pipeline and ecosystem diagrams.

**Framework comparison diagrams**
- Conceptual distinction between TinyML and TinyDL.

**Timeline figures**
- Evolution timeline of TinyML/TinyDL technologies.

**Architecture diagrams**
- Illustrations of lightweight model structures and deployment workflows.

**Comparative tables**
- Hardware platform comparison tables.
- TinyML/TinyDL model comparisons.
- Toolchain and framework comparison tables.
- Dataset and benchmark summaries.

---

## 11. Practical Recommendations

The authors provide several recommendations for future research and practice:

- Design lightweight deep learning models tailored to microcontroller constraints.
- Combine multiple optimization techniques such as pruning, quantization, and NAS.
- Promote hardware–software co-design for TinyDL systems.
- Adopt standardized benchmarking frameworks like MLPerf Tiny.
- Explore emerging directions including federated TinyML and neuromorphic computing.

---

## 12. Limitations of the Review

Limitations mentioned or implied in the paper include:

- Deployment of deep models on microcontrollers remains constrained by memory and energy limitations.
- Benchmarking frameworks for TinyML/TinyDL remain limited.
- Transformer architectures are still difficult to deploy on very small devices.
- Toolchains and frameworks are still evolving and lack full standardization.
- Security and privacy challenges remain underexplored.

Methodological limitations include:

- Absence of a systematic search protocol.
- No formal inclusion/exclusion criteria.
- No PRISMA-based selection process.
- No study quality assessment.

---

## 13. Methodological Strengths of This Review

- Extensive coverage of TinyML and TinyDL research literature.
- Clear taxonomy distinguishing TinyML and Tiny Deep Learning.
- Detailed comparative tables summarizing models, frameworks, and hardware.
- Integration of hardware, software, and algorithm perspectives.
- Identification of research gaps and future research directions.

---

## 14. Potential Methodological Weaknesses

- No systematic search strategy reported.
- Databases used for literature retrieval are not specified.
- Search strings are not reported.
- No inclusion or exclusion criteria defined.
- No screening procedure described.
- No duplicate removal process described.
- No PRISMA diagram or selection flow.
- No quality assessment of included studies.

Overall, the work functions as a narrative survey rather than a systematic literature review.

---

## 15. Extracted SLR Methodology Checklist

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
- [x] Taxonomy / conceptual framework included  
- [x] Benchmark discussion included  
