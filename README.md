<div align="center">

<!-- Typing SVG Header -->
<a href="https://github.com/Aditya2007raj/AI-Resume-Analyzer">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&pause=1000&color=00D9FF&center=true&vCenter=true&width=600&lines=AI+Resume+Analyzer;LLM-Powered+Resume+%E2%86%92+JD+Matching;Built+with+LangChain+%2B+Groq;ATS+Score+%2B+Skill+Gap+Detection" alt="Typing SVG" />
</a>

<br/>

<!-- Badges -->
<p>
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" />
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white" />
  <img src="https://img.shields.io/badge/Groq-F55036?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PC9zdmc+&logoColor=white" />
  <img src="https://img.shields.io/badge/Pydantic-E92063?style=for-the-badge&logo=pydantic&logoColor=white" />
</p>

<p>
  <img src="https://img.shields.io/badge/status-active--development-brightgreen?style=flat-square" />
  <img src="https://img.shields.io/badge/license-MIT-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/PRs-welcome-orange?style=flat-square" />
  <img src="https://img.shields.io/github/stars/Aditya2007raj/AI-Resume-Analyzer?style=flat-square&color=yellow" />
</p>

</div>

---

## 📖 Overview

**AI Resume Analyzer** is an intelligent resume evaluation system that helps job seekers understand how well their resumes align with specific job descriptions.

It extracts information from uploaded resumes, converts it into structured data using **Large Language Models (LLMs)**, and compares it against a job description to generate **ATS-style compatibility insights** — matching skills, missing skills, and actionable recommendations.

---

## ❓ Problem Statement

Recruiters often receive hundreds of resumes for a single position. Candidates usually struggle to determine:

- Whether their resume matches the target role
- Which skills are missing
- How ATS systems may evaluate their profile

**AI Resume Analyzer automates that evaluation process and provides actionable feedback.**

---

## 🎯 Objectives

- 📄 Extract structured information from resumes
- 🧩 Identify candidate skills and experience
- 🔍 Compare resumes against job descriptions
- 📊 Calculate ATS-style compatibility scores
- ❌ Detect missing skills
- 💡 Generate professional hiring insights

---

## 🏗️ System Architecture

```text
PDF Resume
     │
     ▼
PDF Text Extraction
     │
     ▼
Resume Parsing Engine
     │
     ▼
Structured Resume Object
     │
     ├────────► Resume Details
     │
     ▼
Job Description Matcher
     │
     ▼
ATS Evaluation Engine
     │
     ▼
Analysis Report
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| 🖥️ Frontend | Streamlit |
| ⚙️ Backend | Python |
| 🧠 LLM Framework | LangChain |
| ⚡ LLM Provider | Groq |
| 🤖 Model | Llama 3.3 70B Versatile |
| ✅ Data Validation | Pydantic |
| 📑 PDF Processing | PyPDF |
| 🔐 Configuration Management | python-dotenv |

---

## 📂 Project Structure

```text
AI-Resume-Analyzer/
│
├── main.py
├── parser.py
├── matcher.py
├── models.py
├── prompt.py
├── requirements.txt
├── Documentation.md
├── README.md
│
└── uploads/
```

---

## 🧩 Module Breakdown

<details>
<summary><b>📌 main.py</b> — Main Streamlit application</summary>
<br/>

- User Interface
- Resume Upload
- Job Description Input
- ATS Result Visualization
- Session Management

</details>

<details>
<summary><b>📌 parser.py</b> — Resume extraction & parsing</summary>
<br/>

- Reading PDF files
- Extracting text
- Creating LLM structured output chains
- Converting raw resume text into `Resume` objects

**Key Functions:** `get_llm()` • `load_resume_text_from_bytes()` • `parse_resume()`

</details>

<details>
<summary><b>📌 matcher.py</b> — Resume ↔ JD comparison</summary>
<br/>

- Resume and JD comparison
- ATS evaluation
- Skill mapping
- Match score generation

**Key Function:** `match_resume_to_jd()`

</details>

<details>
<summary><b>📌 models.py</b> — Pydantic validation schemas</summary>
<br/>

**Main Models:** `Resume` • `Education` • `Experience` • `Project` • `JDMatchResult`

These schemas act as structured contracts between the application and the LLM.

</details>

<details>
<summary><b>📌 prompt.py</b> — LLM prompt templates</summary>
<br/>

**Resume Prompt** — used for resume extraction, skill extraction, experience extraction, education extraction

**JD Match Prompt** — used for ATS scoring, skill comparison, gap analysis, hiring summary generation

</details>

---

## 🔄 Application Workflow

```mermaid
flowchart TD
    A[📤 Upload PDF Resume] --> B[📑 PyPDF Text Extraction]
    B --> C[🧠 Groq LLM Parsing]
    C --> D[🗂️ Structured Resume Object]
    D --> E[📝 Enter Job Description]
    E --> F[🔍 Resume vs JD Analysis]
    F --> G[📊 ATS Match Score + Skills + Gaps + Summary]
    G --> H[✅ Results Displayed in Streamlit]
```

---

## ✨ Features

### 📄 Resume Parsing
Extracts Candidate Name, Contact Information, Skills, Education, Work Experience, Projects, and Technology Stack.

### 📊 ATS Style Analysis
Provides Match Score, Matching Skills, Missing Skills, Strengths, Gaps, and Hiring Summary.

### ✅ Structured Output
All extracted data is validated using Pydantic models to ensure consistency and reliability.

### 🖥️ Interactive Dashboard
Built with Streamlit — Resume Upload, Job Description Input, Real-time Analysis, ATS Insights, and a Professional UI.

---

## ⚙️ Installation

**1. Clone the repository**
```bash
git clone https://github.com/Aditya2007raj/AI-Resume-Analyzer.git
cd AI-Resume-Analyzer
```
*(Update the URL above if your repo lives under a different GitHub account.)*

**2. Create a virtual environment**
```bash
python -m venv .venv
```

**3. Activate it**

Windows:
```bash
.venv\Scripts\activate
```

Linux / Mac:
```bash
source .venv/bin/activate
```

**4. Install dependencies**
```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Variables

Create a `.env` file in the root directory:

```env
GROQ_API_KEY=your_groq_api_key
```

---

## ▶️ Running the Application

```bash
streamlit run main.py
```

---

## 📤 Example Output

**ATS Score**
```text
87%
```

**✅ Matched Skills**
```text
Python
FastAPI
Docker
PostgreSQL
```

**❌ Missing Skills**
```text
AWS
Kubernetes
CI/CD
```

**📝 Summary**
```text
Candidate demonstrates strong backend development capabilities with relevant
project experience. Additional exposure to cloud technologies and deployment
pipelines would improve alignment with the target role.
```

---

## ⚠️ Limitations

- ATS score is AI-generated and not equivalent to commercial ATS platforms
- Resume quality affects extraction accuracy
- PDF-only support
- Depends on LLM response quality

---

## 🚀 Future Improvements

- [ ] Resume History
- [ ] Authentication System
- [ ] Multiple Resume Support
- [ ] ChromaDB Integration
- [ ] RAG-Based Recommendations
- [ ] Interview Question Generator
- [ ] Resume Improvement Suggestions
- [ ] Multi-Agent Evaluation Workflow

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
Feel free to check the [issues page](https://github.com/Aditya2007raj/AI-Resume-Analyzer/issues).

---

## 📜 License

This project is licensed under the **MIT License**.

---

<div align="center">

## 👤 Author

**Aditya Raj Singh Shekhawat**

Arya College of Engineering · Computer Science & Artificial Intelligence (CSAI)

<p>
  <a href="https://github.com/Aditya2007raj"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="https://linkedin.com/in/your-linkedin"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
</p>

Built with 🐍 Python, 🎈 Streamlit, 🦜 LangChain, and ⚡ Groq

<img src="https://komarev.com/ghpvc/?username=Aditya2007raj&label=Profile+Views&color=00D9FF&style=flat-square" />

</div>
