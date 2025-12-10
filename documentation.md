---
layout: page
title: Documentation
permalink: /documentation/
---

# Documentation & Resources

This page provides links to technical documentation, developer resources, and research references for the FRAMES project.

---

## 📁 Canonical Documentation

The FRAMES canonical documentation provides authoritative specifications for the system:

### System Design

| Document | Description |
|----------|-------------|
| **System Overview** | Complete architecture and component interactions |
| **Database Schema** | Full specification of 37+ PostgreSQL tables |
| **API Reference** | RESTful API endpoints and usage |
| **Agent Architecture** | AI agent roles and coordination protocols |

### Application Specs

| Document | Description |
|----------|-------------|
| **Student LMS Specification** | React PWA requirements and features |
| **Team Lead Workspace** | Notion integration specifications |
| **Researcher Platform** | Jupyter/MLflow/Superset setup |

### Educational Framework

| Document | Description |
|----------|-------------|
| **Module Definition** | Learning module structure and pedagogy |
| **Assessment Framework** | Knowledge validation approaches |
| **Hint System Design** | Progressive scaffolding implementation |

---

## 💻 Developer Resources

### Getting Started

#### Prerequisites

```
- Python 3.9+
- Node.js 18+
- PostgreSQL 15+ (or Neon account)
- Docker 24+ (recommended)
```

#### Quick Start

```bash
# Clone the repository
git clone https://github.com/Lizo-RoadTown/FRAMES-Python.git
cd FRAMES-Python

# Set up Python environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your configuration

# Initialize database
flask db upgrade

# Run development server
flask run
```

### Project Structure

```
FRAMES-Python/
├── backend/
│   ├── app.py              # Main Flask application
│   ├── db_models.py        # SQLAlchemy models
│   ├── energy_engine.py    # Risk calculation engine
│   └── routes/             # API endpoint handlers
├── canon/
│   ├── system_overview.md  # Architecture docs
│   ├── DATABASE_SCHEMA.md  # Database specification
│   └── module_definition.md # Learning module spec
├── docs/
│   └── EDUCATIONAL_FRAMEWORK.md
├── tests/
│   └── ...
└── frontend/               # React application
    └── ...
```

### Key Technologies

| Layer | Technology | Documentation |
|-------|------------|---------------|
| Backend | Flask | [flask.palletsprojects.com](https://flask.palletsprojects.com/) |
| ORM | SQLAlchemy | [docs.sqlalchemy.org](https://docs.sqlalchemy.org/) |
| Database | PostgreSQL/Neon | [neon.tech/docs](https://neon.tech/docs) |
| Frontend | React | [react.dev](https://react.dev/) |
| Styling | Tailwind CSS | [tailwindcss.com](https://tailwindcss.com/) |
| AI | LangChain | [python.langchain.com](https://python.langchain.com/) |

---

## 🤖 Agent System Documentation

### Agent Roles

| Agent | Purpose | Scope |
|-------|---------|-------|
| **Alpha** | Information extraction from documentation | Read-only access to source materials |
| **Beta** | Connection mapping and relationship building | Cross-reference within database |
| **Gamma** | Validation and quality assurance | Flag issues for human review |

### Agent Interaction Protocol

```
1. Input arrives (Notion doc, manual entry, etc.)
           ↓
2. Alpha extracts structured information
           ↓
3. Beta maps relationships to existing data
           ↓
4. Gamma validates consistency and completeness
           ↓
5. If issues: Flag for human review
   If valid: Commit to database
           ↓
6. Downstream systems notified of updates
```

### Safety Guardrails

- **Scope limitations** — Each agent has defined boundaries
- **Human oversight** — Review required for significant changes
- **Audit logging** — Full trace of agent decisions
- **Rate limiting** — Prevent runaway operations
- **Circuit breakers** — Automatic halt on anomalies

---

## 📊 Database Reference

### Core Tables Overview

#### Organization Domain

```sql
-- Universities and institutions
universities (id, name, location, type, ...)

-- Teams within programs
teams (id, university_id, name, focus_area, ...)

-- Academic programs
programs (id, university_id, name, department, ...)
```

#### People Domain

```sql
-- User accounts
users (id, email, name, role, university_id, ...)

-- Role assignments
user_roles (user_id, role_id, team_id, ...)

-- Permissions
permissions (id, resource, action, ...)
```

#### Mission Domain

```sql
-- Space missions/projects
missions (id, team_id, name, phase, status, ...)

-- Mission phases
phases (id, mission_id, name, start_date, end_date, ...)

-- Deliverables and milestones
milestones (id, phase_id, name, due_date, status, ...)
```

#### Learning Domain

```sql
-- Learning modules
modules (id, title, description, prerequisite_ids, ...)

-- Module steps
steps (id, module_id, content, type, order, ...)

-- Assessments
assessments (id, module_id, questions, passing_score, ...)
```

### Query Examples

```sql
-- Find all active modules for a team's focus area
SELECT m.* 
FROM modules m
JOIN team_modules tm ON m.id = tm.module_id
JOIN teams t ON tm.team_id = t.id
WHERE t.focus_area = 'avionics'
AND m.status = 'active';

-- Get learning progress for a cohort
SELECT 
    u.id as user_id,
    COUNT(CASE WHEN lp.status = 'completed' THEN 1 END) as completed,
    COUNT(*) as total
FROM users u
JOIN learning_progress lp ON u.id = lp.user_id
WHERE u.cohort_year = 2024
GROUP BY u.id;
```

---

## 🔬 Research References

### Foundational Theory

1. **Simon, H. A. (1962).** "The Architecture of Complexity." *Proceedings of the American Philosophical Society.*
   - Foundation for nearly decomposable systems theory

2. **Champenois, C., & Etzkowitz, H. (2018).** "From boundary line to boundary space: The creation of hybrid organizations as a Triple Helix micro-foundation." *Technovation.*
   - Framework for understanding university space labs

3. **Williams, J. J., et al. (2016).** "AXIS: Generating Explanations at Scale with Learnersourcing and Machine Learning." *ACM Learning @ Scale.*
   - OATutor pedagogical foundations

### Related Work

- **Knowledge Transfer in Project Teams** — Understanding how expertise moves between cohorts
- **Organizational Resilience** — Measuring and improving program robustness
- **Human-AI Collaboration** — Responsible integration of AI in education

---

## 📬 Support & Contact

### For Developers

- **GitHub Issues:** Report bugs and request features
- **Discussions:** Technical questions and ideas
- **Pull Requests:** Contributions welcome

### For Researchers

- **Data Access:** Contact eosborn@cpp.edu with IRB documentation
- **Collaboration:** Inquire about research partnerships
- **Publications:** Share related work for mutual benefit

### For Institutions

- **Partnerships:** Discuss joining the FRAMES consortium
- **Pilots:** Explore trial implementations
- **Customization:** Discuss specific needs

---

## 📚 Additional Resources

- [Home]({{ site.baseurl }}/) — Project overview
- [About]({{ site.baseurl }}/about) — Background and team
- [Architecture]({{ site.baseurl }}/architecture) — Technical deep dive
- [Applications]({{ site.baseurl }}/applications) — User platforms

---

**Last Updated:** December 2025  
**Contact:** [eosborn@cpp.edu](mailto:eosborn@cpp.edu)
