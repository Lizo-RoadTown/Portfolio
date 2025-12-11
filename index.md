---
layout: article
title: FRAMES
key: page-home
article_header:
  type: overlay
  theme: dark
  background_color: '#1e1e2e'
  background_image:
    gradient: 'linear-gradient(135deg, rgba(30, 30, 46, 0.8), rgba(30, 30, 46, 0.6))'
    src: /Portfolio/assets/images/hero-banner.png
---

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white)
![React](https://img.shields.io/badge/React-18+-61DAFB?logo=react&logoColor=black)
![Flask](https://img.shields.io/badge/Flask-3.0-000000?logo=flask&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-4169E1?logo=postgresql&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active_Development-4CAF50)

# What is FRAMES?

**FRAMES** (Framework for Research & Analytics in Mission Engineering Systems) is a **multi-university research platform** developing predictive models for **organizational mission success** in complex engineering environments.

University space labs serve as the research environment—small enough to fully instrument, with clear mission outcomes and natural experiments in knowledge loss as students rotate. The insights apply far beyond education: any organization undertaking complex emergent technology missions faces the same structural risks.

---

## The Research Question

> **Can we predict mission success or failure based on organizational structure?**

FRAMES is building a predictive model grounded in Herbert Simon's work on near-decomposable systems. By mapping interfaces between people and subsystems, measuring bond strength, and tracking knowledge distribution, the model identifies structural vulnerabilities before they cause mission failure.

---

## Key Capabilities

```mermaid
graph LR
    subgraph FRAMES["FRAMES PLATFORM"]
        A["Organizational<br/>Mapping"]
        B["Risk<br/>Prediction"]
        C["Knowledge<br/>Continuity"]
        D["Mission Success<br/>Modeling"]
    end
    
    A --> B
    B --> C
    C --> D
    D --> A
```

| Capability | Description |
|------------|-------------|
| **Organizational Mapping** | Instrument team structure: interfaces, bond strength, knowledge distribution |
| **Risk Prediction** | Identify structural vulnerabilities before they cause mission failure |
| **Knowledge Continuity** | Track where expertise lives and what breaks when people leave |
| **Mission Success Modeling** | Predictive model trained on real outcomes from complex engineering missions |

---

## Project Scale

| Metric | Value |
|--------|-------|
| **Partner Universities** | 8 institutions |
| **Database Tables** | 37+ structured tables |
| **AI Agents** | 3 specialized agents mapping organizational structure |
| **Predictive Model** | Mission risk prediction based on Simon's molecular model |
| **Research Domains** | 4 theoretical foundations |

**Partnering Universities:** Cal Poly Pomona (Lead), Columbia University, Texas State University, Virginia Tech, Washington State University, University of Illinois, Northeastern University, Mt. San Antonio College

---

## The Real Problem: Team Leads Are Overwhelmed

In university space labs, **team leads carry an impossible burden**:

- **Constant rotation** — Students cycle in and out every semester; team leads start over constantly
- **Onboarding consumes everything** — Hours spent teaching the same basics to each new cohort
- **No time for mentorship** — Administrative burden crowds out hands-on guidance
- **Knowledge walks out the door** — Graduating students take expertise with them
- **Reinventing the wheel** — Each generation rediscovers what predecessors already solved

Team leads want to connect with students, guide projects, and share hard-won expertise. Instead, they're buried in repetitive onboarding, documentation, and process management.

---

## What FRAMES Does for Team Leads

FRAMES exists to **give team leads their time back**:

- **Automated onboarding** — The model handles routine training; team leads handle the human stuff
- **Auto-generated SOPs** — Drop your notes, get lab procedures; no manual documentation grind
- **Smart module recommendations** — Students get the right content at the right time, automatically
- **Knowledge preservation** — Expertise stays in the system when students graduate
- **Workflow automation** — Less administrative overhead, more mentorship time

**The goal:** As the model learns from real outcomes, it gets better at taking documentation burden off team leads—so they can focus on what only humans can do: connect with students and provide hands-on guidance.

---

## The Predictive Model: From Theory to Application

FRAMES operationalizes Herbert Simon's research on Nearly Decomposable Architecture (NDA) into a **diagnostic framework for organizational resilience**.

### The Molecular Analogy

Simon (1962) described complex systems using a molecular analogy:

- **Modules** act like cells or molecular groups—performing most work internally with strong internal bonds
- **Interfaces** are the connection points where modules exchange information, resources, or coordinate actions
- **Couplings** describe bond strength—strong within modules, weaker across external interfaces
- **Interface Mechanisms** are the roles, processes, and tools that maintain connections and prevent degradation

This separation allows modules to adapt internally without destabilizing the whole system. But Simon noted that **weaker external bonds can erode if not reinforced**, leading to fragmentation.

```mermaid
graph TB
    subgraph MOD1["MODULE A"]
        A1((Member))
        A2((Member))
        A3((Member))
        A1 -->|strong| A2
        A2 -->|strong| A3
        A1 -->|strong| A3
    end
    
    subgraph MOD2["MODULE B"]
        B1((Member))
        B2((Member))
        B3((Member))
        B1 -->|strong| B2
        B2 -->|strong| B3
        B1 -->|strong| B3
    end
    
    subgraph INTERFACE["INTERFACE"]
        I1[Mechanism]
        I2[Mechanism]
    end
    
    A2 -.->|weak coupling| I1
    I1 -.->|weak coupling| B1
    A3 -.->|weak coupling| I2
    I2 -.->|weak coupling| B2
```

### Interface Categories

The research identifies three categories of interfaces:

```mermaid
graph LR
    subgraph CONCURRENT["CONCURRENT INTERFACES"]
        C1[Between active modules<br/>working in parallel]
    end
    
    subgraph EXTERNAL["EXTERNAL INTERFACES"]
        E1[Connecting to outside<br/>institutional modules]
    end
    
    subgraph INTERGEN["INTERGENERATIONAL INTERFACES"]
        G1[Linking outgoing and<br/>incoming cohorts]
    end
```

### Knowledge Types at Interfaces

Two primary knowledge-transfer types exist at interfaces, each with different fragility patterns:

| Knowledge Type | Description | Transfer Mechanism | Fragility |
|----------------|-------------|-------------------|-----------|
| **Codified** | Documented, transferable independent of individuals | Walkthroughs, documentation repositories, design reviews | More resilient |
| **Institutional** | Tacit, experience-based, held by individuals | In-person experience, repetition, mentorship | Prone to degradation |

Interfaces dominated by institutional knowledge are more prone to degradation when personnel rotate out. Codified interfaces demonstrate greater resilience.

### Rotational Micro-Modules

In university space labs, the boundary module is internally composed of overlapping, rotational **micro-modules**—student cohorts, sub-teams, and project groups that cycle in and out over time (typically 1-4 semesters).

```mermaid
graph TB
    subgraph TIME["TEMPORAL ROTATION"]
        direction LR
        T1["Semester 1"]
        T2["Semester 2"]
        T3["Semester 3"]
        T4["Semester 4"]
    end
    
    subgraph INCOMING["INCOMING COHORT"]
        I1((New<br/>Members))
    end
    
    subgraph ESTABLISHED["ESTABLISHED COHORT"]
        E1((Active<br/>Members))
    end
    
    subgraph OUTGOING["OUTGOING COHORT"]
        O1((Graduating<br/>Members))
    end
    
    I1 -->|onboarding| E1
    E1 -->|knowledge transfer| O1
    O1 -.->|handoff| I1
```

This creates **predictable knowledge-transfer vulnerabilities**:

- Incoming cohorts join mid-project, receiving information they cannot immediately act on
- Middle cohorts pass along knowledge tied only to their current project phase
- Outgoing cohorts graduate before projects complete, leaving incomplete work and undocumented context

### Six Diagnostic Dimensions

The framework assesses interfaces using six NDA diagnostic dimensions:

| Dimension | Question |
|-----------|----------|
| **Actor Autonomy** | How independently do interdependent actors operate? Are objectives conflicting? |
| **Partitioned Knowledge** | Is knowledge siloed? What integration mechanisms exist? |
| **Emergent Outputs** | How often do goals shift or remain undefined during development? |
| **Temporal Misalignment** | Do timelines differ across modules (academic calendars vs. project cycles)? |
| **Integration Cost** | Is coordination effort sustainable at each interface? |
| **Coupling Degradation** | Are planned interfaces still occurring? Are modules disengaging? |

### What the Model Predicts

| Risk Factor | Prediction |
|-------------|------------|
| **Interface fragility** | Which connections between subsystems will fail under stress |
| **Knowledge concentration** | Single points of failure where expertise is too centralized |
| **Transition risk** | What breaks when key people leave |
| **Subsystem isolation** | Which teams aren't communicating enough |
| **Mission success probability** | Overall likelihood given current structure |

### Why University Space Labs?

These aren't classroom projects—they're NASA-contracted missions with real deliverables:

- **Real contracts** — Actual NASA deliverables with deadlines and consequences
- **Visible interfaces** — Teams small enough to observe every connection
- **Clear outcomes** — Missions succeed or fail; no ambiguity
- **Natural experiments** — Student rotation creates controlled knowledge loss events

The combination of real stakes and observable structure makes university space labs uniquely valuable for organizational research.

### Broader Implications

If the model works here, it applies directly to:

- NASA centers and commercial space programs
- Startup engineering teams
- R&D laboratories
- Any organization undertaking complex emergent technology missions

[Learn more about the architecture →]({{ site.baseurl }}/architecture)

---

## Theoretical Foundations

FRAMES is built on established research:

1. **Nearly Decomposable Architecture** (Herbert Simon) — Models semi-independent organizational modules
2. **Hybrid Autonomous Organizations** (Champenois & Etzkowitz) — University space labs in boundary spaces
3. **OATutor Pedagogy** — Scaffolding, hint pathways, validation steps
4. **Knowledge Transfer Research** — Codified vs tacit knowledge tracking

---

## Contact

**Project Lead:** Elizabeth Osborn  
**Email:** [eosborn@cpp.edu](mailto:eosborn@cpp.edu)  
**Institution:** Cal Poly Pomona  
**Repository:** [GitHub](https://github.com/Lizo-RoadTown/Portfolio)

---

*FRAMES: Predicting mission success through organizational structure analysis.*
