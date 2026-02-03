# DevOps & Scrum
## Making This Work for an Ops Team

---

### Background

We're adopting Scrum as part of the org-wide move to agile. This doc covers how we make that work given we're an operations team (formerly Transition and Release Management), not a product team.

---

### The Goal

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│         SCRUM  ←──→  KEEPING THINGS RUNNING  ←──→  QUALITY     │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

We'll make Scrum work. That said, **Kanban** or **SRE practices** might be a better fit for ops work — it's interrupt-driven and unpredictable by nature. We'll adapt as needed.

---

### Where Scrum Fits

Standard Scrum and where DevOps comes in:

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
                     │   • Gets increments deployed                  │
                     │   • Keeps production running                  │
                     │   • Handles release governance (CAB)          │
                     │   • Brings operational reality to the table   │
                     │                                               │
                     └───────────────────────────────────────────────┘
```

---

### How Ops Is Different

Product teams and ops teams have different realities:

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
│                         OPS-ADAPTED SCRUM (DevOps Teams)                                │
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

**What we'll need to adapt:**

```
┌────────────────────┬────────────────────────────────────────────────────────────────────┐
│ Standard Scrum     │ How We'll Adapt                                                    │
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

### What We Still Own

We were Transition and Release Management a week ago. That work doesn't disappear:

- **CAB** — We're still the operational voice in Change Advisory Board
- **Release governance** — We still own quality gates and go-live readiness
- **Keeping prod stable** — That's still on us

---

### Project Manager vs Scrummaster

These aren't the same role. Moving from PM to Scrummaster is a mindset shift, not a title change.

| | Project Manager | Scrummaster |
|--------|-----------------|-------------|
| **Focus** | Scope, timeline, budget | Process health, team dynamics |
| **Accountable for** | Delivery outcomes | Team effectiveness |
| **Approach** | Directs and controls | Facilitates and serves |
| **Stakeholders** | Manages expectations | Shields team from interference |
| **Decides** | "What" and "when" | "How we work together" |

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

### What a Scrummaster Actually Does

| Responsibility | In Practice |
|----------------|-----------------|
| **Surface impediments** | Flag when we're blocked or overloaded |
| **Monitor WIP** | Call it out when there's too much in flight |
| **Protect focus** | Push back on unplanned interruptions where possible |
| **Facilitate ceremonies** | Run standups, retros, planning, reviews |
| **Coach practices** | Help us get better at how we work |

What they **don't** do: own delivery timelines, define metrics on their own, or replace tech leads.

---

### What Needs to Be in Place First

Before Scrum actually works for us:

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│  ☐  Backlog grooming established and maintained          │
│  ☐  Clear product ownership defined                      │
│  ☐  QA integrated into how we work                       │
│  ☐  Shared understanding of "done"                       │
│  ☐  Space in sprints for ops/unplanned work              │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

---

### Where We Sit

We're in the middle — and that's the point:

```
        ┌─────────────┐
        │  PROJECTS   │
        │  (delivery) │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │   DEVOPS    │◄────  We speak both languages
        │             │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │ OPERATIONS  │
        │ (stability) │
        └─────────────┘
```

We're not here to slow things down or rush things through. We're here to make sure decisions account for both sides.

---

### TL;DR

1. We'll adopt Scrum, but it needs adapting for ops work
2. Project Manager ≠ Scrummaster — different roles, different mindsets
3. We still own CAB and release governance
4. Quality and stability stay front and centre
5. Backlog grooming and clear ownership need to happen first

---

*DevOps Team — 2026*
