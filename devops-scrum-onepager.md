# DevOps & Scrum Adoption
## Operational Considerations for the Transition

---

### Context

The DevOps team (formerly Transition and Release Management) is adopting Scrum as part of the organisation's move to agile. This document outlines key considerations to ensure a successful transition while maintaining operational excellence.

---

### Our Commitment

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│   SCRUM ADOPTION  ←──→  OPERATIONAL EXCELLENCE  ←──→  QUALITY  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

We are committed to making Scrum work for DevOps. However, we note that **Kanban** or **SRE practices** may be better suited to operational work, which is often interrupt-driven and unplanned. We will adapt where necessary.

---

### The Scrum Ecosystem

Standard Scrum framework and where DevOps participates:

```
                              ┌─────────────────────────────────────────┐
                              │            ORGANISATION                 │
                              └─────────────────────────────────────────┘
                                               │
                 ┌─────────────────────────────┼─────────────────────────────┐
                 │                             │                             │
                 ▼                             ▼                             ▼
          ┌─────────────┐              ┌─────────────┐              ┌─────────────┐
          │   PRODUCT   │              │    SCRUM    │              │    SCRUM    │
          │    OWNER    │              │   MASTER    │              │    TEAM     │
          │             │              │             │              │             │
          │ Owns "what" │              │ Owns "how"  │              │ Owns "do"   │
          └──────┬──────┘              └──────┬──────┘              └──────┬──────┘
                 │                             │                             │
                 │                             │                             │
                 ▼                             ▼                             ▼
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                                                                                         │
│    ┌──────────┐      ┌──────────┐      ┌──────────┐      ┌──────────┐      ┌────────┐  │
│    │ PRODUCT  │ ───► │  SPRINT  │ ───► │  SPRINT  │ ───► │  SPRINT  │ ───► │ INCRE- │  │
│    │ BACKLOG  │      │ PLANNING │      │ (2-4 wk) │      │  REVIEW  │      │  MENT  │  │
│    └──────────┘      └──────────┘      └──────────┘      └──────────┘      └────────┘  │
│                                              │                                          │
│                                        Daily Standup                                    │
│                                        Retrospective                                    │
│                                                                                         │
└─────────────────────────────────────────────────────────────────────────────────────────┘
                                               │
                                               ▼
                     ┌───────────────────────────────────────────────┐
                     │                    DEVOPS                     │
                     │                                               │
                     │   • Enables deployment of increments          │
                     │   • Maintains production environment          │
                     │   • Provides release governance (CAB)         │
                     │   • Feeds operational insights back to team   │
                     │                                               │
                     └───────────────────────────────────────────────┘
```

---

### Scrum Adapted for Operations

An operations-focused team has different realities than a product team:

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         TRADITIONAL SCRUM (Product Teams)                               │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                         │
│   100% PLANNED WORK                                                                     │
│   ████████████████████████████████████████████████████████████████████████████████████  │
│                                                                                         │
│   • All work comes from backlog                                                         │
│   • Sprint scope is protected                                                           │
│   • Interruptions are exceptions                                                        │
│                                                                                         │
└─────────────────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         OPERATIONS-ADAPTED SCRUM (DevOps Teams)                         │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                         │
│   PLANNED WORK (60-70%)              │  UNPLANNED/REACTIVE (30-40%)                     │
│   ████████████████████████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  │
│                                                                                         │
│   • Backlog items                    │  • Incidents & outages                           │
│   • Planned improvements             │  • Urgent change requests                        │
│   • Automation work                  │  • Production support                            │
│   • Technical debt                   │  • On-call responsibilities                      │
│                                                                                         │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

**Key Adaptations for Ops:**

```
┌────────────────────┬────────────────────────────────────────────────────────────────────┐
│ Standard Scrum     │ Operations Adaptation                                              │
├────────────────────┼────────────────────────────────────────────────────────────────────┤
│ Fixed sprint scope │ Reserve 30-40% capacity for unplanned work                         │
├────────────────────┼────────────────────────────────────────────────────────────────────┤
│ 2-4 week sprints   │ Consider shorter sprints (1-2 weeks) or Kanban flow                │
├────────────────────┼────────────────────────────────────────────────────────────────────┤
│ Team fully focused │ Account for on-call rotation reducing available capacity           │
├────────────────────┼────────────────────────────────────────────────────────────────────┤
│ Sprint planning    │ Include "interrupt buffer" in planning                             │
├────────────────────┼────────────────────────────────────────────────────────────────────┤
│ Velocity-based     │ Track both planned velocity AND operational load                   │
├────────────────────┼────────────────────────────────────────────────────────────────────┤
│ Definition of Done │ Include operational readiness (monitoring, runbooks, etc.)         │
└────────────────────┴────────────────────────────────────────────────────────────────────┘
```

---

### Retained Responsibilities

As the former Transition and Release Management team, we retain critical functions:

- **CAB Representation** — Continue to provide operational voice in Change Advisory Board
- **Release Governance** — Maintain quality gates and go-live readiness assessments
- **Operational Stability** — Ensure production systems remain reliable through change

---

### Project Manager vs Scrummaster

These roles are **not interchangeable**. A transition from PM to Scrummaster requires a fundamental mindset shift.

| Aspect | Project Manager | Scrummaster |
|--------|-----------------|-------------|
| **Focus** | Scope, timeline, budget | Process health, team dynamics |
| **Accountability** | Delivery outcomes | Team effectiveness |
| **Approach** | Directs and controls | Facilitates and serves |
| **Stakeholders** | Manages expectations | Shields team from interference |
| **Authority** | "What" and "when" | "How we work together" |

```
    PROJECT MANAGER                    SCRUMMASTER
    ───────────────                    ───────────
         │                                  │
         ▼                                  ▼
    ┌─────────┐                       ┌──────────┐
    │ DIRECTS │                       │ ENABLES  │
    │  WORK   │        ═════════►     │   TEAM   │
    └─────────┘       mindset shift   └──────────┘
```

---

### Scrummaster Role in DevOps

The Scrummaster serves the team by:

| Responsibility | What This Means |
|----------------|-----------------|
| **Surface impediments** | Make visible when the team is blocked or overloaded |
| **Monitor WIP** | Flag when work-in-progress exceeds sustainable capacity |
| **Protect focus** | Shield the team from unplanned interruptions where possible |
| **Facilitate ceremonies** | Run standups, retrospectives, planning, reviews |
| **Coach practices** | Help team continuously improve how they work |

The Scrummaster **does not**: own delivery timelines, define metrics unilaterally, or replace technical/operational leadership.

---

### Prerequisites for Success

Before Scrum can function effectively:

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│  ☐  Backlog grooming established and maintained          │
│  ☐  Clear product ownership defined                      │
│  ☐  QA integration into team workflow                    │
│  ☐  Shared understanding of "done"                       │
│  ☐  Space for operational/unplanned work in sprints      │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

---

### Balancing Culture

The DevOps team sits at the intersection of:

```
        ┌─────────────┐
        │  PROJECTS   │
        │  (delivery) │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │   DEVOPS    │◄────  Balanced voice for
        │             │       both perspectives
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │ OPERATIONS  │
        │ (stability) │
        └─────────────┘
```

We advocate for a healthy balance — neither pure project velocity nor pure operational caution, but informed decision-making that considers both.

---

### Summary

1. We adopt Scrum while remaining open about its limitations for ops work
2. Project Manager ≠ Scrummaster — the roles require different mindsets
3. We retain CAB and release governance responsibilities
4. Focus remains on quality and operational stability
5. Backlog grooming and clear ownership are prerequisites

---

*DevOps Team — 2026*
