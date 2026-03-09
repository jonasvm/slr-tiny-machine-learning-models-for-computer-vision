# SLR15 Analysis

## 1. Basic Information

**Title:**  
Software Engineering Approaches for TinyML based IoT Embedded Vision: A Systematic Literature Review

**Authors:**  
Shashank Bangalore Lakshman; Nasir U. Eisty

**Year:**  
2022

**Journal / Conference:**  
SERP4IoT’22 – 4th International Workshop on Software Engineering Research and Practice for the IoT (co-located with ICSE 2022)

**Type of Review:**  
Systematic Literature Review

---

## 2. Scope and Purpose of the Review

**Main Objective**

To identify software engineering (SE) best practices that can support the development, deployment, and maintenance of TinyML-based IoT embedded vision systems.

**Problem Addressed**

TinyML applications running on IoT embedded vision devices face multiple engineering challenges due to:

- extreme hardware constraints (memory, power, compute)
- lack of standardized development workflows
- lack of established software engineering practices tailored for TinyML systems

The review attempts to aggregate SE approaches from machine learning, computer vision, and embedded systems engineering to support TinyML development.

**Scope**

- TinyML
- IoT embedded vision
- Software engineering for machine learning systems
- Edge AI systems

**Main Contributions**

- Identification of software engineering challenges in TinyML engineering
- Mapping of SE practices from:
  - large-scale ML engineering
  - traditional embedded systems engineering
- Proposal of a software engineering workflow for TinyML development
- Suggestions for developer tools to improve TinyML engineering productivity

---

## 3. Search Methodology

### Databases Used

- arXiv
- IEEE
- ACM Digital Library
- SpringerLink

Additional sources:

- Google Scholar
- Google Search
- TinyML.org
- Blogs and tutorials (grey literature)

---

### Search Strings

Example queries used:

- `"TinyML" AND "Computer Vision"`
- `"Software Engineering" AND "Edge Computer Vision"`
- `"Software Engineering" AND "Machine Learning"`
- `"Software Engineering" AND "Embedded Systems"`

---

### Time Range

Not reported.

The paper notes that TinyML was introduced around 2018, which limits the available literature.

---

### Study Types Included

- Primary studies
- Secondary studies
- Grey literature (blogs, tutorials, workshops)

Grey literature was explicitly included because TinyML is a recent field with limited peer-reviewed publications.

---

## 4. Inclusion and Exclusion Criteria

### Inclusion Criteria

- Paper written in English
- Grey literature accepted due to emerging research field
- Research related to TinyML engineering
- Studies related to:
  - machine learning
  - computer vision
  - embedded systems
  - software engineering practices

### Exclusion Criteria

- Software engineering applied only to traditional computing systems
- TinyML systems based on frameworks other than TensorFlow Lite Micro (TFLM)

---

## 5. Deduplication and Screening Process

**Duplicate Removal**

Not reported.

**Title / Abstract Screening**

Yes.  
The authors examined abstracts and conclusions of the retrieved studies to refine the initial pool.

**Full-Text Screening**

Not explicitly described.

**Selection Process**

1. Initial search → 43 sources identified  
2. Abstract and conclusion screening → reduced to 20 sources  
3. Forward and backward snowballing → +13 sources

**Final dataset:**  
33 studies included in the review.

---

## 6. PRISMA or Selection Flow

**PRISMA Diagram**

Not used.

**Selection Counts Reported**

Yes.

Reported counts:

- 43 initial sources
- 20 sources after screening
- 13 sources added via snowballing
- 33 final studies

**Filtering Stages**

Implicit stages:

1. Identification
2. Abstract/conclusion screening
3. Snowballing
4. Final inclusion

---

## 7. Data Extraction Method

The study extracts information related to TinyML engineering challenges and software engineering practices.

Extracted information includes:

- system requirements
- model requirements
- dataset considerations
- model training practices
- model compilation strategies
- evaluation practices
- deployment strategies
- monitoring and maintenance practices
- engineering challenges
- proposed software engineering solutions

These elements are summarized in structured tables mapping:

- TinyML workflow step
- challenge
- proposed solution
- origin of the solution

---

## 8. Quality Assessment / Risk of Bias

**Quality Assessment Performed**

No.

**Quality Assessment Method**

Not reported.

**Number of Criteria**

Not reported.

---

## 9. Types of Analysis Used

The review uses the following synthesis methods:

**Narrative synthesis**

Discussion of TinyML engineering challenges and solutions.

**Taxonomy / structured categorization**

Challenges organized according to TinyML engineering workflow steps.

**Conceptual framework**

Proposed software engineering workflow for TinyML development.

**Comparative tables**

Tables summarizing engineering challenges and recommended practices.

---

## 10. Figures and Tables Used in the Review

### Figures

- Examples of IoT embedded vision devices
- Proposed software engineering workflow for TinyML engineering

### Tables

- Hardware comparison of embedded vision devices
- TinyML engineering challenges
- Protocol summary of the systematic literature review
- Software engineering challenges and solutions across workflow stages

---

## 11. Practical Recommendations

The paper proposes several practical recommendations.

**Software Engineering Workflow**

A structured workflow inspired by:

- CRISP-DM
- Microsoft ML workflow
- TensorFlow Lite Micro workflow

The workflow separates the process into stages such as:

- system requirements
- model requirements
- data engineering
- model training
- model evaluation
- model compilation
- application deployment
- monitoring

**Engineering Best Practices**

- hardware-aware model design
- version control for models and datasets
- continuous integration pipelines
- simulation and emulation tools for debugging

**Developer Tool Recommendations**

Future TinyML developer tools should support:

- integration with TinyML frameworks
- device simulation and emulation
- automatic model deployment
- over-the-air firmware and model updates
- large-scale device management

---

## 12. Limitations of the Review

The authors mention several limitations:

- TinyML literature is still limited due to the recent emergence of the field.
- Many sources come from grey literature.
- Lack of industry surveys or interviews.
- The rapid evolution of TinyML technologies may change the conclusions over time.

---

## 13. Methodological Strengths

- Clearly defined research questions
- Multiple information sources
- Snowballing search strategy
- Inclusion of grey literature appropriate for emerging fields
- Structured protocol summary
- Structured mapping between engineering challenges and solutions

---

## 14. Methodological Weaknesses

- No PRISMA diagram
- No duplicate removal description
- No explicit time window for the search
- No formal quality assessment of studies
- Small number of studies included
- Limited transparency regarding full-text screening

---

## 15. Extracted SLR Methodology Checklist

SLR Methodology Checklist:

- [x] Multiple databases used
- [x] Search strings reported
- [ ] Time window defined
- [x] Inclusion/exclusion criteria defined
- [ ] Deduplication described
- [ ] PRISMA flow diagram used
- [x] Data extraction fields defined
- [ ] Quality assessment performed
- [x] Comparative tables included
- [ ] Quantitative synthesis included
