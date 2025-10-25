# Agent Mode vs. Coding Agent - Quick Comparison

⚠️ **These are TWO DIFFERENT things!**

## Quick Distinction

| Feature           | Agent Mode (in IDE)               | Coding Agent (on GitHub)              |
| ----------------- | --------------------------------- | ------------------------------------- |
| **Where it runs** | Your IDE (VS Code, Visual Studio) | GitHub.com (Actions-powered)          |
| **What it does**  | Autonomous local edits            | Completes assigned tasks, creates PRs |
| **Output**        | Direct edits in IDE               | Pull requests on GitHub               |
| **How to use**    | Open Chat → Switch to Agent mode  | Assign issue to Copilot               |
| **Visibility**    | Local session                     | Team-visible PRs & commits            |
| **PRU usage**     | 2-5 PRUs per complex task         | 1 PRU per model request               |

## Agent Mode (Copilot Edits in IDE)

**Location**: Chat panel in VS Code or Visual Studio

**Purpose**: Multi-step autonomous edits in your local environment

**Workflow**:

```
Open Chat → Agent mode → Define task →
Copilot determines context → Makes local edits →
You review and keep/discard
```

**Best for**:

- Multi-file local refactoring
- End-to-end test generation
- Project scaffolding
- Complex local workflows

**Key feature**: Works in your IDE, doesn't create PRs

## Coding Agent (on GitHub.com)

**Location**: GitHub.com, runs in GitHub Actions

**Purpose**: Autonomous task completion with PR creation

**Workflow**:

```
Assign issue to Copilot → Agent creates branch →
Writes commits → Opens draft PR → Requests review
```

**Best for**:

- Bug fixes
- Incremental features
- Documentation updates
- Technical debt

**Key feature**: Creates PRs, team can see progress

## When to Use Which

| Scenario                     | Use Agent Mode (IDE) | Use Coding Agent (GitHub) |
| ---------------------------- | -------------------- | ------------------------- |
| **Local refactoring**        | ✅ Yes               | ❌ No                     |
| **Issue assigned in GitHub** | ❌ No                | ✅ Yes                    |
| **Need PR for review**       | ❌ No                | ✅ Yes                    |
| **Quick local changes**      | ✅ Yes               | ❌ No                     |
| **Team visibility needed**   | ❌ No                | ✅ Yes                    |
| **Testing locally first**    | ✅ Yes               | ❌ No                     |

## Common Confusion Points

### "They both use agents, right?"

**Yes, but differently**:

- **Agent Mode**: Autonomous IDE assistant for local work
- **Coding Agent**: Autonomous GitHub teammate that creates PRs

### "Can they work together?"

**Sort of**:

1. Use Agent Mode to prototype locally
2. Push your code
3. Create issue for improvements
4. Assign issue to Coding Agent
5. Coding Agent creates PR with refinements

### "Which consumes more PRUs?"

**Depends on task complexity**:

- **Agent Mode**: 2-5 PRUs for multi-file workflows
- **Coding Agent**: 1 PRU per model request (can add up for complex tasks)

## Quick Decision Tree

```
Need team-visible PR?
├─ Yes → Coding Agent (assign issue on GitHub)
└─ No → Agent Mode (Chat panel in IDE)

Need to iterate locally first?
├─ Yes → Agent Mode
└─ No → Coding Agent

Working on existing issue?
├─ Yes → Coding Agent (assign issue)
└─ No → Agent Mode (Chat in IDE)
```

## Module References

- **Agent Mode**: [Building applications with Agent Mode](../Fundamentals_Part_2/1_Building_applications_with_Github_Copilot_agent_mode.md)
- **Coding Agent**: [Accelerate development with Coding Agent](../Fundamentals_Part_2/2_Accelerate_development_with_Github_Copilot_coding_agent.md)
