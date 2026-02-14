---
description: Deep analysis of requirements through tough questioning and risk identification
disable-model-invocation: true
---

# Analyze Requirements

This command performs deep analysis of collected requirements. It uses tough questioning to find gaps, identifies dependencies, and assesses risks.

## Workflow

### 1. Pre-flight Check

- Verify `Product-Spec.md` exists
- Verify user stories exist in Product-Spec.md
- Read `pm-progress.md` for context

If requirements not found:
```
Error: No requirements to analyze. Run /pm:discover first.
```

### 2. Invoke Tough Questioning Skill

Call the `tough-questioning` skill:

```
Invoke skill: tough-questioning
Context: [Product-Spec.md content]
Mode: Critical analysis
```

### 3. Critical Analysis Framework

#### Gap Analysis

For each user story, ask:

```markdown
## Gap Analysis: [Story ID]

### Current Understanding
- What we know: [Summary]
- What's documented: [Checklist]

### Critical Questions
1. What happens if [edge case]?
2. Who handles [responsibility]?
3. What's the fallback for [dependency]?
4. How does this scale when [growth scenario]?
5. What security/privacy concerns exist?

### Identified Gaps
- [Gap 1]
- [Gap 2]
```

#### Dependency Mapping

```markdown
## Dependency Map

### User Story Dependencies
[Story A] → requires → [Story B]
[Story C] → blocked by → [Story D]

### External Dependencies
- Third-party: [Service/API]
- Infrastructure: [Requirements]
- Data: [Sources needed]

### Circular Dependencies
- [Identify any cycles]
```

#### Risk Assessment

```markdown
## Risk Assessment

### Technical Risks
| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| [Risk 1] | High/Med/Low | High/Med/Low | [Strategy] |

### Business Risks
| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| [Risk 1] | High/Med/Low | High/Med/Low | [Strategy] |

### User Experience Risks
| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| [Risk 1] | High/Med/Low | High/Med/Low | [Strategy] |
```

### 4. User Persona Refinement

Deep dive into each persona:

```markdown
## Persona: [Name]

### Demographics
- Role: [Job title]
- Experience: [Technical level]
- Environment: [Where they work]

### Goals & Motivations
- Primary goal: [What they want to achieve]
- Secondary goals: [Other objectives]
- Motivation: [Why they care]

### Pain Points & Frustrations
1. [Pain point 1]
2. [Pain point 2]

### Behavior Patterns
- How they currently solve the problem
- What tools they use
- Workarounds they've created

### Quote
"[Typical thing this persona would say]"
```

### 5. Functional Requirements Specification

```markdown
## Functional Requirements

### FR-001: [Requirement Name]
**Priority**: Must/Should/Could
**Related Stories**: [Story IDs]

**Description**:
[Detailed description of what the system must do]

**Inputs**:
- [Input 1]: [Type, validation rules]
- [Input 2]: [Type, validation rules]

**Outputs**:
- [Output 1]: [Format, content]

**Business Rules**:
1. [Rule 1]
2. [Rule 2]

**Error Handling**:
- [Error case 1]: [How to handle]
```

### 6. Non-Functional Requirements

```markdown
## Non-Functional Requirements

### Performance
- Response time: [Requirement]
- Throughput: [Requirement]
- Concurrent users: [Requirement]

### Security
- Authentication: [Requirement]
- Authorization: [Requirement]
- Data protection: [Requirement]

### Reliability
- Uptime: [Requirement]
- Backup: [Requirement]
- Recovery: [Requirement]

### Usability
- Learning curve: [Requirement]
- Accessibility: [Requirement]
- Internationalization: [Requirement]
```

### 7. Update Documents

#### Product-Spec.md

Update sections:
- Functional Requirements
- Non-Functional Requirements
- User Personas (refined)
- Risk Assessment

#### task-list.json

```json
{
  "id": "analyze-001",
  "category": "analysis",
  "description": "Complete requirement analysis",
  "status": "completed",
  "artifacts": ["Product-Spec.md"]
}
```

### 8. Analysis Summary

```
╔══════════════════════════════════════════════════════════════╗
║                  ANALYSIS COMPLETE                           ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ Functional Requirements: [X] identified                      ║
║ Non-Functional Requirements: [Y] identified                  ║
║                                                              ║
║ Gaps Found: [N]                                              ║
║   • [Gap 1]                                                  ║
║   • [Gap 2]                                                  ║
║                                                              ║
║ Risks Identified: [M]                                        ║
║   High: [H] | Medium: [M] | Low: [L]                         ║
║                                                              ║
║ Dependencies Mapped: [D]                                     ║
║   • [Dependency 1]                                           ║
║   • [Dependency 2]                                           ║
║                                                              ║
║ Next Step: Run /pm:design to create PRD and prototypes       ║
╚══════════════════════════════════════════════════════════════╝
```

### 9. Commit Changes

```bash
git add .
git commit -m "Analyze: Completed requirement analysis

- Added [X] functional requirements
- Added [Y] non-functional requirements
- Identified [N] gaps and [M] risks
- Updated Product-Spec.md with analysis results
"
```

## Important Rules

1. **Be critical** - Find the gaps before development
2. **Challenge assumptions** - Every "obvious" thing needs scrutiny
3. **Think edge cases** - What could possibly go wrong?
4. **Consider scale** - Will this work with 10x users?
5. **Document risks** - Unknowns are risks too
