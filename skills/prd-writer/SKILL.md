# PRD Writer Skill

## Description

Comprehensive PRD (Product Requirements Document) generation skill that transforms analyzed requirements into a complete, professional product specification.

## When to Use

- Triggered by `/pm:design` command
- When requirements analysis is complete
- Before starting prototype design

## PRD Structure

### 1. Document Information

```markdown
# Product Requirements Document

## Document Control
- **Product Name**: [Name]
- **Version**: [X.Y.Z]
- **Status**: [Draft/Review/Approved]
- **Author**: [Name]
- **Date Created**: [Date]
- **Last Updated**: [Date]

## Revision History
| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0.0 | [Date] | [Name] | Initial draft |
```

### 2. Executive Summary

```markdown
## Executive Summary

[2-3 paragraphs providing:
- What the product is
- Why it's being built
- Key benefits
- Target users]
```

### 3. Product Vision

```markdown
## Product Vision

### Vision Statement
[One compelling sentence describing the future state]

### Mission
[What the product aims to achieve]

### Goals
1. [Goal 1 - SMART format]
2. [Goal 2]
3. [Goal 3]

### Non-Goals
1. [Explicitly out of scope]
2. [Future consideration, not now]
```

### 4. Target Users

```markdown
## Target Users

### Primary Persona: [Name]
- **Role**: [Job title]
- **Demographics**: [Age, location, etc.]
- **Goals**: [What they want to achieve]
- **Pain Points**: [Current frustrations]
- **Technical Level**: [Novice/Intermediate/Expert]
- **Quote**: "[Something they would say]"

### Secondary Personas
[Similar structure for other user types]
```

### 5. User Stories & Requirements

```markdown
## User Stories

### Must Have (MVP)
| ID | Story | Effort | Priority |
|----|-------|--------|----------|
| US-001 | [Story] | M | Must |

[Full story details for each]

### Should Have
[Stories]

### Could Have
[Stories]

### Won't Have (This Version)
[Stories]
```

### 6. Functional Requirements

```markdown
## Functional Requirements

### [Feature Area 1]

#### FR-001: [Requirement Name]
- **Priority**: Must/Should/Could
- **Related Stories**: US-XXX
- **Description**: [Detailed description]
- **Business Rules**:
  1. [Rule 1]
  2. [Rule 2]
- **Inputs**: [What user provides]
- **Outputs**: [What system returns]
- **Acceptance Criteria**:
  - [ ] [Criteria 1]
  - [ ] [Criteria 2]

[Repeat for each requirement]
```

### 7. Non-Functional Requirements

```markdown
## Non-Functional Requirements

### Performance
- **Response Time**: [Requirement]
- **Throughput**: [Requirement]
- **Concurrent Users**: [Requirement]

### Security
- **Authentication**: [Requirement]
- **Authorization**: [Requirement]
- **Data Protection**: [Requirement]
- **Compliance**: [GDPR/HIPAA/etc.]

### Reliability
- **Availability**: [99.9% etc.]
- **Backup**: [Frequency and retention]
- **Recovery**: [RTO/RPO]

### Usability
- **Accessibility**: [WCAG level]
- **Internationalization**: [Languages]
- **Learning Curve**: [Expected time]

### Scalability
- **Data Growth**: [Expected growth]
- **User Growth**: [Expected growth]
```

### 8. UI/UX Specifications

```markdown
## UI/UX Specifications

### Design Principles
1. [Principle 1]
2. [Principle 2]

### Screen Inventory
| Screen | Purpose | Priority |
|--------|---------|----------|
| [Name] | [Purpose] | Must |

### User Flows
[Description of key flows]

### Design Tokens
- **Colors**: [Primary, Secondary, etc.]
- **Typography**: [Fonts, sizes]
- **Spacing**: [Grid system]
- **Components**: [Button, Input, etc.]
```

### 9. Technical Constraints

```markdown
## Technical Constraints

### Platform Requirements
- [Web/Mobile/Desktop]
- [Browser support]
- [Device requirements]

### Integration Requirements
- [Third-party services]
- [Internal systems]
- [APIs]

### Technical Stack
- [Frontend framework]
- [Backend framework]
- [Database]
- [Hosting]
```

### 10. Dependencies

```markdown
## Dependencies

### Internal Dependencies
| Dependency | Team | Status | Risk |
|------------|------|--------|------|
| [Dependency] | [Team] | [Status] | [Risk] |

### External Dependencies
| Dependency | Vendor | Status | Risk |
|------------|--------|--------|------|
| [Service] | [Vendor] | [Status] | [Risk] |
```

### 11. Risks & Mitigations

```markdown
## Risks & Mitigations

| Risk | Probability | Impact | Mitigation | Contingency |
|------|-------------|--------|------------|-------------|
| [Risk] | H/M/L | H/M/L | [Strategy] | [Plan B] |
```

### 12. Success Metrics

```markdown
## Success Metrics

### Business Metrics
- [Metric 1]: [Target]
- [Metric 2]: [Target]

### User Metrics
- [Metric 1]: [Target]
- [Metric 2]: [Target]

### Technical Metrics
- [Metric 1]: [Target]
- [Metric 2]: [Target]
```

### 13. Timeline & Milestones

```markdown
## Timeline & Milestones

### Phases
| Phase | Duration | Key Deliverables |
|-------|----------|------------------|
| Discovery | 2 weeks | Requirements |
| Design | 3 weeks | PRD, Prototypes |

### Milestones
- **M1**: [Name] - [Date]
- **M2**: [Name] - [Date]
```

### Appendix

```markdown
## Appendix

### Glossary
| Term | Definition |
|------|------------|
| [Term] | [Definition] |

### References
- [Document 1]
- [Document 2]
```

## Output

Generates a complete `Product-PRD.md` file ready for review.

## Best Practices

1. **Be specific** - Avoid vague language
2. **Be complete** - Cover all aspects
3. **Be measurable** - Use concrete metrics
4. **Be realistic** - Account for constraints
5. **Be visual** - Include diagrams where helpful
6. **Be organized** - Use consistent structure

## Template Reference

See `assets/prd-template.md` for full template.
