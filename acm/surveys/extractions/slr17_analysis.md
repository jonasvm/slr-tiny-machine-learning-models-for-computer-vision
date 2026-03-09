# SLR17 Analysis

## 1. Basic Information

**Title:**  
Intelligence at the Extreme Edge: A Survey on Reformable TinyML

**Authors:**  
Visal Rajapakse  
Ishan Karunanayake  
Nadeem Ahmed

**Year:**  
2023

**Journal / Conference:**  
ACM Computing Surveys (ACM CSUR)

**Type of Review:**  
Survey / Literature Review

---

# 2. Scope and Purpose of the Review

**Main objective of the review**

The paper aims to survey research on **reformable TinyML**, focusing on methods that allow machine learning models deployed on microcontrollers and resource-constrained devices to **adapt, update, or retrain after deployment**.

**Problem the review claims to solve**

Traditional TinyML systems usually deploy **static models that only perform inference**, which prevents adaptation to changing environments, concept drift, or evolving datasets.

The review investigates mechanisms that allow **post-deployment learning and adaptation** in TinyML systems.

**Scope**

- TinyML
- Edge AI
- IoT devices and microcontrollers
- On-device learning
- Incremental learning
- Online learning
- Federated learning
- Over-the-air (OTA) model updates

**Main contributions claimed by the authors**

- A comprehensive survey of **reformable TinyML approaches**
- A **taxonomy of reformable TinyML learning strategies**
- Analysis of **hardware platforms, tools, and frameworks**
- Discussion of **applications, challenges, and future research directions**

---

# 3. Search Methodology

## Databases Used

The paper reports using multiple academic and research platforms:

- Google Scholar
- Semantic Scholar
- Papers with Code
- Connected Papers
- IEEE Xplore
- ACM Digital Library
- Elsevier (ScienceDirect)

---

## Search Strings

Not reported.

The authors mention using combinations of keywords such as:

- TinyML  
- Incremental learning  
- Online learning  
- Federated learning  
- Over-the-air updates  
- Concept drift  
- Collaborative machine learning

Exact search queries are not provided.

---

## Time Range

Not reported.

The paper does not define a specific publication time window.

---

## Study Types Included

Not explicitly defined.

Based on the analyzed works, the study includes:

- Journal articles
- Conference papers
- Research articles

---

# 4. Inclusion and Exclusion Criteria

## Inclusion Criteria

- Studies related to **IoT systems and edge computing**
- Research implementing **machine learning on microcontrollers or constrained devices**
- Papers addressing:
  - Online learning
  - Incremental learning
  - Federated learning
  - OTA model updates
  - Collaborative or distributed TinyML
- Studies involving **energy-efficient embedded AI**

## Exclusion Criteria

Not explicitly reported.

---

# 5. Deduplication and Screening Process

**Duplicate removal**

Not reported.

**Title/Abstract screening**

Yes.  
The authors state that titles, abstracts, and conclusions were reviewed to determine relevance.

**Full-text screening**

Not explicitly reported.

**Selection process**

The selection process described by the authors includes:

1. Searching literature using relevant keywords across several databases.
2. Screening papers by analyzing **title, abstract, and conclusion**.
3. Expanding the search by exploring **references of relevant papers** (snowballing).

---

# 6. PRISMA or Selection Flow

**PRISMA used**

No.

**Selection flow diagram**

Not reported.

**Counts of papers at each stage**

Not reported.

**Stages of filtering**

Not reported.

---

# 7. Data Extraction Method

The authors extract several attributes from the reviewed studies, including:

- Machine learning architecture
- Learning approach (offline, online, distributed)
- Hardware platforms (microcontrollers and embedded systems)
- Software frameworks
- Datasets used
- Evaluation metrics
- Application domain
- Accuracy metrics
- Inference latency
- Energy consumption
- Memory usage
- Training time

These attributes are summarized and compared across studies in several tables.

---

# 8. Quality Assessment / Risk of Bias

**Quality assessment exists**

No.

**Method or rubric used**

Not reported.

**Number of criteria**

Not reported.

The paper does not include a formal quality assessment or risk-of-bias evaluation of the selected studies.

---

# 9. Types of Analysis Used

The authors synthesize the literature using multiple analytical approaches:

**Narrative synthesis**

Each research work is discussed and categorized according to its learning strategy and deployment model.

**Taxonomy development**

The paper proposes a taxonomy of **reformable TinyML approaches**, including:

- On-device offline learning
- Online learning
  - Lazy learning
  - Eager learning
- Network-reliant approaches
  - Distributed learning
  - Over-the-air updates

**Comparative tables**

Several tables compare:

- architectures
- datasets
- frameworks
- hardware platforms
- evaluation metrics

**Trend and challenge analysis**

The review discusses:

- industrial use cases
- research challenges
- future research opportunities

---

# 10. Figures and Tables Used in the Review

Typical figures and tables used in the paper include:

**Figures**

- Comparison of edge computing and cloud computing paradigms
- TinyML system architecture diagrams
- Taxonomy of reformable TinyML approaches
- TinyML development workflow

**Tables**

- Comparison with previous surveys
- State-of-the-art reformable TinyML implementations
- Hardware and software platform comparisons
- Benchmarking frameworks for TinyML
- Code generation and deployment tools

---

# 11. Practical Recommendations

The authors highlight several recommendations for researchers and practitioners:

- Development of **online learning algorithms suitable for microcontrollers**
- Improved **benchmarking frameworks for TinyML evaluation**
- Efficient **communication mechanisms for distributed IoT learning**
- Exploration of **task offloading to edge or cloud infrastructures**
- Handling **data quality and concept drift in real-world deployments**

They also suggest exploring integration of TinyML with:

- blockchain
- explainable AI
- decentralized learning systems
- serverless edge computing

---

# 12. Limitations of the Review

Limitations mentioned or implied include:

- Lack of standardized benchmarking frameworks
- Heterogeneous hardware platforms across studies
- Limited publicly available implementations
- Strong resource constraints of microcontrollers
- Limited datasets and reproducibility in TinyML research
- Early stage of research on reformable TinyML systems

---

# 13. Methodological Strengths of This SLR

- Uses **multiple academic databases**
- Employs **keyword-based search strategy**
- Includes **reference snowballing**
- Provides a **structured taxonomy of the research field**
- Includes **detailed comparative tables**
- Covers **hardware, software, datasets, and metrics**

---

# 14. Potential Methodological Weaknesses

- Search strings are **not reported**
- No **time window defined**
- No **PRISMA diagram**
- No **counts of papers in each selection stage**
- Deduplication process **not described**
- No **quality assessment of included studies**
- Inclusion/exclusion criteria **not fully formalized**

---

# 15. Extracted SLR Methodology Checklist

**SLR Methodology Checklist**

- [x] Multiple databases used  
- [ ] Search strings reported  
- [ ] Time window defined  
- [x] Inclusion/exclusion criteria defined  
- [ ] Deduplication described  
- [ ] PRISMA flow diagram used  
- [x] Data extraction fields defined  
- [ ] Quality assessment performed  
- [x] Comparative tables included  
- [ ] Quantitative synthesis included
