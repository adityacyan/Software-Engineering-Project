# Software Requirement Specification (SRS)  
**Project Name:** Automated Exam Paper Evaluation System  
**Version:** 1.0 
**Prepared For:** School & College Teachers  

---

## 1. Introduction

### 1.1 Purpose  
The system is designed to help teachers and professors automate the evaluation of exam papers. It leverages OCR and LLMs to read student answer sheets, compare them against teacher-provided question papers and answer keys, and assign marks with short feedback.

### 1.2 Scope  
- Input: Scanned handwritten answer sheets (students) + question paper & answer key (teacher).  
- Processing: OCR → text parsing → semantic similarity evaluation / LLM-based grading.  
- Output: Student-wise evaluation with marks and short comments.  
- Deployment: Web-based application.  
- Users: Teachers, professors, academic staff.  

### 1.3 Definitions  
- **OCR:** Optical Character Recognition for extracting text from scanned student answer sheets.  
- **LLM:** Large Language Model for semantic similarity and grading.  
- **Answer Key:** Teacher-provided correct answers used to align evaluation.  

---

## 2. System Overview

1. Teacher uploads:  
   - Question paper  
   - Answer key  
   - Student scanned answer sheets  
2. OCR processes answer sheets into text.  
3. System evaluates answers:  
   - Objective questions: Exact/close match evaluation.  
   - Subjective questions: Semantic similarity/LLM-based scoring.  
4. Marks assigned + short explanation of deductions.  
5. Teacher receives detailed evaluation reports.

---

## 3. Functional Requirements

### 3.1 User Management  
- Teacher registration & login (authentication required).  
- Role-based access: Teachers only.  

### 3.2 Exam Setup  
- Upload question paper (PDF/DOC).  
- Upload answer key.  
- Define marks allocation per question.  

### 3.3 Student Paper Submission  
- Upload scanned handwritten answer sheets (PDF/JPG/PNG).  
- OCR extracts answers.  

### 3.4 Evaluation  
- **Objective Questions:** Automatic grading (exact/close match).  
- **Subjective Questions:** LLM evaluates with semantic similarity to key.  
- Marks assigned per question.  
- Short explanation if marks deducted.  

### 3.5 Output  
- Individual student reports:  
  - Question-wise marks  
  - Total score  
  - Short feedback (e.g., "missed definition," "explanation incomplete")  
- Export results (PDF, CSV).  

---

## 4. Non-Functional Requirements

### 4.1 Performance  
- Optimized for classroom-level loads (50–200 answer sheets per batch).  
- Low-latency OCR and evaluation pipeline.  

### 4.2 Security  
- Secure authentication for teachers.  
- Data privacy for student answer sheets.  
- Future option for local deployment (running LLM on local machine).  

### 4.3 Scalability  
- Initial scope: small classroom-level.  
- Future extensibility for larger batches.  

### 4.4 Usability  
- Intuitive web interface.  
- Clear result visualization.  

---

## 5. System Architecture (High-Level)

- **Frontend:** Web UI for teachers.  
- **Backend:**  
  - OCR module  
  - LLM evaluation module (cloud initially, optional local with Ollama later)  
  - Evaluation engine (marks assignment, explanation generation)  
- **Database:** Stores exams, answer keys, results.  

---

## 6. Use Cases

### Use Case 1: Teacher Registers & Logs In
**Actor:** Teacher  
**Precondition:** Teacher not registered.  
**Steps:**  
1. Teacher opens web app.  
2. Fills registration form with email/password.  
3. System verifies and stores credentials.  
4. Teacher logs in using credentials.  
**Postcondition:** Teacher authenticated.  

---

### Use Case 2: Teacher Creates Exam Setup
**Actor:** Teacher  
**Precondition:** Teacher logged in.  
**Steps:**  
1. Teacher uploads question paper file.  
2. Teacher uploads answer key.  
3. Teacher assigns marks per question.  
4. System saves exam configuration.  
**Postcondition:** Exam setup ready for evaluation.  

---

### Use Case 3: Teacher Uploads Student Answer Sheets
**Actor:** Teacher  
**Precondition:** Exam setup completed.  
**Steps:**  
1. Teacher uploads batch of scanned answer sheets.  
2. OCR module extracts text from images.  
3. Extracted text linked to student ID/roll number.  
**Postcondition:** Student answers stored for evaluation.  

---

### Use Case 4: Automatic Evaluation
**Actor:** System  
**Precondition:** Student answers available.  
**Steps:**  
1. System compares each student answer to the key.  
   - Objective: exact/close match check.  
   - Subjective: semantic similarity via LLM.  
2. System assigns marks.  
3. System generates short explanation for deductions.  
**Postcondition:** Marks + feedback ready.  

---

### Use Case 5: Teacher Reviews Results
**Actor:** Teacher  
**Precondition:** Evaluation completed.  
**Steps:**  
1. Teacher accesses result dashboard.  
2. Views per-student marks, question-wise breakdown, comments.  
3. Optionally edits/overrides system-assigned marks.  
4. Exports results (PDF/CSV).  
**Postcondition:** Teacher has finalized evaluation reports.  

---

## 7. Constraints  
- English language only (initial version).  
- Handwritten student answers only (no typed answers).  
- Internet connection required for cloud LLM evaluation (initial).  

---

## 8. Future Enhancements  
- Local LLM processing with Ollama.  
- Multi-language support.  
- LMS integrations (Google Classroom, Moodle).  
- Detailed analytics dashboards.  

---

## 9. Deliverables  
- Web application (MVP).  
- Documentation (user manual, deployment guide).  
- Evaluation reports (PDF/CSV export).  
