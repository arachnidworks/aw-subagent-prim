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

2. **Create your environment file**:
   ```bash
   cp .env.example .env
   ```

3. **Edit `.env`** with your ClickUp API key:
   ```
   CLICKUP_API_KEY=your_api_key_here
   CLICKUP_TEAM_ID=9014297733
   ```
   Get your API key from ClickUp Settings > Apps.

4. **Start Claude Code**:
   ```bash
   claude
   ```
   The MCP server will connect automatically. Run `/mcp` to verify.

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
├── .env.example                 # Environment template (copy to .env)
├── .env                         # Your local secrets (gitignored)
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
- **Node.js v18+** (for MCP server)
- **ClickUp API key** with access to ArachnidWorks workspace
- The ClickUp MCP uses [@taazkareem/clickup-mcp-server](https://github.com/taazkareem/clickup-mcp-server)

## Troubleshooting

### MCP not connecting
- Run `/mcp` in Claude Code to check status
- Verify `.env` file exists with correct values
- Ensure Node.js v18+ is installed: `node --version`

### Agent not following instructions
- Make sure you're in the `aw-pm-agent` directory when starting Claude
- Run `git pull` to get latest CLAUDE.md updates
