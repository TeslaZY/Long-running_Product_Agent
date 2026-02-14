# Analysis Template

## Gap Analysis Document

### Document Information
- **Product**: [Product Name]
- **Version**: [X.Y.Z]
- **Date**: [Date]
- **Analyst**: [Name]

---

## 1. Requirement Overview

### 1.1 Scope
[Brief description of what was analyzed]

### 1.2 User Stories Covered
| ID | Title | Status |
|----|-------|--------|
| US-001 | [Title] | Analyzed |
| US-002 | [Title] | Analyzed |

---

## 2. Gap Analysis

### 2.1 Functional Gaps

#### Gap-001: [Gap Title]
- **Related Story**: US-XXX
- **Description**: [What is missing or unclear]
- **Impact**: [High/Medium/Low]
- **Recommendation**: [What should be added]

#### Gap-002: [Gap Title]
[Repeat structure]

### 2.2 Non-Functional Gaps

#### Gap-NF-001: [Gap Title]
- **Category**: [Performance/Security/Usability/etc.]
- **Description**: [What is missing]
- **Impact**: [High/Medium/Low]
- **Recommendation**: [What should be added]

### 2.3 Edge Case Gaps

| Scenario | Documented? | Gap Description | Action Needed |
|----------|-------------|-----------------|---------------|
| [Scenario 1] | No | [Description] | [Action] |
| [Scenario 2] | Partial | [Description] | [Action] |

---

## 3. Risk Assessment

### 3.1 Technical Risks

| ID | Risk | Probability | Impact | Mitigation | Owner |
|----|------|-------------|--------|------------|-------|
| TR-001 | [Risk] | H/M/L | H/M/L | [Strategy] | [Name] |

### 3.2 Business Risks

| ID | Risk | Probability | Impact | Mitigation | Owner |
|----|------|-------------|--------|------------|-------|
| BR-001 | [Risk] | H/M/L | H/M/L | [Strategy] | [Name] |

### 3.3 User Experience Risks

| ID | Risk | Probability | Impact | Mitigation | Owner |
|----|------|-------------|--------|------------|-------|
| UR-001 | [Risk] | H/M/L | H/M/L | [Strategy] | [Name] |

---

## 4. Dependency Analysis

### 4.1 Story Dependencies

```
[Story A] → requires → [Story B]
[Story C] → blocked by → [Story D]
[Story E] → parallel with → [Story F]
```

### 4.2 External Dependencies

| Dependency | Type | Status | Risk |
|------------|------|--------|------|
| [API Name] | Third-party | Available | Low |
| [Service] | Infrastructure | TBD | High |

---

## 5. Assumption Register

| ID | Assumption | Validated? | Risk if Wrong | Validation Method |
|----|------------|------------|---------------|-------------------|
| A-001 | [Assumption] | No | High | [Method] |

---

## 6. Questions Log

### Unanswered Questions

| ID | Question | Asked To | Status | Answer |
|----|----------|----------|--------|--------|
| Q-001 | [Question] | [Stakeholder] | Pending | - |

### Decisions Needed

| ID | Decision | Options | Deadline | Decision Maker |
|----|----------|---------|----------|----------------|
| D-001 | [Decision] | [A/B/C] | [Date] | [Name] |

---

## 7. Recommendations

### Critical (Must Address Before Design)
1. [Recommendation 1]
2. [Recommendation 2]

### High Priority (Address Before Development)
1. [Recommendation 1]
2. [Recommendation 2]

### Medium Priority (Address During Development)
1. [Recommendation 1]

### Low Priority (Nice to Have)
1. [Recommendation 1]

---

## 8. Sign-off

| Role | Name | Date | Signature |
|------|------|------|-----------|
| Product Manager | | | |
| Tech Lead | | | |
| Stakeholder | | | |
