# PRD: NGEOA Curriculum Structure

**Product:** NGEOA Heavy Equipment Operator Training Curriculum
**Version:** 1.0
**Date:** 2026-04-05
**Author:** Claude (via Eric Coffie)
**Priority:** P0

---

## Overview

### Problem Statement

NGEOA has a website describing an 8-week heavy equipment training program, but lacks:
- Detailed curriculum documentation that demonstrates educational rigor
- Standardized module format for consistent delivery
- Defensible methodology (Job Task Analysis) for curriculum design
- Materials required for accreditation applications
- Documentation needed for grant applications

### Solution

Create a comprehensive curriculum documentation package modeled on the GovCon BD Upskilling structure, adapted for heavy equipment operator training.

### Success Metrics

| Metric | Target |
|--------|--------|
| Module documents created | 16 (8 weeks x 2 modules) |
| Curriculum overview complete | 1 document |
| JTA methodology documented | 1 document |
| NCCER alignment mapped | 100% of modules |
| Grant-ready format | Meets DOL requirements |

---

## Requirements

### R1: Curriculum Overview Document

**File:** `/curriculum/overview.md`

**Must Include:**
- Program structure (8 weeks, hours per week)
- Domain blueprint with weights
- JTA methodology reference
- Week-by-week topic summary
- Completion requirements
- Certificate criteria
- Materials package list

**Format:**
```markdown
# NGEOA Heavy Equipment Operator Training - Curriculum Overview

## Program Structure
| Attribute | Details |
|-----------|---------|
| Duration | 8 weeks |
| Format | Hands-on + classroom |
| Hours | 40 hours/week |
| Certification | NGEOA + OSHA 10 |

## Domain Blueprint (JTA-Validated)
| Domain | Weight | Description |
|--------|--------|-------------|
| D1 | X% | Safety & Compliance |
| D2 | X% | Equipment Fundamentals |
...
```

### R2: Domain Blueprint

**Domains for Heavy Equipment Operators:**

| Domain | Proposed Weight | Content |
|--------|-----------------|---------|
| **D1: Safety & Compliance** | 20% | OSHA 10, site safety, PPE, hazard recognition |
| **D2: Equipment Fundamentals** | 15% | Types, components, pre-operation inspection |
| **D3: Excavator Operations** | 20% | Digging, grading, trenching, loading |
| **D4: Loader Operations** | 15% | Material handling, loading trucks, stockpiling |
| **D5: Backhoe Operations** | 10% | Combination operations, utility work |
| **D6: Skid Steer Operations** | 10% | Compact equipment, attachments |
| **D7: Job Site Skills** | 10% | Reading plans, communication, teamwork |

**Total: 100%**

### R3: Module Format Standard

Each module must include (adapted from BD Upskilling):

```markdown
# Module X.X: [Title]

## Header
- Module number and title
- Domain mapping (D1-D7)
- Hours: Classroom / Hands-on
- Equipment required
- NCCER alignment (if applicable)

## Learning Objectives
- 3-5 measurable outcomes using action verbs
- Example: "Operate excavator to dig a 4' trench within 6" of grade stakes"

## Safety Briefing
- Hazards specific to this module
- Required PPE
- Emergency procedures

## Pre-Operation Checklist
- Equipment inspection items
- Fluid checks
- Safety features verification

## Lesson Content
- Core concepts with demonstrations
- Step-by-step procedures
- Common mistakes to avoid
- Tips from experienced operators

## Practical Exercise
- Hands-on activity description
- Performance criteria
- Time allocation
- Instructor supervision requirements

## Assessment Criteria
- Skills checklist
- Performance standards
- Pass/fail thresholds

## Knowledge Check (Optional)
- 5-10 questions for reinforcement
- Scenario-based questions

## Instructor Notes
- Teaching tips
- Common student challenges
- Equipment setup instructions
```

### R4: 8-Week Curriculum Structure

| Week | Focus | Modules | Equipment |
|------|-------|---------|-----------|
| 1 | Safety & Orientation | 1.1 OSHA 10, 1.2 Equipment Overview | Classroom |
| 2 | Pre-Operation & Fundamentals | 2.1 Inspection, 2.2 Basic Controls | All equipment |
| 3 | Excavator I | 3.1 Basic Operation, 3.2 Digging Fundamentals | Excavator |
| 4 | Excavator II | 4.1 Grading, 4.2 Loading Trucks | Excavator |
| 5 | Front-End Loader | 5.1 Operation, 5.2 Material Handling | Loader |
| 6 | Backhoe | 6.1 Operation, 6.2 Utility Trenching | Backhoe |
| 7 | Skid Steer & Attachments | 7.1 Operation, 7.2 Attachments | Skid Steer |
| 8 | Integration & Assessment | 8.1 Combined Operations, 8.2 Final Evaluation | All |

### R5: NCCER Alignment

Map each module to NCCER Heavy Equipment Operations curriculum:

| NGEOA Module | NCCER Module | NCCER ID |
|--------------|--------------|----------|
| 1.1 OSHA 10 | Orientation to the Trade | 22101 |
| 2.1 Inspection | Heavy Equipment Safety | 22102 |
| 3.1 Excavator Basics | Excavators | 22207 |
| 5.1 Loader Operation | Loaders | 22209 |
| 6.1 Backhoe Operation | Backhoes | 22204 |
| 7.1 Skid Steer Operation | Compaction Equipment (partial) | 22205 |

### R6: JTA Methodology Document

**File:** `/research/jta-methodology.md`

**Must Document:**
- Data sources (O*NET, job postings, employer interviews)
- Task frequency analysis
- Domain weight calculation
- Alignment with industry standards
- Validation from employers/subject matter experts

**O*NET Reference:** Heavy and Tractor-Trailer Truck Drivers (53-3032.00) and Construction Equipment Operators (47-2073.00)

---

## Technical Requirements

### File Structure

```
/ngeoa-website/curriculum/
├── overview.md
├── week-1/
│   ├── module-1.1-osha-10.md
│   └── module-1.2-equipment-overview.md
├── week-2/
│   ├── module-2.1-pre-op-inspection.md
│   └── module-2.2-basic-controls.md
├── week-3/
│   ├── module-3.1-excavator-basics.md
│   └── module-3.2-digging-fundamentals.md
├── week-4/
│   ├── module-4.1-grading.md
│   └── module-4.2-loading-trucks.md
├── week-5/
│   ├── module-5.1-loader-operation.md
│   └── module-5.2-material-handling.md
├── week-6/
│   ├── module-6.1-backhoe-operation.md
│   └── module-6.2-utility-trenching.md
├── week-7/
│   ├── module-7.1-skid-steer.md
│   └── module-7.2-attachments.md
└── week-8/
    ├── module-8.1-combined-operations.md
    └── module-8.2-final-evaluation.md
```

### Integration with CRM

- Each module completion tracked per student
- Assessment scores stored
- Instructor sign-off captured
- Hours logged

---

## Dependencies

| Dependency | Status | Owner |
|------------|--------|-------|
| BD Upskilling templates | Available | Reference |
| NCCER curriculum (for alignment) | Need to purchase | Eric |
| O*NET data | Free online | Research |
| Employer input | Pending | Brian/Cynthia |
| Equipment list | Pending | Program team |

---

## Acceptance Criteria

- [ ] Curriculum overview document complete
- [ ] All 16 modules documented in standard format
- [ ] JTA methodology documented with sources
- [ ] NCCER alignment mapped for all applicable modules
- [ ] Reviewed by at least 1 subject matter expert
- [ ] Website updated with curriculum summary

---

## Out of Scope

- NCCER ATS application (separate PRD)
- Instructor training program
- Student enrollment system
- Equipment procurement

---

## Timeline

| Phase | Duration | Deliverable |
|-------|----------|-------------|
| Week 1 | 5 days | Overview + Week 1-2 modules |
| Week 2 | 5 days | Week 3-5 modules |
| Week 3 | 5 days | Week 6-8 modules + JTA doc |
| Week 4 | 3 days | Review, revisions, website update |

---

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-04-05 | Initial PRD |
