# SkillBridge AI

SkillBridge AI is a full-stack platform that connects student skills with relevant industry opportunities through skill assessment, role matching, and personalized insights.

The platform provides separate experiences for students, industry users, academicians, and institutions. Candidate-role matching uses deterministic scoring based on skill requirements, while an optional local Ollama layer can explain the results without modifying the underlying scores.

1. `cd backend && python -m pip install -r requirements.txt`
2. Copy `backend/.env.example` to `backend/.env`; set strong `SECRET_KEY` and `JWT_SECRET_KEY`. The default database is `database/skillbridge.db`.
3. From `backend/`: `python -m flask --app run.py db upgrade`, then `python seed_reference_data.py` if role/skill catalogs are empty.
4. Optional demo: `DEMO_PASSWORD='choose-a-local-demo-password' python seed_demo.py --reset-passwords`. It creates the four demo role logins and reuses the five `student1@test.com` through `student5@test.com` accounts, adding missing skill/portfolio data and submitting their applications. The reset flag updates only these named demo/test accounts. Existing portfolios, job requirements, owners and application statuses are preserved.
5. From `backend/`: `python run.py`.
6. From `frontend/`: `npm install && npm run dev`. Open `http://localhost:5173`.

The Vite development server proxies `/api` to Flask on port 5001 by default and follows `PORT` from the root/backend `.env`. Use `API_PROXY_TARGET` in the frontend environment for an explicit override. On macOS, port 5000 may be occupied by AirPlay; use port 5001 and restart both servers. Keep `VITE_API_BASE_URL=/api` for local development. For a separate frontend deployment, set `VITE_API_BASE_URL` to the full API URL and configure `CORS_ORIGINS` on the backend. The Ollama runtime is optional; see `backend/README.md` for local AI configuration and resume support.

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
