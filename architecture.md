---
layout: page
title: Architecture
permalink: /architecture/
---

# System Architecture

FRAMES employs a six-layer architecture designed for scalability, security, and research utility. At its core is a **Space Lab Predictive Model**—a custom system trained on actual student outcomes from university aerospace programs, not a generic AI.

---

## The Six-Layer Model

```
┌─────────────────────────────────────────────────────────────────┐
│                      REAL WORLD LAYER                           │
│            Actual engineering team activities                   │
│                            ↓                                    │
├─────────────────────────────────────────────────────────────────┤
│                 DIGITAL OBSERVATION LAYER                       │
│         Notion workspaces · GitHub · Manual entry               │
│                            ↓                                    │
├─────────────────────────────────────────────────────────────────┤
│                INTERPRETATION / AGENT LAYER                     │
│    LangChain orchestration · LangGraph workflows · MCP servers  │
│                            ↓                                    │
├─────────────────────────────────────────────────────────────────┤
│                    CANONICAL DATA LAYER                         │
│                Neon PostgreSQL · 37+ Tables                     │
│                            ↓                                    │
├──────────────────┬──────────────────┬──────────────────────────┤
│    Student       │    Team          │    Research              │
│    LMS           │    Tools         │    Platform              │
│    React PWA     │    Notion Space  │    MLflow + Analytics    │
├──────────────────┴──────────────────┴──────────────────────────┤
│                   GOVERNANCE / LOGGING LAYER                    │
│         Audit trails · FERPA compliance · Risk management       │
└─────────────────────────────────────────────────────────────────┘
```

---

## Layer 1: Real World Layer

**Purpose:** Where authentic engineering activities occur

This layer represents actual project work as it happens—design reviews, code commits, team meetings, and technical decisions. FRAMES observes this layer without interfering with natural workflows.

---

## Layer 2: Digital Observation Layer

**Purpose:** Capture team activities through digital touchpoints

Team leads and members document their work using familiar tools. The key principle is **minimal friction**—teams work naturally while FRAMES captures structured and unstructured data.

**Data Sources:**

- **Notion workspaces** — Mission documentation, meeting notes, decisions
- **GitHub repositories** — Code commits, pull requests, issues
- **Manual entry** — Structured forms for specific data points
- **LlamaIndex integration** — Content indexing for semantic search (planned)

**Design Philosophy:** FRAMES adapts to teams, not the other way around.

---

## Layer 3: Interpretation / Agent Layer

**Purpose:** Transform observations into structured, actionable data

This layer employs a multi-agent system orchestrated through **LangChain** with **LangGraph** for workflow state management. Agents operate with risk-based autonomy levels.

### Agent Architecture

Three specialized roles with distinct responsibilities:

#### The Interpreter

Analyzes incoming data to identify:

- Key decisions and their rationale
- Technical specifications and requirements
- Task assignments and dependencies
- Risk factors and concerns

**Autonomy Level:** High — can read and analyze without human approval

#### The Builder

Constructs and modifies system artifacts:

- Creates new database records
- Links information across domains
- Generates learning module content
- Updates cross-team relationships

**Autonomy Level:** Medium — requires human approval for significant changes

#### The Validator

Ensures data quality and system consistency:

- Consistency and completeness checking
- Conflict detection and resolution
- FERPA compliance verification
- Human review queue management

**Autonomy Level:** Low — flags issues for human decision

### Workflow Orchestration (LangGraph)

```text
┌─────────────────────────────────────────────────────────────────┐
│                     EXPLORATION MODE                            │
│          Interpreter reads, analyzes, suggests                  │
│                            ↓                                    │
├─────────────────────────────────────────────────────────────────┤
│                      DRAFTING MODE                              │
│        Builder proposes changes (staged, not committed)         │
│                            ↓                                    │
├─────────────────────────────────────────────────────────────────┤
│                     EXECUTION MODE                              │
│         Human approves → Changes applied to database            │
│                            ↓                                    │
├─────────────────────────────────────────────────────────────────┤
│                       COMMIT MODE                               │
│       Validator verifies → Audit log → Finalization             │
└─────────────────────────────────────────────────────────────────┘
```

### MCP Server Integration (LangChain)

Model Context Protocol servers provide secure, controlled access to external systems:

| MCP Server | Purpose | Risk Surface |
|------------|---------|--------------|
| **Notion** | Read team documentation | Low |
| **GitHub** | Read repositories, issues | Low |
| **Filesystem** | Access local resources | Medium |
| **PostgreSQL** | Database operations | High (gated) |

**Safety Principles:**

- All operations logged to governance layer
- Risk-based approval workflows
- No autonomous changes to production data without human approval
- Circuit breakers for runaway operations

---

## Layer 4: Canonical Data Layer

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
| **ML Pipeline** | training_data, model_versions, predictions | Machine learning |

#### Key Schema Features

- **Temporal tracking** — All entities track creation/modification times
- **Soft deletion** — Records marked inactive, never truly deleted
- **Audit logging** — Every change recorded for research and compliance
- **Flexible metadata** — JSONB fields for evolving requirements
- **ML-ready** — Feature columns optimized for model training

### Data Flow Principles

```text
Input Sources          Processing           Output Consumers
─────────────          ──────────           ────────────────
Notion Docs     ──┐                   ┌──→  Student LMS
GitHub Events   ──┼──→  Validation   ──┼──→  Team Dashboards
Manual Entry    ──┼──→  Enrichment   ──┼──→  Research Exports
Agent Output    ──┘     ML Features  └──→  Analytics + MLflow
```

---

## Layer 5: Application Layer

Three distinct applications serve different stakeholder needs:

### Student Learning Management System

**Technology:** React 18+ PWA
**Purpose:** Personalized learning for individual contributors

Features:

- Module-based learning paths generated from team activities
- Progress tracking and visualization
- Adaptive hint systems and scaffolding
- Assessment and competency validation
- Offline capability (Progressive Web App)

### Team Lead Workspace

**Technology:** Notion + Integrations
**Purpose:** Mission coordination and documentation

Features:

- Mission planning templates
- Real-time status dashboards
- Cross-team visibility
- Automated progress reporting
- Bi-directional sync with FRAMES

### Researcher Platform

**Technology:** MLflow + Jupyter + Analytics Dashboard
**Purpose:** Data analysis, ML experimentation, and research workflows

Features:

- Secure data access (anonymized by default)
- Pre-built analysis notebooks
- MLflow experiment tracking and model registry
- Prediction API for module recommendations
- Visualization dashboards
- Export tools for publication

---

## The Space Lab Predictive Model

This is the core innovation of FRAMES. Rather than relying on external LLM APIs that know nothing about aerospace engineering education, we're training a model on **real outcomes from real students in real space lab programs**.

### What the Model Learns From

| Data Source | What It Teaches the Model |
|-------------|---------------------------|
| **Module completions** | Which learning paths lead to success |
| **Time-on-task patterns** | Where students struggle vs. breeze through |
| **Assessment results** | What competencies actually stuck |
| **Team outcomes** | Which missions succeeded and why |
| **Cohort comparisons** | What distinguishes high-performing teams |

### What the Model Predicts

```text
INPUT: Student's current progress, engagement patterns, background
                              ↓
         SPACE LAB PREDICTIVE MODEL
                              ↓
OUTPUT:
  → "Start with Module 7—students like you succeed 84% more often"
  → "You're likely to struggle with thermal analysis; here's extra prep"
  → "Your learning path is taking longer than average—consider office hours"
  → "This module isn't working for anyone—flagged for redesign"
```

### Why Not Just Use ChatGPT?

| External LLM | Space Lab Predictive Model |
|--------------|----------------------------|
| Trained on the internet | Trained on *your students' actual outcomes* |
| Guesses what might work | Knows what *did* work |
| Generic advice | "Students with your profile who took this path had 92% success" |
| Can't explain why | Every prediction tied to real data points |
| API costs per query | Runs locally, no ongoing fees |
| Black box | Fully auditable for research |

### The Agents Feed the Model

The three agents (Interpreter, Builder, Validator) don't make predictions—they structure observations into training data:

```text
REAL WORLD ACTIVITY
   A student completes Module 5, struggles on Step 3, asks for hint
                              ↓
INTERPRETER AGENT
   Extracts: completion_time, hint_requests, error_patterns
                              ↓
BUILDER AGENT
   Structures into feature vector, links to student profile
                              ↓
VALIDATOR AGENT
   Checks consistency, FERPA compliance, data quality
                              ↓
TRAINING DATA
   Feeds the Space Lab Predictive Model
                              ↓
MODEL IMPROVES
   Next prediction is more accurate because it learned from this outcome
```

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

### Data and Infrastructure

| Technology | Version | Purpose |
|------------|---------|---------|
| **PostgreSQL** | 15+ | Primary database |
| **Neon** | — | Serverless Postgres |
| **Docker** | 24+ | Containerization |
| **GitHub Actions** | — | CI/CD |

### AI, ML, and Analytics

| Technology | Purpose |
|------------|---------|
| **LangChain** | Agent orchestration, MCP server integration |
| **LangGraph** | Workflow state management |
| **LlamaIndex** | Content indexing (Notion integration) |
| **MLflow** | Experiment tracking, model registry |
| **scikit-learn / PyTorch** | Model training |
| **Custom ML Model** | Domain-specific predictions (in development) |

---

## Layer 6: Governance and Logging Layer

**Purpose:** Ensure compliance, auditability, and risk management

### Compliance Framework

FRAMES handles educational data subject to FERPA and institutional policies:

| Requirement | Implementation |
|-------------|----------------|
| **FERPA Compliance** | Student data anonymization, access logging |
| **Audit Trails** | Every operation logged with timestamp, actor, action |
| **Data Retention** | Configurable retention policies per data type |
| **Access Control** | Role-based permissions, university isolation |

### Risk-Based Agent Autonomy

Agent operations are classified by risk level:

| Risk Level | Examples | Approval Required |
|------------|----------|-------------------|
| **Low** | Reading docs, generating reports | None |
| **Medium** | Creating draft records, suggestions | Human review |
| **High** | Modifying production data, bulk operations | Explicit approval |

### Logging Architecture

```text
All Operations → Governance Layer → Audit Database
                      ↓
              Risk Assessment
                      ↓
         ┌──────────┴──────────┐
    Auto-approve          Queue for
    (low risk)          human review
```

---

## Security Architecture

### Authentication and Authorization

- OAuth 2.0 / OIDC integration with university identity providers
- Role-based access control (RBAC) with granular permissions
- Per-university data isolation (multi-tenant)
- API key management for integrations
- Session management with secure token handling

### Data Protection

- Encryption at rest (AES-256)
- Encryption in transit (TLS 1.3)
- Automated PII detection and handling
- SQL injection prevention (parameterized queries)
- XSS protection (Content Security Policy)
- Regular security audits

### AI Safety Controls

- Sandboxed agent execution environments
- Rate limiting and circuit breakers
- Human-in-the-loop for sensitive operations
- Comprehensive audit logging of all agent actions
- Rollback capability for agent-initiated changes

---

## API Architecture

The FRAMES API follows RESTful principles with 50+ endpoints organized by resource:

```text
/api/v1/
├── /auth           # Authentication
├── /users          # User management
├── /teams          # Team operations
├── /missions       # Mission tracking
├── /modules        # Learning content
├── /assessments    # Evaluations
├── /analytics      # Research queries
├── /agents         # AI operations
├── /ml             # Model predictions (new)
└── /governance     # Audit and compliance
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
3. **Index:** LlamaIndex processes content for semantic search
4. **Interpret:** Interpreter agent identifies decision elements
5. **Build:** Builder agent proposes database updates (staged)
6. **Validate:** Validator agent checks consistency, FERPA compliance
7. **Approve:** Human reviews and approves changes (if medium/high risk)
8. **Store:** Validated data written to PostgreSQL
9. **Log:** Governance layer records complete audit trail
10. **Distribute:**
    - Student LMS receives new learning context
    - ML pipeline updates training features
    - Dashboards reflect fresh data
    - Analytics available for research

---

## Learn More

- [Applications]({{ site.baseurl }}/applications) — User-facing platforms in detail
- [Documentation]({{ site.baseurl }}/documentation) — Developer resources
- [About]({{ site.baseurl }}/about) — Project background and team
