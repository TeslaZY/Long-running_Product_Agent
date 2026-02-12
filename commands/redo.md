---
description: Redo a specific task - marks it as incomplete and starts implementation
---

# Redo Task

Re-execute a previously completed or in-progress task.

## Usage

```bash
/redo <task-id>
```

## Examples

```bash
# Redo the UI prompt generation task
/redo ui-001

# Redo a specific frontend task
/redo fe-002

# Redo a test task
/redo test-001
```

## Behavior

When `/redo <task-id>` is invoked:

### 1. Validate Task Exists
- Read `task-list.json`
- Find the task by ID
- If not found, show error and suggest using `/tasks` to see available IDs

### 2. Show Task Information
```
╔══════════════════════════════════════════════════════════════╗
║                      REDO TASK: fe-002                        ║
╠══════════════════════════════════════════════════════════════╣
║ Task: Implement core layout and navigation                   ║
║ Phase: 5 - Frontend Development                              ║
║ Priority: critical                                           ║
║ Previous Status: completed                                   ║
╠══════════════════════════════════════════════════════════════╣
║ Steps:                                                       ║
║ 1. Create main layout component                              ║
║ 2. Implement navigation                                      ║
║ 3. Set up routing                                            ║
║ 4. Create responsive structure                               ║
╠══════════════════════════════════════════════════════════════╣
║ Verification:                                                ║
║ - Layout renders correctly                                   ║
║ - Navigation works                                           ║
║ - Responsive on different screens                            ║
║ - No console errors                                          ║
╚══════════════════════════════════════════════════════════════╝

Proceed with redo? [Y/n]
```

### 3. Update Task Status
- Set `passes: false`
- Update `statistics.in_progress_tasks` if appropriate
- Log the redo action in `agent-progress.md`

### 4. Handle Downstream Tasks
**Warning:** Redoing a task may affect tasks that depend on it.

```
⚠️  WARNING: This task has dependent tasks that may be affected:
  - fe-003: Implement header component (depends on fe-002)
  - fe-004: Implement sidebar (depends on fe-002)

These tasks may need to be re-verified after redoing fe-002.

Proceed? [Y/n]
```

### 5. Execute Task
- Follow the task's `steps` array
- Use appropriate skills based on task `category`
- Run all `verification` steps
- Mark as `passes: true` when complete
- Commit changes

## Important Notes

1. **Git Safety**: Before redoing, ensure current work is committed
2. **Downstream Impact**: Consider affected tasks before proceeding
3. **Clean State**: Leave the project in a working state
4. **Documentation**: Update `agent-progress.md` with redo details

## Related Commands

- `/tasks` - View all tasks and their IDs
- `/continue` - Continue with next pending task
- `/progress` - View overall progress

