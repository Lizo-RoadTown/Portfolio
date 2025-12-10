---
layout: page
title: Applications
permalink: /applications/
---

# FRAMES Applications

FRAMES provides three distinct applications, each designed for a specific stakeholder group. Together, they form a comprehensive ecosystem for learning, coordination, and research.

---

## Student Learning Management System

**For:** Individual contributors and new team members  
**Technology:** React 18+ Progressive Web App

### Overview

The Student LMS is the primary interface for learners joining university engineering programs. It provides structured onboarding through modules built from real project experiences.

### Key Features

#### Personalized Learning Paths

- **Adaptive progression** — Content adjusts to demonstrated competency
- **Multiple tracks** — Paths for different roles (software, hardware, systems)
- **Clear milestones** — Visible progress toward team readiness

#### Module Structure

Each learning module follows a consistent pedagogical approach:

```
Module: [Topic Name]
├── Learning Objectives
├── Core Content
│   ├── Concepts & Theory
│   ├── Real-World Context (from actual projects)
│   └── Worked Examples
├── Hint System
│   ├── Progressive hints
│   ├── Scaffolded support
│   └── "Ask for help" integration
├── Knowledge Checks
│   ├── Self-assessment questions
│   ├── Practical exercises
│   └── Scenario-based challenges
└── Module Completion
    ├── Competency badge
    └── Recommended next modules
```

#### Research-Backed Pedagogy

The LMS incorporates principles from **OATutor** research:

- **Scaffolding** — Complex tasks broken into manageable steps
- **Hint pathways** — Support available but not intrusive
- **Validation** — Confirm understanding before advancing
- **Spaced practice** — Review and reinforcement over time

#### Offline Capability

As a Progressive Web App (PWA), students can:

- Download modules for offline study
- Work without internet connectivity
- Sync progress when reconnected
- Receive push notifications for updates

### User Experience

```
┌────────────────────────────────────────────────┐
│  Dashboard                                     │
│  ┌──────────────────────────────────────────┐  │
│  │ Your Progress: ████████░░░░ 67%          │  │
│  │                                          │  │
│  │ Current Module: Avionics Fundamentals    │  │
│  │ Time to Complete: ~2 hours               │  │
│  │                                          │  │
│  │ [Continue Learning →]                    │  │
│  └──────────────────────────────────────────┘  │
│                                                │
│  Your Achievements                             │
│  • Systems Basics      Complete               │
│  • Safety Protocols    Complete               │
│  • Team Workflows      In Progress            │
│                                                │
│  Upcoming                                      │
│  • Lab session: Thursday 2pm                  │
│  • Design review: Friday 10am                 │
└────────────────────────────────────────────────┘
```

---

## Team Lead Workspace

**For:** Team leads and project managers  
**Technology:** Notion with custom integrations

### Overview

The Team Lead Workspace provides mission coordination tools built on Notion's flexible platform. It integrates with FRAMES while keeping familiar workflows.

### Key Features

#### Mission Planning

- **Template library** — Pre-built structures for common mission types
- **Milestone tracking** — Clear phase gates and deliverables
- **Resource allocation** — Team capacity and assignments
- **Risk registers** — Tracked concerns with mitigation plans

#### Cross-Team Visibility

```
┌─────────────────────────────────────────────────┐
│  Mission Dashboard: BroncoSat-2                 │
├─────────────────────────────────────────────────┤
│                                                 │
│  Phase: Design Review █████░░░░░ 52%           │
│                                                 │
│  Team Status:                                   │
│  ├─ Avionics         ██████░░░░ On Track      │
│  ├─ Power            ████████░░ Ahead         │
│  ├─ Communications   ████░░░░░░ At Risk       │
│  └─ Software         ██████░░░░ On Track      │
│                                                 │
│  Active Concerns: 2                             │
│  Next Milestone: PDR (Dec 15)                  │
│                                                 │
└─────────────────────────────────────────────────┘
```

#### Documentation Flow

When team leads document activities:

1. Write naturally in Notion
2. FRAMES agents process content
3. Data flows to canonical database
4. Insights surface in dashboards
5. Learning content auto-updates

#### Integration Points

- **GitHub** — Code repository sync
- **Slack** — Notifications and updates
- **Calendar** — Meeting and deadline sync
- **JIRA** — For teams using traditional PM tools

### Templates Available

| Template | Purpose |
|----------|---------|
| **Mission Brief** | High-level project overview |
| **Design Document** | Technical specifications |
| **Test Plan** | Verification and validation |
| **Risk Assessment** | Concern tracking |
| **Meeting Notes** | Decisions and action items |
| **Handoff Guide** | Knowledge transfer to next cohort |

---

## Researcher Platform

**For:** Faculty, graduate students, and research staff  
**Technology:** Jupyter + MLflow + Apache Superset

### Overview

The Researcher Platform provides secure, ethical access to FRAMES data for studying collaboration, learning, and organizational dynamics.

### Key Components

#### Jupyter Notebooks

Pre-configured environments for data analysis:

- **Python 3.9+** with scientific stack
- **Pandas, NumPy, SciPy** for data manipulation
- **Matplotlib, Seaborn, Plotly** for visualization
- **Scikit-learn, TensorFlow** for modeling

#### MLflow Experiment Tracking

For reproducible research workflows:

- Track experiments with full provenance
- Version datasets and models
- Compare results across runs
- Share findings with collaborators

#### Apache Superset Dashboards

Interactive visualizations for:

- Collaboration patterns
- Learning analytics
- Cross-institutional comparisons
- Longitudinal trends

### Data Access Principles

**Privacy First:**

- Data anonymized by default
- IRB-approved access protocols
- Role-based permissions
- Audit logging of all queries

**Research Ethics:**

- Clear data use agreements
- Student consent framework
- Institutional data ownership
- Publication guidelines

### Example Research Queries

```python
# Collaboration Network Analysis
collaboration_data = frames.query("""
    SELECT 
        team_id,
        interaction_type,
        timestamp,
        -- Anonymized participant IDs
        participant_hash
    FROM interactions
    WHERE institution = :institution
    AND date BETWEEN :start AND :end
""", params={...})

# Learning Path Effectiveness
module_performance = frames.query("""
    SELECT 
        module_id,
        avg(completion_rate) as avg_completion,
        avg(time_to_complete) as avg_time,
        count(distinct user_hash) as learners
    FROM learning_events
    GROUP BY module_id
""")
```

### Available Datasets

| Dataset | Description | Access Level |
|---------|-------------|--------------|
| **Learning Events** | Module completion, hints, assessments | Anonymized |
| **Collaboration Patterns** | Team interaction frequencies | Aggregated |
| **Project Outcomes** | Mission completion, quality metrics | Aggregated |
| **Survey Responses** | Self-reported data (consented) | IRB Approved |

---

## Application Integration

The three applications work together through the shared canonical data layer:

```
┌───────────────┐     ┌───────────────┐     ┌───────────────┐
│   Student     │     │   Team Lead   │     │   Researcher  │
│     LMS       │     │   Workspace   │     │   Platform    │
└───────┬───────┘     └───────┬───────┘     └───────┬───────┘
        │                     │                     │
        │    ┌────────────────┴────────────────┐    │
        │    │                                 │    │
        └────┤      FRAMES API Layer           ├────┘
             │   (Authentication, RBAC)        │
             └────────────────┬────────────────┘
                              │
                 ┌────────────┴────────────┐
                 │                         │
                 │   Canonical Database    │
                 │   (Neon PostgreSQL)     │
                 │                         │
                 └─────────────────────────┘
```

### Data Flow Examples

**Student completes module:**
1. LMS records completion → Database
2. Researcher Platform sees analytics update
3. Team Lead dashboard shows team readiness

**Team Lead documents decision:**
1. Notion entry → Agent processing → Database
2. LMS receives new context for relevant modules
3. Researcher Platform has new collaboration data

---

## Learn More

- [Architecture]({{ site.baseurl }}/architecture) — Technical deep dive
- [Documentation]({{ site.baseurl }}/documentation) — Developer resources
- [About]({{ site.baseurl }}/about) — Project background
