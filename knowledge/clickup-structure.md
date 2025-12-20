# ClickUp Structure

## Hierarchy

ClickUp is organized in embedded hierarchies:

1. **Spaces** – Highest-level container (e.g., Delivery, Process Library)
2. **Folders** – Organizational layers within Spaces (e.g., client folders by AM)
3. **Lists** – Collections of tasks within a Folder (e.g., individual client lists)
4. **Tasks (Deliverables)** – Actionable items representing work to be completed (e.g., Newsletter Template)
5. **Subtasks (Internal Steps)** – Smaller steps nested within a Task (e.g., Newsletter Wireframe, Newsletter Design)

**Note**: Subtasks cannot have their own subtasks (nested subtasks get messy fast). If you feel nesting is needed, create multiple parent tasks instead.

## ArachnidWorks Workspace Structure

### Delivery Space (Primary)
Contains all client work organized by Account Manager:

- **--General** folder: Internal work (PTO, Internal Meetings, Tool Testing, etc.)
- **Alexis** folder: Alexis's client lists
- **Kenny** folder: Kenny's client lists  
- **Lulu** folder: Lulu's client lists
- **Mackenzie** folder: Mackenzie's client lists
- **Madelyn** folder: Madelyn's client lists
- **Monica** folder: Monica's client lists

### Other Spaces
- **Process Library**: Task templates by category
- **Operations**: Expenses, Employee Onboarding, PTO Calendar
- **Administration**: HR, IT, Product Development, Finance
- **New Business Development**: Leads, Deals, Accounts, Contacts
- **Billing**: Annual billing records

## Status Definitions

### Gearing Up
**Accountable**: Account Management

Tasks or ideas identified but not yet ready for execution. May lack full specs, require additional information, or haven't been prioritized. This is a holding area for potential deliverables.

### Ready
**Accountable**: Assigned Team Member

**Subtasks**: Have complete specs, clear context, and defined outputs. Assigned to an individual with time estimates and scheduling alignment. Moving here signals all requirements are in place and work is ready for execution by the due date.

**Parent Tasks**: If any subtasks are in Ready, the parent may be moved to Ready. Non-ready subtasks won't be executed until they're in Ready.

### In Progress
**Accountable**: Assigned Team Member

**Subtasks**: In active execution. The assignee moves a task here once work begins, covering everything from spec review through build, testing, and validation.

**Parent Tasks**: This status is not used at the parent level—it adds no value. Active tasks can just stay in Ready.

### Internal Blocked
**Accountable**: Account Management

**Subtasks**: Cannot progress due to an unexpected internal issue. A comment should be assigned to the AM outlining the blocker. Expected to be resolved internally without client involvement.

**Parent Tasks**: Move here if a dependent subtask is blocked and the deliverable is stalled.

### Waiting on Client
**Accountable**: Account Management

**Subtasks**: Reached a standstill due to client-side dependency. Assignee has completed all possible internal work, but progress requires client action (review, credentials, permissions, etc.).

**Parent Tasks**: If any subtask is Waiting on Client, the parent should be too—even if some subtasks continue. This lets AMs quickly see what needs client involvement.

### Done
**Accountable**: Assigned Team Member or Account Management

**Subtasks**: Everything completed according to spec. All testing, review, and accuracy checks finished. Moving here signals it's fully complete and client-ready.

**Parent Tasks**: When all subtasks are completed, move the parent to Done. If future changes are needed, pull back to Ready with a new subtask.

### Archived
**Accountable**: None

Not used. No task should be in this status—it's just a required status group by ClickUp.

## Internal Review

Internal review typically happens through a subtask assigned to the AM. It's ultimately up to the AM to determine their review approach based on context.
