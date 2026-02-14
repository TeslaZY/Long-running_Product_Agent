# Requirement Discovery Skill

## Description

Interactive requirement discovery skill that collects user needs through structured interviews and generates comprehensive user stories.

## When to Use

- Triggered by `/pm:discover` command
- When user needs to gather requirements for a new feature
- When expanding existing product scope

## Capabilities

1. **User Persona Discovery**
   - Identify primary and secondary user personas
   - Understand user environment and context
   - Map user goals and motivations

2. **Feature Discovery**
   - Elicit feature requirements through questions
   - Understand user workflows
   - Identify edge cases and alternatives

3. **User Story Generation**
   - Convert requirements to user stories
   - Define acceptance criteria
   - Prioritize using MoSCoW method

## Process

### Step 1: Context Review

```
Read Product-Spec.md
Understand current product vision
Review existing user stories (if any)
```

### Step 2: Discovery Questions

Ask structured questions:

```markdown
## For User Personas

1. Tell me about the people who will use this product
2. What is their technical expertise level?
3. Where do they work? When do they use similar products?
4. What are their biggest frustrations today?

## For Features

1. Walk me through how a user would [action]
2. What information does the user need to provide?
3. What result do they expect to see?
4. What could go wrong in this process?
5. How do they solve this problem today?

## For Success Criteria

1. How will you know if this feature is successful?
2. What metrics matter most?
3. What would make a user say "wow"?
```

### Step 3: Generate User Stories

For each discovered requirement:

```markdown
## US-[ID]: [Title]

**As a** [user type]
**I want** [goal]
**So that** [benefit]

### Acceptance Criteria
- [ ] Given [context], when [action], then [outcome]
- [ ] Given [context], when [action], then [outcome]
- [ ] Given [context], when [action], then [outcome]

### Priority: [Must/Should/Could/Won't]
### Effort: [S/M/L/XL]
### Dependencies: [Story IDs]
```

### Step 4: Prioritization

Use MoSCoW prioritization:

- **Must Have**: Critical for MVP, non-negotiable
- **Should Have**: Important but not critical
- **Could Have**: Nice to have if time permits
- **Won't Have**: Explicitly out of scope

## Output

### User Stories Document

```markdown
# User Stories

## Must Have (MVP)

### US-001: [Story Title]
[Story details...]

## Should Have

### US-002: [Story Title]
[Story details...]

## Could Have

### US-003: [Story Title]
[Story details...]

## Won't Have (This Version)

### US-004: [Story Title]
[Story details...]
```

### Updated Product-Spec.md

Append user stories to Product-Spec.md

## Best Practices

1. **Listen actively** - Let the user talk, then probe deeper
2. **Ask "why"** - Understand the root cause, not just symptoms
3. **Validate** - Repeat back what you heard
4. **Stay focused** - Keep scope in mind
5. **Document everything** - Every insight is valuable
6. **Use concrete examples** - Abstract requirements lead to confusion

## Template Reference

See `assets/user-story-template.md` for detailed user story format.
