# SLR46 Analysis

## 1. Basic Information

**Title:** Embedded Deep Learning Accelerators: A Survey on Recent Advances  

**Authors:** Ghattas Akkad, Ali Mansour, Elie Inaty  

**Year:** 2024 (published online 2023)  

**Journal / Conference:** IEEE Transactions on Artificial Intelligence  

**Type of review:** Survey / Narrative Review  

---

## 2. Scope and Purpose of the Review

**Main objective of the review**

The paper aims to provide an overview of recent advances in embedded deep learning accelerators designed for resource-constrained systems, with a particular focus on RISC-V processors and edge computing platforms.

**Problem the review claims to solve**

Deep neural networks require significant computational power, memory bandwidth, and energy consumption, which makes their deployment on embedded systems challenging. The review analyzes hardware accelerator designs that aim to address these constraints.

**Scope**

- Embedded deep learning accelerators  
- Edge AI and embedded machine learning  
- RISC-V processors  
- CNN accelerators  
- Object detection accelerators  
- Transformer accelerators  
- Hardware–software co-design for embedded ML  

**Main contributions claimed by the authors**

- Overview of recent deep learning accelerators for embedded systems  
- Analysis of RISC-V ISA extensions for machine learning workloads  
- Review of heterogeneous accelerator architectures  
- Comparative discussion of existing hardware implementations  
- Identification of open challenges and future research directions  

---

## 3. Search Methodology

**Databases Used**

Not reported.

**Search Strings**

Not reported.

**Time Range**

Not explicitly defined.  
The cited literature generally spans approximately 2015–2023.

**Study Types Included**

Based on references cited in the paper, the included studies appear to include:

- Journal articles  
- Conference papers  
- Preprints (e.g., arXiv)  
- Hardware architecture papers  

However, explicit study-type inclusion criteria are not reported.

---

## 4. Inclusion and Exclusion Criteria

Not reported.

The paper does not explicitly define formal inclusion or exclusion criteria for selecting the reviewed studies.

---

## 5. Deduplication and Screening Process

**Duplicate removal**

Not reported.

**Title and abstract screening**

Not reported.

**Full-text screening**

Not reported.

**Selection process**

The paper does not describe a systematic screening or filtering process.  
Studies appear to have been manually selected and organized according to accelerator architecture categories.

---

## 6. PRISMA or Selection Flow

**PRISMA used**

No.

**Counts of papers at each stage**

Not reported.

**Filtering stages**

Not reported.

No PRISMA diagram or equivalent selection flow diagram is provided.

---

## 7. Data Extraction Method

The review extracts several types of information from the analyzed studies.

Typical extracted fields include:

**Hardware architecture**

- Accelerator architecture design  
- Processing elements  
- Memory hierarchy  
- Hardware organization  

**Target processor or platform**

- RISC-V processors  
- ARM-based embedded systems  
- FPGA implementations  
- Heterogeneous CPU–FPGA systems  

**Model type**

Examples include:

- CNN models  
- YOLO object detection models  
- SSD object detection models  
- 3D CNN models  
- Transformer models (e.g., BERT)

**Performance metrics**

- Inference latency  
- Frames per second (FPS)  
- Throughput (e.g., GOPS)  
- Execution time  

**Hardware resource usage**

- LUT utilization  
- DSP blocks  
- BRAM usage  
- FPGA resources  
- Chip area  

**Energy and power**

- Power consumption  
- Energy efficiency  

**Accuracy metrics**

- Classification accuracy  
- Detection accuracy  
- Mean Average Precision (mAP)

---

## 8. Quality Assessment / Risk of Bias

**Quality assessment present**

No.

**Assessment method**

Not reported.

**Number of criteria**

Not reported.

The paper does not include a formal methodological quality assessment of the included studies.

---

## 9. Types of Analysis Used

The literature is synthesized using multiple qualitative approaches.

**Narrative synthesis**

The main synthesis method consists of descriptive explanations of accelerator architectures and implementations.

**Taxonomy / categorization**

The literature is organized into categories such as:

- CNN accelerators  
- Object detection accelerators  
- Transformer accelerators  
- ISA extensions for ML  
- In-memory computing architectures  

**Comparative tables**

Several tables compare hardware implementations using metrics such as performance, power consumption, and resource utilization.

**Architecture analysis**

The paper provides detailed descriptions of accelerator architectures and system designs.

**Trend analysis**

The authors identify technological trends, including:

- increasing adoption of RISC-V for ML acceleration  
- heterogeneous computing architectures  
- in-memory computing approaches  

---

## 10. Figures and Tables Used in the Review

The paper includes several types of figures and tables.

**Architecture diagrams**

Examples include diagrams of CNN accelerators, object detection accelerators, and RISC-V-based systems.

**Hardware comparison tables**

Tables compare accelerator implementations based on resource usage and hardware configurations.

**Performance comparison tables**

Tables report metrics such as:

- latency  
- throughput  
- energy consumption  
- resource utilization  

**State-of-the-art summary tables**

Summary tables consolidate information about multiple accelerator designs and their characteristics.

---

## 11. Practical Recommendations

The authors suggest several research directions for future work.

**In-memory computing and 3D integration**

Reducing data transfer costs by bringing computation closer to memory.

**Model optimization techniques**

Use of:

- pruning  
- knowledge distillation  
- model compression  
- partitioning strategies  

**Memory communication optimization**

Improving memory hierarchies and data reuse to reduce bandwidth bottlenecks.

**Toolchain and compiler development**

Development of compilers and frameworks to simplify deployment of ML models on RISC-V hardware.

**Algorithm–hardware co-design**

Designing machine learning algorithms that are optimized for embedded hardware accelerators.

**Optical AI accelerators**

Exploring optical computing approaches for future AI hardware.

---

## 12. Limitations of the Review

The paper discusses limitations primarily related to the field rather than the review methodology.

Examples include:

- limited hardware resources on embedded platforms  
- memory bandwidth bottlenecks  
- challenges deploying large neural networks on edge devices  
- complexity of heterogeneous accelerator systems  

However, methodological limitations of the review itself are not explicitly discussed.

---

## 13. Methodological Strengths of This Review

- Broad coverage of embedded deep learning accelerator architectures  
- Detailed discussion of hardware design techniques  
- Comparative tables summarizing performance and resource usage  
- Coverage of multiple model families (CNNs, object detection models, transformers)  
- Discussion of future research challenges in edge AI hardware  

---

## 14. Potential Methodological Weaknesses

- No systematic search strategy described  
- Databases used for literature collection are not reported  
- Search strings are not provided  
- No inclusion or exclusion criteria defined  
- No description of screening or deduplication process  
- No PRISMA flow diagram  
- No formal quality assessment of included studies  

These characteristics indicate that the paper is a **narrative survey rather than a formal systematic literature review**.

---

## 15. Extracted SLR Methodology Checklist

SLR Methodology Checklist:

- [ ] Multiple databases used  
- [ ] Search strings reported  
- [ ] Time window defined  
- [ ] Inclusion/exclusion criteria defined  
- [ ] Deduplication described  
- [ ] PRISMA flow diagram used  
- [x] Data extraction fields defined  
- [ ] Quality assessment performed  
- [x] Comparative tables included  
- [x] Quantitative synthesis included
