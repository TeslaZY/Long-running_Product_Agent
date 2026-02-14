---
description: Initialize a new product project - collect basic requirements and create project framework
disable-model-invocation: true
---

# Initialize Product Project

This command starts a new product management project. It collects basic product information and creates the initial documentation framework.

## Workflow

### 1. Dependency Check

Before starting, check and install required dependencies:

#### 1.1 Check Pencil MCP (Required for Prototyping)

```javascript
// Check if Pencil MCP is available
try {
  mcp__pencil__get_editor_state({include_schema: false})
  console.log("✓ Pencil MCP is available")
} catch (error) {
  console.log("✗ Pencil MCP not found")
  // Prompt user to install
}
```

**If Pencil MCP is not available:**

```
╔══════════════════════════════════════════════════════════════╗
║              DEPENDENCY REQUIRED                            ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ Pencil MCP is required for prototype design (/pm:design)    ║
║                                                              ║
║ Installation:                                                ║
║ 1. Install Pencil MCP server                                 ║
║ 2. Configure in Claude Code settings                         ║
║                                                              ║
║ Would you like to:                                           ║
║   [1] Continue without Pencil (limited functionality)        ║
║   [2] Show installation guide                                ║
║   [3] Abort and install Pencil first                         ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

#### 1.2 Check Git (Recommended)

```bash
# Check if git is installed
git --version
```

**If Git is not available:**

```
⚠ Git not found. Git is recommended for version control.
  You can continue without it, but document commits will be skipped.

Install: brew install git (macOS) or apt install git (Linux)
```

#### 1.3 Dependency Summary

Display dependency status:

```
╔══════════════════════════════════════════════════════════════╗
║                 DEPENDENCY CHECK                            ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ Pencil MCP:  ✓ Available / ✗ Not found                      ║
║ Git:         ✓ Available / ✗ Not found                      ║
║                                                              ║
║ Status: Ready to proceed / Action needed                     ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

### 2. Mode Detection

Check current state:
- If `Product-Spec.md` exists → Prompt user to use `/pm:discover` instead
- If no `Product-Spec.md` → Proceed with initialization

### 3. Collect Basic Information

Ask the user the following questions (adapt based on their initial input):

```markdown
## Product Initialization Questions

1. **Product Name**: What is the name of your product/project?
2. **Product Vision**: In one sentence, what problem does this product solve?
3. **Target Users**: Who are the primary users of this product?
4. **Core Value**: What is the main benefit users will get?
5. **Platform**: Web / Mobile / Desktop / API / Other?
6. **Timeline**: Any specific timeline constraints?
7. **Priority**: Speed / Quality / Cost - which is most important?
```

### 4. Invoke Requirement Discovery Skill

After collecting basic info, invoke the `requirement-discovery` skill to:
- Generate initial user stories
- Identify key features
- Create feature categories

### 5. Create Project Documents

Generate the following files:

#### Product-Spec.md (Framework)

```markdown
# Product Specification: [Product Name]

**Version:** 1.0.0
**Created:** [Date]
**Status:** Draft

## Executive Summary

[Product vision from user input]

## Product Overview

### Problem Statement
[Problem the product solves]

### Target Users
[User personas - to be expanded]

### Success Metrics
[Key metrics for measuring success]

## Feature Categories

### Must Have (MVP)
- [ ] [Feature 1]
- [ ] [Feature 2]

### Should Have
- [ ] [Feature 3]

### Could Have
- [ ] [Feature 4]

### Won't Have (This Version)
- [ ] [Feature 5]

## User Stories

[To be populated by /pm:discover]

## Functional Requirements

[To be populated by /pm:analyze]

## Non-Functional Requirements

[To be populated by /pm:analyze]

## UI/UX Design

[To be populated by /pm:design]

## Appendix

### Glossary
- [Key terms]

### References
- [Related documents]
```

#### task-list.json (Initial)

```json
{
  "project_info": {
    "name": "[Product Name]",
    "description": "[Product vision]",
    "type": "product-design",
    "created_at": "[Date]",
    "current_phase": "discovery",
    "dependencies": {
      "pencil_mcp": true,
      "git": true
    }
  },
  "statistics": {
    "total_tasks": 0,
    "completed_tasks": 0,
    "pending_tasks": 0
  },
  "phases": [
    {
      "id": "discovery",
      "name": "需求发现",
      "status": "in_progress",
      "tasks": []
    },
    {
      "id": "analysis",
      "name": "需求分析",
      "status": "pending",
      "tasks": []
    },
    {
      "id": "design",
      "name": "PRD & 原型",
      "status": "pending",
      "tasks": []
    },
    {
      "id": "review",
      "name": "评审交付",
      "status": "pending",
      "tasks": []
    }
  ]
}
```

#### pm-progress.md

```markdown
# PM Agent Progress Log

## Session: [Date]

### Completed
- Initialized product project
- Created Product-Spec.md framework
- Created task-list.json

### Current Phase
Discovery - Collecting requirements and user stories

### Next Steps
1. Run `/pm:discover` to collect detailed requirements
2. Run `/pm:analyze` for deep analysis
3. Run `/pm:design` to create PRD and prototypes
```

### 6. Output Format

Display initialization summary:

```
╔══════════════════════════════════════════════════════════════╗
║                 PROJECT INITIALIZED                          ║
╠══════════════════════════════════════════════════════════════╣
║ Product: [Name]                                              ║
║ Vision: [One-line vision]                                    ║
║                                                              ║
║ Dependencies:                                                ║
║   Pencil MCP: ✓                                              ║
║   Git:        ✓                                              ║
║                                                              ║
║ Documents Created:                                           ║
║   ✓ Product-Spec.md (framework)                              ║
║   ✓ task-list.json                                           ║
║   ✓ pm-progress.md                                           ║
║                                                              ║
║ Next Step: Run /pm:discover to collect detailed requirements ║
╚══════════════════════════════════════════════════════════════╝
```

### 7. Commit Changes

If Git is available:

```bash
git add .
git commit -m "Initialize PM project: [Product Name]

- Created Product-Spec.md framework
- Created task-list.json
- Created pm-progress.md
- Ready for requirement discovery phase
"
```

## Dependency Installation Guide

### Pencil MCP Installation

1. **Install Pencil MCP Server**
   ```bash
   # Follow Pencil MCP installation instructions
   # Usually available via npm or manual download
   ```

2. **Configure Claude Code**
   ```json
   // Add to Claude Code MCP settings
   {
     "mcpServers": {
       "pencil": {
         "command": "path-to-pencil-mcp",
         "args": []
       }
     }
   }
   ```

3. **Restart Claude Code** to load the MCP server

4. **Verify Installation**
   - Run `/pm:init` again
   - Pencil MCP should show as available

### Git Installation

- **macOS**: `brew install git`
- **Ubuntu/Debian**: `sudo apt install git`
- **Windows**: Download from https://git-scm.com

After installation:
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

## Important Rules

1. **Always check dependencies first** - Ensure tools are available
2. **Always start fresh** - This command is for new projects only
3. **Collect enough context** - Don't rush through questions
4. **Keep it simple** - Framework first, details come later
5. **Guide the user** - Help them think through their product
6. **Set expectations** - Make clear what happens next
7. **Handle missing deps gracefully** - Allow partial functionality
