# Tough Questioning Skill

## Description

Critical analysis skill that challenges assumptions, identifies gaps, and ensures requirements are complete and well-defined through rigorous questioning.

## When to Use

- Triggered by `/pm:analyze` command
- When requirements seem incomplete or vague
- Before finalizing any specification

## Philosophy

**"The best product managers are the toughest critics of their own ideas."**

This skill applies the "毒舌产品经理" (Tough-talking PM) approach:
- Challenge every assumption
- Find gaps before development
- Think about edge cases
- Consider scale and failure

## Questioning Framework

### 1. Assumption Challenge

For every stated requirement, ask:

```markdown
## Assumption Audit

**Stated Assumption**: [What is assumed to be true]

**Challenging Questions**:
1. What if this assumption is wrong?
2. How would the product behave differently?
3. What evidence supports this assumption?
4. Under what conditions would this fail?

**Risk Level**: [High/Medium/Low]
**Mitigation**: [How to handle if assumption is wrong]
```

### 2. Edge Case Discovery

```markdown
## Edge Case Questions

1. What happens if the user enters [unexpected input]?
2. What if the network is slow or unavailable?
3. What if there are 10x more users than expected?
4. What if the user tries to do [impossible action]?
5. What if two users try to modify the same data?
6. What happens at midnight on New Year's Eve?
7. What if the user's session expires mid-action?
8. What if the user has [accessibility need]?
```

### 3. Scalability Questions

```markdown
## Scale Scenarios

Current: [Expected scale]
Future: [10x scale]

Questions:
1. Will this work with 10x data volume?
2. Will response time be acceptable?
3. Will the UI still be usable?
4. Will background processes complete in time?
5. Will storage costs be acceptable?
```

### 4. Security & Privacy

```markdown
## Security Checklist

1. Who should/shouldn't have access?
2. What sensitive data is involved?
3. How is data protected in transit/at rest?
4. What audit trails are needed?
5. What happens if credentials are compromised?
6. Are there compliance requirements (GDPR, HIPAA)?
```

### 5. Business Logic Gaps

```markdown
## Business Rule Questions

1. What happens if [business rule] is violated?
2. Who has the authority to override?
3. What are the consequences of [action]?
4. How does this affect billing/reporting?
5. What if [external system] is unavailable?
```

## Analysis Templates

### Gap Analysis Matrix

```markdown
## Gap Analysis: [Feature]

| Aspect | Documented | Gaps Found | Risk | Action |
|--------|------------|------------|------|--------|
| User Flow | ✓ | [gap] | High | [action] |
| Error Handling | ✗ | [gap] | Med | [action] |
| Edge Cases | ✗ | [gap] | Low | [action] |
| Scale | ✓ | [gap] | Med | [action] |
```

### Risk Assessment

```markdown
## Risk: [Risk Name]

**Description**: [What could go wrong]
**Probability**: [High/Medium/Low]
**Impact**: [High/Medium/Low]
**Mitigation**: [How to prevent or handle]
**Contingency**: [What to do if it happens]
**Owner**: [Who is responsible]
```

## Output

### Analysis Report

```markdown
# Requirement Analysis Report

## Executive Summary
- Stories analyzed: [N]
- Gaps found: [M]
- Risks identified: [K]

## Critical Gaps
1. [Gap 1] - [Impact]
2. [Gap 2] - [Impact]

## High-Priority Risks
1. [Risk 1] - [Mitigation]
2. [Risk 2] - [Mitigation]

## Recommendations
1. [Recommendation 1]
2. [Recommendation 2]
```

## Best Practices

1. **Be constructive** - Challenge to improve, not to criticize
2. **Document everything** - Every question and answer matters
3. **Think like a user** - Consider all user types
4. **Think like an attacker** - What could go wrong?
5. **Think like operations** - How will this be maintained?
6. **Prioritize by impact** - Not all gaps are equal

## Tone Guidelines

- Direct but not rude
- Challenging but supportive
- Critical but constructive
- Thorough but efficient

Remember: The goal is to find problems NOW, not during development or after launch.
