# Prim Roadmap

## Current State

Prim is the ArachnidWorks PM Agent, handling task creation, updates, and project management guidance via ClickUp MCP.

**Version**: 1.0.0

---

## Short-Term

### Availability Improvements
- [ ] Smarter capacity calculation (account for meeting time, not just task estimates)
- [ ] Team-wide availability view across multiple assignees
- [ ] Recurring task awareness when checking availability

### Task Creation Polish
- [ ] Batch task creation (multiple related tasks at once)
- [ ] Task templates for common request types
- [ ] Auto-suggest assignees based on skill matching

---

## Medium-Term

### Workload Intelligence
- [ ] Proactive workload alerts ("Kenny is overbooked next Tuesday")
- [ ] Historical velocity tracking per team member
- [ ] Deadline risk detection

### Client Context
- [ ] Client preference memory (e.g., "ToP prefers detailed descriptions")
- [ ] Project-level context that carries across tasks
- [ ] Retainer hour tracking integration

---

## Long-Term

### Predictive PM
- [ ] Estimate accuracy tracking and calibration
- [ ] Task duration predictions based on historical data
- [ ] Sprint/capacity planning assistance

### Multi-System Integration
- [ ] Time tracking integration (Harvest, Toggl)
- [ ] Slack notifications for task updates
- [ ] Client portal status sync

---

## Completed

- [x] Core task creation with ClickUp MCP
- [x] Time estimate handling (two-step workaround for MCP limitation)
- [x] User identity persistence (.claude/user.json)
- [x] Availability checking by date range
- [x] PM guidance from knowledge base

---

## Contributing

To propose roadmap items, discuss with the team or create an issue in the Prim repo.
