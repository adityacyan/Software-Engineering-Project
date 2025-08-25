# 1. Introduction  

## Objectives  
1. **Automation:** Automate over 90% of the grading process.  
2. **Accuracy:** Achieve a grading accuracy of 95% or higher.  
3. **Efficiency:** Reduce the average grading time per sheet by at least 80%.  
4. **Security:** Ensure end-to-end security of all student data.  
5. **Usability:** Provide an intuitive interface for teachers and professors.  

## Performance Issues  
- The system must process batches of 50–200 answer sheets quickly, without OCR/LLM errors.  
- The OCR pipeline must minimize scanning failures.  
- Low latency in grading results is expected (real-time or near real-time).  

## Management & Technical Constraints  
- Limited to English-language handwritten exam papers.  
- Requires internet connection for cloud-based LLM evaluation.  
- Must adhere to academic data privacy standards.  

---

# 2. Project Estimates  

## Historical Data Used  
- Reference to existing OCR-based evaluation systems.  
- Benchmarks from manual evaluation time (average ~10–15 minutes per sheet).  

## Estimation Technique  
- Expert judgment + analogy-based estimation.  

## Estimates  
- **Development Duration:** ~4–5 months (MVP).  
- **Effort:** ~8–10 person-months.  
- **Cost:** Based on small development team (3–4 people).  

---

# 3. Project Schedule  

- **Phase 1 (Month 1):** Requirement analysis, system architecture design.  
- **Phase 2 (Month 2–3):** Core development (OCR pipeline, LLM evaluation).  
- **Phase 3 (Month 4):** Frontend integration, reporting system, testing.  
- **Phase 4 (Month 5):** Deployment, teacher feedback, refinements.  

---

# 4. Project Resources  

## People  
- Project Manager (1)  
- Backend Developer (1)  
- Frontend Developer (1)  
- ML/OCR Specialist (1)  
- QA Engineer (1)  

## Software  
- OCR Engine (**Tesseract**)  
- LLM API (**OpenAI / Local Ollama**)  
- Backend: **Python (FastAPI / Django)**  
- Frontend: **React.js**  
- Database: **PostgreSQL / MySQL (TBD)**  

## Special Resources  
*(To be detailed if needed)*  

---

# 5. Staff Organisation  

## Team Structure  
- **Development Team:** Backend, frontend, OCR/ML modules.  
- **QA Team:** Testing, bug tracking, user acceptance.  
- **Support Team:** Documentation, deployment.  

## Management  
*(Roles & responsibilities to be expanded as needed)*  

---

# 6. Risk Management  

1. **Poor Handwriting Recognition** → OCR might struggle with messy handwriting.  
   - *Mitigation:* Preprocessing filters, confidence thresholds, teacher override option.  

2. **LLM Accuracy Risks** → Inconsistent grading for subjective answers.  
   - *Mitigation:* Semantic similarity thresholds, manual overrides.  

3. **Data Security Risks** → Potential student data leaks.  
   - *Mitigation:* Encrypted storage, secure authentication.  

4. **Scalability Issues** → High loads (1000+ sheets) may cause delays.  
   - *Mitigation:* Batch processing, cloud scaling.  

---

# 7. Project Tracking & Control  

## Metrics Used  
- % automation in grading achieved.  
- OCR accuracy rate vs. ground truth.  
- Average evaluation time per sheet.  
- Number of teacher overrides (manual corrections).  
- Security audit logs.  

---

# 8. Miscellaneous  

- **Deliverables:**  
  - Web-based MVP  
  - User documentation  
  - Deployment guide  
  - Evaluation reports (PDF/CSV)  

- **Future Enhancements:**  
  - Local/offline LLM support  
  - Multi-language support  
  - LMS integrations  
  - Advanced analytics  
