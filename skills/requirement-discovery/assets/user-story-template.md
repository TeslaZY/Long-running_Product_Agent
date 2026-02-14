# User Story Template

## Standard Format

```markdown
## US-[ID]: [Story Title]

**As a** [type of user]
**I want** [goal/desire]
**So that** [benefit/value]

### Context
[Brief background or situation]

### Acceptance Criteria
- [ ] Given [precondition], when [action], then [expected result]
- [ ] Given [precondition], when [action], then [expected result]
- [ ] Given [precondition], when [action], then [expected result]

### Priority
- [ ] Must Have (MVP)
- [ ] Should Have
- [ ] Could Have
- [ ] Won't Have

### Effort Estimate
- [ ] Small (1-2 days)
- [ ] Medium (3-5 days)
- [ ] Large (1-2 weeks)
- [ ] Extra Large (2+ weeks)

### Dependencies
- [List of related story IDs]

### Notes
[Any additional context or considerations]
```

## Example

```markdown
## US-001: User Login

**As a** registered user
**I want** to log in with my email and password
**So that** I can access my personalized dashboard

### Context
Users need secure access to their accounts after registration.

### Acceptance Criteria
- [ ] Given a registered user, when they enter valid credentials, then they are redirected to their dashboard
- [ ] Given a registered user, when they enter invalid credentials, then they see an error message
- [ ] Given a logged-in user, when they close the browser, then they remain logged in for 7 days
- [ ] Given a user, when they click "forgot password", then they receive a reset email

### Priority
- [x] Must Have (MVP)

### Effort Estimate
- [ ] Small
- [x] Medium
- [ ] Large
- [ ] Extra Large

### Dependencies
- US-000: User Registration

### Notes
- Consider social login for future versions
- Must comply with password security best practices
```

## INVEST Criteria

Good user stories should be:

- **I**ndependent - Can be developed separately
- **N**egotiable - Details can be discussed
- **V**aluable - Provides value to users
- **E**stimable - Can be estimated for effort
- **S**mall - Can be completed in one sprint
- **T**estable - Has clear acceptance criteria

## Common Patterns

### CRUD Operations

```markdown
## US-XXX: Create [Entity]
**As a** [user]
**I want** to create a new [entity]
**So that** [benefit]

## US-XXX: Read [Entity]
**As a** [user]
**I want** to view [entity] details
**So that** [benefit]

## US-XXX: Update [Entity]
**As a** [user]
**I want** to modify [entity] information
**So that** [benefit]

## US-XXX: Delete [Entity]
**As a** [user]
**I want** to remove [entity]
**So that** [benefit]
```

### Search/Filter

```markdown
## US-XXX: Search [Entities]
**As a** [user]
**I want** to search for [entities] by [criteria]
**So that** I can quickly find what I need

### Acceptance Criteria
- [ ] Given [entities exist], when I search by [criteria], then matching results are displayed
- [ ] Given no matches, when I search, then I see "no results" message
- [ ] Given many results, when I search, then results are paginated
```

### Workflow

```markdown
## US-XXX: [Action] Approval
**As a** [user]
**I want** to approve/reject [item]
**So that** [business process continues]

### Acceptance Criteria
- [ ] Given pending [item], when I approve, then [next state]
- [ ] Given pending [item], when I reject, then [alternate state]
- [ ] Given [item] requires comment, when I approve/reject, then comment is required
```
