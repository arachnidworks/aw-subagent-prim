# AW PM Agent

A Claude-powered project management agent for creating and managing tasks in ClickUp following ArachnidWorks standards.

## Purpose

This agent helps Account Managers quickly create well-structured tasks in ClickUp without manually filling in every field. It:

- Asks the right clarifying questions based on AW's PM documentation
- Ensures tasks are properly specced before creation
- Enforces standards (due dates, time estimates, assignees, statuses)
- Creates parent tasks and subtasks with appropriate structure

## Setup

### First-Time Setup

1. **Clone the repository**:
   ```bash
   git clone git@github.com:arachnidworks/aw-pm-agent.git
   cd aw-pm-agent
   ```

2. **Start Claude Code**:
   ```bash
   claude
   ```

3. **Authenticate with ClickUp**:
   - Run `/mcp` in Claude Code
   - Click the ClickUp authentication link
   - Sign in with your ClickUp account and authorize access
   - Return to Claude Code - you're now connected

4. **Identify yourself**:
   - On first run, the agent will ask for your name
   - It matches you against the team roster to get your ClickUp ID
   - Your info is saved locally in `.claude/user.json` for future sessions

### Daily Usage

```bash
cd aw-pm-agent
git pull              # Get latest agent updates
claude                # Start the agent
```

### Alternative: Claude Desktop

1. Connect this repository via GitHub MCP in Claude Desktop
2. Enable the ClickUp MCP connector
3. Start a conversation and ask Claude to create tasks

Note: Claude Code CLI is recommended as it better respects the CLAUDE.md instructions.

### Example Prompts

- "Create a task for ToP to write a blog post, due Friday, assign to John"
- "I need to set up a website redesign project for PMI with subtasks"
- "What's the difference between Gearing Up and Ready status?"
- "Update task ABC-123 to change the due date to next Monday"

## Repository Structure

```
aw-pm-agent/
├── CLAUDE.md                    # Main agent instructions
├── README.md                    # This file
├── .mcp.json                    # MCP server configuration
├── .claude/                     # Local config (gitignored)
│   └── user.json                # Your identity (created on first run)
├── knowledge/                   # PM standards and documentation
│   ├── pm-principles.md         # Core PM philosophy
│   ├── task-creation.md         # How to create good tasks
│   ├── clickup-structure.md     # Statuses, hierarchy, architecture
│   ├── task-management.md       # Managing existing tasks
│   └── spec-framework.md        # The 4-part spec framework
├── reference/                   # Lookup data
│   ├── clients.json             # Client ID → Name → List ID
│   └── team-members.json        # Team roster with roles
└── examples/                    # Example interactions
    └── common-scenarios.md
```

## Updating the Agent

When you discover improvements:

1. Edit the relevant files in this repo
2. Commit and push changes
3. Claude Desktop will pull the latest on next session

## Key Standards Enforced

- **No Time Travel**: Tasks in Ready/In Progress are never overdue
- **Due Date = Do Date**: Complete on the due date
- **Subtasks < 4 hours**: Break up larger work
- **One assignee per subtask**: Clear ownership
- **Spec before Ready**: Tasks must be fully defined

## Dependencies

- **Claude Code CLI** (recommended) or Claude Desktop
- **ClickUp account** with access to ArachnidWorks workspace

## Troubleshooting

### MCP not connecting
- Run `/mcp` in Claude Code to check status
- If it shows "Needs authentication", click the link to authenticate via OAuth
- If ClickUp MCP is missing, the agent will add it automatically on startup

### Agent not following instructions
- Make sure you're in the `aw-pm-agent` directory when starting Claude
- Run `git pull` to get latest CLAUDE.md updates

### Reset user identity
- Delete `.claude/user.json` to be prompted again on next startup
- Useful if you need to switch users or fix incorrect info

## Future Enhancements

Ideas for improving the PM Agent. These can be implemented as needs arise.

### Template Reference
Create `reference/templates.json` with common task patterns (blog post, landing page, newsletter, etc.) including pre-built subtask structures with typical estimates. Would allow AMs to say "create a blog post task" and get a ready-made structure.

### Proactive Capacity Warnings
Currently the agent can check availability when asked (e.g., "when does John have time next week?"). A future enhancement would be to proactively warn when assigning a task would push someone over capacity.

### Time Estimate Validation
Automatically warn when:
- Subtask estimates exceed 4 hours (suggest breaking up)
- A day's total assignments exceed 7 hours (capacity warning)

### Quick Status Commands
Support shorthand commands for common queries:
- `overdue` → Show overdue tasks
- `today` → Show tasks due today
- `capacity [name] [day]` → Check workload

### Estimate Reference Guide
Add typical time estimates by task type to knowledge files:
- Blog post: 2-3h draft + 30m review
- Social graphics (set of 3): 1.5h
- Landing page design: 3-4h
- Landing page dev: 4-6h
- Newsletter: 2h design + 1h dev

### Quick Reference Section
Add condensed reference info to top of CLAUDE.md (most-used clients, common estimates) to reduce file lookups and speed up responses.

### Multi-LLM Support
Adapt the agent to work with other LLMs beyond Claude (e.g., Gemini, GPT). Would require abstracting the instructions into a format that works across different models and potentially using a different MCP client setup for each platform.
