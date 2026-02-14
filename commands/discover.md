---
description: Discover and collect detailed requirements through user interviews and story generation
disable-model-invocation: true
---

# Discover Requirements

This command collects detailed requirements through interactive discovery sessions. It generates user stories and creates a requirements pool.

## Workflow

### 1. Pre-flight Check

- Verify `Product-Spec.md` exists
- Read current `Product-Spec.md` to understand context
- Check `task-list.json` for current phase

If no `Product-Spec.md`:
```
Error: No product found. Run /pm:init first.
```

### 2. Invoke Requirement Discovery Skill

Call the `requirement-discovery` skill with current product context:

```
Invoke skill: requirement-discovery
Context: [Product-Spec.md content]
Mode: Interactive discovery
```

### 3. Discovery Session

Conduct interactive discovery through questions:

#### User Persona Discovery

```markdown
## User Persona Questions

1. **Primary Persona**: Describe your typical user in detail
   - Job title/role?
   - Technical sophistication?
   - Daily workflows?

2. **Secondary Personas**: Who else will use this product?

3. **User Environment**: Where and when will they use it?
   - Office / Home / Mobile?
   - Time of day?
   - Frequency of use?

4. **Pain Points**: What problems do they currently face?
```

#### Feature Discovery

```markdown
## Feature Discovery Questions

For each feature area:

1. **Core Workflow**: Walk me through how a user would use this feature
2. **Input**: What information does the user provide?
3. **Output**: What does the user get back?
4. **Edge Cases**: What could go wrong?
5. **Alternatives**: How do they solve this today?
```

#### Success Criteria Discovery

```markdown
## Success Criteria Questions

1. **User Success**: How do you know when a user has succeeded?
2. **Business Success**: What business outcomes matter?
3. **Technical Success**: Any performance requirements?
4. **Adoption**: How will you measure adoption?
```

### 4. Generate User Stories

Based on discovery, generate user stories in the format:

```markdown
## User Story: [ID]

**As a** [user type]
**I want** [goal]
**So that** [benefit]

### Acceptance Criteria
- [ ] Given [context], when [action], then [outcome]
- [ ] Given [context], when [action], then [outcome]

### Priority: [Must/Should/Could/Won't]
### Effort Estimate: [S/M/L/XL]
### Dependencies: [List of story IDs]
```

### 5. Update Documents

#### Product-Spec.md

Update the following sections:
- User Stories (add new stories)
- Feature Categories (refine if needed)

#### task-list.json

Add discovery tasks:

```json
{
  "id": "disc-001",
  "category": "discovery",
  "description": "Collect user persona requirements",
  "status": "completed",
  "artifacts": ["Product-Spec.md"]
}
```

#### pm-progress.md

```markdown
### Discovery Session: [Date]
**Stories Collected**: X
**Features Identified**: Y
**Next**: Run /pm:analyze for deep analysis
```

### 6. Requirements Pool Summary

Generate a summary of the requirements pool:

```
╔══════════════════════════════════════════════════════════════╗
║                REQUIREMENTS DISCOVERED                       ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ User Personas:                                               ║
║   1. [Persona 1] - [Brief description]                       ║
║   2. [Persona 2] - [Brief description]                       ║
║                                                              ║
║ User Stories:                                                ║
║   Must Have:  [X] stories                                    ║
║   Should Have: [Y] stories                                   ║
║   Could Have: [Z] stories                                    ║
║                                                              ║
║ Key Features:                                                ║
║   • [Feature 1]                                              ║
║   • [Feature 2]                                              ║
║   • [Feature 3]                                              ║
║                                                              ║
║ Next Step: Run /pm:analyze for deep requirement analysis     ║
╚══════════════════════════════════════════════════════════════╝
```

### 7. Commit Changes

```bash
git add .
git commit -m "Discover: Collected [X] user stories

- Added [Y] user personas
- Identified [Z] key features
- Updated Product-Spec.md with user stories
- Updated task-list.json
"
```

## Important Rules

1. **Be interactive** - Discovery is a conversation, not a form
2. **Dig deeper** - Use "why" and "tell me more" liberally
3. **Validate understanding** - Repeat back what you hear
4. **Stay focused** - Keep scope in mind
5. **Document everything** - Every insight matters
