---
layout: page
title: Architecture
permalink: /architecture/
---

# System Architecture

FRAMES employs a sophisticated five-layer architecture designed for scalability, security, and research utility. This page provides a technical deep dive into how the system works.

---

## The Five-Layer Model

```
┌─────────────────────────────────────────────────────────────────┐
│                      REAL WORK LAYER                            │
│           Team Leads document missions in Notion                │
│                            ↓                                    │
├─────────────────────────────────────────────────────────────────┤
│                   AI INTERPRETATION LAYER                       │
│         Alpha · Beta · Gamma agents (safe, controlled)          │
│                            ↓                                    │
├─────────────────────────────────────────────────────────────────┤
│                    CANONICAL DATA LAYER                         │
│                Neon PostgreSQL · 37+ Tables                     │
│                            ↓                                    │
├──────────────────┬──────────────────┬──────────────────────────┤
│    Student       │    Team          │    Research              │
│    LMS           │    Tools         │    Platform              │
│    React PWA     │    Notion Space  │    Jupyter + MLflow      │
└──────────────────┴──────────────────┴──────────────────────────┘
```

---

## Layer 1: Real Work Layer

**Purpose:** Capture authentic engineering activities as they happen

This layer is where actual project work occurs. Team leads and members document their activities, decisions, and progress using familiar tools like Notion. The key principle is **minimal friction**—teams shouldn't have to change how they work just to feed the FRAMES system.

**Key Components:**

- Notion workspaces for each team
- Mission documentation templates
- Activity logging protocols
- Meeting notes and decisions

**Design Philosophy:** FRAMES adapts to teams, not the other way around.

---

## Layer 2: AI Interpretation Layer

**Purpose:** Transform unstructured documentation into structured data

Three specialized AI agents process work documentation:

### Agent Alpha — The Extractor

Reads team documentation and extracts:

- Key decisions and their rationale
- Technical specifications and requirements
- Task assignments and dependencies
- Risk factors and concerns

### Agent Beta — The Connector

Links extracted information to:

- Database schema elements
- Learning module content
- Cross-team relationships
- Historical patterns

### Agent Gamma — The Validator

Ensures data quality through:

- Consistency checking
- Completeness verification
- Conflict detection
- Human review flagging

**Safety Principles:**

- All agents operate in controlled scopes
- Human review required for significant actions
- Full audit trail of agent decisions
- No autonomous changes to production data

---

## Layer 3: Canonical Data Layer

**Purpose:** Single source of truth for all FRAMES data

### Database Architecture

FRAMES uses **Neon PostgreSQL** with 37+ tables organized into logical domains:

#### Core Domains

| Domain | Tables | Purpose |
|--------|--------|---------|
| **Organizations** | universities, teams, programs | Institutional structure |
| **People** | users, roles, permissions | Identity and access |
| **Missions** | missions, phases, milestones | Project tracking |
| **Learning** | modules, steps, assessments | Educational content |
| **Analytics** | events, metrics, reports | Research data |

#### Key Schema Features

- **Temporal tracking** — All entities track creation/modification times
- **Soft deletion** — Records marked inactive, never truly deleted
- **Audit logging** — Every change recorded for research
- **Flexible metadata** — JSONB fields for evolving requirements

### Data Flow Principles

```
Input Sources          Processing           Output Consumers
─────────────          ──────────           ────────────────
Notion Docs     ──┐                   ┌──→  Student LMS
Manual Entry    ──┼──→  Validation   ──┼──→  Team Dashboards
API Imports     ──┼──→  Enrichment   ──┼──→  Research Exports
Agent Output    ──┘     Storage      └──→  Analytics Tools
```

---

## Layer 4: Application Layer

Three distinct applications serve different stakeholder needs:

### Student Learning Management System

**Technology:** React 18+ PWA  
**Purpose:** Personalized learning for individual contributors

Features:

- Module-based learning paths
- Progress tracking and visualization
- Hint systems and scaffolding
- Assessment and validation
- Offline capability (PWA)

### Team Lead Workspace

**Technology:** Notion + Integrations  
**Purpose:** Mission coordination and documentation

Features:

- Mission planning templates
- Status dashboards
- Cross-team visibility
- Integration with external tools
- Automated reporting

### Researcher Platform

**Technology:** Jupyter + MLflow + Superset  
**Purpose:** Data analysis and research workflows

Features:

- Secure data access (anonymized by default)
- Pre-built analysis notebooks
- Custom query capabilities
- Visualization dashboards
- Export tools for publication

---

## Technology Stack

### Backend

| Technology | Version | Purpose |
|------------|---------|---------|
| **Python** | 3.9+ | Primary language |
| **Flask** | 3.0+ | API framework |
| **SQLAlchemy** | 2.0+ | ORM |
| **Celery** | 5.3+ | Task queue |
| **Redis** | 7+ | Caching |

### Frontend

| Technology | Version | Purpose |
|------------|---------|---------|
| **React** | 18+ | UI framework |
| **TypeScript** | 5+ | Type safety |
| **TanStack Query** | 5+ | Data fetching |
| **Tailwind CSS** | 3+ | Styling |

### Data & Infrastructure

| Technology | Version | Purpose |
|------------|---------|---------|
| **PostgreSQL** | 15+ | Primary database |
| **Neon** | — | Serverless Postgres |
| **Docker** | 24+ | Containerization |
| **GitHub Actions** | — | CI/CD |

### AI & Analytics

| Technology | Purpose |
|------------|---------|
| **LangChain** | Agent orchestration |
| **OpenAI API** | Language models |
| **MLflow** | Experiment tracking |
| **Superset** | Dashboards |

---

## Security Architecture

### Authentication & Authorization

- OAuth 2.0 / OIDC integration
- Role-based access control (RBAC)
- Per-university data isolation
- API key management for integrations

### Data Protection

- Encryption at rest (AES-256)
- Encryption in transit (TLS 1.3)
- Automated PII detection and handling
- Regular security audits

### AI Safety

- Sandboxed agent execution
- Rate limiting and circuit breakers
- Human-in-the-loop for sensitive operations
- Comprehensive audit logging

---

## API Architecture

The FRAMES API follows RESTful principles with 50+ endpoints organized by resource:

```
/api/v1/
├── /auth           # Authentication
├── /users          # User management
├── /teams          # Team operations
├── /missions       # Mission tracking
├── /modules        # Learning content
├── /assessments    # Evaluations
├── /analytics      # Research queries
└── /agents         # AI operations
```

**API Features:**

- OpenAPI 3.0 specification
- JWT authentication
- Rate limiting per client
- Comprehensive error responses
- Pagination and filtering

---

## Data Flow Example

Here's how information flows through FRAMES when a team lead documents a design decision:

1. **Capture:** Team lead writes decision in Notion
2. **Detect:** Webhook notifies FRAMES of new content
3. **Extract:** Agent Alpha identifies decision elements
4. **Connect:** Agent Beta links to relevant modules and teams
5. **Validate:** Agent Gamma checks consistency, flags if needed
6. **Store:** Validated data written to PostgreSQL
7. **Distribute:** 
   - Student LMS receives new learning context
   - Dashboards update with fresh data
   - Analytics pipeline processes for research

---

## Learn More

- [Applications]({{ site.baseurl }}/applications) — User-facing platforms in detail
- [Documentation]({{ site.baseurl }}/documentation) — Developer resources
- [About]({{ site.baseurl }}/about) — Project background and team
