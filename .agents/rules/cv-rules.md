---
trigger: always_on
---

# Agent Workspace Rules: CV & LaTeX Engineering

## 1. Truthfulness & Data Integrity (Zero-Hallucination Policy)
* **Never invent facts:** All dates, company names, titles, certifications, degrees, and institutions must match `EN/CareerMasterDocument/` exactly.
* **Metric preservation:** Do not fabricate numbers, percentages, or metrics. Only use quantified results explicitly listed in `Quantifiable_Results.md` or the respective job files.
* **Chronology:** Maintain strict reverse-chronological order for work experience and education.

## 2. LaTeX Syntax & Safety
* **Special Character Escaping:** Ensure reserved LaTeX characters are properly escaped in any text injected from Markdown files:
  * `%` $\rightarrow$ `\%`
  * `&` $\rightarrow$ `\&`
  * `_` $\rightarrow$ `\_`
  * `$` $\rightarrow$ `\$`
  * `#` $\rightarrow$ `\#`
* **Macro Preservation:** Do not alter preamble declarations, custom macros (e.g., `\resumeItem`, `\resumeSubheading`), spacing commands, or document class settings in `CV_Jairo_Cabrera.tex`.
* **Clean Diff:** Only edit the body environments (e.g., within `\begin{itemize}` / `\end{itemize}` or specific section commands).

## 3. ATS & Content Standards
* **Bullet Formula:** Phrase bullet points starting with strong past-tense action verbs (e.g., *Architected*, *Engineered*, *Reduced*, *Automated*), focusing on **Action + Context + Quantifiable Result**.
* **Targeting:** Match keywords naturally from `target_job.md` to items found in `EN/CareerMasterDocument/Keywords.md` and `Technologies.md`. Never engage in "keyword stuffing" or hidden text tricks.
* **Length Constraint:** Keep the final document fitted to the target page budget (e.g., exactly 1 or 2 pages) without overflowing by just a few trailing lines.

## 4. File Boundary Permissions
* **Write Access:** Write/modify only `CV_Jairo_Cabrera.tex` (or files inside `output/`).
* **Read-Only:** Treat all files in `EN/CareerMasterDocument/` as strictly read-only.