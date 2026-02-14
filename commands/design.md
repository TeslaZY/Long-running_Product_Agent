---
description: Create comprehensive PRD and interactive prototypes using Pencil MCP
disable-model-invocation: true
---

# Design PRD & Prototype

This command creates a complete Product Requirements Document (PRD) and generates interactive prototypes using Pencil MCP.

## Workflow

### 1. Pre-flight Check

- Verify `Product-Spec.md` exists with analyzed requirements
- Read `pm-progress.md` to confirm analysis phase is complete
- Check for functional requirements in Product-Spec.md

If analysis not complete:
```
Warning: Requirements not fully analyzed. Consider running /pm:analyze first.
Continue? [Y/n]
```

### 2. Invoke PRD Writer Skill

Call the `prd-writer` skill:

```
Invoke skill: prd-writer
Context: [Product-Spec.md content]
Output: Complete PRD document
```

### 3. PRD Document Generation

Generate a comprehensive PRD:

```markdown
# Product Requirements Document

## Document Information
- **Product Name**: [Name]
- **Version**: 1.0.0
- **Status**: Draft
- **Author**: [PM Name]
- **Date**: [Date]

## 1. Executive Summary
[2-3 paragraph overview of the product]

## 2. Product Vision
[Long-term vision and goals]

## 3. Target Users

### 3.1 Primary Persona
[Detailed persona description]

### 3.2 Secondary Personas
[Additional user types]

## 4. User Stories & Requirements

### 4.1 Must Have (MVP)
| ID | Story | Priority | Effort |
|----|-------|----------|--------|
| US-001 | [Story] | Must | S |

### 4.2 Should Have
[Stories]

### 4.3 Could Have
[Stories]

## 5. Functional Requirements

### 5.1 [Feature Area]
#### FR-001: [Requirement Name]
- **Description**: [What it does]
- **Acceptance Criteria**:
  - [ ] [Criteria 1]
  - [ ] [Criteria 2]

## 6. Non-Functional Requirements

### 6.1 Performance
- Response time: < 2s
- Concurrent users: 1000+

### 6.2 Security
- [Security requirements]

### 6.3 Reliability
- 99.9% uptime

## 7. UI/UX Specifications

### 7.1 Design Principles
- [Principle 1]
- [Principle 2]

### 7.2 Screen Specifications
[Detailed screen descriptions]

## 8. Technical Constraints
[Technical limitations and requirements]

## 9. Dependencies
[External and internal dependencies]

## 10. Risks & Mitigations
[Risk assessment from analysis]

## 11. Success Metrics
[KPIs and measurement criteria]

## 12. Timeline & Milestones
[Project timeline]

## Appendix
- Glossary
- References
- Revision History
```

### 4. Invoke Prototype Designer Skill

Call the `prototype-designer` skill:

```
Invoke skill: prototype-designer
Context: [PRD content]
Tool: Pencil MCP
Output: Interactive prototype
```

### 5. Prototype Generation

#### 5.1 Screen Planning

Based on PRD, plan the screens:

```markdown
## Prototype Screen Plan

### Screen 1: [Name]
- Purpose: [What it shows]
- Key Elements:
  - [Element 1]
  - [Element 2]
- User Actions:
  - [Action 1]
  - [Action 2]
- Navigation:
  - To: [Screen X]
  - From: [Screen Y]
```

#### 5.2 Use Pencil MCP

For each screen, use Pencil MCP tools:

```javascript
// 1. Get editor state
mcp__pencil__get_editor_state()

// 2. Get design guidelines
mcp__pencil__get_guidelines({topic: "landing-page"})

// 3. Create screen frame
mcp__pencil__batch_design({
  operations: `
    screen=I(document, {type: "frame", name: "Screen Name", width: 1440, height: 900})
    header=I(screen, {type: "frame", name: "Header", height: 64})
    content=I(screen, {type: "frame", name: "Content", layout: "vertical"})
  `
})

// 4. Get screenshot for review
mcp__pencil__get_screenshot({nodeId: screen})
```

#### 5.3 Design System Integration

```markdown
## Design Tokens

### Colors
- Primary: #Hex
- Secondary: #Hex
- Background: #Hex

### Typography
- Heading: [Font, Size]
- Body: [Font, Size]

### Spacing
- Base unit: 8px
- Gap sizes: 8, 16, 24, 32

### Components
- Button: [Specs]
- Input: [Specs]
- Card: [Specs]
```

### 6. Interactive Prototype

Create navigation between screens:

```markdown
## Prototype Flow

1. **Entry Point**: [Screen 1]
2. **Main Flow**:
   - [Screen 1] → [Action] → [Screen 2]
   - [Screen 2] → [Action] → [Screen 3]
3. **Alternative Flows**:
   - [Screen 1] → [Action] → [Screen 4]
```

### 7. Update Documents

#### Product-Spec.md

Add PRD section reference.

#### task-list.json

```json
{
  "id": "design-001",
  "category": "design",
  "description": "Create PRD and prototypes",
  "status": "completed",
  "artifacts": ["Product-PRD.md", "prototypes/"]
}
```

### 8. Design Summary

```
╔══════════════════════════════════════════════════════════════╗
║                  DESIGN COMPLETE                             ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ PRD Generated:                                               ║
║   ✓ Product-PRD.md                                           ║
║   ✓ 12 sections completed                                    ║
║                                                              ║
║ Prototypes Created:                                          ║
║   ✓ [N] screens                                              ║
║   ✓ Interactive navigation                                   ║
║   ✓ Design tokens defined                                    ║
║                                                              ║
║ Files:                                                       ║
║   • Product-PRD.md                                           ║
║   • prototypes/[product-name].pen                            ║
║                                                              ║
║ Next Step: Review with stakeholders, then iterate            ║
╚══════════════════════════════════════════════════════════════╝
```

### 9. Commit Changes

```bash
git add .
git commit -m "Design: Created PRD and prototypes

- Generated comprehensive PRD document
- Created [N] prototype screens
- Defined design tokens and components
- Ready for stakeholder review
"
```

## Important Rules

1. **Complete PRD first** - Document before designing
2. **Use design system** - Consistent tokens across screens
3. **Interactive prototypes** - Show real user flows
4. **Iterate based on feedback** - Design is never done
5. **Export for sharing** - Make prototypes accessible
