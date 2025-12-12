---
layout: article
title: AI Agents
key: page-agents
permalink: /agents/
---

FRAMES uses AI agents to interpret team activities, support documentation, and reduce the burden on team leads—all with human oversight and control.

---

## The Problem

Team leads are overwhelmed—responsible for technical work, training, documentation, coordination, and handoff management. Critical knowledge goes undocumented because there's no time.

**FRAMES agents help by:**

- Extracting knowledge from team activities
- Drafting documentation for human review
- Identifying patterns and risks
- Reducing administrative burden

---

## Three-Level Architecture

FRAMES agents operate at three autonomy levels with human oversight:

| Agent Level | Role | Autonomy | Example |
|-------------|------|----------|---------|
| **Alpha** | Observation | None | Analyze patterns, generate reports |
| **Beta** | Drafting | Low | Propose documentation, flag risks |
| **Gamma** | Execution | Medium | Update records (with approval), trigger notifications |

All actions are logged and audited. Agents can learn and improve autonomously, but can't make actual changes without human approval.

---

## Workflow (LangGraph-Powered)

Four-stage workflow: **Explore** → **Draft** → **Execute** → **Commit**

1. **Explore** — Agent reads sources, analyzes context, identifies patterns
2. **Draft** — Agent proposes changes (staged, not committed)
3. **Execute** — Human reviews and approves
4. **Commit** — Validator verifies, audit log written, finalized

Agents learn and collaborate autonomously. Humans approve actual changes.

---

## What Agents Do

**Knowledge Extraction:**
Parse team activities (meeting notes, GitHub commits, design reviews) → identify procedures and decisions → draft documentation (SOPs, decision records, handoff guides).

**Risk Detection:**
Monitor for knowledge concentration, inactive interfaces, upcoming departures without handoff plans, and siloed expertise.

**Documentation Support:**
Convert meeting notes to structured procedures, propose updates when practices change, generate handoff checklists, create onboarding guides from common questions.

---

## MCP Server Integration

Agents access external systems through Model Context Protocol (MCP) servers—secure, controlled connections:

| MCP Server | Purpose | Access Level |
|------------|---------|--------------|
| **Notion** | Read team workspaces, documentation | Read-only |
| **GitHub** | Read repositories, issues, commits | Read-only |
| **PostgreSQL** | Database operations | Gated—requires approval |
| **Filesystem** | Access local resources | Controlled |

---

## Human Oversight

Agents learn and analyze autonomously, but human approval is required for actual changes:

1. **Learning & Analysis** — Agents monitor data, recognize patterns, and improve autonomously
2. **Collaboration** — Agents share insights and iterate on content without human gates
3. **Publication Gate** — Human approval required before changes reach databases or users
4. **Audit Trail** — Full logging of all agent activities and approved changes

Agents can get smart, but can't DO anything without human permission.

---

## Use Cases

### For Team Leads

- Let agents draft documentation from your meeting notes
- Get alerts when knowledge is concentrating in one person
- Generate handoff checklists automatically when team members leave

[Learn more about Team Lead Tools →](/Portfolio/team-tools/)

### For Administrators

- See aggregated risk patterns across teams
- Monitor interface health without adding burden to teams
- Get early warning of structural vulnerabilities

[Learn more about FRAMES for Administrators →](/Portfolio/administrators/)

### For Researchers

- Study how AI assistance affects knowledge retention
- Analyze agent-generated documentation patterns
- Compare team performance with and without agent support

[Learn more about FRAMES for Researchers →](/Portfolio/researchers/)

---

## Technical Details

For implementation, API documentation, and integration:
[Technical Documentation →](/Portfolio/technical/) | [GitHub Repository](https://github.com/Lizo-RoadTown/Portfolio)

---

## Contact

**Elizabeth Osborn** | Cal Poly Pomona
[eosborn@cpp.edu](mailto:eosborn@cpp.edu)
Available for technical discussions and collaboration.
