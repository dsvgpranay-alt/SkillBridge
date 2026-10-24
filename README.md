# SkillBridge AI

SkillBridge AI is a full-stack platform that connects student skills with relevant industry opportunities through skill assessment, role matching, and personalized insights.

The platform provides separate experiences for students, industry users, academicians, and institutions. Candidate-role matching uses deterministic scoring based on skill requirements, while an optional local Ollama layer can explain the results without modifying the underlying scores.

## Features

### Student
- Create and manage a student profile
- Track skills and assessment results
- View skill scores and role matches
- Explore industry opportunities
- Apply for opportunities
- Maintain a digital skill passport
- Upload resume data for profile enrichment

### Industry
- Create and manage company profiles
- Post internship and other opportunities
- View applicants
- Review deterministic candidate-role matches
- Shortlist candidates
- View industry-level summaries

### Academician
- Manage faculty profiles
- Post FDP and academic opportunities
- View and manage applications

### Institution
- View aggregate skill-gap analytics
- Analyze skill demand across opportunities
- Access institution-scoped reports

### AI-Assisted Insights
- Optional local Ollama integration
- Explains candidate-role matching results
- Does not modify or generate the underlying numerical scores
- Can be configured to run completely locally

## Tech Stack

### Frontend
- React
- Vite
- JavaScript
- HTML/CSS

### Backend
- Python
- Flask
- SQLAlchemy
- Flask-Migrate
- JWT Authentication
- REST APIs

### Database
- SQLite

### AI
- Ollama 

## Architecture

```text
React + Vite
     |
     | REST API
     v
Flask Backend
     |
     +-- Authentication
     +-- Validation
     +-- Business Services
     +-- Skill Intelligence
     +-- Role Matching
     |
     v
SQLAlchemy
     |
     v
SQLite Database
```
# Project Structure 

```text
SkillBridge-AI/
│
├── backend/
│   ├── routes/
│   ├── services/
│   ├── models/
│   ├── migrations/
│   ├── database/
│   ├── run.py
│   ├── seed_reference_data.py
│   ├── seed_demo.py
│   ├── provision_institution.py
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   └── ...
│   ├── package.json
│   └── vite.config.js
│
└── README.md
```
## Project Status

SkillBridge AI is an academic full-stack project focused on connecting student skills with relevant industry and academic opportunities through deterministic skill matching and role-based workflows.
