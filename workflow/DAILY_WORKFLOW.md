# Daily Workflow & Process

## 1. Memory & Identity

### Morning Routine
- **First Step**: Check `SOUL.md` to remember core values and purpose
- **Second Step**: Check `IDENTITY.md` to recall communication style and personality
- **Purpose**: Ground yourself in who you are and how you should talk

### Daily Logging
- Maintain a daily log in the `memory/` folder
- Track progress, decisions, and learnings
- Prevents loss of context and builds institutional knowledge

---

## 2. Available Tools & Skills

### Built-in Capabilities

#### Image & Video Generation
- **Tool**: ComfyUI
- **Use Cases**: Generate images, process videos, create visual content
- **Workflow**: Initiate, then continue other tasks while rendering

#### Audio & Music Creation
- **Tool**: Suno
- **Use Cases**: Generate music, create audio content
- **Workflow**: Queue creation, continue work while processing

#### Web Research
- **Tool**: Web Search
- **Use Cases**: Fetch fresh information, verify current data
- **When to Use**: Need real-time or up-to-date information

#### Code & Development
- **Capabilities**: Full codebase exploration, refactoring, debugging, implementation
- **When to Use**: Any development or scripting needs

---

## 3. Sub-agents

### Purpose
Spawn specialized sub-agents to handle heavy-lifting tasks, enabling concurrent work

### Best Practices

**When to Use Sub-agents**:
- Long-running processes (video rendering, complex computations)
- Specialized exploration or research tasks
- Parallel workstreams (you continue chatting while agent works)

**Agent Options**:
- **Explore Agent**: Fast read-only codebase exploration
  - Use for: Q&A about codebase, understanding structure
  - Thoroughness options: quick, medium, thorough

### Workflow Pattern
1. Identify heavy-lifting task
2. Spin up sub-agent with clear task description
3. Continue your work on other items
4. Receive agent results when complete
5. Integrate results into main workflow

---

## 4. Task Execution Pattern

### Sequential Workflow
```
Morning Check-in
    ↓
[SOUL.md] + [IDENTITY.md] Review
    ↓
Daily Log Update
    ↓
Identify Tasks
    ↓
├─→ Quick Tasks (direct)
├─→ Heavy Tasks (spin up sub-agent)
└─→ Tool-dependent Tasks (initiate + continue work)
    ↓
Execute & Log
    ↓
End of Day Review
```

### Concurrent Work Pattern
- Initiate tool process (ComfyUI render, Suno generation, web search)
- Spin up sub-agent if needed
- Continue on other tasks
- Collect results when ready
- Integrate findings

---

## 5. Documentation

### Key Files to Maintain
- `SOUL.md`: Core values and purpose
- `IDENTITY.md`: Communication style and personality traits
- `memory/daily-logs/`: Date-stamped daily logs
- `memory/learnings.md`: Lessons and insights
- `memory/task-templates.md`: Reusable task patterns

### Logging Template
```
## [Date] - Daily Log

### Completed
- Task 1
- Task 2

### In Progress
- Task 3

### Learnings
- Insight 1
- Insight 2

### Tomorrow's Focus
- Task A
- Task B
```

---

## 6. Quick Reference Checklist

- [ ] Morning: Review SOUL.md
- [ ] Morning: Review IDENTITY.md
- [ ] Log daily progress
- [ ] Break work into direct vs. delegated tasks
- [ ] Initiate long processes early (render time, generation)
- [ ] Use sub-agents for heavy lifting
- [ ] Collect results and integrate
- [ ] Evening: Update daily log with completion status
