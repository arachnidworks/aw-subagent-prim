# Common Scenarios

Example interactions showing how the PM Agent handles various task creation and management scenarios.

## Simple Task Creation

### Blog Post Task
```
User: Create a task for ToP to write a blog post about maximizing credit card rewards, due next Friday, assign to John

Agent: Creating task in Travel on Points list...

Task created:
- **Name**: Write blog post: Maximizing credit card rewards
- **List**: ToP (Travel on Points)
- **Assignee**: John Grgurich
- **Due Date**: [next Friday's date]
- **Status**: Gearing Up

Quick questions to finalize:
1. Any target word count or SEO keywords?
2. Should I add a review subtask for the AM?
3. Ready to move to "Ready" status, or keep in "Gearing Up" for spec refinement?

[Task link]
```

### Internal Meeting Task
```
User: Add an internal meeting for tomorrow at 2pm, 1 hour, I'm facilitating

Agent: Creating internal meeting task...

Task created:
- **Name**: Internal Meeting - [tomorrow's date]
- **List**: Internal Meetings
- **Assignee**: [user]
- **Due Date**: [tomorrow]
- **Time Estimate**: 1 hour
- **Status**: Ready

[Task link]
```

## Complex Deliverable with Subtasks

### Landing Page Project
```
User: We need to build a landing page for PMI's new product launch

Agent: Got it—landing page for Phoenix Mecano. Let me gather the spec:

**Context**: What's the product being launched? Any campaign this ties into?

User: It's their new DewPoint sensor. Part of Q1 product push.

Agent: **Instructions**: Any specific sections, messaging requirements, or design direction?

User: Follow the existing PMI brand guide. Needs hero section, features grid, specs table, and contact form. Should match their current site style.

Agent: **Resources**: Do you have copy, product images, or spec sheets ready? Any wireframes?

User: Copy doc is in progress, product images are on their shared drive. No wireframe yet.

Agent: **Expected Output**: Design only, or design + development? Any specific conversion goals?

User: Full build to staging. Goal is demo requests via the form.

Agent: Perfect. I'll create the parent task with subtasks for each phase:

**Parent Task**: PMI DewPoint Landing Page
- Due: [suggest date based on complexity]
- Status: Gearing Up (waiting on copy)

**Subtasks**:
1. Wireframe/Layout Planning - Drew - 2h
2. Visual Design - Drew - 4h  
3. Copy Integration - John - 2h (blocked until copy ready)
4. Development - Mike - 4h
5. QA & Testing - [AM] - 1h
6. Client Review - [AM] - 1h

Should I create this structure? Any adjustments to the subtask breakdown or assignments?
```

## Task Updates

### Changing Due Date
```
User: Push the ToP blog post to next Wednesday instead

Agent: I'll search for that task...

Found: "Write blog post: Maximizing credit card rewards" (ToP)
Current due date: [Friday]

Updating to: [next Wednesday]

Done. Task due date updated. Note: Make sure John knows about the change if he was planning around the original date.

[Task link]
```

### Reassigning a Task
```
User: Actually assign that PMI wireframe to Mark instead of Drew

Agent: Updating "Wireframe/Layout Planning" subtask...

Changed assignee from Drew Ahrens to Mark Wisniewski.

Done. Should I notify Mark via assigned comment, or will you handle that separately?
```

## Handling Blocked Tasks

### Internal Block
```
User: The PMI dev work is blocked—we don't have staging access

Agent: I'll update the task status. For Internal Blocked tasks:

1. Moving "Development" subtask to **Internal Blocked**
2. Adding comment: "Blocked: No staging access. Need credentials from client or WPEngine setup."

Who should resolve this? I can assign a comment to the appropriate AM.

User: Assign to Madelyn

Agent: Done. Comment assigned to Madelyn Marks on the blocked subtask.

Should I also move the parent task to Internal Blocked, or keep it in Ready since other subtasks can continue?
```

### Client Waiting
```
User: ToP hasn't approved the copy yet, mark it waiting

Agent: I'll update the relevant tasks:

1. Moving "Copy Integration" subtask to **Waiting on Client**
2. Moving parent task to **Waiting on Client** (since this blocks progress)
3. Adding comment: "Waiting on client copy approval"

When do you expect to hear back? I'll set the due date accordingly.

User: Probably Monday

Agent: Updated due dates to Monday. I'd recommend following up with the client Friday if you haven't heard back.
```

## PM Guidance Questions

### Status Clarification
```
User: What's the difference between Gearing Up and Ready?

Agent: **Gearing Up**: Tasks that are identified but not fully specced or ready for execution. The AM is still working on defining the task—gathering requirements, writing specs, or waiting for information.

**Ready**: Tasks that are fully specced, assigned, and ready to be executed on their due date. When something is in Ready:
- All four spec elements are complete (Context, Instructions, Resources, Expected Output)
- Assignee is set
- Time estimate is realistic
- Due date is the date it should be completed

**Key rule**: Don't move to Ready until someone could execute the task without asking questions.
```

### Capacity Question
```
User: John has too much work Thursday, what should I do?

Agent: A few options based on PM principles:

1. **Check actual capacity**: What's John's total estimated hours Thursday? Standard is ~6-7 hours.

2. **Reprioritize**: First Come, First Serve applies—tasks scheduled earlier get priority. What can move to Friday?

3. **Reassign**: Is there another copywriter (Brett) with capacity who could take something?

4. **Split the work**: Can any task be broken into smaller pieces with some done Thursday, rest Friday?

Want me to search John's tasks for Thursday to see the full picture?
```

## Error Handling

### Client Not Found
```
User: Create a task for XYZ Corp

Agent: I don't have "XYZ Corp" in my client reference. Could you:
1. Provide the client ID/acronym (like "ToP" or "PMI")?
2. Or is this a new client that needs to be added to ClickUp first?

If it's internal work, I can put it in the appropriate General list instead.
```

### Missing Required Info
```
User: Create a task for design work

Agent: I need a bit more to create this properly:

1. **Which client?** (or is this internal?)
2. **What's being designed?** (landing page, social graphics, email template?)
3. **Who should do it?** (Drew, Elva, or Mark?)
4. **When is it due?**

Even a rough answer helps—we can refine the spec after creation.
```
