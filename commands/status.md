---
description: View current project status, phase, and next steps
disable-model-invocation: true
---

# Project Status

This command shows the current status of the product management project, including phase progress and recommended next steps.

## Workflow

### 1. Check Project State

```bash
# Check for project files
ls -la Product-Spec.md task-list.json pm-progress.md 2>/dev/null
```

If no files found:
```
╔══════════════════════════════════════════════════════════════╗
║                    NO PROJECT FOUND                          ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ No active project detected in this directory.                ║
║                                                              ║
║ To start a new project, run:                                 ║
║   /pm:init                                                   ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

### 2. Read Project Files

- Read `Product-Spec.md` for product info
- Read `task-list.json` for task status
- Read `pm-progress.md` for session history

### 3. Determine Current Phase

```markdown
## Phase Detection Logic

1. **No Product-Spec.md** → Not Started
2. **Product-Spec.md exists, no user stories** → Init Complete, needs Discovery
3. **User stories exist, no analysis** → Discovery Complete, needs Analysis
4. **Analysis complete, no PRD** → Analysis Complete, needs Design
5. **PRD exists** → Design Complete, needs Review
```

### 4. Generate Status Report

```
╔══════════════════════════════════════════════════════════════╗
║                    PROJECT STATUS                            ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ Product: [Name]                                              ║
║ Version: [X.Y.Z]                                             ║
║ Status: [Draft/Review/Approved]                              ║
║                                                              ║
╠══════════════════════════════════════════════════════════════╣
║                      PROGRESS                                ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ Phase 1: Init        [████████░░] 80%  ✓                    ║
║ Phase 2: Discover    [████░░░░░░] 40%  ◐                    ║
║ Phase 3: Analyze     [░░░░░░░░░░]  0%                       ║
║ Phase 4: Design      [░░░░░░░░░░]  0%                       ║
║                                                              ║
╠══════════════════════════════════════════════════════════════╣
║                    STATISTICS                                ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ User Stories:      [X] total, [Y] complete                   ║
║ Requirements:      [X] functional, [Y] non-functional        ║
║ Risks:             [H] high, [M] medium, [L] low             ║
║ Prototype Screens: [N]                                       ║
║                                                              ║
╠══════════════════════════════════════════════════════════════╣
║                    NEXT STEPS                                ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ Current Phase: [Phase Name]                                  ║
║                                                              ║
║ Recommended Actions:                                         ║
║   1. [Action 1]                                              ║
║   2. [Action 2]                                              ║
║                                                              ║
║ Run: /pm:[next-command]                                      ║
║                                                              ║
╠══════════════════════════════════════════════════════════════╣
║                   RECENT ACTIVITY                            ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ [Date] - [Activity description]                              ║
║ [Date] - [Activity description]                              ║
║ [Date] - [Activity description]                              ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

### 5. Phase-Specific Details

#### If in Init Phase
```markdown
## Init Phase Details
- Product vision defined: ✓/✗
- Target users identified: ✓/✗
- Basic framework created: ✓/✗

Next: Run /pm:discover to collect user stories
```

#### If in Discovery Phase
```markdown
## Discovery Phase Details
- User personas: [N] defined
- User stories: [N] collected
  - Must Have: [X]
  - Should Have: [Y]
  - Could Have: [Z]

Next: Run /pm:analyze for deep requirement analysis
```

#### If in Analysis Phase
```markdown
## Analysis Phase Details
- Functional requirements: [N]
- Non-functional requirements: [N]
- Risks identified: [N]
- Gaps found: [N]

Next: Run /pm:design to create PRD and prototypes
```

#### If in Design Phase
```markdown
## Design Phase Details
- PRD status: [Draft/Complete]
- Prototype screens: [N]
- Design tokens: [Defined/Not defined]

Next: Review with stakeholders, iterate as needed
```

### 6. Quick Actions

```markdown
## Available Commands

| Command | Description |
|---------|-------------|
| /pm:init | Start new project |
| /pm:discover | Collect requirements |
| /pm:analyze | Analyze requirements |
| /pm:design | Create PRD & prototype |
| /pm:status | View this status |
```

## Important Rules

1. **Always check for files first** - Handle missing files gracefully
2. **Be informative** - Show relevant details for current phase
3. **Guide the user** - Suggest clear next steps
4. **Show progress** - Visual progress bars help understanding
5. **Keep it concise** - Don't overwhelm with information
