# Ontology Requirements Specification Document (v2)

### Changelog: What has changed compared to Version 1 (v1)?

* **Expanded Class Hierarchy:** The `Course` class was branched into `MandatoryCourse` and `ElectiveCourse`. The `Person` class was expanded to include `AcademicStaff`, which is further divided into `Professor` and `ResearchAssistant`. The `SubField` class was introduced to model academic sub-departments.
* **New Object Properties:** Added `worksIn` (linking staff to sub-fields), `hasSubField` (linking departments to sub-fields), `hasCourse`, `offeredIn`, and `supervises`.
* **New Data Properties:** Added `courseCode`, `courseName`, `semester`, `fullName`, `title`, `email`, `avesisURL`, `studentID`, `GPA`, `departmentName`, and `subFieldName` to hold real-world data.
* **Disjointness Constraints:** Implemented strict disjoint rules between `Professor`, `ResearchAssistant`, and `Student`; as well as between `MandatoryCourse` and `ElectiveCourse`.
* **Data Source Shift:** Transitioned from dummy data to real-world academic data extracted from the Manisa Celal Bayar University (MCBU) Bologna Information System and AVESİS portal, utilizing LLMs for unstructured text parsing.

---

### ORSD Table

| Ref | Section | Content |
| :--- | :--- | :--- |
| **1** | **Purpose** | To formalize the semantic relationships within the Manisa Celal Bayar University (MCBU) Faculty of Engineering ecosystem, specifically modeling student enrollments, faculty-subfield assignments, and complex mandatory/elective course prerequisite structures to enable automated academic reasoning. |
| **2** | **Scope** | The ontology covers the MCBU Engineering Faculty (CSE, MEE, and IE departments), their academic sub-fields, academic staff (Professors and Research Assistants), students, academic terms, and course hierarchies. It excludes administrative staff, campus facilities, and financial systems. |
| **3** | **Implementation Language** | OWL 2 (Web Ontology Language) / RDF, developed using Protégé. METHONTOLOGY framework applied. |
| **4** | **Intended End-Users** | University Students, Academic Advisors, and Department Heads. |
| **5** | **Intended Uses** | Automated prerequisite validation, curriculum workload analysis, course recommendation systems, and serving as a structured knowledge base for future machine-learning-based risk analysis models. |
| **6** | **Ontology Requirements** | |
| | **a. Non-Functional Requirements** | - Must be developed using W3C Semantic Web standards (OWL).<br>- Must support automated reasoning (e.g., using HermiT) without logical conflicts.<br>- Must enforce disjointness among distinct academic roles to ensure data integrity.<br>- Must scale to accommodate new faculties. |
| | **b. Functional Requirements (CQs)** | **CQ1:** What are the mandatory courses offered in the 5th semester of the CSE department?<br>**CQ2:** What are the prerequisites for the "Automata Theory" course?<br>**CQ3:** In which sub-field does a specific Professor work, and which courses do they teach?<br>**CQ4:** Who are the Research Assistants working in the Operations Research sub-field?<br>**CQ5:** Which courses is a specific Student currently enrolled in? |
| **7** | **Pre-Glossary of Terms** | |
| | **a. Terms from CQs** | Mandatory Course, Semester, Department, Prerequisite, Sub-field, Professor, Research Assistant, Enrolled, Teach. |
| | **b. Terms from Answers** | `hasPrerequisite`, `belongsTo`, `worksIn`, `hasSubField`, `teaches`, `isEnrolledIn`, `hasCourse`, `offeredIn` (Object Properties). |
| | **c. Objects** | `Student`, `Professor`, `ResearchAssistant`, `MandatoryCourse`, `ElectiveCourse`, `Department`, `SubField`, `AcademicTerm` (Core Classes). |


