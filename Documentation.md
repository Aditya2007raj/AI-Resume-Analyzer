# AI Resume Analyzer

## Project Overview

AI Resume Analyzer is an intelligent resume screening and job matching platform that helps candidates evaluate how well their resumes align with a target job description.

The application uses Large Language Models (LLMs) to:

- Extract structured information from resumes
- Identify candidate skills and experience
- Compare resumes against job descriptions
- Calculate ATS-style compatibility scores
- Detect missing skills
- Generate professional hiring insights

The system is built using Python, Streamlit, LangChain, Groq LLM, and Pydantic.

---

# Problem Statement

Recruiters often receive hundreds of resumes for a single position.

Candidates usually struggle to determine:

- Whether their resume matches the target role
- Which skills are missing
- How ATS systems may evaluate their profile

This project automates that evaluation process and provides actionable feedback.

---

# Features

## Resume Parsing

Extracts:

- Candidate Name
- Contact Information
- Skills
- Education
- Work Experience
- Projects
- Technology Stack

---

## ATS Style Analysis

Provides:

- Match Score
- Matching Skills
- Missing Skills
- Strengths
- Gaps
- Hiring Summary

---

## Structured Output

All extracted data is validated using Pydantic models to ensure consistency and reliability.

---

## Interactive Dashboard

Built with Streamlit:

- Resume Upload
- Job Description Input
- Real-time Analysis
- ATS Insights
- Professional UI

---

# Technology Stack

## Frontend

- Streamlit

## Backend

- Python

## LLM Framework

- LangChain

## LLM Provider

- Groq

## Model

- Llama 3.3 70B Versatile

## Data Validation

- Pydantic

## PDF Processing

- PyPDF

## Configuration Management

- Python Dotenv

---

# Project Architecture

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

# Folder Structure

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

# Module Description

## main.py

Main Streamlit application.

Responsibilities:

- User Interface
- Resume Upload
- Job Description Input
- ATS Result Visualization
- Session Management

---

## parser.py

Responsible for:

- Reading PDF files
- Extracting text
- Creating LLM structured output chains
- Converting raw resume text into Resume objects

Key Functions:

- get_llm()
- load_resume_text_from_bytes()
- parse_resume()

---

## matcher.py

Responsible for:

- Resume and JD comparison
- ATS evaluation
- Skill mapping
- Match score generation

Key Function:

- match_resume_to_jd()

---

## models.py

Contains Pydantic schemas.

Main Models:

- Resume
- Education
- Experience
- Project
- JDMatchResult

These schemas act as structured contracts between the application and the LLM.

---

## prompt.py

Contains all prompt templates.

### Resume Prompt

Used for:

- Resume extraction
- Skill extraction
- Experience extraction
- Education extraction

### JD Match Prompt

Used for:

- ATS scoring
- Skill comparison
- Gap analysis
- Hiring summary generation

---

# Workflow

## Step 1

User uploads a PDF resume.

---

## Step 2

PyPDF extracts textual content.

---

## Step 3

The extracted text is sent to Groq LLM.

---

## Step 4

The LLM converts the resume into a structured Resume object.

---

## Step 5

User enters a Job Description.

---

## Step 6

Resume and JD are analyzed.

---

## Step 7

The system calculates:

- ATS Match Score
- Matched Skills
- Missing Skills
- Strengths
- Gaps
- Candidate Summary

---

## Step 8

Results are displayed in Streamlit.

---

# Installation

## Clone Repository

```bash
git clone https://github.com/Aditya2007raj/AI-Resume-Analyzer.git
cd AI-Resume-Analyzer
```

## Create Virtual Environment

```bash
python -m venv .venv
```

### Windows

```bash
.venv\Scripts\activate
```

### Linux / macOS

```bash
source .venv/bin/activate
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Environment Variables

Create a `.env` file:

```env
GROQ_API_KEY=your_groq_api_key
```

---

# Running the Application

```bash
streamlit run main.py
```

---

# Example Output

## ATS Score

```text
87%
```

## Matched Skills

```text
Python
FastAPI
Docker
PostgreSQL
```

## Missing Skills

```text
AWS
Kubernetes
CI/CD
```

## Summary

Candidate demonstrates strong backend development capabilities with relevant project experience. Additional exposure to cloud technologies and deployment pipelines would improve alignment with the target role.

---

# Limitations

- ATS score is AI-generated and not equivalent to commercial ATS platforms.
- Resume quality affects extraction accuracy.
- PDF-only support.
- Depends on LLM response quality.

---

# Future Improvements

- Resume History
- Authentication System
- Multiple Resume Support
- ChromaDB Integration
- RAG-based Recommendations
- Interview Question Generator
- Resume Improvement Suggestions
- Multi-Agent Evaluation Workflow

---

# Author

Aditya Raj Singh Shekhawat

Arya College of Engineering 

Computer Science & Artificial Intelligence (CSAI)

Built with Python, Streamlit, LangChain, Groq, and Pydantic.
