# 📄 AI-Powered Career Master Document & CV Templates

> **Transform your career history into specialized, high-converting, ATS-optimized CVs and Cover Letters using AI.**

This repository is a modular, AI-ready **Career Master Document system**. Instead of maintaining multiple static resume versions, you document an exhaustive, high-resolution record of your entire career in one place. When you apply for a new role, an AI assistant reads your master files and the target job description to generate a perfectly tailored CV, LaTeX resume, or Cover Letter.

---

## 🗂️ Repository Structure

```
cv-templates/
│
├── 📁 CareerMasterDocument/               # Your Master Career Knowledge Base
│   ├── 📄 Personal_Information.md         # Contact info, social links, spoken languages
│   ├── 📄 Professional_Summary.md         # Bank of tailored profile summaries & hooks
│   ├── 📄 CareerVision.md                 # Core values, work philosophy & cover letter builder
│   ├── 📄 Skills.md                       # Functional competencies & engineering practices
│   ├── 📄 Technologies.md                 # Granular tech stack, frameworks, tools & languages
│   ├── 📄 Keywords.md                     # ATS keyword matrix & industry terminology
│   ├── 📄 Achievements.md                 # Awards, honors, hackathons & milestones
│   ├── 📄 Certifications.md               # Licenses, vendor credentials & specialized courses
│   ├── 📄 Education.md                    # Degrees, coursework, GPA & academic honors
│   ├── 📄 Projects.md                     # Technical portfolio, open source & client projects
│   ├── 📄 Leadership.md                   # Team management, mentorship & initiative logs
│   ├── 📄 Quantifiable_Results.md         # Consolidated metrics (latency, revenue, SLA, scale)
│   ├── 📄 Publications_Talks.md           # Research papers, conference talks & articles
│   │
│   └── 📁 Work_Experience/                # 💼 Individual Job Records (Add as many as needed!)
│       ├── 📄 job1.md                     # Master job template / Most recent experience
│       ├── 📄 job2.md                     # (Optional) Previous company / role
│       └── 📄 job3.md                     # (Optional) Previous company / role
│
├── 📁 Developer_template/                 # 📐 LaTeX & PDF Resume Templates
│   ├── 📄 template.tex                    # Clean, ATS-compliant LaTeX CV template
│   └── 📄 template.pdf                    # Compiled visual preview of the CV template
│
├── 📄 target_job.md                       # 🎯 Paste the job description you are targeting here
└── 📄 README.md                           # 📖 This step-by-step setup guide
```

---

## 🚀 Step-by-Step Setup Guide

Follow these steps to populate your master repository:

### Step 1: Fill Out Your Core Identity & Vision
1. Open [Personal_Information.md](CareerMasterDocument/Personal_Information.md): Fill in your name, contact details, LinkedIn, GitHub, portfolio URLs, and spoken languages.
2. Open [CareerVision.md](CareerMasterDocument/CareerVision.md): Define your career North Star, engineering values (*0-to-1 building vs. maintenance*), target problem spaces, and personal anecdotes. This serves as the foundation when an AI writes your cover letters.

### Step 2: Document Your Work Experience
Inside the [Work_Experience/](CareerMasterDocument/Work_Experience/) folder:
- [job1.md](CareerMasterDocument/Work_Experience/job1.md) contains a comprehensive, categorized template.
- **You can add as many jobs inside `Work_Experience/` as you need!**  
  Simply duplicate `job1.md` and create `job2.md`, `job3.md`, or name them by company (e.g., `google.md`, `startup_x.md`).
- > [!IMPORTANT]
  > **Write more, not less!** Do not cut or summarize prematurely here. Record every system designed, API built, team mentored, and metric achieved. Let the AI do the pruning when generating a tailored CV.
- Format achievements using the Google X-Y-Z formula:  
  **"Accomplished [X] as measured by [Y] by doing [Z]"**.

### Step 3: Populate Your Skills, Tech Stack & Evidence
1. **[Technologies.md](CareerMasterDocument/Technologies.md):** List your programming languages, backend frameworks, databases, cloud providers, and DevOps tooling.
2. **[Skills.md](CareerMasterDocument/Skills.md):** Describe your functional engineering capabilities (e.g., *Microservice Decomposition*, *Relational Schema Design*, *Agentic Workflow Orchestration*).
3. **[Keywords.md](CareerMasterDocument/Keywords.md):** Add ATS search terms, acronyms, and variations (e.g., *LLMs / Large Language Models*, *RAG*).
4. **[Projects.md](CareerMasterDocument/Projects.md):** Detail 3–5 flagship personal, open-source, or client projects with problem, architecture, tech stack, and measurable impact.
5. **[Achievements.md](CareerMasterDocument/Achievements.md):** Log awards, hackathons, scholarships, and career milestones.
6. **[Education.md](CareerMasterDocument/Education.md) & [Certifications.md](CareerMasterDocument/Certifications.md):** Record formal degrees, coursework, and professional credentials.

---

## 🎯 How to Generate a Tailored CV (Automated Workflow)

You do **not** need to write or fiddle with manual prompts! This repository includes a pre-configured agent workflow ([`.agents/workflows/create-new-cv.md`](.agents/workflows/create-new-cv.md)) with all role prompts, data integrity rules, ATS constraints, and LaTeX generation instructions built-in.

### 1. Paste the Target Job
Copy the target job posting, role title, requirements, and responsibilities into [target_job.md](target_job.md) and save the file.

### 2. Run the Workflow
Trigger the automated CV creation workflow in your AI assistant:
- **Slash Command (Antigravity IDE / Agent UI):**
  ```text
  /create-new-cv
  ```
- **Direct Agent Instruction:**
  ```text
  Execute the workflow in `.agents/workflows/create-new-cv.md`
  ```

### 3. What the Workflow Does Automatically:
1. **Validates Input:** Reads [target_job.md](target_job.md) and verifies that a real job posting is present (stops if the placeholder is still there).
2. **Knowledge Extraction:** Cross-references the job requirements against your master files in [CareerMasterDocument/](CareerMasterDocument/) (experience, projects, skills, technologies, and achievements).
3. **Keyword & Metric Alignment:** Extracts matching ATS keywords and quantifiable metrics.
4. **CV Generation:** Updates the CV template with targeted, high-impact bullet points adhering strictly to factual data (zero hallucinations).

---

## 🛠️ Compiling the LaTeX CV Template (PDF Generation)

> **🤖 Automated by AI:**  
> The AI assistant will automatically compile your generated LaTeX CV into a production-ready PDF upon running the workflow.

However, for the AI (or you) to compile `.tex` files into `.pdf` locally on your system, you need a LaTeX engine installed.

### Recommended Installations (Pick One):

#### ⚡ Option A: Tectonic (Strongly Recommended — Lightweight & Fast)
[Tectonic](https://tectonic-typesetting.github.io/) is a modern, self-contained TeX engine that automatically downloads required LaTeX packages on the fly with zero manual configuration.
- **Windows (PowerShell / Winget):**
  ```powershell
  winget install tectonic
  ```
- **macOS (Homebrew):**
  ```bash
  brew install tectonic
  ```
- **Linux:**
  ```bash
  curl --proto '=https' --tlsv1.2 -fsSL https://drop-sh.fullyjustified.net | sh
  ```

#### 📦 Option B: MiKTeX or TeX Live (Standard Distributions)
- **Windows (MiKTeX):**
  ```powershell
  winget install MiKTeX.MiKTeX
  ```
- **Ubuntu / Debian (TeX Live):**
  ```bash
  sudo apt update && sudo apt install texlive-latex-extra
  ```

#### 🌐 Option C: Overleaf (Zero-Install Online Fallback)
If you prefer not to install anything locally, simply upload [Curriculum_Vitae.tex](createdCV/Curriculum_Vitae.tex) directly to [Overleaf](https://www.overleaf.com/) and click **Recompile** to download your PDF.

---

## 💡 Best Practices & Maintenance
- **Update Continuously:** Every time you ship a major feature, complete a certification, or hit a performance milestone, add a bullet point with metrics to the relevant file.
- **Never Fake Metrics:** Ground all quantitative claims (%, $, latency, scale) in real achievements.
- **Let the AI Filter:** Your master document can be 10+ pages long; the AI's job is to extract the single best page for each unique application.
