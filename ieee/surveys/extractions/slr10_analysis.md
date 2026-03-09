# SLR10 Analysis

## 1. Basic Information

**Title:**  
Real-Time Apple Detection System Using Embedded Systems With Hardware Accelerators: An Edge AI Application

**Authors:**  
Vittorio Mazzia, Aleem Khaliq, Francesco Salvetti, Marcello Chiaberge

**Year:**  
2020

**Journal / Conference:**  
IEEE Access

**Type of review:**  
Not a review. Primary research article (experimental study).

---

## 2. Scope and Purpose of the Review

**Main objective of the review:**  
Not reported. The paper does not conduct a literature review. Instead, it proposes and evaluates an embedded deep learning system for real-time apple detection in orchards.

**Problem the review claims to solve:**  
The paper addresses the challenge of performing accurate and real-time fruit detection in orchard environments using low-power embedded hardware suitable for edge AI applications.

**Scope:**  
Edge AI, embedded systems, computer vision, object detection, precision agriculture.

**Main contributions claimed by the authors:**

- Proposal of a real-time apple detection system based on a modified YOLOv3-tiny architecture.
- Adaptation of YOLOv3-tiny to improve detection of small objects such as apples in orchard environments.
- Deployment and evaluation of the model on multiple embedded platforms (Raspberry Pi + Intel Movidius NCS, Jetson Nano, Jetson AGX Xavier).
- Evaluation of detection accuracy, inference speed, and power consumption on edge devices.
- Demonstration that edge AI solutions can perform real-time fruit detection with acceptable accuracy and low power consumption.

---

## 3. Search Methodology

**Databases Used:**  
Not reported.

**Search Strings:**  
Not reported.

**Time Range:**  
Not reported.

**Study Types Included:**  
Not reported.

---

## 4. Inclusion and Exclusion Criteria

Not reported.

The paper does not define criteria for including or excluding studies because it does not conduct a systematic or structured literature review.

---

## 5. Deduplication and Screening Process

**Duplicate removal described:**  
Not reported.

**Title/abstract screening described:**  
Not reported.

**Full-text screening described:**  
Not reported.

**Selection process:**  
Not applicable. The paper does not perform study selection or screening of literature.

---

## 6. PRISMA or Selection Flow

**PRISMA used:**  
No.

**Counts of papers reported at each stage:**  
Not reported.

**Stages of filtering:**  
Not applicable.

---

## 7. Data Extraction Method

Not applicable for literature review.

However, the paper extracts and evaluates experimental data related to the proposed system. The main evaluated variables include:

- neural network architecture (modified YOLOv3-tiny)
- dataset used for training and testing
- training parameters
- detection precision
- detection recall
- mean Average Precision (mAP)
- intersection over union (IoU)
- inference speed (frames per second)
- power consumption
- hardware platform characteristics
- price/performance ratio of embedded devices

---

## 8. Quality Assessment / Risk of Bias

**Quality assessment exists:**  
No.

**Method or rubric used:**  
Not reported.

**Number of criteria:**  
Not reported.

---

## 9. Types of Analysis Used

The paper uses experimental and quantitative analysis rather than literature synthesis.

The main types of analysis include:

- quantitative evaluation of detection performance using precision, recall, and mean Average Precision (mAP)
- comparison between the original YOLOv3-tiny architecture and the modified architecture
- benchmarking of embedded hardware platforms
- analysis of inference speed and power consumption
- qualitative visual inspection of detection results on orchard images

---

## 10. Figures and Tables Used in the Review

Typical figures and tables include:

- architecture diagrams of YOLOv3-tiny and the modified model
- detection pipeline illustrations
- qualitative detection examples with bounding boxes
- tables comparing detection accuracy metrics
- tables comparing inference speed across embedded platforms
- tables showing power consumption and price/performance ratios

Examples include:

- model architecture diagrams
- detection examples in orchard scenes
- performance comparison tables for different devices
- experimental evaluation metrics (precision, recall, mAP)

---

## 11. Practical Recommendations

The authors suggest that the proposed system can support several practical agricultural applications, including:

- real-time apple counting
- crop yield estimation
- robotic fruit harvesting
- orchard monitoring and management

The results indicate that embedded edge AI devices such as Jetson Nano provide a good balance between cost and performance for deploying such systems.

The methodology could also be adapted for other small-object detection tasks in edge computing environments.

---

## 12. Limitations of the Review

The limitations mentioned or implied in the paper include:

- experiments conducted using a relatively small dataset collected from a specific orchard environment
- focus on a single object class (apples)
- limited evaluation across different agricultural scenarios
- image registration for accurate apple counting is not addressed
- evaluation limited to selected embedded hardware platforms

---

## 13. Methodological Strengths of This SLR

Although this is not a systematic review, the study presents several methodological strengths in its experimental design:

- use of real-world orchard images for training and testing
- modification of an existing deep learning architecture to address a specific problem (small object detection)
- deployment and evaluation on multiple embedded hardware platforms
- analysis of both accuracy and hardware efficiency metrics
- comparison between the proposed model and baseline architecture

---

## 14. Potential Methodological Weaknesses

From a systematic review perspective, the main weaknesses include:

- absence of a systematic literature search
- no defined search strategy or search strings
- no defined inclusion or exclusion criteria
- no study screening process
- no PRISMA flow diagram
- no quality assessment of prior studies

From an experimental perspective:

- limited dataset size
- evaluation restricted to apple detection
- limited analysis of generalization to other environments

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
