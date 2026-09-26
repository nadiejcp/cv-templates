---
description: Generates a tailored CV in English based on CareerMasterDocument and target_job.md.
---

---
inputs:
  job_description_file: "target_job.md"
  base_directory: "CareerMasterDocument"
  template: "template.tex"
outputs:
  target_file: "createdCV/Curriculum_Vitae.tex"
  pdf_file: "createdCV/Curriculum_Vitae.pdf"
---

# Role & Context
Act as an expert technical recruiter and professional resume writer.

# Pre-checks
Before proceeding with generation, validate the following:
1. **Target Job Content:** Verify that `target_job.md` exists and contains a non-empty, valid job description. If missing or empty, notify the user and stop execution.
2. **Template Existence:** Verify that `template.tex` exists in the root directory. If absent, alert the user that a template must be selected first, then stop execution.
3. **Redundancy Check:** If `createdCV/Curriculum_Vitae.pdf` already exists, check whether its content is already tailored to the current `target_job.md`. If it already satisfies the target requirements, notify the user that an updated CV for this role already exists and ask for confirmation before overwriting.

# Task
1. Read the target role requirements directly from `target_job.md`.
2. Cross-reference files in `CareerMasterDocument/` to extract the most relevant experience, technical skills, and quantifiable achievements matching the target role.
3. Populate `template.tex` with the extracted content and write the result to `createdCV/Curriculum_Vitae.tex`.
4. If a LaTeX compiler (`pdflatex`, `xelatex`, or `latexmk`) is available in the environment, compile `createdCV/Curriculum_Vitae.tex` to produce `createdCV/Curriculum_Vitae.pdf` otherwise notify the user to install one of them.

# Instructions & Constraints
* **Source of Truth:** Match requirements solely against `target_job.md`.
* **Data Integrity:** Strictly preserve factual dates, companies, education, and job history from `CareerMasterDocument/`. Do not fabricate metrics, technologies, or roles.
* **Template Structure:** Preserve all LaTeX macros, packages, and layout conventions defined in `template.tex`. Escape special LaTeX characters (`%`, `_`, `&`, `$`, `#`) in dynamic content.
* **Language:** English.